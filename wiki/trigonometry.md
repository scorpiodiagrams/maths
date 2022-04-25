~~~Markdown
#Trigonometry


## Why Triangles?

Rectangles are easier than triangles.  We can easily get the area of a rectangle.  It's the product of the length of the two sides.  So why bother with triangles?

We can use triangles to get information about any shape with straight sides.  If we can calculate the length of the sides of triangles from other sides and angles, then we can divide a shape like this five pointed star into triangles and work out what the lengths are.

~~~Scorpio
##Geometry
caption: Five pointed star
boxed: 250
*:A: (A)
*:B: (B)
*:C: (C)
*:D: (D)
*:E: (E)
:A: at: 200,220
:B: at: 260,43
:C: at: 320,220
:D: at: 160,110
:E: at: 360,110
bond: A B
bond: B C
bond: C D
bond: D E
bond: E A
:info:
card:
## Five pointed star
We can work out the lengths and angles in a five pointed star from triangles that make it up.
~~~Markdown

Because we can divide shapes made with straight lines up into triangles they are a good foundation for work in geometry.  They are better in many ways than rectangles.  Any rectangle can be sliced into two triangles along its diagonal.  If we can do the geometry of triangles we also can do the geometry of rectangles


## Preliminaries

> **Similar** - Two triangles are *similar* if they have the same angles.  The two triangles may be different sizes, but the angles and proportions are the same.

> **Hypotenuse** - The longest side in a triangle.  It is always opposite the largest angle.

> **Parallel** - Two straight lines are parallel if no matter how far you extend them, they never meet.

> **180<sup>o</sup>** - The angles of any triangle add up to $$180^\circ$$.  

But why?  Why do the angles always add up to $$180^\circ$$?  Are we in fact actually sure that they do?
#Right([angles add to 180](#180degrees))

> **90<sup>o</sup>** - In a right-angled triangle, one of the angles is $$90^\circ$$.  The other two angles add up to $$90^\circ$$.  

In a right-angled triangle, the hypotenuse is opposite the right-angle.  The right-angle is the largest angle in that triangle.  

Why?  

Because if one angle is $$90^\circ$$ it is the largest.  The remaining two angles must sum to $$90^\circ$$, to make a total of $$180^\circ$$ so neither of the other two angles can be larger than $$90^\circ$$.

## Why Right angled Triangles?

Trigonometry pays special attention to right-angled triangles.  The functions $$\sin$$, $$\cos$$ and $$\tan$$ are functions that relate side lengths and angles in right angled triangles.

< #DropCap(? &nbsp; ) Why do we use triangles with $$90^o$$ angles?<br>Wouldn't $$60^\circ$$ angles, the angles in an equilateral triangle, be a *nicer* choice?

The reason is that any triangle can be divided into two right angle triangles.  We can *drop a perpendicular* onto the hypotenuse that divides the triangle.  We build up results for any triangles using right angled triangles as our building blocks.  

It would be possible to use triangles with $$60^\circ$$ angles, but then to subdivide any triangle, we could need three of them.   

Here is a triangle, $$\triangle ABC$$, subdivided into two right-angled triangles.

~~~Scorpio
##Geometry
caption: Subdividing a triangle
boxed: 200
*:A: (A)
*:B: (B)
*:C: (C)
*:D: (D)
:A: at: 126,140
:B: at: 260,34
:C: at: 466,140
:D: at: 260,140
bond: A B
bond: B C
bond: C A
bond: B D
angle: B D A
angle: C D B
:info:
card:
##Dividing a triangle
"Something about dropping a perpendicular"
~~~Markdown

The two right angles are shown with the squarish pieces.

$$\angle BDA$$ is a right angle and so is $$\angle CDB$$.

All three triangles in the diagram are different shapes.  None are #Code(similar) to each other.

## What Trigonometry does

Trigonometry looks for ways to compute all the information about a triangle given part of the information.  For example trigonometry can calculate:

* Length of missing side if given two sides and the angle between them
* Angle at any corner, given the lengths of the three sides.
* Area of a triangle given the length of all three sides.

This is easier to do if the triangle is a right-angled triangle.  For example to get the #NUTC(area of a right-angled triangle) multiply the length of the two shorter sides and then halve that number.  

The formula for the area of an arbitrary triangle given the side lengths is more complex.  However, because we can divide any triangle into two right-angled triangles we can still calculate the area given some information about lengths of sides and angles.

#[
 *diagram of area of a right angle triangle.  reminder that we can make rectangles.*
#]

One of the big nice results about right-angle triangles is the relationship between the lengths of the sides.

> <h3>Pythagoras:</h3>The square of the length of the hypotenuse is equal to the sum of the squares of the lengths of the other two sides.

With that result we can calculate the length of any side of a right angle triangle, given the lengths of two other sides, provided we're told which side is opposite the right-angle.
#Right([Pythagoras Theorem](#pythagoras))

## Tables of Triangle Sizes

We've broken straight sided shapes down into triangles, and now we've broken triangles down into pairs of right-angle triangles.  

The force that is driving this is that we want to be able calculate things.  Perhaps we could look up information about different triangles in some table, to relate missing information to known information?

Suppose we wanted a book that tabulated information for lengths of the misisng side in triangles given two sides and an angle.  How big would the book have to be?

Suppose we covered angles from 0<sup>o</sup> to 180<sup>o</sup> in steps of 1<sup>o</sup>, and lengths from 0 to 1m in steps of 1mm.

We'd then have
* 180 angles
* x 1000 lengths for one side
* x 1000 lengths for the other side.

So the book would have 180,000,000 triangles in it.  We can do #NUTC(a bit better) than that.
#[
* First a length of 75cm and 45cm gives the same result as 45cm and 75cm, so we can pretty much halve the number of triangles to list to 90,000,000.
* Second, because 7.5cm with 4.5cm gives the same information as 75cm with 45cm.  We can always scale the triangle up, to choose one side to be 1m and then we only need 180 x 1000 i.e. 180,000 triangles in the book.  We then scale the result back by scaling down by the same amount.
#]

The push in trigonometry is to reduce the number of parameters in a problem.  The length-angle-length triangle problem has three parameters to it.  The length-angle-length problem for right-angle triangles has two parameters to it, since we always have a right-angle as the angle.  

> We sometimes say that functions that take two arguments, like addition, subtraction, multiplication and division, are *dyadic* functions.<br><br>Functions that take one argument, such as square root, are *monadic*.

For right-angle triangles the missing length is a dyadic function of the two lengths.  The Pythagoras Theorem saves us from having to have a book or table to look this function up in.  It translates the triangle dyadic problem into the dyadic problem of addition, which we don't need a table for, since we can just calculate it. 

Arguably there is a cost.  We need to translate by squaring and square rooting.  The squaring and square rooting perhaps each require a table for their monadic function.  Even with that table, it's a big win over having a large table for the dyadic function.

### Dyadic to Monadic
#### Why programmers care
<br>
This numer of parameters to a function is important in computer programs that do geometry.  Often you can speed up programs using a 'look up table' or LUT, which is a list of precomputed values for particular parameters.  If the functions are dyadic, the tables will be huge, and increase rapidly in size as you try to increase precision.  If the functions are monadic, a LUT is much more feasible.  Even better is to have a short formula which avoids the need for any LUT at all.

## Sine and Cosine

Sine and Cosine are the names given to standard functions that relate side lengths in right angle triangles.
* * how they are monadic* 
* * how they are the same function *
* * why Cosine is better than Sine *

## Tan


## Sine and Cosine of angles bigger than $$90^\circ$$



#NUT(Sine and Cosine)
#[
Yet to come:
Including
* Beat frequencies
* Pi
#]

!!Katex
\sin^2{(x)} + \cos^2{(x)} = 1
~~~Markdown