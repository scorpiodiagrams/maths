!!Markdown

# Pythagoras

 *standard square on the hypotenuse diagram here*


> "The square of the length of the hypotenuse is equal to the sum of the squares of the lengths of the other two sides."

There are various ways to prove this, some complex, some beautiful, some algebraic.  One proof I like is this one:

!!Scorpio
##Geometry
caption: Subdividing a right-angle triangle
boxed: 200
*:A: (A)
*:B: (C)
*:C: (B)
*:D: (D)
:A: at: 126,140
:B: at: 180,16
:C: at: 466,140
:D: at: 182,138
bond: A B
bond: B C
bond: C A
bond: B D
angle: B D A
angle: C D B
angle: A B C
:info:
card:
##Dividing a triangle
"Something about dropping a perpendicular"

!!Markdown


If angle $$\angle ACB$$ of the original triangle is a right angle, then something wonderful happens when you divide the triangle into two.  

> When you divide the right-angle-triangle, the three triangles $$\triangle ACB$$, $$\triangle ADC$$ and $$\triangle CDB$$ are similar triangles.  

Are we sure?  #NUTC(Are they really similar?)
#[
We can see that the angles match up. Let us use $$\theta$$ for angle $$\angle CAB$$.  Then $$\angle ABC$$ is $$90^\circ - \theta$$, because the angles in $$\triangle ACB$$ add up to $$180^\circ$$. But the angles in $$\triangle CBD$$ also add up to $$180^\circ$$ so $$\angle DCB = 90^\circ - \angle ABC = 90^\circ - (90^\circ - \theta) = \theta$$.

Yes, it all works.
#]

## Relating the lengths

Now we can use the fact that the three triangles are just scaled versions of each other to get a formula about the longest side.

### Relating the lengths of sides

If we shrink or enlarge the diagram and all the triangles so that $$AB$$ has length 1, then we can relate the lengths of all the sides a little more easily.

< This scaling is a handy trick in mathematics to make calculation easier.  For example some maths uses units for length and time in which the speed of light is 1 to make the equations nicer.<br><br>  When you've got to the end of the calculation and are reporting the results, you need to remember that you did the scaling.

Let's put AB=1 and letters a and b to stand for the shorter side lengths, CB and AC. 

!!Scorpio
##Geometry
caption: Subdividing a right-angle triangle
boxed: 200
*:A: (A)
*:B: (C)
*:C: (B)
*:D: (D)
:A: at: 126,140
:B: at: 180,16
:C: at: 466,140
:D: at: 182,138
bond: A B --["  b  "]--
bond: B C --["  a  "]--
bond: C A 
bond: B D
angle: B D A
angle: C D B
angle: A B C
:info:
card:
##Dividing a triangle
"Something about dropping a perpendicular"

!!Markdown

The length AB = 1.  

#### to calculate AD
AB is the hypotenuse of the big triangle.  AC is the hypotenuse of a similar and smaller triangle.  AD/AC = AC/AB by using the scaling of these similar triangles.  Substituting 1 for AB and b for AC we get AD/b = b/1.  So <b>AD = b<sup>2</sup></b>

The same kind of calculation will work to calculate the length DB.

#### to calculate DB
The length AB = 1.  AB is the hypotenuse of the big triangle.  CB is the hypotenuse of a similar and smaller triangle.  DB/CB = CB/AB by using the scaling of these similar triangles.  Substituting 1 for AB and a for CB we get DB/a = a/1.  So <b>DB = a<sup>2</sup></b>

As AD + DB = AB = 1, we've proved that in any right-angle triangle <b>b<sup>2</sup> + a<sup>2</sup> = 1</b>.

No, wait!  We've proved Pythagoras is true if the hypotenuse has length 1, not that all right-angle triangles have a hypotenuse of 1.  

### Boostng the result
We can boost this result to work on any right-angle triangle, for example one with a length of hypotenuse of c.  If the sides are length a, b and hypotenuse c, we scale that triangle to a similar triangle with sides a/c, b/c and 1.  From that triangle and our result that works for hypotenuse of 1, we know that (a/c)<sup>2</sup> + (b/c)<sup>2</sup> = 1.  Or in other words a<sup>2</sup> + b<sup>2</sup> = c<sup>2</sup>, which is the full Pythagoras result for any sized right-angle triangle.

In a sense proving for triangles with a hypotenuse of 1 is as powerful as proving for any hypotenuse, as we easily recover the full result by scaling.


## Other Proofs

There are other proofs of Pythagoras theorem, and different proofs give different ways of looking at the result and seeing that it must be true.  This proof just given brings out that:

> A key reason we look at right-angle triangles at all is because we can divide any triangle into two right-angle triangles.

This subdividing fuelled our proof.  The squaring comes into the equation in the proof because in calculating AD (or DB) we use ratios of sides of the triangle twice.  We go from AB to AC to AD using a ratio twice.  We go from AB to CB to DB using a ratio twice.

That's enough about Pythagoras for the moment.

You may want to return to this page when you're familiar with #NUTC(sine and cosine) functions.  
#[
## Trig

Let us call $$\angle BAC=\theta$$ and again have AB of legth 1  Then:

$$\angle BAC=\theta$$ so $$AC=AB \cos\theta = \cos\theta$$
$$\angle DAC=\theta$$ so $$AD=AC \cos\theta = \cos^2\theta$$

Similarly: 

$$\angle BAC=\theta$$ so $$CB=AB \sin\theta = \sin\theta$$
$$\angle DCB=\theta$$ so $$DB=CB \sin\theta = \sin^2\theta$$

AD + DB = AB = 1.  So with this diagram we've shown that $$\sin^2\theta + \cos^2\theta = 1$$

This is the same proof as before, except instead of saying b we say $$\cos\theta$$ and instead of saying a we say $$\sin\theta$$.  

$$\sin^2\theta + \cos^2\theta = 1$$ for the same reason that <b>b<sup>2</sup> + a<sup>2</sup> = 1</b>.  The trig proof *is* Pythagoras.  It's choosing to look at Pythagoras theorem in terms of trig functions of angles.
#]