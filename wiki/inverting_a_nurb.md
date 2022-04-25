!!MathsStart
!!Markdown
#Inverting a NURB

###A Square Root
A computer can readily do addition, multiplication and division.  How can we use it to calculate a square root, for example the square root of 3?

> **Newton Raphson** is an efficient process for calculating the inverse of a function.  It is popular for finding square roots - which is the same thing as solving $$y=x^2$$ for a chosen $$y$$.

The Newton Raphson technique relies on the observation that over small regions many functons are close to being a straight line.  If you zoom in on the function $$y=x^2$$ the curvature becomes less and less visible.  In turn this suggests a way to find an $$x$$ such that $$x^2=3$$ by linear approximations.

* We start with some ballpark guess at $$x$$.  
* Update x to a better guess, 'pretending' it's a straight line at that point.
* Repeat until we are 'close enough'.

Here's how we use this to calculate $$\sqrt{3}$$.

####Ballpark Guess
We know $$x=1$$ is too small and $$x=2$$ is too big, so we could start with a ballpark guess for $$\sqrt{3}$$ of $$x=1.5$$.  

$$1.5^2$$ is $$2.25$$, so $$x=1.5$$ is also too low.  We could do a process of 'binary halving' and try $$x=1.75$$ next, and gradually narrow down the region for $$x$$.  However the linear approximation method is better.  It will get us more digits of $$x$$ faster.

####Linear approximation
The derivative of $$x^2$$ is $$2x$$.  Plugging in $$x=1.5$$ we have that the slope of $$y=x^2$$ at $$x=1.5$$ is $$3$$.  If the curve $$y=x^2$$ were actually a straight line at $$x=1.5$$, we could move along that straight line to the exact answer. We'd move $$+0.75$$ in $$y$$ value, and read off the exact $$x$$ value of $$\sqrt{3}$$.  

The curve $$y=x^2$$ isn't a straight line, so we won't get the exact answer, but the curve comes closer and closer to being a straight line the more you zoom in.  The technique makes excellent improvements in the guess.

To move $$+0.75$$ in $$y$$ when $$\frac{dy}{dx}=3$$ we'd need to add $$\frac{+0.75}{3}$$ to our $$x$$ of $$1.5$$, so we'd get $$1.75$$ for our new $$x$$. That happens to be the same guess as the binary halving idea would have reached.  The gains from Newton Raphson become apparent as you get closer to the answer.  $$x=1.75$$ is already a good update.

####Repeat the linear approximation step
How good is the updated value of $$x=1.75$$?  $$1.75^2$$ is $$3.0625$$.  That's better than $$x=1.5$$ giving $$2.25$$ was.  And we can repeat the steps.  The slope at $$x=1.75$$ is $$3.5$$.  We'd need to subtract $$\frac{0.0625}{3.5}$$ from $$1.75$$ giving $$x=1.7321$$.  How good is this value for $$x$$?  $$1.7321^2$$ is $$3.0003$$.  Newton Raphson converges very quickly if the initial guess is reasonably close.

####What's behind this?
Linear functions are easy to invert compared to polynomials like $$x^2$$.  In particular for a linear function $$y=mx+c$$, we can quickly get the inverse function $$x=\frac{y-c}{m}$$.  

Newton Raphson leverages inverse of linear functions to invert a polynomial.  It rests on the derivative providing a local linear approximation.
< In the square root calculation we had $$y$$ as a function of x, i.e.  $$y=f(x)$$.  We calculated the error in $$y$$ value for that x, and used it to make a linear approximation to the right change to update $$x$$.  We took a step towards $$x=f^{-1}(y)$$ using the approximation that the curve is straight at the chosen point.  We knew $$\frac{\mathrm{d}y}{\mathrm{d}x}$$ and divided by it, which is the same thing as multiplying by $$\frac{\mathrm{d}x}{\mathrm{d}y}$$, the derivative of $$x=f^{-1}(y)$$.

###As an Inverse
Newton Raphson allows us to calculate a polynomial function in the opposite direction to the way the function is defined.  The function is defined as $$y$$ in terms of $$x$$.  Newton Raphson allows us to calculate $$x$$from $$y$$.

The calculation works because derivatives are linear approximations to a function at each point.  We can get the derivative of the inverse function at our chosen $$x$$ because it is the reciprocal of the derivative of the forward function.

##The NURB problem

NURBS are useful in computer graphics.  They give us a way to warp a texture or image.  NURBs tell us how to map coordinates in a texture to coordinates on screen.

One of the simplest NURB formulas is a bilinear transformation.  

Suppose we have two-dimensional coordinates in the texture, which we will call $$s$$ and $$t$$.  With a bilinear transformation the colour from the texture at position $$s,t$$ may end up on screen at the position $$V_x,V_y$$ where:
 $$\qquad V = A(1-s)(1-t) + Bs(1-t)t + C(1-s)t + Dst$$
!!Markdown

You can see that the function maps the unit square in coordinates $$s$$ and $$t$$ to a quadrilateral with corners A,B,C and D.  For example put $$s=0$$ and $$t=0$$, and you get the point A.

Why would we want to 'invert' a NURB?

If we have a large texture and are mapping it to a small area of the screen, it is inefficient to map each pixel of the texture in turn and place it on screen.  Ideally instead we would like to iterate through pixels on that part of the screen and then quickly determine where each of those pixels should come from.

The inverse function for a NURB is not as directly calculable as the forward function.  Given a $$V_x,V_y$$ it is not so easy to calculate what $$s$$ and $$t$$ would be.

> This is where the **Jacobian** comes in.  It can be used to generalise the Newton Raphson procedure.  

The slope in the Newton Raphson becomes a multidimensional gradient.  In the matrix below, the $$x_i$$ take the role of $$s$$ and $$t$$, and the $$f_j$$ take the role of $$V_x$$ and $$V_y$$.  We've jumped from just two texture coordinates $$s,t$$ and two coordinates on screen $$x,y$$ to an arbitrary number of each.  We might as well get the full benefit of generality of the Jacobian.
!!Katex
\mathbf J = 
\begin{bmatrix}
    \dfrac{\partial f_1}{\partial x_1} & \cdots & \dfrac{\partial f_1}{\partial x_n}\\
    \vdots                             & \ddots & \vdots\\
    \dfrac{\partial f_m}{\partial x_1} & \cdots & \dfrac{\partial f_m}{\partial x_n}
\end{bmatrix}
!!Markdown
For epsilon small, we have
!!Katex
f(x+\epsilon) = f(x) + f'(x) \epsilon + o( \epsilon ^2 )
!!Markdown
We can read this as an equation in a single scalar variable $$x$$, and $$f(x)$$, $$\epsilon$$ and $$f'(x)$$ all being scalar.  
We can also read this as a vector equation where $$x$$, $$f(x)$$ and $$\epsilon$$ are all vectors.  The Jacobian <em>is</em> the multidimensional derivative. 
!!Katex
f(x+\epsilon) = f(x) + \mathbf J \epsilon + o( \epsilon ^2 )
!!Markdown

If you're wondering why the individual derivatives in the definition of $$\mathbf J$$ are written $$\frac{\partial\, this}{\partial\, that}$$ rather than $$\frac{\mathrm{d}\, this}{\mathrm{d}\, that}$$, it is to indicate they are 'partial derivatives'.  It's a notation to remind us that the full derivative has more components to it.

##Calculating the Inverse

We are looking for the inverse function $$f^{-1}$$, so that given a particular point $$(f_0, f_1 \ldots f_m)$$ we can calculate what $$( x_0, x_1 \ldots x_n)$$ would give that value.  Another way to look at this is that we have an estimate $$x$$ (a vector) and want to update it to a better estimate by finding $$\epsilon$$ (a vector).

The calculation and reasoning is very similar to that in the case of calculating $$\sqrt{3}$$.  In that calculation we were using the equation below, where $$f(x)=x^2$$ and where $$2x$$ takes the place of $$\mathbf J$$ :
!!Katex
3 = (x+\epsilon)^2 = x^2 + 2x \epsilon + o( \epsilon ^2 )
!!Markdown
In that calculation of $$\sqrt{3}$$ we got an estimate for $$\epsilon$$ by ignoring the $$o(\epsilon^2)$$as follows:
!!Katex
\epsilon = \frac{(x+\epsilon)^2 -x^2}{2x}
!!Katex
\epsilon = \frac{3-1.75^2}{2\times 1.75}
!!Markdown
We then updated $$x$$ by adding our estimate of $$\epsilon$$ and repeated.
----
With the multivariate case we have:
!!Katex
\mathbf J \epsilon = f(x+\epsilon) - f(x)
!!Markdown
To 'divide' by the Jacobian, we multiply by the matrix inverse.
!!Katex
\epsilon = \mathbf J^{-1}\left( f(x+\epsilon) - f(x) \right)
!!Markdown
We then update $$x$$ (a vector now) by adding our estimate of $$\epsilon$$ (also a vector) and repeat.

< Using the matrix inverse of $$\mathbf J$$ is exactly analogous to using the reciprocal of the gradient.

Both $$\mathbf J$$ and $$\mathbf J^{-1}$$ are easy to calculate. This allows us to do Newton Raphson in this multi-dimesnional setting where $$x$$ is a vector, and to iterate to find $$x$$ for a desired value of $$f(x)$$.  

In the context of texture mapping for a NURB there is an excellent way to get the initial estimate that Newton Raphson needs.  In screen coordinates, i.e. in the values of $$f(x)$$, we are making small steps.  The texture coordinates for the previous pixel provide a good estimate for the texture coordinates of the current pixel.  In practice the estimates are so good, the function $$f$$ so close to linear, that for typical NURBs a single update is all that is needed at each pixel.

!!MathsEnd