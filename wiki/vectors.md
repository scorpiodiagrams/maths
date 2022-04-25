~~~Markdown
#Vectors


##What a vector is
A vector in 3 dimensional space is a collection of 3 numbers.  Here's an example:
#!!Katex:\begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} \, 
The numbers may represent a displacement, for example the first number is how much to move West or East, the second how much to move North or South, and the third how much to move up or down. Positive numbers are in one direction, negative numbers in the opposite direction.  We may also write:
#!!Katex:x = \begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} \, 
We then say that 'x' is a vector, and we can use the symbol x in equations rather than the three numbers.  The three numbers are called components of the vector.


###Number of dimensions

The idea of a vector also works in 2 dimensional space, with just two numbers in each vector, or in four dimension space with four numbers in each vector.

##Length of a vector

We can calculate the length of any vector from its components.  To get the length, we square each of the components, add these together, and then take the square root.  
So for this vector:
#!!Katex:\begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} \, 
The calculation is:
#!!Katex: \sqrt{0.1^2 + 1.7^2 + 0.3^2} = \sqrt{2.99} = 1.73

The formula for length always works.  Why?  
* The length formula #NUTC(follows from the Pythagoras theorem).
#[
* What is #NUTC(Pythagoras' Theorem)?
#[
The Pythagoras theorem gives the length of the long side of a right angle triangle from the lengths of the two shorter sides.  If the short sides are length 'a' and 'b', then the long side has length:
#!!Katex: \sqrt{ a^2 + b^2 }

For practice with the Pythagoras theorem, see these [examples](https://en.wikibooks.org/wiki/Trigonometry/The_Pythagorean_Theorem).  They include a diagram that makes using Pythagoras to calculate the length of the diagonal of a box easier to follow.
#]

In three dimensions, the length of the diagonal of a rectangular box with sides 'a', 'b' and 'c' is:
#!!Katex: \sqrt{ a^2 + b^2 +c^2}
This is repeated use of the Pythagoras theorem.  The diagonal of the sides 'a' and 'b' is:
#!!Katex: \sqrt{ a^2 + b^2 }
This diagonal, along with side 'c' are the short sides of a right angle triangle whose diagonal is the diagonal of the rectangular box.  Writing the length of the diagonal of the box out in full we get:
#!!Katex: \sqrt{\left(\sqrt{ a^2 + b^2 }\right)^2 + c^2}
Taking a square root of a<sup>2</sup>+b<sup>2</sup> and then squaring again is just making this equation more complicated than necessary.  We can simplify it down to:
#!!Katex: \sqrt{ a^2 + b^2  + c^2}
#]

If the vector has four or more dimensions the equation for the length extends in the 'obvious way'.  Just square all the numbers, add them together, and take the square root.

This formula for the length of a vector defines what length is for a vector.  

##Notation
The length of a vector x is often written:

#!!Katex: \| x \|

The length, i.e. the function || . || that takes a vector and gives its length, is called 'the norm' of the vector space.  The formula for length we've just presented is for 'the euclidean norm'.  For wackier ways of measuring distance in space there are other norms.

##Maths with Vectors

Including how to:
* #NUTC(Add two vectors)
#[
#!!Katex:\begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} + \begin{bmatrix} 0.5 \\ -0.2 \\ 0.1 \end{bmatrix} = \begin{bmatrix} 0.6 \\ 1.5 \\ 0.4 \end{bmatrix} \, 
* #NUTC(Subtraction works) in the obvious way too.
#[
#!!Katex:\begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} - \begin{bmatrix} 0.5 \\ -0.2 \\ 0.1 \end{bmatrix} = \begin{bmatrix} -0.4 \\ 1.9 \\ 0.2 \end{bmatrix} \, 
#]
#]
* #NUT(Multiply a vector) by a constant
#[
#!!Katex: 3\begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} = \begin{bmatrix} 0.3 \\ 5.1 \\ 0.9 \end{bmatrix} \, 
#]
* #NUTC(Divide a vector) by a constant
#[
#!!Katex: \frac{1}{3}\begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} = \begin{bmatrix} 0.033 \\ 0.566 \\ 0.1 \end{bmatrix} \, 
It is quite often useful to divide a vector by its length to get a 'unit vector'.  That is a vector that has length one.
#]

And these #NUT(Operations on Vectors)
#[
* #NUT(Dot Product)
#[
The dot product of two vectors multiplies the components pairwise, and then adds those all together, like so:
#!!Katex:\begin{bmatrix} 0.1 \\ 1.7 \\ 0.3 \end{bmatrix} . \begin{bmatrix} 0.5 \\ -0.2 \\ 0.1 \end{bmatrix} = 0.05+ -0.34 +0.03 = -0.26
It is important to remember that the dot product takes two vectors and gets a single number out as the result.  Often to distinguish the single numbers from the vectors, the single numbers are called 'scalars'.  The dot product of two vectors yields a scalar.

The dot product is a rather useful function.  Two vectors are perpendicular exactly when their dot product is zero.
#!!Katex: u.v = 0 \,\, \text{iff u and v are perpendicular}
The double *'f'* in #NUTC(*'iff'*) is not a typo.
#[
Here *'iff'* is short for *'if and only if'*.  In other words the two statements on either side of *'iff'* are equivalent.  They are different ways of saying the same thing.  
#]
----
Dot products also behave 'like products should' algebraically.  In particular if u, v and w are vectors then:
#!!Katex: u . ( v + w ) = u.v + u.w
* Why dot product is inevitable, once you accept the euclidean norm
#]
* #NUT(Vector Product)
#[
Blah blah blah...
#]
#]
