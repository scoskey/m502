## Homework 10, due Thursday, April 18

* Let $T$ be the theory of arithmetic, that is, the sentences true in the structure $(\mathbb N;+,\cdot,0,1,\lt)$. Show there is a model of $T$ with an initial segment isomorphic to $\mathbb N$, and additional "infinite" number greater than $\mathbb N$.
* Show that the class of all finite graphs is not first-order axiomatizable (that is, there is no theory $\Sigma$ such that the models of $\Sigma$ are exactly the finite graphs).
* Let $T$ be a complete theory with an infinite model. Can $T$ have any finite models?

### Supplemental problems

* Let $\mathcal A$ be a nonstandard model of the theory of arithmetic. By the above exercise we know that $\mathcal A$ has an initial segment isomorphic to $\mathbb N$. Show that this initial segment has no supremum.
* Let $\mathcal A$ be a nonstandard model of the theory of arithmetic. Show that $\mathcal A$ contains an element which is disivible by every (standard) prime number $p$.
* Let $\mathcal A$ be a nonstandard model of the theory of arithmetic. Show that $\mathcal A$ contains an "infinite" prime number.
* Show that the class of all infinite graphs is not finitely axiomatizable (that is, there is no finite theory $T$ such that the models of $T$ are exactly the infinite graphs).

## Homework 9, due Thursday, April 11

* Suppose that $P$ is a unary predicate and $Q$ is a propositional variable. Give a formal proof of the following: $(\forall x(P(x)\to Q))\to((\forall xP(x))\to Q)$.
* Suppose that $R$ and $S$ are unary predicates. Show that there exists a formal proof of the following: $\forall x(R(x)\to S(x))\to(\exists x R(x)\to \exists x S(x))$.
* Kunen, exercise II.11.16. Suppose $R$ is a binary predicate and use the soundness theorem to show that there does not exist a formal proof of $\forall y\exists x R(x,y)\to\exists x\forall y R(x,y)$.
* Give an example of a structure $A$ and a formula $\phi(x)$ such that $A\models\exists x\phi(x)$ but there is no term $\tau$ such that $A\models\phi(\tau)$.

### Supplemental problems

* Show that logical axiom 3 is valid.
* Show that relation defined by $\sigma\sim\tau$ if and only if $\Sigma\vdash\sigma=\tau$ is an equivalence relation.
* Kunen, exercise II.10.6.
* (2pts) Kunen, exercise II.11.11.
* Kunen, exercise II.11.14
* Kunen, exercise II.11.15

## Homework 8, due Thursday, March 28

* Prove that the connectives $\vee$, $\wedge$, and $\leftrightarrow$ can all be defined using only $\neg$ and $\rightarrow$.
* Using the signature of ordered field theory, write well-formed sentences stating each of the following theorems.
  * Every bounded set has a supremum.
  * Every cubic polynomial has a root.
  * The triangle inequality.
* Prove Kunen, Lemma II.5.4.

### Supplemental problems

* (2pts) Write a computer program that takes a Polish lexicon and string of symbols as input, and determines whether the given string is a well-formed expression.

## Homework 7, due Thursday, March 14

* Define $+$, $\times$, and $<$ on the rational numbers as they were constructed in class.
* Find the rank of the objects: $\mathbb N,\mathbb Z,\mathbb Q,\mathbb R,-2/3,\pi$. (See Kunen, exercise I.15.2 for reference.)
* Write each statement as a standard logical expression. Then develop a lexicon and convert it to prefix notation.
  * The polynomial $x^4+3x+5$ has a root.
  * Any natural $n$ can be written as the sum of four squares.
* Convert the expressions from prefix notation to standard logical notation. The arity function may be inferred from the standard meaning of the symbols, except: $x$ has arity $1$; $A$ has arity $1$ and means "absolute value".
  * $\forall a\mathord{\rightarrow}\mathord{\in}aS\mathord{\leq}ab$
  * $\forall\epsilon\exists N\forall n\mathord{\rightarrow}\mathord{>}nN\mathord{<}A\mathord{-}xnL\epsilon$

### Supplemental problems

* A linear order is said to be *dense* Prove the following classical theorem: Any two  countable, dense linear orders without endpoints are isomorphic to one another.
* Define $+$, $\times$, and $<$ on the real numbers constructed in class.
* (2pts) Kunen, exercise I.15.10 (forget the last sentence).
* Kunen, exercise I.15.14.
* Kunen, exercise I.15.15.
* (2pts) Kunen, exercise II.4.7.

## Homework 6, due Thursday, March 7

* Show that $(\kappa^{\lambda})^\mu=\kappa^{\lambda\mu}$ and $\kappa^{\lambda+\mu}=\kappa^\lambda\kappa^\mu$.
* Find the cardinality of the following sets:
  * The set of finite subsets of $\omega_1$
  * The set of countable subsets of $\omega_1$
  * The set of functions whose domain is a countable subset of $\omega_1$ and whose range is contained in $\omega_2$
  * The set of functions whose domain is a countable subset of $\omega_2$ and whose range is contained in $\omega_1$
* For any $\alpha$ the Axiom of Union holds in $V_\alpha$.
* For limit $\lambda$ the Axioms of Pairing and Power Set hold in $V_\lambda$.

### Supplemental problems 6

* Kunen, exercise I.13.18. Prove that there is a cardinal $\alpha$ such that $\alpha=\beth_\alpha$.
* (2pts) The GCH is equivalent to the statement that $\kappa^{\mathrm{cf}(\kappa)}=\kappa^+$ for all cardinals $\kappa$.
* Kunen, exercise I.14.15. If $K$ is a proper class satisfying $y\subset K\implies y\in K$ then $WF\subset K$.
* (2pts) Kunen, exercise I.14.17. Prove a stronger version of the replacement axiom (see the text).
* Kunen, exercise I.14.23. Prove the version of the induction theorem known as $\in$-induction (see the text).

## Homework 5, due Thursday, February 28

* Kunen, exercise I.11.31. Prove that the $\aleph$ sequence is strictly increasing and that every infinite cardinal is in the $\aleph$ sequence.
* Kunen, exercise I.11.33. Prove that there exists an $\aleph$-fixed point.
* Show that the Choice Set version of AC and the Choice Function version of AC are equivalent.
* Kunen, exercise I.12.13. (Without AC) There is a surjective function from $\mathcal P(\omega)$ to $\omega_1$.

### Supplemental problems 5

* (2pts) Based on Kunen, exercise I.11.6, first part. Give a careful drawing of the graph of a bijection between [0,1] and [0,1/2). Include any helpful explanations with your drawing so it is clear what you mean.
* Kunen, exercise I.11.35. Prove there is an uncountable ordinal without using Replacement or Choice.
* Kunen, exercise I.11.36. Every countable strict total ordering is isomorphic to a subset of $\mathbb Q$.
* Kunen, exercise I.12.17(i). (Without AC) there is an injection from $\omega$ to $A$ iff $A$ is not Dedekind finite.
* Kunen, exercise I.12.17(ii). (With AC) Dedekind finite is equivalent to finite.

## Homework 4, due Thursday, February 14

* The lexicographic product of two well-orders is again a well-order.
* Use the recursion theorem to show that the following are functions. (You may assume that you already know that $+,\times$ are functions.)
  * $f(n)=$ the $n$th prime number
  * $f(n)=2^n$
  * $f(n)=n^{n^n}$
* Kunen, exercise I.11.3.

### Supplemental problems 4

* Kunen, exercise I.9.6, parts (1)(2)
* Kunen, exercise I.9.6, parts (3)(4)
* Show that the cartesian product $A\times B$ can be constructed using the Power Set axiom instead of the Replacement axiom.
* (2pts) Is there an uncountable subset of $\mathbb R$ which is well-ordered by the usual ordering on $\mathbb R$?

## Homework 3, due Thursday, February 7

* Which of the following rules hold for a function f?
  * $f\`\`(A\cup B)=f\`\`A\cup f\`\`B$
  * $f\`\`(A\cap B)=f\`\`A\cap f\`\`B$
  * if $A\subset B$ then $f\`\`A\subset f\`\`B$
* Draw a graph of each of the following relations on $\mathbb R$:
  * $R$ = &lt;
  * $xSy$ iff $x^2=y^2$
  * $xTy$ iff $x^2=1-y^2$
* Kunen, exercise I.7.19. If $R$ is a finite relation, then $R$ is well-founded iff $R$ is acyclic.
* Kunen, exercise I.7.20. If $R$ is a well-order on $X$ and $A\subset X$, then the restriction of $R$ to $A$ is a well-order on $A$.
* Kunen, exercise I.8.11. If $\alpha$ is an ordinal then $S(\alpha)$ is an ordinal; and $\alpha&lt;S(\alpha)$; and $\gamma&lt;S(\alpha)$ iff $\gamma\leq\alpha$.

### Supplemental problems 3

* Kunen, exercise I.7.13. The lexicographic product of (strict) linear orders is a strict total order.
* Kunen, exercise I.7.23. The lexicographic product of two well-orders is again a well-order.
* If $R,S,T$ are arbitrary relations show that $(R\circ S)\circ T=R\circ(S\circ T)$.
* If $f$ and $g$ are functions, show that $f\cap g$ is a function. Under what circumstances will $f\cup g$ be a function?
* Let $\mathcal F$ is a family of functions such that for all $f,g\in F$ we have $f\cup g$ is a function. Show that $\bigcup\mathcal F$ is a function.
* Show that the class of all ordered pairs is not a set.
* Kunen, exercise I.7.16. Suppose $[x,y]$ is an arbitrary pairing function and $R$ is a set of such pairs. Then the domain $\\{x:\exists y [x,y]\in R\\}$ is a set.
* (2pts) Let $A$ and $B$ be finite *disjoint* sets, and consider the following game. Two players alternate playing an element $\langle a,b\rangle\in A\times B$ subject to the condition that $a$ and $b$ may not *both* have been used already. The game ends when one player is left without a legal move, and that player is the loser. What is an upper bound on the number of moves in this game? Which player has a winning strategy?

## Homework 2, due Thursday, January 31

* Kunen, exercise I.6.3. Find a model of extensionality plus there is no empty set.
* Kunen, exercise I.6.15. If $\langle x,y\rangle=\langle x',y'\rangle$ then $x=x'$ and $y=y'$.
* Decide whether each of the following alternative definitions of $\langle x,y\rangle$ is a good one:
  * $\langle x,y\rangle= ${ x, {y} }
  * $\langle x,y\rangle=$ { x, {x,y} }
  * $\langle x,y\rangle=${ {x}, { {y} } }

### Supplemental problems 2

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

### Supplemental problems 1

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