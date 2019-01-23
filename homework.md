## Homework 2, due Thursday, January 31

* Kunen, exercise I.6.3. Find a model of extensionality plus there is no empty set.
* Kunen, exercise I.6.15. If $\langle x,y\rangle=\langle x',y'\rangle$ then $x=x'$ and $y=y'$.
* Decide whether each of the following alternative definitions of $\langle x,y\rangle$ is a good one:
  * $\langle x,y\rangle= ${ x, {y} }
  * $\langle x,y\rangle=$ { x, {x,y} }
  * $\langle x,y\rangle=${ {x}, {{y}} }
* ...

### Supplemental problems

* Kunen, exercise I.6.11 and I.6.13.
* The axiom of comprehension begins $\exists y\ldots$. Show that in fact this $y$ is unique.
* Show that the naive comprehension axiom (I.6.4) is false in the instance when $Q(x)$ is $\neg\exists u(x\in u\wedge u\in x)$.
* Generalize the previous problem further.

## Homework 1, due Thursday, January 24

* Interpret each of the symbolic expressions as English mathematical statements.
  * $(\forall N\in\mathbb N)(\exists n&gt;N)(\forall a,b)(n=ab\implies n=a\vee n=b)$
  * $S\subset\mathbb R\wedge(\exists x\in S)(\forall y\in S)(y\leq x)$
* Write each of the English mathematical statements as symbolic expressions.
  * The sum of any two odd numbers is even.
  * Every real cubic polynomial has a real root.
* Recall that the ``exclusive or'' connective is written $P\oplus Q$ and is equivalent to $(P\wedge\neg Q)\vee(\neg P\wedge Q)$.
  * Write a truth table for $P\oplus Q$.
  * Draw a Venn diagram for $P\oplus Q$.
  * Is $\oplus$ associative? Prove your answer.
* Kunen, exercise I.2.1

### Supplemental problems

* Write the statement more formally and prove it: "The empty set is unique."
* Find the definition of the $\cap$ operation on page 10. Give a definition of the $\cup$ and $\smallsetminus$ (set difference) operations. Then prove the De Morgan law: $x\smallsetminus(y\cup z)=(x\smallsetminus y)\cap(x\smallsetminus z)$.
* Prove by induction: if $A$ is a set with $n$ elements, then $A$ has exactly $2^n$ subsets.
* Show that Set Existence axiom follows from the other axioms.
* (2pts) Show that the Pairing axiom follows from the other axioms.
* (2pts) Show that the Separation (Comprehension) axiom follows from the other axioms.

<script type='text/x-mathjax-config'>
  MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']], processEscapes: true}});
</script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML'></script>