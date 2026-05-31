## Extra notes for module 1

**Textbook: Vector Calculus by Marsden and Tromba**

**Module: 1**

**Date completed: 30/05/26**

*These are extra notes on the subjects and topics, which have been taken when solving questions from the textbook I am working on*

#### Cauchy Schwarz Inequality:

From the dot product we know that:

$\vec{u} \cdot \vec{v} = |v||u| \cos{\theta}$

Now $\cos \theta$ range between $0$ and $1$ so the dot product cannot in any circumstance be greater than the multiple of the magnitudes of two vectors and is only equal when the two vectors are parallel . From this we derive the Cauchy-Schwarz Identity.

$a \cdot b \leq |a||b|$ 

#### Triangle inequality

$|a+b| \leq |a|+|b|$

The proof is simple, and accomplished using the Cauchy Schwarz inequality 

$(a+b) \cdot (a+b) \leq ({|a|+|b|})^2$

$|a|^2+|b|^2+2a \cdot b \leq |a|^2+|b|^2+2|a||b|$

Then apply Cauchy Schwarz to complete the proof

#### Functions

Functions are mappings from a domain to a range, in vector calculus we usually deal with mappings from $\mathbb{R}^ n \to \mathbb{R}^ m$ , the function is called **Scalar valued** if m=1 and vector valued if m>1.
