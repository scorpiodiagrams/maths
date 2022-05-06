
# Bresenham Algorithms

Straight lines and circular arcs are important elements of more complex diagrams.  The Bresenham algorithms are particulalry fast ways to draw them.

The lines and arcs on a computer screen are made from pixels.  The Bresenham algorithms work out which pixels to paint without visiting every pixel on the screen in turn.

## Lines

For a straight line that joins $$A$$ to $$B$$ the Bresenham algorithm starts at $$A$$ and takes steps in $$x$$ direction and $$y$$ direction.

Without loss of generality we can assume that the Bresenham algorithm is taking $$x$$ goes to $$x+1$$ steps and sometimes a $$y$$ goes to $$y+1$$ step with it.  The other cases, for example $$y$$ decreasing by $$1$$ with each step and $$x$$ sometimes increasing by 1 are very similar.  

We could join $$A$$ to $$B$$ by taking all the $$x$$ steps first and then taking as many $$y$$ steps as needed.  This would get from $$A$$ to $$B$$ but not with a good approximation to a straight line.  We instead want to spread the $$y$$ steps out evenly amongst the $$x$$ steps.

The key to doing this is to use the slope of the line.

Suppose the slope of the line is 0.3, in other words for every 10 steps in $$x$$ we want to take 3 steps in $$y$$.  We keep a track of an error, $$E$$ and make a small correction every so often to keep $$E$$ small.

~~~Raw
Repeat{
  x = x+1
  E = E+0.3
  if( E >= 1.0 ){
    y = y+1
    E = E-1
  }
  plotAt(x,y)
}
~~~

If E starts at 0 it will go in sequence 0.3, 0.6, 0.9, 1.2.  The 1.2. will be reduced back down to 0.2, and $$y$$ incremented.  $$E$$ will stay between 0 and 1.

If $$x$$ takes 100 steps, $$E$$ gets increased by a total of 30, and hence for E to end up below 1, $$y$$ will have been incremented by 1, 30 times.  These increments will have happened fairly evenly spread along the course of adjusting $$x$$.

I just chose 0.3 as an example.  It works equally well for other values.

## Integers

The Bresenham algorithms come from a time when floating point arithemtic was much more expensive than integer arithmetic.

Instead of adding 0.3, the algorithm would have the slope as a ratio, say 307/401, rather than as a decimal, 0.766... and the algorithm would look like this:

~~~Raw
Repeat{
  x = x+1
  E = E+307
  if( E >= 401 ){
    y = y+1
    E = E-401
  }
  plotAt(x,y)
}
~~~

$$x$$, $$y$$ and $$E$$ would all be integers, and $$E$$ would stay between 0 and 401.
