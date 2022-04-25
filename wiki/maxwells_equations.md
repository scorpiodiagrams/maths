~~~Markdown

# A Rat's Guide to Maxwell's Equations
### A rationalist's tour of Maxwell's equations

~~~Scorpio
# MaxwellEqn
!!Hide
\nabla \cdot \mathbf{F} = 4\pi\rho
!!Hide
\nabla \times \mathbf{F} = \frac{i}{c}\left( \frac{\partial \mathbf{F}}{\partial t} + 4\pi\mathbf{J} \right)
~~~Markdown
The two equations above together describe electromagnetic fields.  They describe how magnetism affects electricity and how electricity affects magnetism.  The first describes how fields spread out.  The second describes how fields change over time.  

These are *Maxwell's equations*.

Maxwell solved these equations and found that an electromagnetic disturbance would travel at the speed of light.  He deduced that light could be electromagnetic in nature.

> #DropCap(") The agreement of the results seems to show that light and magnetism are affections of the same substance, and that light is an electromagnetic disturbance propagated through the field according to electromagnetic laws. #DropCapRight(")

There is a lot of mathematical [machinery](#maxwell_the_maths) to these equations.

As well as the mathematical machinery, you also need to understand #NUTC(what the mathematics) is about.  That comes clearer with some history about where the maths came from.#[
#!!Katex: F \,\, \text{- electromagnetic field}
#!!Katex: J \,\, \text{- electromagnetic flow}
#!!Katex: \rho \,\, \text{- charge and magnetic density}
#!!Katex: \pi \,\, \text{- the usual constant 3.1415...}
#!!Katex: i \,\, \text{- the square root of minus one}
#!!Katex: c \,\, \text{- the speed of light}
#]

Maxwell's equations are amazing
* They combine:
** Ampere's Law and
** Faraday's Law
* Maxwell added a missing constant and put the equations together.

 **Let There be Light!**

## Motivations to Study Maxwell's Equations
### As a #NUTC(unification)
#[
Maxwell's equations brought electricity and magnetism together in a unification, and in the process showed that light (and radio waves, gamma rays, microwaves and x-rays) were part of electromagnetic phenomena too.

Such a unification suggests how combining pieces of knowledge can lead to new and deep insights.

> The key to unification of ideas is finding some similarity between distinct ideas - and then carefully exploring the similarities and differences.#]

### As #NUTC(symbol technology)
#[
It's worth spending time appreciating the symbol technology. 

> Thousands of years of mathematical study have gone into formulating a symbolic language powerful and distinct from normal human language.  In that language, formal ways of rearranging symbols have power.

> Maxwell's equations shaped that language.

Maxwell's equations deal with simultaneous coupled changes of multiple quantities.  

* It's no accident that machine learning frameworks dealing with gradients of change in multiple coupled quantities are based on tensors, an onward development of the notation in Maxwell's equations for fields.

Maxwell's equations lead to tools for handling oscillations simultaneously in three dimensions.  

* Those tools are also relevant in propagation of information in neural networks.  The idea that neural networks can oscillate is not mainstream.  That's because the set ups that work have been chosen so as to damp the oscillations.  Oscillations show up clearly in recurrent neural networks where an output from the network is fed back in as an input.  An important role of common  'non-linear' elements in networks is to damp those oscillations.#]

## Faraday's and Ampere's Law

The tl/dr; is that before Maxwell there were two separate laws.


## Consequences

## History and Variations

* The four-equation formulation
* The Integral formulation

## Quantum Wave Equations

## Open Questions

Why are there #NUTC(no magnetic monopoles)?#[
The normal presentation of Maxwell's equations has four equations, twice as many equations as shown here, because the real and imaginary parts are broken out separately.

When presented as four equations they #NUTC(leave a puzzle):#[ 

> #DropCap(?) "Why do the equations for magnetic field lack a term for 'magnetic monopoles' whilst the equations for electric field have a term for 'electric monopoles' (aka electrons/protons)?"
#]

When Maxwell's equations are presented using complex numbers and just two equations, the nature of the 'no magnetic monopoles' question changes.  The #NUTC(question becomes...)#[

< #DropCap(?) "Why aren't there more types of electromagnetic monopole?"

The subtle shift here is recognising that if there is some type of electromagnetic monopole carrying a mix of electric and magnetic properties, we can multiply the equations through by a constant, so as to choose that the unit of electromagnetic charge that kind of particle holds is one, with no imaginary part.  Choosing that the magnetic part vanishes and the electric part doesn't is 'just' a choice of how we measure electromagnetic charge and how we present the equations.

There is still a real question as to why there aren't more types, and indeed why 'the electron' and 'the proton' have exactly opposite electromagnetic charge.

We have made the equations more symmetric and in one sense simpler, by presenting the equations using complex numbers.  By doing so we have separated a constraint on electromagnetic particles out from the equations about how electromagnetism behaves.#]
#]

~~~Markdown

 *The intention in this nutshell is to explain the maths behind Maxwell's equations, of which there is a lot.  There are multiple places we can do better than standard explanations, similar to how the betterexplained website does things.  After that we move on to explaining why there are no magnetic monopoles.*

