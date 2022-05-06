## Circles

For a curved arc that joins $$A$$ to $$B$$ the Bresenham algorithm starts at $$A$$ and takes steps in $$x$$ direction and $$y$$ direction.

Without loss of generality we can assume that the Bresenham algorithm is drawing a circle centred at 0,0, and taking $$x$$ goes to $$x+1$$ steps and sometimes a $$y$$ goes to $$y-1$$ step with it.  The other cases are similar.  The algorithm may need to switch whether it is 'driving' with $$xx$$ or $$y$$ as it progresses.  

One approach, when drawing a complete circle, is to draw just one eight of the circular arc using the Bresenham calculations and fill in the other points by symmetry. 

The key to the algorithm is keeping track of an error $$E$$, which measures the error in the square of the distance. 

Suppose $$x$$ starts off as 0, the radius $$R$$ is 100, and $$y$$ starts of as 100.  The initial error $$E$$ is zero.  The following formula is valid, and we will keep it valid as we change $$x$$ and $$y$$.

$$x^2+y^2 = R^2 + E$$

This is the equation for a circle, with the addition of an error term, $$E$$ which we aim to keep small, so that what we draw is a good approximation to a circle.

* When we increase $$x$$ by 1, the left hand side increases by $$(x+1)^2-x^2$$, which is $$2x +1$$ 
* When we decrease $$y$$ by 1, the left hand side 'increases' by $$(y-1)^2-y^2$$, which is $$-2y+1$$, so the left hand side decreases, as this will be a negative value.

The above tells us how the error term $$E$$ increases or decreases when $$x$$ or $$y$$ or both change.  We can therefore track how $$E$$ changes.

We can balance the changes in $$x$$ and $$y$$ to keep $$E$$ small, which in turn means taking a step in $$y$$ every so often, in addition to the steps in $$x$$.

Here's the algorithm:

~~~Raw
Repeat{
  E = E+2*x+1	
  x = x+1
  if( E >= (2*y-1) ){
    E = E-2*y+1
    y = y-1
  }
  plotAt(x,y)
}
~~~

$$E$$ will stay below $$2y$$.

The Bresenham algorithms come from a time when computers struggled to calculate images fast enough.  Tricks for further reducing the amount of calculation were worthwhile.  

If we choose our centre as (0.5,-0.5) rather than (0,0):

$$(x-0.5)^2+(y+0.5)^2 = R^2 + E$$

* When we increase $$x$$ by 1, the left hand side increases by $$(x+0.5)^2-(x-0.5)^2$$, which is $$2x$$ 
* When we decrease $$y$$ by 1, the left hand side 'increases' by $$(y-0.5)^2-(y+0.5)^2$$, which is $$-2y$$.

The algorithm becomes:

~~~Raw
Repeat{
  E = E+2*x	
  x = x+1
  if( E >= 2*y ){
    E = E-2*y
    y = y-1
  }
  plotAt(x,y)
}
~~~

We can then track $$E/2$$ rather than $$E$$ and save ourselves some multiplication, as follows:

~~~Raw
Repeat{
  E = E+x	
  x = x+1
  if( E >= y ){
    E = E-y
    y = y-1
  }
  plotAt(x,y)
}
~~~

&nbsp;