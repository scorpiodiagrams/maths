~~~Markdown
## 180 degrees

> **180<sup>o</sup>** - The angles of any triangle add up to $$180^\circ$$. <br><br>The symbol **<sup>o</sup>** after the 180 is read as *degrees*.

Why do the angles of a triangle always add up to $$180^\circ$$?  Are we in fact actually sure that they do?

Firstly there's the question of how big a degree is.  By convention there are 360<sup>o</sup> in a full rotation.  

> Long ago, 360 was probably chosen as the number of degrees because it is divisible exactly by a wide range of numbers.  2,3,5,6,10,15,20,30 all divide 360.  

There's another way of measuring angles called *gradians* which has 100 gradians in a full rotation.  In gradians a triangle's angles always add up to 50.

The challenge is why?  Why when you sum the angles of a triangle do you always get the same result?  Why does it not matter what kind of triangle you choose?  Its angles will always add up to 50 gradians (if measured in gradians) or 180 degrees (if measured in degrees)?

## The Tessellation Argument
### An almost good enough argument
Here's a diagram that shows a tessellation of triangles.  It's the same triangle 🔺abc many times over.  Where three lines cross, the three angles of the triangle are each found twice.  The tessellation shows that twice the sum of the angles is 360 degrees, so the sum of the angles of a triangle is 180.
~~~Scorpio
##Geometry
caption: Tessellation
boxed: 250
*:A: (A)
*:B: (B)
*:C: (C)
*:D: (D)
*:E: e
*:F: f
*:G: g
*:H: h
*:I: i
*:J: j
*:K: k
*:L: l
*:M: a
*:N: n
*:O: o
*:P: p
*:Q: q
*:R: b
*:S: c
*:T: t
*:U: u
*:V: v
*:W: w
*:X: x
:A: at: 170,40
:B: at: 270,40
:C: at: 370,40
:D: at: 470,40
:E: at: 570,40
:F: at: 120,90
:G: at: 220,90
:H: at: 320,90
:I: at: 420,90
:J: at: 520,90
:K: at: 70,140
:L: at: 170,140
:M: at: 270,140
:N: at: 370,140
:O: at: 470,140
:P: at: 20,190
:Q: at: 120,190
:R: at: 220,190
:S: at: 320,190
:T: at: 420,190
:U: at: 70,240
:V: at: 170,240
:W: at: 270,240
:X: at: 370,240
bond: A P
bond: B U
bond: C V
bond: D W
bond: E X
bond: A E
bond: F J
bond: K O
bond: P T
bond: U X
bond: A X
bond: B T
bond: C O
bond: D J
bond: F W
bond: K V
:A:B:C:D:E:F:G:H:I:J:K:L:N:O:P:Q:T:U:V:W:X:
hide:

~~~Markdown

As a way to show that the angles add up to 180, this looks great.  

But how do we know that the triangles actually do fit together like this, that they fit exactly and that this would work for any other triangle too?

< We could use the fact that the angles add up to 180 to argue that the triangles do fit at the corners, but then we wouldn't be able to use the tessellation argument to argue that the angles add up to 180!

We'd have an argument that because the angles add up to 180 they must add up to 180.  We wouldn't have proved anything.

## Using Symmetry
### An argument that can be made to work

~~~Scorpio
##Geometry
caption: Tessellation
boxed: 150
*:A: l
*:B: a
*:C: b
*:D: c
:A: at: 170,40
hide:
:B: at: 270,40
:C: at: 220,90
:D: at: 320,90
bond: A B
bond: A C
bond: B C
bond: B D
bond: C D
~~~Markdown

Here we've taken the original triangle and added a single copy.

The top and bottom edge look to be parallel.  We now use a symmetry argument to show that they are parallel.

> If the top and bottom edges were not parallel, we could extend them and they would meet, either on the right or on the left.<br><br>But if the lines meet on one side, they must meet on both, because of the symmetry of the figure.  Lines can't meet in two places (unless they are the same line), so no matter how far we we extend both lines they don't meet, in other words the top and bottom edges are parallel.

How do we know that two straight lines cross each other at most once?  How come we can assume that?  Come to that, how do we know that 'parallel lines' are a thing, that it is possible for some pairs of lines to 'go on forever without crossing'?

The short answer is that that is how the game is played.  Some assumptions such as that lines cross at at most one point are allowed.  The rules of what assumptions are allowed in geometry were laid down by Euclid.  There are 'non Euclidean' version of geometry in which other rules hold, and no pairs of lines are parallel.

#### Completing the symmetry argument

We now add a third copy of the triangle like so:

~~~Scorpio
##Geometry
caption: Tessellation
boxed: 150
*:A: l
*:B: a
*:C: b
*:D: c
*:E: d
:A: at: 170,40
hide:
:B: at: 270,40
:C: at: 220,90
:D: at: 320,90
:E: at: 120,90
hide:
bond: A B
bond: A C
bond: B C
bond: B D
bond: C D
bond: A E
bond: E C
~~~Markdown

We use the exact same symmetry argument to show that the bottom edge of this third triangle is parallel to the top edge of the second triangle we added.  This is enough to show that the bottom edge is as straight as it appears to be, and hence that the three angles add up to 180<sup>o</sup>.

We've used symmetry to show that the tessellation does fit together, or rather that enough of it fits together for our purposes.

## Using Half Size
### An argument that works

Another way to show the angles add up to 180<sup>o</sup> is to take the original triangle 🔺abc, shown here slightly bigger, and bisect each edge, and join those points together.

~~~Scorpio
##Geometry
caption: Half size
boxed: 250
*:A: a
*:B: b
*:C: c
*:D: E
hide:
*:E: F
hide:
*:F: G
hide:
:A: at: 240,80
:B: at: 140,180
:C: at: 340,180
:D: at: 190,130
:E: at: 290,130
:F: at: 240,180
bond: A B
bond: A C
bond: B C
bond: D E
bond: E F
bond: D F
~~~Markdown

We then use similarity of triangles to argue that each of the new edges of the inner triangle is half the length of one of the sides of the original triangle.

That establishes that the inner triangle is similar to the outer triangle, with sides exactly half the length.  That doesn't affect the angles, so we have shown we have four triangles that are similar to the original triangle, and that they fit in the arrangement shown.

This then is essentially the tessellation argument, except we've found a different way to show that the triangles do fit together the way they look as if they do.

## Why be so careful?

Why isn't the original tessellation argument 'good enough' on its own?  Why do we have to justify that the pieces do fit?

The reason is that sometimes very plausible diagrams of how things fit together [don't actually work](https://en.wikipedia.org/wiki/Missing_square_puzzle).

## Another reason for care

Another reason for being careful is that the angles of a triangle don't always add up to 180<sup>o</sup>, e.g if the triangle is drawn on a sphere.  Small triangles very nearly have angles adding to 180<sup>o</sup>, but the larger triangles don't.  In one large [spherical triangle](https://en.wikipedia.org/wiki/Spherical_trigonometry) all three angles are 90<sup>o</sup>.

This shows that arguments about geometry depend on what you allow in the geometry.  Spherical geometry allows for two straight lines to intersect more than once.  Spherical geometry allows enlarging and shrinking of triangles to not preserve the angles.  Our arguments that the angles add up to 180<sup>o</sup> always must depend on some reasonable property of geometry that is not true in spherical geometry.