---
fontsize: 11pt
header-includes: |
  \usepackage{setspace}\onehalfspacing
  \usepackage{geometry}
  \usepackage{hyperref}
  \def\set#1{{\left\{#1\right\}}}
  \def\abs#1{{\left|#1\right|}}
  \def\lt{<}
---

# Math 502 course notes

Based largely on our textbook Ken Kunen, *The Foundations of Mathematics*.

## Introduction

### 1. Introduction to foundations

While mathematics has been studied for millennia, the foundations of modern mathematics dates back to the 1800s. While there are several proposals for the foundations of mathematics, the standard and most popular consists of two main components: logic and set theory. Loosely, logic allows us to study statements and proofs, and set theory allows us to build mathematical objects.

Logic and set theory are used in tandem to form the foundations of mathematics. Thus it will not be too surprising to know there is a somewhat circular relationship between the two. In this course we will follow Kunen and make the choice to cover set theory first and logic second. However we will need a minimum understanding of logic to begin talking about set theory. Thus we will begin 

If there is time, we will study the more recent topic of computability theory in Part III.

However before we begin Part I we will need to preview just enough logic from Part II that we can talk about set theory.

Logical symbols: and, or, not, implies, iff, for all, there exists, and variables

Non-logical symbols: the relations, functions, and constant symbols used in a given context. Examples include $+,\times,<,0$.

Sentences versus formulas...

The axiomatic method: for any area of study, we first choose a universe of discourse and an appropriate collection of non-logical symbols. We then write down a collection of axioms that govern how the symbols behave. Finally we try to prove theorems using only the axioms.

* Example 1: geometry
* Example 2: group theory
* Example 3: arithmetic

Our main example will be set theory. Set theory is important for two key reasons. First it is a foundational theory, meaning all of the above theories can be studied inside of set theory. Second it allows us to study the idea of infinity, since after all we know there are infinite sets.

In set theory the universe of discourse consists of all possible sets. The only non-logical symbol will be the binary set membership relation $\in$. The remaining set relations and operations will be definable from this one alone.

BIG IDEA: In particular everything is a set, even the elements of a set! We say that the universe consists of *hereditary sets*.

BIG IDEA: Essentially all mathematical objects can be built using hereditary sets.

BIG IDEA: Something about infinity.

Axioms and models. Perhaps using quasi orders, partial orders, linear orders, and finite directed graph models.

## Part I: Set theory

### 2. Naive set theory

Operations on sets. look at Joy of Sets.

### 3. Axiomatic set theory: Axioms to get going

* Set theory is officially the axioms for the set membership relation $\in$.
* There are many additional set relations and operations, but these can all be defined in terms of $\in$. For example consider subset, union, intersection, and empty set.
* Draw some sample models and play around
* The axioms of set theory must at least get the hereditarily finite sets right.
* Axiom of (Empty) Set Existence: not officially necessary, but let's just start with this.
* Axiom of Extensionality: This axiom distinguishes set theory from other types of collections (lists, multisets). 
* Axiom of Pairing:
* Axiom of Union:
* Proposition: there exists a nonempty set
* Proposition: there exists a set with more than one element
* Proposition: there exists a set with more than two elements
* In general, one can see how all sets involving $\set{\ }$ and $\emptyset$ may be created

### 3.5 The Axiom of Separation and Russell's paradox

* Axiom of Separation: Allows to form subsets. This justifies the use of the set-builder notation $\set{z\in x\mid \phi(z)}$.
* Naive Axiom of Comprehension: $\set{z\mid P(z)}$. This leads to two problems: the use of non-logical phrases such as "the least natural number that can be defined in fewer than 20 words", and Russell's paradox. The modern comprehension axiom is also called the separation axiom.
* The Axiom of Separation is really an axiom scheme. Thus set theory officially has infinitely many axioms.

### 4. Numbers, functions, and the Axiom of Replacement

* We have promised that set theory is somehow the theory of everything, meaning all other objects of mathematical study can be regarded as sets. Perhaps the most important objects in mathematics are natural numbers. How can these be regarded as objects in the universe of sets?
* Von Neumann ordinals: an ordinal is a counting number (as opposed to a quantity measuring number). Define $0,1,2,3,\ldots$ as particular hereditarily finite sets.
* We have also promised that set theory is somehow the theory of the infinite, meaning we can study different kinds of infinity using sets. The axiom of infinity will allow us to count into the infinite.
* In general, an ordinal is equal to the collection of ordinals that came before it. Thus the Von Neumann ordinals will be extended into the infinite by setting $\omega=\set{0,1,2,3,\ldots}$, $\omega+1=\set{0,1,2,3,\ldots,\omega}$ and so on. Infinity plus one!
* Thus we have a successor function $S(\alpha)$ or $\alpha+1$ is equal to $\alpha\cup\set{\alpha}$. 
* Another of the most important mathematical objects is a function. You may have seen the definition of a function as a set of ordered pairs (input,output).
* Ordered pair: $(a,b)$ is defined to be $\set{\set{a},\set{a,b}}$. We have to check this "works". Observe that other more naive attempts don't work.
* Binary relation: any set whose elements are ordered pairs. If $R$ is a set of ordered pairs $(a,b)$ then we write $aRb$ to mean that $(a,b)$ is an element of $R$. Example: less than
* Function: 
* In elementary mathematics, we usually teach that a function is a formula or rule. But in formal mathematics, a function is really its graph.
* Domain and range: these concepts are valid for binary relations (and in particular for functions). Note both the domain and range of $R$ are subsets of $\bigcup\bigcup R$.
* Injective, surjective, and bijective: ...
* Cartesian product: Most binary relations, and thus most functions, are constructed as a subset of a cartesian product $A\times B=\set{(a,b)\mid a\in A, b\in B}$.
* In order to show that the cartisian product exists, we actually need a new axiom!
* Replacement Axiom: For each logical formula $\phi(x,y)$ satisfying $\phi(x,y)$ and $\phi(x,y')$ implies $y=y'$, the following is an axiom: For all A, there exists B which is the image of phi restricted to the domain $A$.
* Once again, the replacement axiom is an axiom scheme.
* Theorem. For any sets $A,B$ we can construct the cartesian product $A\times B$.
* Proof: First, for each $b\in B$ we can use replacement with $\phi(x,y)$ being "$(x,b)=y$" and domain $A$ to construct each $A\times\set{b}$. Then use replacement with phi(x,y) being "$A\times\set{x}=y$" to construct the set $\set{A\times\set{b}\mid b\in B}$. Finally apply union to this to get $AxB$.
* For example, suppose we have constructed the set $\mathbb N$ of natural numbers. Then we can construct the cartesian product $\mathbb N\times\mathbb N$. We can further construct the less than binary relation on $\mathbb N$. If we have already constructed the $+$ and $x$ operations (which we'll do still later), we can further construct functions such as $f(n)=n^2+2n+5$.

### 5. Well-orders

* We have introduced functions as relations but there are several other special types of relations.
* Order relations: Like the $\lt$ relation on $\mathbb R$.
* Def: A (strict) linear order is a binary relation $R$ on a set $X$ (meaning both the domain and range are contained in $X$) satisfying the axioms transitive, irreflexive, and trichotomy
* Equivalence relations: Like equality, congruence, similarity, isomorphism.
* Def: An equivalence relation is a binary relation R on a set X satisfying the axioms transitive, reflexive, and symmetric.
* Isomorpism of linear orders: ...
* For example, on $\mathbb R$ the $\lt$ and $>$ relations are isomorphic to one another. However on $[0,1)$ they are not.
* Examples of linear orders: most number sets such as $\mathbb N,\mathbb Z,\mathbb Q,\mathbb R$, and the induced ordering on any subset of these.
* The key example in set theory is the ordering of the ordinals as introduced above. The $\in$ relation is a linear order.
* What is an ordinal really? In addition to being a linear order, one key property is that it only has ...'s that go to the right.
* Def: A relation $R$ on a set $X$ is called well-founded if for all nonempty subsets $Y\subset X$, $Y$ has an $R$-minimal element (an element $y\in Y$ such that for all $z\in Y$ it is not true that $zRy$).
* Def: A well-founded relation that is also a linear order is called a well-order.
* Examples: None of $\mathbb Z,\mathbb Q,\mathbb R$ are well-orders, but N and ordinals are.
* Theorem: A relation R is a well-order iff there is no infinite R-descending sequence.
* Proof: ($\rightarrow$) Note that an infinite $R$-descending sequence has no $R$-minimal element. ($\leftarrow$) If $R$ is not well-founded and $X$ has no $R$-minimal element, pick any $x(0)\in X$ and recursively choose $x(n+1)\in X$ such that $x(n+1)Rx(n)$.
* (Later we will make the concepts "infinite", "recursively", and "choose" formal.)

### 6. Ordinals

* We have already seen two special properties that the Von Neumann ordinals have: They are linear orders with $\in$ as the order relation, and they are well-founded. These two properties can be combined by saying that ordinals are well-ordered by $\in$.
* But ordinals aren't the only sets with these properties, because for example any set of ordinals would have it: {1,3,5,7}. We need one more property.
* Def: A set z is transitive if for all x,y, $x\in y\in z$ implies $x \in z$. In other words, elements of elements are elements. Alternatively, elements are subsets. (Confusing note: this use of the word transitive is slightly different than the use for orderings.)
* The example A={1,3,5,7} fails to be transitive because $4 \in 5 \in A$ but $4 \notin A$.
* Def: A set $\alpha$ is an ordinal if (1) $\alpha$ is well-ordered by $\in$ and (2) $\alpha$ is a transitive set.
* The collection of all ordinals is denoted ON or ORD. (We say collection because later we'll see it's not a set.)
* It will take some work to prove that ORD is really the Von Neumann ordinals that we introduced informally above. Essentially, it is everything you get by starting with 0, taking successors, and taking unions.
* Although ORD is not a set, we will show it also satisfies the defining properties of each individual ordinal.
* Theorem: (1) The collection ORD is well-ordered by $\in$; (2) The collection ORD is a transitive class.
* Before proving this theorem, we prove the corollary: ORD is not a set. If it were, then by definition of ordinal we would have ORD in ORD. This means ORD has an infinite descending sequence, contradicting that it is well-founded.
* Proof of (2): We must show that if $\alpha$ is an ordinal, and $z \in \alpha$, then z is an ordinal.
  * To see z is well-ordered, note that $\alpha$ is transitive, so z is a subset of alpha, which means z is well-ordered by $\in$ (since well-ordered passes to subsets).
  * To see z is a transitive set, let $x \in y \in z$. Since alpha is transitive, $x \in \alpha$. Since $\alpha$ is linearly ordered by $\in$, $x \in z$.
* Proof of (1): We have to show ORD satisfies transitivity, irreflexivity, trichotomy, and well-founded.
    * transitivity of order: If alpha in beta in gamma, since gamma is a transitive set, we have alpha in gamma.
    * irreflexivity: If $\alpha \in \alpha$, then the ordinal $\alpha$ would be irreflexive too.
    * well-founded: Let X be a nonempty subset of ORD. Let $\alpha \in X$. If $\alpha$ is minimal, great. Otherwise let $X'=\alpha \cap X$, a nonempty subset of $\alpha$. Since $\alpha$ is well-ordered, $X'$ has a minimal element, and this works for X too.
    * trichotomy: Let $\alpha, \beta$ be given.
      * claim: the intersection delta of alpha,beta is in ORD. Indeed, the well-ordered property passes to subsets, and the transitive set property passes to intersections.
      * claim: if delta is a proper subset of alpha, then delta is in alpha. Indeed let xi=min(alpha-delta). Then gamma in xi implies gamma in delta (otherwise the min would be lower), and gamma in delta implies gamma in xi (otherwise xi in gamma in delta, implies xi in delta). Thus delta=xi.
      * claim: either alpha is contained in beta or beta is contained in alpha. If neither, by the above delta is in alpha intersect beta = delta, contradicting irreflixivity.
      * Now wlog alpha is a subset of beta, and not equal to beta. Then by the second cliam, alpha is in beta, as desired.
* Whew!

### 7. More ordinals

* We have defined a set alpha to be an ordinal if it is well-ordered by $\in$ and a transitive set. We have shown the ordinals are a proper class that is itself well-ordered by $\in$ and transitive.
* The ordinal successor operation: $S(\alpha)$ or $\alpha+1$ = $\alpha \cup \set{\alpha}$. In principal this may be carried out on any set, but it is most useful on ordinals because then it always produced another ordinal.
* What about alpha-1? Our discussion suggests that there will be two kinds of ordinals.
* Def: an ordinal $\alpha$ is a successor of $\alpha=S(\beta)$ for some $\beta$.
* Def: an ordinal $\alpha$ is a limit if it is not 0 and not a successor.
* The ordinal we have called $\omega$ will be our first limit ordinal. We are now just about ready to go to $\omega$ and beyond.
* Def: an ordinal $\alpha$ is a natural number if it is a successor and all its elements are successors. This gives us a clever way to define finite without really knowing anything about finite or infinite sets!
* Axiom of Infinity: the collection of natural numbers is a set, called either $\omega$ (thought of as an ordinal) or $\mathbb N$ (thought of as a number set).
* Kunen's version actually says there exists a set containing 0 and closed under successor. Given such a set one may use comprehension to obtain $\omega$.
* Proposition: $\omega$ is an ordinal, it is a limit ordinal, and it is the least limit ordinal.
* Proof: $\omega$ is a subset of ORD, which immediately implies that it is well-ordered by $\in$. Moreover the definition implies $\omega$ is an initial segment of ORD, and this further implies that $\omega$ is a transitive set. Thus $\omega$ is an ordinal. To see that it is a limit ordinal, observe that if it were a successor ordinal then we would have $\omega\in\omega$, contradicting irreflexivity in ORD. Finally every element of $\omega$ is a successor ordinal, so $\omega$ is the first limit ordinal.
* Once we have that $\omega$ exists, we can construct its finite successors. We can construct further ordinals such as $\omega+\omega$ using the axiom of replacement.
* We can also construct ordinals by constructing well-ordered relations of various kinds. To motivate this, consider some well-ordered relations that are not ordinals: {1,3,5,7}, {1-1/n}, {1-1/n,1}. Each of these is equivalent to a true ordinal: 4, $\omega$, $\omega+1$.
* Theorem: If R is any well-ordered relation on a set A, then R is isomorphic to a unique ordinal. (Remind isomorphic. It means lines dont cross.)
* Proof:
  * We first show the unique portion of the theorem, by showing that if $\alpha,\beta$ are ordinals and $\alpha\neq\beta$, then $\alpha,\beta$ are not isomorphic to one another. The contrapositive says that if $\alpha,\beta$ are isomorphic then they are identical.
  * For this, suppose $f\colon\alpha\cong\beta$. We wish to show that f is the identity function. If it isn't the identity function, then there exists $\xi\in\alpha$ which is the first point moved by $f$. (Use the well-foundedness of $\alpha$ here.) If $f(\xi)=\mu<\xi$ then we would also have $f(\mu)=\mu$, contradicting that f is injective. On the other hand if $f(\xi)=\mu>\xi$ then nothing can possibly map to $\xi$, contradicting that $f$ is surjective.
  * We next show the existence portion of the theorem, which will be seen to have an inductive flavor.
  * Let R be a well-ordered relation on A. For each $a\in A$ let pred(a) denote the set of R-predecessors of A. Define a set of "good" elements by G={a:pred(a) is isomorphic to an ordinal}. Using the uniqueness proved above, and the axiom of replacement, we may define a function on G by f(a)=the unique ordinal such that pred(a) is isomorphic to f(a). We now make a series of observations:
    * G is an R-initial segment of A, since if $a\mathrel{R}b\in G$ and $pred(b)\cong\beta$ we can restrict this isomorphism to $pred(a)$.
    * f is an order-preserving map from G into the ordinals, meaning that $aRb$ implies $f(a)\in f(b)$.
    * f(G) is an initial segment of the ordinals, since if $\beta\in\alpha=f(a)$ then there is an isomorphism of pred(a) with $\alpha$ carrying some b to $\beta$, and then $f(b)=\beta$.
  * It follows that the range of f IS an ordinal, call it $\xi$. To complete the proof, it is enough to show that G=A. If this is not the case, then let a be the minimum element of $A\setminus G$. Then pred(a) is exactly G, and it follows that f is an isomorphism of pred(a) with $\xi$. The definition of G now means that $a\in G$ after all, a contradiction!
* Whew!

### 8. Ordinals and induction

* We have seen that if R is a well-order on a set A, then (A,R) is isomorphic to a unique ordinal alpha. This ordinal is called the ordertype or just type of (A,R).
* Lexicographic ordering. If (A,R) and (B,S) are linear orders, we can form their lexicographic product which is an order on the cartesian product AxB defined by (a,b)&lt;(a',b') iff a&lt;a', or a=a' and b&lt;b'.
* The product of two ordinals. If alpha and beta are ordinals, then we can take a lexicographic product to get a well-order on pairs. This well-order isn't an ordinal, but one may verify it is well-orderd. By the above it is isomorphic to an ordinal. We actually define alpha.beta to be the lex product beta X alpha. The reason is that we want alpha.beta to be alpha, beta many times. Or in other words each element of beta is replaced by a copy of alpha. E.g. omega.2 is what we previously called omega+omega, whereas 2.omega is just omega.
* The sum of two ordinals. alpha+beta is the type of the lexicographic order on {0}xalpha union {1}xbeta. Intuitively a copy of alpha is followed by a copy of beta. E.g. we get alpha+alpha = 2 x alpha = alpha.2.
* Both multiplication and addition are associative but not commutative. A complete list of arithmetic laws can be found in the book on page 41.
* Ordinals also have a supremum operation sup(X)=union(X). We know supremums exist by well-foundedness of ON, but we actually have a formula for it.
* We can see in small examples that ordinal multiplication is just repeated ordinal addition. We will also have ordinal exponentiation, which will be repeated ordinal multiplication.
* We have to be clear about what "repeated" means for infinite ordinals! It is finally time to talk about induction and recursion on the ordinals. Officially, we haven't even proved that the factorial exists!
* As a preview, recall that recursive definitions on the natural numbers have two parts, a base case and a recursive case. For example, 0!=0 and (n+1)!=(n+1)n!. Recursive definitions on the ordinals have three parts, a base case, a successor case, and a limit case.
* To use ordinal exponentiation as an example, we will define: alpha^0=1, alpha^(beta+1) = (alpha^beta).alpha, and if lambda is a limit then alpha^lambda = sup{alpha^beta : beta&lt;lambda}.
* Before stating the transfinite recursion principle, we should probably state the transfinite induction principle/scheme: If phi(x) is a formula, and phi(0) is true and for all beta phi(beta) implies phi(beta+1) and for all lambda (beta&lt;lambda implies phi(beta)) implies phi(lambda), then phi(x) is true of all ordinals.
* This principle is simply equivalent to the well-ordering of ON. If some phi failed to satisfy the conclusion, there would be a least counterexample, contradicting the hypothesis.
* A recursive definition is a little more complicated. You are trying to define a function F on all ordinals, and you do so using a function G of all values of F defined so far. In the end, F(alpha) = G( F(0), ... , F(beta), ... ) (beta&lt;alpha).
* Ex: For the factorial function one uses G(empty)=0 and G(s\_0,...,s\_n-1) = ns\_n-1.
* Ex: For the fibonacci numbers one uses G(empty)=0, G(1)=1, and G(s\_0,...,s\_n-1)=s\_n-2+s\_n-1.
* Ex: For ordinal exponentiation with base alpha, one uses G(empty)=1, G(s\_0,...,s\_beta)=s\_beta . alpha, and G(s\_0,...&lt;lambda) = union s\_beta.
* The transfinite recursion principle: Let G(x) be a proper class function (defined by a function-like formula phi(x,y)). Then there is a proper class function F(x) such that for every alpha we have $F(\alpha)=G(F\restriction\alpha)$.
* The proof is similar to the proof of the classical recursion principle, and it relies on the principle of induction plus replacement. We will content ourselves with a summary in the case of $G(s)=n\cdot s\restriction n$.
  * We want to build the function F(n)=n!. We do this by building a sequence of approximations F\_n. Each function F\_n has domain n={0,...,n-1} and behaves like the usual factorial.
  * We prove by induction that for each n, there exists a unique function F\_n with the property described above. The base case is trivial. The inductive step is true because we can define f\_n+1 (n) = nf\_n(n-1), and check this is unique.
  * We finally let F(n)=F\_n+1 (n). This is the desired item.
* The general theorem is proved by: (1) substitute whatever G is into the proof, (2) at limit stages obtain F\_lambda by taking a union of the previous F\_beta's.
* We can finally make sense of the intuitive idea of doing something iteratively. This will be of fundamental importance to our study of the infinite.
* Example: epsilon\_0.
* Example: transitive closure: Define U^nz inductively, and then tc(z)=UU^nz.

### 9. Cardinality and the Axiom of Power Set

* We used the axiom of infinity to show that the natural numbers is a set. It is not difficult to build the integers and then rational numbers from the natural numbers. However we have not shown that the set of real numbers exists.
* The usual definition uses cuts: R = { C : C is a subset of Q satisfying blah blah }. However observe that this is not a valid set builder. We again need another axiom.
* The Axiom of Power Sets: For any set x, let P(x) denote the collection of all subsets of x. The axiom says that for any set x, the collection P(x) is a set.
* It is now possible to define real numbers using cuts, as described above.
* The real numbers are actually just one of many digit-type spaces. Others include Cantor space 2^N^ and Baire space N^N^.
* Notation: If A and B are sets, then Fun(A,B) or sometimes ^A^B or sometimes B^A^  denotes the space of all functions from A to B. To explain this notation, consider examples like R^n^.
* Proposition: If A and B are sets, then Fun(A,B) is a set.
* Proof: A function from A to B is a subset of AxB with the function-like property. Thus the set of all functions can be constructed as a subset of P(AxB) using comprehension.
* Cardinality. Recall that a set A is countable if there exists a sequence (an) enumerating A. In set theory terms, we are just saying that there exists a function from omega to A that is surjective.
* We have shown that there exist large ordinals like epsilon0. But is this ordinal really large? In fact it is still countable! The reason is that in the construction we are just taking lexicographic products and countable unions. Each of these operations preserves countability. This is the difference between ordinality (length) and cardinality (amount).
* The power set axiom is what lets things get truly large. Before explaining we recall the notation and terminology of cardinality.
* We say that $\abs{A}\leq\abs{B}$ if there is an injection, $\abs{A}=\abs{B}$ if there is a bijection, and $\abs{A}<\abs{B}$ if there is an injection but no bijection.
* Note that so far we have told you how cardinality works, but not what cardinality is. We will remedy this later.
* Cantor's theorem. If $A$ is any set, then $\abs{A}<\abs{\mathcal P(A)}$.
* Proof.
  * The function $i(a)=\set{a}$ is an injection $A\to\mathcal P(A)$.
  * Now suppose that $f$ is any function $A\to\mathcal P(A)$. We will show that some subset D of A is not in the range of f. Thus f is not a bijection. Since f was arbitrary this proves the theorem.
  * The definition of D is { a in A : a notin f(a) }. This is called a diagonalizer.
  * Example: suppose $f(a)=\set{b,c,z}$, $f(b)=\set{a,b,c,d}$, $f(c)=\set{a,d,e,g,h}$, $f(d)=\set{d,w,z}$, .... Then we would let $D=\set{a,c,...}$. This is guaranteed not to be in the range because it differs from every $f(x)$ on the subject of $x$.
  * Formally, suppose towards a contradictoin that D is in the range and let f(a)=D. Then ask whether a in D (it implies a notin D) and whether a notin D (it implies a in D).
* Corollary. There are infinitely many distinct cardinalities, and infinitely many distinct uncountable cardinalities. For example, omega, P(omega), P(P(omega)), etc.
* Corollary. The digit spaces 2^N^, N^N^, and R are uncountable. The first space is exactly P(omega), and the first space embeds into the latter two.
* But what is the exact cardinality of N^N^ and R?
* Cantor-Schroder-Bernstein theorem. If $\abs{A}\leq\abs{B}$ and $\abs{B}\leq\abs{A}$ then $\abs{A}=\abs{B}$.
* Proof.
  * Since there is an injection from B to A, we may replace every element of B by its corresponding element in A and assume without loss of generality that B is a subset of A.
  * We can now draw a picture of the sets A, B, f(A), f(B), f(f(A)), etc
  * The picture is divided into "rings" A-B, B-f(A), f(A)-f(B), f(B)-f(f(A)), etc, together with the "inner most ring" C (intersection).
  * We now divide the rings into three classes, those starting with A, those starting with B, and C:
    * class 1: A-B, f(A)-f(B), f(f(A))-f(f(B)), etc
    * class 2: B-f(A), f(B)-f(f(A)), etc
    * class 3: C
  * The function f sends the first class down the line, the second class down the line, and the third class to itself.
  * Now define a function g which applies f to class 1, and the identity to classes 2 and 3. This is a bijection from A to B.
* Corollary. The digit spaces 2^N^, N^N^, and R are all the same cardinality as P(omega). Proof. We just have to show that there are injections from N^N^ and R back into P(omega). For N^N^, the graph of any element is a subset of NxN. Since NxN is in bijection with N, we can regard it as an element of P(N). For R, exercise.

### 10. Cardinals

* Previously we defined the behavior of $\abs{A}$ in terms of injections and bijections. But what exactly is $\abs{A}$?
* One of the earliest definitions of $\abs{A}$ was the set of all sets that are in bijection with A. Thus 3 is the set of all 3-element sets. But this object is a class not a set.
* Once we again use the idea of representatives, so $\abs{A}$ will be a particular set of size A (if possible). And once again we turn to the ordinals.
* Def: An ordinal alpha is called a cardinal if it isn't in bijection with any lower ordinal.
* Ex: 0,1,2,... are all ordinals that are cardinals. omega is also a cardinal. But as we have seen, omega^2^ and so on are not cardinals.
* Def: If A is any set then $\abs{A}$ = a cardinal kappa such that there is a bijection between A and kappa. Note that if this exists it must be unique.
* Ex: This supports standard calculations like $\abs{\text{divisors of 10}}=4$.
* Ex: If A is a countable set, then $\abs{A}=\omega$.
* Question: What is $\abs{\mathbb R}$?
* In principle, there may be sets A which are not in bijection with any ordinals/cardinals. In such a case $\abs{A}$ cannot be defined to be an ordinal or any particular object. Thus to approach cardinals in this way we need an axiom.
* Axiom of Choice: For any set A, there is a bijection of A with some ordinal. In particular there is a bijection of A with some cardinal kappa.
* Prop: Every natural number ordinal is a cardinal.
* Proof: Show by induction that no natural number is in bijection with an earlier one.
* Prop: Every infinite cardinal is a limit ordinal.
* Proof: Clearly omega+1 is in bijection with omega. Use this to show that if omega$\leq$alpha, then alpha+1 is in bijection with alpha.
* Prop: Any limit (union) of cardinals is a cardinal
* Proof: Let kappa = a union of kappa\_beta's. If kappa is in bijection with some lower xi, then we would have xi&lt;kappa\_beta for some beta. Then we have xi$\leq$kappa\_beta$\leq$kappa$\leq$xi. By Cantor-Schroder-Bernstein there is a bijection between xi and kappa\_alpha, contradicting that kappa\_alpha is a cardinal.
* The next result shows that there are uncountable ordinals. This follows from AC and Cantor's theorem, but we can prove it without AC.
* Hartog's Theorem: For any set A, there is a cardinal kappa such that there is no injection from kappa to A.
* Proof.
  * Let W be the set of binary relations R on subsets of A such that R is a well-order of its domain. (We are using power set to know this exists.) Let kappa be the supremum of the ordertypes of the orderings in W. (We are using replacement to know this exists.)
  * Then there is no injection from kappa to A. Indeed if there were then the ordering on kappa may be sent through the injection to give a well-ordering on a subset of A. This would again mean that kappa is in kappa.
  * Finally kappa is a cardinal. Indeed if kappa were in bijection with some alpha&lt;kappa, then there is a subset of A that is alpha-ordered, and we could produce an injection from kappa to A.
* Applying Hartog's theorem to A=n, we obtain n+1. Applying Hartog's thoerem to A=omega, we obtain the existence of an uncountable cardinal. Applying this repeatedly, we obtain a tower of uncountable cardinals.
* Def. Given any cardinal kappa, let kappa+ denote the last cardinal that is greater than kappa.
* Def.
  * Let aleph0 be the first infinite cardinal, omega
  * Let aleph(alpha+1) = aleph(alpha)+
  * Let aleph(lambda) = sup(aleph(beta)), beta&lt;lambda
* Ordinal arithmetic doesn't increase cardinality. For example:
* Prop. If kappa is an infinite cardinal then $\abs{\kappa\times\kappa}=\abs{\kappa}$.
* Proof. We must show kappa x kappa is injectible into kappa. Assume it is true for every alpha&lt;kappa. Let R be the usual increasing boxes ordering of kappa x kappa. Then every initial segment of R is contained in some alpha x alpha, and hence injectible into alpha. It follows that R is injectible into kappa. (If it weren't then kappa would be injectible into some initial segment of R and hence into some alpha&lt;kappa contradicting it is a cardinal.)
* Continuing this logic one can determine that even iterated ordinal exponentiation etc does not increase cardinality. In particular the countable ordinals extend inconceivably far before finally being dominated by aleph1.
* Ordinal exponentiation vs cardinal exponentiation

### 11. Axiom of Choice

* We have said that the axiom of choice allows us to regard all cardinals as special ordinals that are not in bijection with any smaller ordinal. But what does the axiom say exactly?
* Axiom of Choice: If F is a set of nonempty sets which are pairwise disjoint, then there exists a set C such that $\abs{C cap A}=1$ for all A in F.
* In other words, C is a choice or selection of one element from each member of the family.
* Observe the disjointness assumption is necessary, since for instance F={ {2}, {2,3}, {3} } does not have a choice set.
* There is a non-disjoint version: If F is a family of nonempty sets, then there exists a function c:F to UF such that c(a) in A for all A in F.
* So in the above example, we could have c({2})=2, c({2,3})=2, and c({3})=3 without any contradiction.
* Exercise: The two statements are equivalent.
* The Axiom of Choice may seem somewhat arbitrary, but it turns out it is used many times over in modern mathematics:
  * Every set has an ordinal cardinality
  * The union of countable sets is countable
  * The product of nonempty sets is nonempty
  * Every vector space has a basis
  * There exists a Lebesgue nonmeasurable set
* Ok, the Axiom of Choice is fundamental, and it seems innocent enough. So why is it controversial? Unlike the other axioms it is non-constructive in the sense that it doesn't tell you exactly what the elements of C will be.
* We now start to investigate some of these useful consequences of AC.
* Well Ordering Principle: For every set A, there a well-ordering R of A.
* Proof. It is equivalent to show there exists a bijection between some ordinal and A. For this, let c be a choice function on P(A) minus empty set, and use recursion to define a function from ORD to A until it fails. Let f(0)=c(A), and generally let f(beta)=c(A minus everything so far). If alpha is the first failure, then f defines a bijection from alpha to A. (And there must be a failure since otherwise the proper class ORD injects into the set A.)
* Cor. Every set has an ordinal cardinality.
* Proof. By WOP there exists a bijection between some ordinal xi and A. Using well-foundedness of ORD we can find the least ordinal kappa in bijection with A. This is clearly a cardinal.
* Cor. For any sets A,B, we have $\abs{A}\leq\abs{B}$ or $\abs{B}\leq\abs{A}$ (or both).
* Proof. By WOP, both A and B are in bijection with ordinals alpha and beta. By trichotomy of ORD, we either have an injection from alpha to beta or from beta to alpha (or both).
* Theorem. The union of countably many countable sets is countable. More generally, for any cardinal kappa, the union of at most kappa many sets of cardinality at most kappa has cardinality at most kappa.
* Proof. Let kappa be a cardinal and let F be such a family. Using WOP we can find a well-ordering of F of ordertype at most kappa. Using WOP on each element A of F we can find a well-ordering of A of ordertype at most kappa. Using the Axiom of Choice we can select a sequence of well-orderings, one for each set A, of A. Using this sequence we can define a functon f from kappa x kappa onto UF by: f(alpha,beta)= the betath element of the alphath set of F, or if undefined, any element. Since kappa x kappa has cardinality kappa, this shows that there is a surjection from kappa onto UF. This completes the proof because of the following lemma.
* Lemma. There is a surjection from A to B if and only if there is an injection from B to A.
* Proof. Exercise.
* The next result is one of several maximal principles used frequently in mathematics.
* Zorn's Lemma. Suppose P is a set with a partial order &lt;, and assume that every chain of P has an upper bound in P. Then P has a maximal element.
* Here a partial order is irreflexive and transitive (no trichotomy). A chain is a totally ordered subset. An upper bound is what it sounds like. A maximal element is an element with nothing greater (but possibly incomparable).
* Cor. Every vector space has a basis.
* Proof. Let V be a vector space and let P be the set of all linearly independent subsets of V, partially ordered by proper-subset. Then every chain of P has an upper bound (the union). Hence ZL implies there exists a maximal independent set. Such a set B must be a basis: if v were some vector not in span(B) then B U {v} would be independent, contradicting maximality.
* Proof of ZL. Begin with a choice function for the power set of P, as before. Use recursion to define an order-preserving function from ORD into P as far as one can go. That is let f(0)=any element, and f(beta+1) be any element greater than f(beta). At limits lambda we have a chain so there is an upper bound. If beta+1 is the first failure, then f(beta) is a maximal element.
* Many of the theorems we proved using AC are in fact equivalent to AC.
* Thoerem. WOP is equivalent to AC.
* Proof. Assuming WOP we can construct choice functions by simply choosing the "least" item.
* Theorem. ZL is equivalent to AC.
* Assuming ZL we can construct choice functions by considering the partial set of partial choice functions partially ordered by extension. A maximal partial choice function will be a choice function.
* These are the highlights.

### 12. Cardinal Arithmetic

* We have defined arithmetic for ordinals and explored some of its properties.
* Assuming AC, we can define an arithmetic of cardinals as well. We use context and hinting to distinguish between ordinal and cardinal arithmetic!
  * $\kappa+\lambda=\abs{\kappa+\lambda}$ as ordinals
  * $\kappa\times\lambda=\abs{\kappa\times\lambda}$ as ordinals
  * $\kappa^\lambda=\abs{\mathop{\mathrm{Fun}}(\lambda,\kappa)}$
* Unlike ordinal + and x, the cardinal + and x are not very exciting. This is because we have seen that ordinal arithmetic does not increase cardinality.
* Thoerem. kappa + lambda and kappa x lambda have their usual meaning for finite cardinals. If one of the two is infinite, then kappa + lambda and kappa x lambda are both equal to max(kappa,lambda).
* Proof. For the statement about finite cardinals, we can simply use induction. Next suppose $\kappa\leq\lambda$ and $\lambda$ is infinite. Then $\lambda\leq\kappa+\lambda\leq\lambda\cdot\lambda$ which is in bijection with $\lambda$. Similarly $\lambda\leq\kappa\times\lambda\leq\lambda\times\lambda$ which is in bijection with $\lambda$. By CSB, in both cases we get $\lambda$.
* However cardinal exponentiation is new. The notation comes from finite cardinals where k^l^ has the same cardinality as Fun(l,k). We simply extend this to cardinals.
* What is the value of 2^kappa^? Cantor's diagonalization theorem tells us that it is at least kappa+. In principle it could be equal to kappa+.
* Continuum hypothesis CH: 2^omega^ = aleph1.
* Generalized continuum hypothesis GCH: 2^kappa^=kappa+ for all cardinals kappa.
* CH is really a statement about analysis. CH says there is no set of real numbers that uncountable but also not in bijection with all real numbers.
* Both CH and GCH have important consequences. However it is known that neither statement can be proved using the axioms of ZFC. Conversely it is known that both statements are consistent with the axioms of ZFC.
* More generally, set theorists consider the cardinal function kappa $\mapsto$ 2^kappa^. It is called the "continuum function". It turns out the continuum functon can essentially be anything you want it to be, except for a few basic rules.
* For example it is clear that the continuum function has to be properly progressive ($\kappa\leq2^\kappa$) and increasing ($\kappa\leq\lambda\implies2^\kappa\leq2^\lambda$).
* To explain the additional rules, we need to look at cofinality.
* To motivate cofinality, consider the comparison of aleph1 versus aleph\_omega. On the one hand, clearly aleph\_omega is much larger. But on the other hand, no countable sequence can ever converge to aleph1, while there is a countable sequence that can converge to aleph\_omega. Thus there is another notion of size at work.
* Def. If kappa is a cardinal (or really any ordinal) then cofinality of kappa cf(kappa) is the least ordinal alpha such that there exists an injective unbounded function f from alpha to kappa.
* Example: cf(aleph1) = aleph1
* Example: cf(aleph\_omega) = aleph0
* Def. kappa is called regular if cf(kappa)=kappa, and singular if cf(kappa)&lt;kappa.
* Fact. cf(kappa) is always a cardinal, and fact it is a regular cardinal (or in other words cf(cf(kappa))=cf(kappa).)
* Theorem. Successor cardinals are regular, that is, cf(kappa+)=kappa+.
* Proof. This is just a restatement of the fact that the union of kappa many sets of size kappa has size kappa. Indeed, if cf(kappa+)$\leq$kappa, then there would be an unbounded function f:kappa to kappa+. Thus kappa+ would be the union over all alpha&lt;kappa of f(alpha). This implies kappa+ has cardinality at most kappa, a contradiction.
* Limit cardinals are usually singular, but they do not have to be. We can say simply that if lambda is a limit then cf(aleph\_lambda)=cf(lambda).
* Konig's Cofinality Lemma. cf(kappa^lambda^)&gt;lambda.
* Before giving the proof, we remark that this is a non-obvious limitation on what the continuum function can be. For example while we could have 2^omega^ equalling aleph\_n for any n, we cannot have 2^omega^=aleph\_omega!
* Proof. To simplify the proof, we will prove the simpler statement that cf(2^kappa^)&gt;kappa. So assume towards a contradiction that cf(2^kappa^)$\leq$kappa. Then there is an unbounded sequence beta\_alpha in 2^kappa^ of length kappa or less.
* We will repeat the Cantor diagonalization idea. There are only 2^kappa^ many functions from kappa to 2^kappa^. Thus we can enumerate them f\_xi for xi&lt;2^kappa^. We will now diagonalizes against this list to find a function d not in the list. To do so let d(alpha) disagree with f\_xi(alpha) for all xi&lt;beta\_alpha (we have more items available than items to avoid).
* Then $d$ disagrees with every $f_\xi$ somewhere, completing the contradiction and the proof.

### 13. Axiom of Foundation

* We have long asserted that sets can be constructed from the empty set and the axioms we have introduced so far.
* What we haven't done is ruled out the possibility that there are other sets in the universe. Thus in principle there may be sets which cannot be constructed using the axioms we have introduced so far, and in principle some of these sets may be undesirable.
* For examples: we never want a set $x$ such that $x\in x$, or any two sets such that $a\in b\in a$. More generally we never want cycles of sets with the property that $a_0\in a_1\in a_2\in\cdots\in a_n\in a_1$.
* We can also recognize this as a wellfoundedness requirement. Thus we also do not want decending chains $\cdots\in a_3\in a_2\in a_1\in a_0$. Such sets cannot be constructed from the empty set and the axioms so far because there is no base to start with.
* Axiom of Foundation: Every nonempty set has an $\in$-minimal element. Formally it says that $(\forall y\neq\emptyset)(\exists x\in y)(x\cap y=\emptyset)$.
* The axiom implies that the $\in$ relation on $V$ is wellfounded, at least as far as $V$ knows. (Unfortunately we cannot escape the possibility that $V$ has illfounded subcollections which are not sets.)
* The Axiom of Foundation is very important for understanding and visualizing the structure of the universe of sets.
* Thus it is a remarkable fact that we haven't used it yet! The explanation is that all the sets we have studied so far are wellfounded anyway: The empty set, hereditarily finite sets, ordinals, sets of ordinals, cardinals, and so forth.
* We now return to the construction of sets beginning with the empty set. This time we are assuming all axioms of ZFC.
* Def. The cumulative hierarchy of sets $V_\alpha$ is defined as follows. Let $V_0=\emptyset$. For any ordinal $\beta$ let $V_{\beta+1}=P(V_\beta)$. For any limit ordinal $\lambda$ let $V_\lambda=\bigcup_{\alpha<\lambda}V_\alpha$.
* Prop. $V_\alpha$ is a transitive set.
* Proof. Recall this means if $x\in y\in V_\alpha$ then $x\in V_\alpha$. We prove this by induction. Suppose $V_\alpha$ is transitive and let $x\in y\in V_{\alpha+1}$. Then $x\in y\subset V_\alpha$, so $x\in V_\alpha$, so $x\subset V_\alpha$, so $x\in V_{\alpha+1}$. For limit stages, the union of transitive sets is transitive.
* Prop. $V_\alpha\subset V_{\alpha+1}$.
* Proof. We have $V_\alpha\in P(V_\alpha)=V_{\alpha+1}$, so by transitivity $V_\alpha\subset V_{\alpha+1}$.
* The $V_\alpha$ grow and we will prove they eventually subsume all sets. Thus we can use them to define a rank (notion of complexity).
* Def. If $x$ appears in any $V_\alpha$ we define $\mathrm{rank}(x)$ to be the least ordinal $\beta$ such that $x$ appears in $V_{\beta+1}$.
* Prop. If $x\in y$ then $\mathrm{rank}(x)<\mathrm{rank}(y)$.
* Proof. Suppose $\mathrm{rank}(y)=\alpha$ and so $y$ first appears in $V_{\alpha+1}$. Then $x\in y\subset V_\alpha$ so $x$ appears in $V_\alpha$ or earlier which means $\mathrm{rank}(x)<\alpha$.
* Prop. For any ordinal $\alpha$ we have $\mathrm{rank}(\alpha)=\alpha$.
* Proof. We prove this by induction. Suppose it is true of $\alpha$. Then $\alpha$ appears in $V_{\alpha+1}$ so $\alpha+1=\alpha\cup\set{\alpha}$ appears in $V_{\alpha+2}$. Moreover if $\alpha+1$ appeared in any earlier $V_\beta$ then so would $\alpha$. At limits, standard argument.
* Prop. For any set $y$, we have $\mathrm{rank}(y)=\mathrm{sup}\set{\mathrm{rank}(x)+1\mid x\in y}$.
* Proof. Let $\alpha$ denote this value. Then for all $x\in y$ we have that the rank of $x$ is $<\alpha$ so $x$ appears in $V_\alpha$. It follows that $y$ appears in $V_{\alpha+1}$. If $y$ appeared any earlier than the supremum would be lower.
* In the following we let WF be the union of all $V_\alpha$, a proper class. Then WF is somehow the collection of sets that can be constructed from the empty set using the axioms.
* Theorem. (1) WF satisfies the Axiom of Foundation. (2) Conversely if the Axiom of Foundation is true then $V=WF$.
* Proof (1). Suppose $y$ is in WF. Then $y$ has a rank and every member of $y$ has a rank. Let $x$ be an element of $y$ of minimal rank. Then $x\cap y=\emptyset$.
* Proof (2). Let $y$ be any set. Assuming the Axiom of Foundation we must show $y$ appears in some $V_\alpha$. Let $y'$ be the transitive closure of $\set{y}$, that is the set of all finite-level elements of $y$ and $y$ itself. It is sufficient to show that $y'$ appears in some $V_\alpha$.
* Assume to the contrary that $y'$ is not in WF. Then $y'$ must have elements which are not in WF. By Foundation we can find an $\epsilon$-minimal element $x\in y'$ which is not in WF. Minimality (plus $x\subset y'$) implies all elements of $x$ must be in WF. It follows that $x\in WF$, a contradiction.
* More generally, the Axiom of Foundation is said to be relatively consistent with the other axioms of ZFC. The Axiom of Foundation does not follow from the other axioms, but it can be assumed without problem by passing from $V$ to $WF$.

### 14. Set Theory As Foundation

* We have said that set theory can be used as a foundation for essentially all of mathematics. So far we have explicitly constructed the natural numbers and alluded to the construction of the real numbers.
* Now we do so more explicitly.
* Def. $\mathbb N=\omega$.
* Def. $\mathbb Q$ is the set of triples $(i,m,n)$ in $2\times\omega\times\omega$ satisfying $n\neq0$ and $\mathrm{gcd}(m,n)=1$.
* Here we intrepret $i=0$ as positivet, $i=1 as negative, $m$ as the numerator, and $n$ as the denominator.
* Def. $\mathbb Z$ is the subset of $\mathbb Q$ where $n=1$.
* It is an exercise to define the operations $+,\times$ and the $<$ relation on $\mathbb Q$ with this definition. For instance $(0,m,n)\times(0,m',n')=$ the result of canceling common factors from $(0,mm',nn')$.
* Observe that with this definiton we don't have $\mathbb N\subset\mathbb Z$. However we can identify $\mathbb N$ with the subset of $(0,m,1)$. This identification would be cumbersome to write explicitly, but once we agree it can be done in principle, we abuse notation and pretend it is being done behind the scenes.
* So far everything constructed is contained in $V_\omega$.
* Def. $\mathbb R$ is the set of dedekind cuts of $\mathbb Q$. Here $C\subset\mathbb Q$ is a cut if
  * $C\neq\emptyset,\mathbb Q$
  * $C$ is closed downwards
  * $C$ has no last element
* Again one must define the opertaions $+,\times$ and $<$ relation. For instance $C+C'=\set{q+q'\mid q\in C,q'\in C'}$.
* Def. $\mathbb C=\mathbb R\times\mathbb R$.
* Def. $\mathbb R[x]$ is the set $\mathbb R^{<\omega}=\bigcup_n\mathbb R^n$. Each sequence $a_0,\ldots,a_n$ is interpreted as the polynomial $a_0+a_1x+\cdots+a_nx^n$.
* Def. $\mathbb R[[x]]$ is the set $\mathrm{Fun}(\omega,\mathbb R)$. Each sequence $a_0,a_1,\ldots$ is interpreted as the formal series $\sum a_nx^n$.
* There are also algebraic descriptions of these constructions: $\mathbb N$ is a semigroup, $\mathbb Z$ is the group completion of that, $\mathbb Q$ is the field of fractions of that, $\mathbb R$ is the real closure of that, $\mathbb C$ is its algebraic closure of that.
* We can also express logic in set theory! A logical expression is a sequence of logical symbols $\wedge,\vee,\forall,\exists,\ldots$ and variables and non-logical symbols. We can use even numbers $2k$ for variables $x_1,x_2,\ldots$, and use odd numbers for the other symbols. Thus a logical expression is a finite sequence of natural numbers, or element of $\omega^{<\omega}$.
* A proof is sequence of logical expressions, where each one follows from the previous by simple deductive rules. Thus a proof is a finite sequence of elements of $\omega^{<\omega}$, or an element of $()\omega^{<\omega})^{<\omega}$. It is still an element of $V_\omega$!

### 14.5 More on CH

* Recall CH states that there is no set $A\subset\mathbb R$ such that $A$ which is uncountable and not in bijection with $\mathbb R$.
* Since we have said CH cannot be disproved from the axioms of ZFC, it should be "hard" to find a counterexample set $A$.
* Theorem. If $A\subset\mathbb R$ and $A$ is open or closed, then $A$ is not a counterexample to the continuum hypothesis.
* For open sets this statement is clear, since every nonempty open set contains intervals and it is easy to see that intervals of $\mathbb R$ are in bijection with $\mathbb R$ itself.
* For closed sets we can perform the following analysis.
* Def: Recall a set is perfect if it contains all its limit points (it is closed) and every point is a limit point.
* Lem 1. If P is a nonempty perfect set then P has the same cardinality as $\mathbb R$.
* Proof 1. Construct a tree of points $a_s\in P$ for $s\in2^{<\omega}$ and neighborhoods $N_s$ by induction. Given $a_s,N_s$ find two points $a_{s\frown0},a_{s\frown1}\in N_s$ within $1/2^n$ of $a_s$ and contained in disjoint neighborhoods $N_{s\frown0},N_{s\frown1}\subset N_s$. This can be done because $a_s$ is a limit point.
* Next given $b\in 2^\omega$ the sequence $(a_s\mid s\subset b)$ is Cauchy and hence convergent to a point $a_b$. Since $P$ is perfect, $a_b\in P$. It is clear from the disjoint neighborhood condition that distinct branches $b$ give rise to distinct points $a_b$, and thus we have shown $P$ contains uncountably many elements.
* Lem 2. If $A$ is any closed set, then $A=C\cup P$ is the union of a countable set and a perfect set.
* Proof 2. We use the method of Cantor derivatives. Given $A$ we let $A'=$ the set of limit points of $A$. Then $A\setminus A'$ is countable because otherwise we would be able to find uncountably many disjoint neighborhoods. Repeating the process, we define:
  * $A^{\alpha+1}=(A^\alpha)'$
  * $A^\lambda=\bigcap_{\beta<\lambda}A^\beta$
* By the same argument as above, this process must terminate with a perfect set $P=A^\alpha$ and a countable set of thrown out points $C=A\setminus A^\alpha$.
* In fact, we can prove much more than this. Recall that a set $A$ is called Borel if it can be constructed from the open and closed sets by applying countable unions and intersections.
* The Borel sets are often said to be those which can be explicitly constructed. Such constructions can be of any countable ordinal length. Almost every set you come across is Borel.
* Theorem. If $A\subset\mathbb R$ is a Borel set then $A$ is not a counterexample to the continuum hypothesis.
* The proof is to show that the topology of $\mathbb R$ can be carefully modified in such a way as to make $A$ closed. Then apply the prevous theorem!

## Part II: Model theory

### 15. Syntax

* We have talked about how set theory is a foundation for the construction of mathematical objects. But the actual development of set theory used the same ordinary mathematical reasoning as one would use in any other area of mathematics: definitions, theorems, proofs.
* Mathematical logic is a foundation for mathematical reasoning itself. It will help us answer questions like: What is a set or another mathematical object? What makes a theorem statement meaningful? What is a proof?
* General logic is an area of philosophy that studies more general reasoning and concepts, but this is really a nother subject.
* Mathematical logic begins with mathematical language. While one can imagine making a wide variety of choices for the language, it is natural to restrict to the "first order" logic we have been using in this course and in ordinary mathematics. We have seen that this language is powerful enough to express almost all mathematical concepts, and we will see that it is simple enough that we can reason and prove thoerems about it.
* "First order" means we have quantifiers and they range over elements of a univers. "Second order" means the quantifiers may range over sets and functions, but we will not study this.
* Logic has two parts: proof theory and model theory. In proof theory we study what it means to give a correct proof of a statement from a set of given axioms. In model theory we study a given set of axioms and the possible universes where the axioms are true.
* For example, group theory consists of the axioms
  * $(\forall x,y,z)(xy)z=x(yz)$
  * $(\exists u)(\forall x)xu=x\wedge ux=x\wedge(\exists y)xy=u$
* If we let $\phi$ be the sentence $(\forall x,y,z)xy=xz\rightarrow y=z$ then $\phi$ is a theorem of group theory. Proof theory says we can find a proof of $\phi$ from the axioms. Model theory says that $\phi$ is true in every universe of the axioms (group).
* Until now we have been fairly informal with logic, mixing the official symbols with english and additional ad-hoc symbols. Now it is time to be perfectly formal.
* In math we often mix prefix ($\neg P$, $f(x)$, $-3$), infix ($x+y$, $x>y$, $P\rightarrow Q$), and postfix ($n!$, $f'$, $\kappa^+$) notations.
* For this class we officially adopt prefix notation for everything. This helps us reduce ambiguity such as $P\rightarrow Q\rightarrow R$. It also eliminates the need for parentheses.
* For example the expression $f(n!,x)>5$ will be written $>f!nx5$. Take a minute to think about that!
* In order to read such an expression, the reader will have to know the arity of each symbol, that is, how many inputs the symbol is supposed to eat.
* Def. An alphabet is a set $\Sigma$ of symbols.
* Def. An expression in a given alphabet is a finite sequence of symbols of the alphabet.
* Def. A lexicon consists of an alphabet together with an arity function $a\colon\Sigma\to\omega$.
* Def. An expression is well-formed if it is of the form $s\tau_1\cdots\tau_n$ where $\tau_i$ are well-formed expressions.
* Example. The lexicon for expressing polynomials with coefficients $1--4$ consists of alphabet $\set{1,2,3,4,x,+,\cdot}$ with arity function $a(1),\ldots,a(4),a(x)=0$ and $a(+)=a(\cdot)=2$. Then the expression $+\cdot\cdot xx+\cdot2x1$ is one way to represent the polynomial $3x^2+2x+1$. This begins with $s=+$ and is followed by $\tau_1=\cdot3\times xx$ and $\tau_2=+\cdot2x1$. Each of these may then be further broken down. (There are several other representations due to associativity and commutativity.)
* Example. The expression $+\cdot+\cdot$ is not well-formed.
* We now wish to argue that well-formed expressions can only be parsed or read in one way. That is, there are not different $\tau_i$'s that do the job. This is in contrast to $P\rightarrow Q\rightarrow R$, which needs parentheses, which makes the following harder to state and prove.
* Theorem. Let $\sigma$ be a well-formed expression. (1) No proper initial segment of $\sigma$ is well-formed. (2) If $\sigma$ starts with the symbol $s$ of arity $n$ then there exist unique well-formed expressions $\tau_1,\ldots,\tau_n$ such that $\sigma=s\tau_1\cdots\tau_n$.
* Proof. Assume the theorem is true for all expressions which are shorter than $\sigma$. By definition of well-formed, there exist $\tau_i$ such that $\sigma=s\tau_1\cdots\tau_n$. Let $\sigma'$ be a well-formed initial segment of $\sigma$ (not necessarily proper). Then again there exist $\tau'_i$ such that $\sigma'=s\tau'_1\cdots\tau'_n$. Then $\tau_1=\tau'_1$ since otherwise one would be an initial segment of the other, and contradicting the inductive hypothesis. Similarly $\tau_i=\tau'_i$ for all $i$. Thus $\sigma'=\sigma$ and the $\tau_i$ are unique, establishing both (1) and (2).
* Cor. If $\sigma$ is well-formed, then every symbol of $\sigma$ is the beginning of a unique well-formed subexpression called the scope of the occurrence of the symbol.
* Proof. Assume the theorem is true for expressions shorter than $\sigma$. The first symbol of $\sigma$ has scope $\sigma$. Any other symbol appears in some $\tau_i$ and we can apply the inductive hypothesis.
* Activity: Play around with the statement "there are infinitely many primes". Write it in traditional syntax, prefix, and parse tree.

### 16. First order syntax

* In the first part of the course, we have used first-order logic and logical notation in a somewhat informal way. That is, we introduced the symbols and said what they mean, but we left it to intuition to express and interpret formulas properly.
* In the previous class, we defined lexicon, prefix notation, and the concept of well-formed expression. We proved that well-formed expressions are not at risk for having multiple interpretations, as well as some other useful facts.
* Now it is time to apply the concept of well-formed expressions to first-order logic, thus finally making the logic a formal system.
* The lexicon of first-order logic consists of the alphabet $\Sigma=\set{\forall,\exists,\wedge,\vee,\rightarrow,\leftrightarrow,=,\neg}\cup\set{x_n\mid n\in\omega}$. The arity function is defined as $a(x_i)=0$, $a(\neg)=1$, and all others are $2$.
* In a given context, we will extend the lexicon to include additional function and relation symbols with given arity. Examples include $+,\cdot,<$.
* Def. A signature $\mathcal L$ of first-order logic consists of function symbols $f_i$ and relation symbols $R_j$ as well as arity values $a(f_i)$ and $a(R_j)$. This is the context described above.
* Def. Given a signature $\mathcal L$, the corresponding first-order lexicon consists of $\mathcal L$ together with the first-order lexicon described above.
* We next wish to define the well-formed formulas of first-order logic. Note that this is not as simple as saying that a well-formed formula is a well-formed expression in the lexicon of first-order logic. While it is true that we want our formulas to be well-formed expressions, there are actually some well-formed expressions that should not be formulas. For example consider the expressions $\forall xy$, or $\forall>xyz$.
* Def. Let $\mathcal L=\set{f_i,R_j}$ be a signature of first-order logic.
  * The *terms* of $\mathcal L$ are the well-formed expressions in the lexicon consisting of just the $f_i$ and $x_n$.
  * The *atomic formulas* of $\mathcal L$ are the expressions of the form (1) $R\tau_1\cdots\tau_n$, where $R$ is an $n$-ary relation symbol and $tau_i$ are terms, or; (2) $=\tau_1\tau_2$ where $\tau_i$ are terms.
  * The *well-formed formulas* of $\mathcal L$ are the expressions of the form (1) an atomic formula; (2) $\forall x\phi$ or $\exists x\phi$ where $x$ is a variable and $\phi$ is a wff; (3) $\neg\phi$ where $\phi$ is a wff, or; (4) $\wedge\phi\psi$, $\vee\phi\psi$, $\rightarrow\phi\psi$, $\leftrightarrow\phi\psi$, where $\phi,\psi$ are wffs.
* Like the definition of well-formed expression, this definition is recursive. But unlike the definition of well-formed expression, we have placed further limitations on precisely which well-formed expressions are legal.
* For example, $\forall x\forall y\wedge=++xy\cdot\cdot zzw\cdot3x>\cdot xy\cdot xz$. Put another way $\forall x\forall y(x+y)+z^2w=3x\wedge xy>xz$. Evaluate which are terms, atomics, and general formulas.
* We are claiming that the well-formed formulas are the expressions that can be given meaning. However there are still a few barriers before we can think of assigning a truth value to a wff.
* First, some wffs have free variables, that is, variables that are never quantified. Consider the statement of real numbers $\forall x x\cdot x\geq y$. This would be true if $y=0$, but it would be false if $y=1$. We can repair this by quantifying the $y$, for example, $\exists y\forall x x\cdot x\geq y$ is true of real numbers.
* Def. If $\phi$ is a wff, an occurrence of $x$ in $\phi$ is said to be *bound* if it lies inside the scope of a $\forall x$, and free otherwise.
* Def. If $\phi$ is a wff, $\phi$ is called a *sentence* if it has no free variables occurring.
* The sentences are the well-formed formulas for which we can conceivable assign a truth value. But we may not be able to yet. For example consider the sentence $\exists y\forall x x\leq y$. This sentence is false of real numbers but true of the unit interval $[0,1]$.
* For another example consider $\forall x x\geq 0\rightarrow \exists y y\cdot y=x$. This is true of real numbers but false of rational numbers.
* In order to decide the truth value of a sentence, we need to be told the context of the variables. The first example above says "the universe has an upper bound," but what is the universe?
* The question of what is the universe leads us to model theory. We have seen that set theory is a foundational theory, which means that essentially all mathematical structures can be built using sets. Given a language $\mathcal L$, we can use set theory to study the special sets that can serve as universes for well-formed formulas of $\mathcal L$.
* If $\mathcal L$ is a language of first-order logic, an $\mathcal L$-structure $\mathcal A$ consists of:
  * A set $A$, the universe of the structure
  * For each $n$-ary function symbol $f$ a function $f^{\mathcal A}\colon A^n\to A$
  * For each $n$-ary relation symbol $R$ a relation $R^{\mathcal A}\subset A^n$
  * For each $0$-ary function symbol $c$ a constant $c^{\mathcal A}\in A$
  * For each $0$-ary relation symbol $P$ a truth value $P^{\mathcal A}\in\set{T,F}$
* For example, all the models in the first week's set theory homework are structures for $\mathcal L=\set{\in}$.
* For example, $(\mathbb Q;<)$ is a structure in the language of linear orders.
* For example, $(\mathbb R;0,1,+,\cdot,<)$ is a structure in the language of ordered fields.
* Thus we will not define whether a given sentence $\sigma$ is true or false in general, but whether it is true or false in a given structure $\mathcal A$. We will say that $\mathcal A$ satisfies $\sigma$, and write $\mathcal A\models\sigma$, when $\sigma$ is true in $\mathcal A$.
* The formal definiton of satisfaction is somewhat involved, but will work the way you want it to! For example, returning to the sentence $\forall x x\geq 0\rightarrow \exists y y\cdot y=x$, we will have that $(\mathbb R;+,\cdot,0,1)\models\sigma$ and $(\mathbb Q;+,\cdot,0,1)\not\models\sigma$.

### 17. Satisfaction

In this section we give a formal definition of the satisfaction relation $\mathcal A\models\sigma$. Unsurprisindly, the definition will once again be by induction on the construction of the sentence $\sigma$. Of course all the subformulas of $\phi$ are terms and formulas, not sentences, so we will need to handle the case when formulas $\phi$ have free variables.

However, if $\phi(x)$ has free variable $x$, then the statement $\mathcal A\models\phi(x)$ doesn't make sense because we don't know what $x$ is. We instead define the more complicated statement $\mathcal A\models\phi(x)[x\to a]$.

**Example**. Let $\mathcal A$ be the model $(\mathbb N,+,\cdot,0,1)$ and let $\phi(x)$ be the formula $x^2<10$. Then $\mathcal A\models\phi(x)[x\to3]$ and $\mathcal A\not\models\phi(x)[x\to4]$.

We begin our recursive definiton of satisfaction by showing how to evaluate the terms.

**Definition**. Let $\mathcal L$ be a language of first-order logic and $\mathcal A$ be an $\mathcal L$-structure. Let $s$ be a set of substitutions $x\to a$ of variables being used by elements of $A$ (in other words, a function from the set of variables being used to $A$). Then:

* If $x$ is a variable of $\tau$, define $\mathop{\mathrm{val}}_{\mathcal A}(x)[s]$ to be $s(x)$
* If $c$ is a constant symbol of $\tau$, define $\mathop{\mathrm{val}}_{\mathcal A}(c)[s]$ to be $c^{\mathcal A}$
* If $f$ is an $n$-ary function symbol and $\tau_1,\ldots,\tau_n$ are terms, define $\mathop{\mathrm{val}}_{\mathcal A}(f\tau_1\cdots\tau_n)[s]=f^{\mathcal A}(\mathop{\mathrm{val}}_{\mathcal A}(\tau_1)[s],\ldots,\mathop{\mathrm{val}}_{\mathcal A}(\tau_n)[s])$.

**Example**. Let $\mathcal A$ be the model $(\mathbb N,+,\cdot,0,1)$ and let $\tau$ be the term $x\cdot y$. Let $s$ be the substitution $x\to 3,y\to 4$. Then $\mathop{\mathrm{val}}_{\mathcal A}(\tau)[s]=\mathop{\mathrm{val}}_{\mathcal A}(x)[s]\cdot \mathop{\mathrm{val}}_{\mathcal A}(y)[s]=3\cdot 4=12$.

We next define satisfaction for atomic formulas.

**Definition**. Let $\mathcal L$ be a language of first-order logic and $\mathcal A$ be an $\mathcal L$-structure. Let $s$ be a set of substitutions. Then:

* If $\phi$ is the formula $R\tau_1\cdots\tau_n$ then $\mathcal A\models\phi[s]$ is true if and only if $(\mathop{\mathrm{val}}_{\mathcal A}(\tau_1)[s],\ldots,\mathop{\mathrm{val}}_{\mathcal A}(\tau_n)[s])\in R^{\mathcal A}$.
* If $\phi$ is the formula $=\tau_1\tau_2$ then $\mathcal A\models\phi[s]$ is true if and only if $\mathop{\mathrm{val}}_{\mathcal A}(\tau_1)[s]=\mathop{\mathrm{val}}_{\mathcal A}(\tau_2)[s]$
* If $\phi$ is the formula $P$, a propositional relation, then $\mathcal A\models\phi$ is true if and only if $P^{\mathcal A}=T$.

Note that in this definition the equality relation is treated specially. This guarantees that the equality relation always represents true equality, and not some funny model-specific notion of equality.

We finally define satisfaction for general formulas.

**Definition**. Let $\mathcal L$ be a language of first-order logic and $\mathcal A$ be an $\mathcal L$-structure. Let $s$ be a set of substitutions. Then:

* If $\phi$ is $\alpha\wedge\beta$ then $\mathcal A\models\phi[s]$ is true if and only if $\mathcal A\models\alpha[s]$ and $\mathcal A\models\beta[s]$
* Similarly use the truth tables for $\wedge,\to,\leftrightarrow$
* If $\phi$ is $\neg\alpha$ then $\mathcal A\models\phi[s]$ is true if and only if $\mathcal A\not\models\alpha[s]$.
* If $\phi$ is $\exists x\alpha$ then $\mathcal A\models\phi[s]$ is true if and only if there is some $a\in A$ such that $\mathcal A\models\alpha[t]$, where $t$ is the modification of $s$ where we let $t(x)=a$.
* If $\phi$ is $\forall x\alpha$ then $\mathcal A\models\phi[s]$ is true if and only if for all $a\in A$ we have $\mathcal A\models\alpha[t]$, where $t$ is the modification of $s$ where we let $t(x)=a$.

Note that if $\sigma$ is a sentence, then no substitution function $s$ is needed (because anything it specifies will eventually be overwritten by the quantifiers). Thus we can write $\mathcal A\models\sigma$ without the $s$.

**Example**. Let $\mathcal A$ be the model $(\mathbb Q,<)$ and let $\sigma$ be the sentence $\forall x\forall y\exists z x>y\rightarrow x>z>y$. Then $\mathcal A\models\sigma$ if and only if for all $a\in\mathbb Q$ and for all $b\in\mathbb Q$ we have that there exists $c\in\mathbb Q$ such that $\mathcal A\models x>y\rightarrow x>z>y[x\to a,y\to b,z\to c]$. The latter is true if and only if for all $a,b$ there exists $c$ such that $a>b\implies a>c>b$. This is true since we can always let $c=(a+b)/2$.

We often apply the satisfaction relation to a set of sentences.

**Definition**. If $\mathcal L$ is a language of first-order logic, then an $\mathcal L$-theory is a set of $\mathcal L$-sentences.

**Definition**. Let $T$ be an $\mathcal L$-theory and let $\mathcal A$ be an $\mathcal L$-structure. We say $\mathcal A\models T$ if for every $\sigma\in T$ we have $\mathcal A\models\sigma$. In this case we also say that $\mathcal A$ is a *model* of $T$.

This fulfills the notion that model theory provides the universes where a given collection of axioms is true. For example if $T$ is group theory, the models of $T$ are groups. If $T$ is set theory, the models of $T$ are universes of set theory.

With the concept of satisfaction in hand, we may further define many semantic notions.

* Semantic validity: A sentence $\sigma$ is *semantically valid* if for every structure $\mathcal A$ we have $\mathcal A\models\sigma$.
* Semantic implication: A sentence $\sigma$ *semantically implies* a sentence $\tau$ if for every model $\mathcal A$ we have $\mathcal A\models \sigma$ implies $\mathcal A\models\tau$.
* Semantic consistency: A theory $T$ is *semantically consistent* if it admits a model $\mathcal A\models T$.

Each of these has syntactic versions involving proofs.

* Syntactic validity: A sentence $\sigma$ is *semantically valid* if there is a proof of $\sigma$.
* Syntactic implication: A sentence $\sigma$ *syntactically implies* a sentence $\tau$ if there is a proof using $\sigma$ of $\tau$.
* Syntactic consistency: A theory $T$ is *semantically consistent* if it cannot be used to derive a falsehood.

We will see that in each case the semantic and syntactic notions are equivalent. Of course this means we have to be very careful to define proof itself properly, something we will do in the next section.

Returning to the semantically valid sentences, we proceed with several examples.

**Example**. Every propositional tautology is a semantically valid sentence in the appropriate language. Recall that a propositional tautology is a sentence involving just $0$-ary relations which can be verified by truth tables. For examples, the following are propositional tautologies: $P\wedge Q\to P$; $(P\to Q)\leftrightarrow (\neg P\vee Q)$; $(P\wedge(\mathcal P\to Q))\to Q$.

Similarly, if one begins with a propositional tautology and replaces each propositional variable with a first-order sentence, one obtains a semantically valid sentence.

There are many more examples of semantically valid statements that are genuinely first-order, and don't derive from propositional tautologies.

**Example**. The following are semantically valid: $\forall x x=x$; $\forall x R(x)\to\neg\exists x\neg R(x)$; $\forall x\phi(x)\to\phi(\tau)$; $\phi(\tau)\to\exists x\phi(x)$.

### 18. Formal proofs

An informal proof is an explanation. A formal proof is a sequence of sentences ending with a desired statement. In order to be a correct proof, it must be possible to justify each of the statements in the sequence in one of several ways.

The most obvious way to justify a statement is when it is something we are assuming (an axiom). The next most obvious way is if it is logically apparent, such as a tautology. A somewhat more meaningful step of justification is *modus ponens*, which says that if $\alpha$ is true and $\alpha\to\beta$ is true then $\beta$ is true. 

**Definition**. Let $T$ be a theory and $\sigma$ be a sentence of some fixed language $\mathcal L$. We say that $T$ *proves* $\sigma$, written $T\vdash\sigma$, if there exists a sequence of sentences $\sigma_1,\ldots,\sigma_n$ such that $\sigma_n$ is $\sigma$, and for all $i$ we have one of the following:

* $\sigma_i$ is an element of $T$;
* $\sigma_i$ is an instance of a logical axiom (described below);
* there exist $j,k\lt i$ such that $\sigma_k$ is $\sigma_j\to\phi_i$.

We must say what it means for a sentence to be a logical axiom. Given our discussion of valid sentences, it may seem natural to define the logical axioms to be the valid sentences. However this has some disadvantages, since it can be difficult to tell whether a given sentence is valid. Instead we define the logical axioms to be a sufficiently powerful but still easy-to-describe subset of the valid sentences.

**Definition**. A sentence $\sigma$ is a *logical axiom* if it is of one of the following types:

* Propositional tautologies
* Universal instantiation: $\forall x\phi(x)\to\phi(\tau)$, for $\tau$ a term without $x$
* Existential generalization: $\phi(\tau)\to\exists x\phi(x)$, for $\tau$ a term without $x$
* Equality: $\forall x\forall y\forall z (x=x)\wedge(x=y\leftrightarrow y=x)\wedge(x=y\wedge y=z\to x=z)$, and $\forall x\forall y x=y\to f(x)=f(y)$, and $\forall x\forall y x=y\to R(x)\leftrightarrow R(y)$, and ditto for all arities.
* Quantifier duality: $\neg\forall x\phi\leftrightarrow \exists x\neg\phi$
* Quantifier distribution: $\forall x(\phi\to\psi)\to(\forall x\phi\to\forall x\psi)$
* Extra quantifier: $\phi\to\forall x\phi$ (where $x$ is not a free variable of $\phi$)

It is easy to see that each of these logical axioms is a valid sentence. There are vastly more valid sentences not in the list. But we will eventually see that the list has enough power to prove the rest of the valid sentences. This was the main criteria used in choosing the axioms!

**Example**. We will prove that $T=\emptyset$ proves the sentence $\forall x\exists y x=y$.

1. $\forall x x=x$ (Equality)
2. $\forall x x=x\to \exists y x=y$ (EG)
3. $[\forall x x=x\to \exists y x=y]\to [\forall x x=x\to \forall x\exists y x=y]$ (Quantifier distribution)
4. $\forall x x=x\to \forall x\exists y x=y$ (Modus ponens 2,3)
5. $\forall x\exists y x=y$ (Modus ponens 1,4)

Recall our distinction between semantic truth (satisfaction) and syntactic truth (proofs). The next theorem states that anything we can prove is true. That is, it states that our concept of proof is *sound*.

**Soundness Theorem**. If $T\vdash\sigma$ then $T\models\sigma$.

*Proof*. Assume that $\sigma_1,\ldots,\sigma_n$ is a proof from $T$ of $\sigma$. Assume that $\mathcal A\models T$. We will show that for all $i$, we have $\mathcal A\models\sigma_i$. For the base case $i=1$, we know that $\phi_1$ is either in $T$ or a logical axiom. In either case $\mathcal A\models\sigma_1$. Next assume inductively that $\mathcal A\models\sigma_j$ for all $j\lt i$. If $\sigma_i$ is in $T$ or a logical axiom we are done. Otherwise there is $j$ such that $\mathcal A\models\sigma_j$ and $\mathcal A\models \sigma_j\to\sigma_i$. By definition of $\models$ for $\to$, we must have $\mathcal A\models\sigma_i$. This completes the proof because now we know $\mathcal A\models\sigma_n$ which is $\sigma$.

The completeness theorem is the converse of the soundness theorem. Thus it says that everything that is true can be proved. We will prove the completeness theorem in the next section.

The definition of proof that we have given is of theoretical value, but not of great practical value. It can be very difficult to take substantial mathematical results and formalize them in this system. In the rest of the section we mention a few tactics for making the work of finding proofs at least somewhat more accessible.

One common tactic in mathematics is to prove a lemma and use it as a step in a theorem. The next result makes this easy to do.

**Deduction theorem**. $T\vdash\alpha\to\beta$ if and only if $T\cup\set{\alpha}\vdash\beta$.

*Proof*. The forward implication is just modus ponens. For the reverse implication, assume that $T\cup\set{\alpha}\vdash\beta$ and let $\sigma_1,\ldots\sigma_n$ be a proof. We will show by induction that for all $i$ we have $T\vdash\alpha\to\sigma_i$.

As before, the base case is trivial. Next assume that $T\vdash\sigma_j$ for all $j\lt i$. If $\sigma_i$ lies in $T$, is $\phi$, or is a logical axiom, then it is clear that $T\vdash\phi\to\sigma_i$. Otherwise $\sigma_i$ followed by modus ponens. By inductive hypothesis, we then have $T\vdash\sigma\to\sigma_j$ and $T\vdash\sigma\to(\sigma_j\to\sigma_i)$. It follows using easy tautologies and modus ponens that $T\vdash\sigma\to\sigma_i$. This completes the induction.

**Proof by contradiction**. If $T\cup\set{\neg\sigma}\vdash\alpha\wedge\neg\alpha$, then $T\vdash\sigma$.

*Proof*. If $T\cup\set{\neg\sigma}\vdash\alpha\wedge\neg\alpha$, then using tautologies we have $T\cup\set{\neg\sigma}\vdash\sigma$. By the deduction theorem, $T\vdash \neg\sigma\to\sigma$. By a tautology, $T\vdash\sigma\vee\sigma$ and therefore $T\vdash\sigma$.

**Universal generalization and existential instantiation**. Let $c$ be a constant symbol not in $\mathcal L$. If $T\vdash\phi(c)$ then $T\vdash\forall x\phi(x)$. If $T\cup\set{\phi(c)}\vdash\alpha$ then $T\cup\set{\exists x\phi(x)}\vdash\alpha$.

*Proof*. Bleh.

The last two rules formalize common proof notions. The UG rule is for proofs that end "...but c was arbitrary". The EI rule is for proofs that begin "Fix a constant c such that...". In the future we will also use the abbreviations UI and EG as deductive rules corresponding to the logical axioms of the corresponding name.

**Example**. We will prove that $T=\emptyset$ proves the sentence $\forall x P(x)\wedge Q(x)\to \forall y P(y)$.

1. We will prove the lemma $\forall x P(x)\wedge Q(x)$ proves $\forall y P(y)$. 
    a. $\forall x P(x)\wedge Q(x)$ (Given)
    c. $P(c)\wedge Q(c)$ (UI)
    d. $P(c)\wedge Q(c)\to P(c)$ (Tautology)
    e. $P(c)$ (MP c,d)
    g. $\forall y P(y)$ (UG)
2. $\forall x P(x)\wedge Q(x)\to \forall y P(y)$ (Deduction, 1)

### 19. Completeness I

Recall that we have proved the Soundness Theorem, which states that any syntactic consequence of $T$ is also a semantic consequence of $T$, that is, if $T\vdash\sigma$ then $T\models\sigma$. In this section we will prove the converse.

**Completeness Theorem, version I** If $T\models\sigma$ then $T\vdash\sigma$.

We will actually prove the completeness theorem in another form. Recall that a theory $T$ is semantically consistent if there is a model of $T$. Recall also that a theory $T$ is syntactically consistent if $T\not\vdash\sigma\wedge\neg\sigma$.

**Completeness Theorem, version II** If $T$ is syntactically consistent, then $T$ has a model.

To see the two statements are equivalent, first suppose that version I is true and let $T$ be a syntactically consistent theory. If $T$ has no models, then $T\models\sigma\wedge\neg\sigma$ is vacuously true, hence $T\vdash\sigma\wedge\neg\sigma$, a contradiction.

Conversely suppose that version II is true and let $T\models\sigma$. Then there is no model of $T\cup\set{\neg\sigma}$, so $T\cup\set{\neg\sigma}$ is syntactically inconsistent. From our proposition on proofs by contradiction, we conclude that $T\vdash\sigma$.

Thus proving the completeness theorem is really about building models. If $T$ is reasonable in the sense that it doesn't lead us to a contradiction, then it should be possible to build a universe in which $T$ is true. This sounds like a somewhat tall order!

The BIG IDEA is to build the model using the terms of the language. In order to illustrate

**Example**. Let $\mathcal L=\set{+,\times,0,1,\lt}$ and let $T$ be the standard axioms of arithmetic of the natural numbers (associativity, commutativity, and so on). Our model will include the terms $0$, $1$, $1+1$, $1+1+1$, and so on, pretty good substitutes for the actual natural numbers! Of course there are many other terms such as $1+0+0+1$, but our theory knows that this one is really equivalent to $1+1$. In other words, there is an equivalence relation on terms given by $\tau_1\sim\tau_2$ if and only if $T\vdash\tau_1=\tau_2$.

This example worked smoothly, but we should wonder what we would do if the constant symbol $1$ was not present in the language. We can make a theory in this language that is equivalent to $T$ by defining $1$ as the least natural number greater than $0$. But this language doesn't have any interesting terms. In general when building a model of $T$ we will use the terms of an expanded language where constant symbols have been added for each possible definition.

This idea is called a Henkin construction. In order to begin, we first make a structure from terms.

**Definition**. Let $T$ be a theory. The structure $\mathcal H_0=\mathcal H_0(T)$ is defined as follows.

* The domain of $\mathcal H_0$ consists of the terms of $\mathcal L$ with no  variables.
* If $f$ is a function symbol, then $f^{\mathcal H_0}\tau_1\cdots\tau_n$ is defined to be the term $f\tau_1\cdots\tau_n$.
* If $R$ is a relation symbol, then $R^{\mathcal H_0}\tau_1\cdots\tau_n$ is defined to be true if and only if $T\vdash R\tau_1\cdots\tau_n$.

This is a good start, but we have seen this model may have several problems. First, it doesn't identify terms that the theory knows are equivalent. Second, if there aren't any constant symbols in the language, this model will be empty. And third, it still might not be a model of $T$.

**Definition**. Let $T$ be a theory. The structure $\mathcal H=\mathcal H(T)$ is defined as follows.

* The domain of $\mathcal H$ consists of the equivalence classes $[\tau]$ of elements of $\mathcal H_0$ with respect to the equivalence relation defined by $\tau_1\sim\tau_2$ if and only if $T\vdash\tau_1=\tau_2$.
* If $f$ is a function symbol, then $f^{\mathcal H}[\tau_1]\cdots[\tau_n]$ is defined to be the equivalence class $[f\tau_1\cdots\tau_n]$.
* If $R$ is a relation symbol, then $R^{\mathcal H}[\tau_1]\cdots[\tau_n]$ is defined to be true if and only if $T\vdash R\tau_1\cdots\tau_n$.

One must check that this definition is well-defined, that is, the function values and relation values are independent of the equivalence class representatives. This can be done using the logical proof axioms pertaining to equality.

**Lemma**. If $\sigma$ is an atomic sentence, then $\mathcal H\models\sigma$ if and only if $T\vdash\sigma$.

*Proof sketch*. The key is to show by induction that $\mathrm{val}_{\mathcal H}(\tau)=[\tau]$ for all terms $\tau$. Then If $\sigma$ is the sentence $R\tau_1\cdots\tau_n$, our definition of $R^{\mathcal H}$ guarantees the desired result. $\square$

We are clearly on our way to obtaining a model of $T$. But quantifiers are still a big problem.

**Example**. Let $\mathcal L=\set{\lt,a,b}$, where $a,b$ are constant symbols, and let $T$ be the theory of $\omega$. Then $\mathcal H$ has domain $\set{a,b}$ but the model does not decide whether $a\lt b$ or $b\lt a$. Thus the theory $T$ includes trichotomy but the model $\mathcal H$ does not satisfy trichotomy.

To fix this problem, we will work only with complete theories $T$.

**Definition**. A theory $T$ is *complete* if for every sentence $\sigma$ we have either $\sigma\in T$ or $\neg\sigma\in T$.

**Lemma**. If $T$ is a syntactically consistent theory, there exists a complete syntactically consistent theory $\bar T$ such that $T\subset\bar T$.

*Proof*. Let $P$ be the partial order consisting of all syntactically consistent theories $U$ extending $T$. Then $P$ is partially ordered by set inclusion. Then chains of $P$ are bounded because the union of a chain of syntactically consistent theories is still syntactically consistent.

By Zorn's lemma, there exists a maximal consistent theory $\bar T$. such that $T\subset\bar T$. We claim that $\bar T$ is complete. Indeed, if $\sigma\notin\bar T$, then $\bar T\cup\set{\sigma}$ is inconsistent, so by our theorem about proofs by contradiction, $\bar T\vdash\neg\sigma$. Since $\bar T$ is maximal, it follows that $\neg\sigma\in T$. $\square$

We remark that if $T$ is a complete theory $\alpha\vee\beta\in T$, then we must have either $\alpha\in T$ or $\beta\in T$. Thus if we revisit the above example and complete $T$ before building $\mathcal H$, we will either have $a\lt b$ or $b\leq a$, whichever Zorn's lemma picks for us.

But there is still one big issue left to address. Continuing the above example, let $T$ be the theory of $\omega$ together with the sentences $a$ has three predecessors and $b$ has four. Then our model $\mathcal H$ will satisfy $a\lt b$, but it still will not satisfy the sentence $\exists x x\lt a$.

Generally speaking, a given language may not have enough terms to make $\mathcal H$ a real model of $T$. In order to fix this, we need to add new terms, constant symbols, that witness existential formulas.

**Definition**. A theory $T$ is said to have *witnessing terms* if whenever $\phi(x)$ is a formula with one free variable $x$ there exists a term $\tau$ such that $T\vdash\exists x\phi(x)\to\phi(\tau)$.

For example consider $\mathbb R$ as a field. If $\phi(x)$ is $\forall y xy=y+y$ then a witnessing term would be $1+1$. If $\phi(x)$ is $xx=1+1$ then there is no witnessing term and we will need to add one. The following is the crux of the Henkin construction.

**Lemma**. If $T$ is a syntactically consistent theory, then there exists a syntactially consistent theory $T'$ in an expanded language such that $T\subset T'$ and $T'$ has witnessing terms.

Assuming this lemma is true, let us outline the proof of the Completeness Theorem.

Given a syntactically constistent theory, we first extend it to a theory with witnessing terms, and then to a complete theory $T^\ast$ in the expanded language. We let $\mathcal H$ be the Henkin model corresponding to $T^\ast$.

We must prove that $\mathcal H$ is a model of $T^\ast$ and hence of $T$. This is done by induction on the complexity of the sentence (not the length). We have already addressed atomic sentences. The difficult part is the $\exists$ quantifier step, but noe can use the witnessing property in this part!

### 20. Completeness and its consequences

We still owe the proof of the lemma.

**Lemma**. If $T$ is a syntactically consistent theory, then there exists a syntactially consistent theory $T'$ in an expanded language such that $T\subset T'$ and $T'$ has witnessing terms.

*Proof*. We first show how to add a witnessing term for a single formula $\exists x\phi(x)$. To do this, we let $\mathcal L'=\mathcal L\cup\set{c}$, and let $T'=T\cup\set{\exists x\phi(x)\to\phi(c)}$.

We claim that $T'$ is syntactically consitent. If it isn't, then there is a proof from $T'$ of a contradictory sentence $\alpha\wedge\neg\alpha$. By the proof-by-contradiction theorem, there is a proof from $T$ of $\neg(\exists x\phi(x)\to\phi(c))$. Using a tautology, there is a proof from $T$ of $\exists x\phi(x)$ and a proof from $T$ of $\neg\phi(c)$. By UG, there is a proof from $T$ of $\forall x\neg\phi(x)$. This is clearly a contradiction, establishing the claim.

Now to add witnessing terms for all formulas, we inductively define $\mathcal L^{(n)},T^{(n)}$ as follows. Firstlet $\mathcal L^{(0)}=\mathcal L$ and $T^{(0)}=T$. If $\mathcal L^{(n)},T^{(n)}$ have been defined, we let $\mathcal L^{(n+1)}$ include new constant symbols for each existential formula of $\mathcal L^{(n)}$, and let $T^{(n+1)}$ include corresponding sentences for each. Then by an argument similar to the above, each $\mathcal T^{(n)}$ is syntactically consistent, and it follows that $T'=\bigcup\mathcal T^{(n)}$ is syntactically consistent. Moreover with $T'$ we have "caught our tail" meaning that $T'$ has witnessing terms. $\square$

**Completeness Theorem, version II**. If $T$ is syntactically consistent, then $T$ has a model.

*Proof*. We apply the lemmas we have proved in sequence. Given $T$, we first extend it to a theory with witnessing terms and then further extend it to a complete theory $T^\ast$ in the expanded language. We then let $\mathcal H$ be the Henkin/Herbrand model of $T^\ast$. 

We claim that for all sentences $\sigma$ we have $\sigma\in T^\ast$ if and only if $\mathcal H\models\sigma$, so that $\mathcal H$ really is a model of $T^\ast$. For this we proceed by induction on the *complexity* of $\sigma$. For this we can assume that the only connectives in $\sigma$ are $\wedge,\neg,\exists$ and proceed by indnuction on the number of occurrences of these symbols.

We have already proved the result for atomic sentences $\sigma$ directly from the definition of $\mathcal H$.

If $\sigma$ is of the form $\neg\alpha$, then the result follows from the inductive hypothesis for $\alpha$ and the completeness of $T^\ast$. Indeed, we have $\sigma\in T^\ast$ iff $\alpha\notin T^\ast$ iff $\mathcal H\not\models\alpha$ iff $\mathcal H\models\sigma$. Similarly if $\sigma$ is of the form $\alpha\wedge\beta$ then the result is immediate from the inductive hypothesis for $\alpha$ and $\beta$ and the completness of $T^\ast$.

Finally if $\sigma$ is of the form $\exists x\phi(x)$ then since $T^\ast$ has witnessing terms there is a term $\tau$ in the expanded language such that the sentence $\exists x\phi(x)\to\phi(\tau)$ is in $T^\ast$. Now:

\begin{align*}
  \sigma\in T^\ast &\implies \phi(\tau)\in T^\ast & \text{completeness of $T^\ast$}\\
  &\implies \mathcal H\models\phi(\tau) & \text{inductive hypothesis}\\
  &\implies \mathcal H\models\sigma
\end{align*}

And conversely:

\begin{align*}
  \mathcal H\models\sigma &\implies \mathcal H\models\phi(\tau) &\text{for some term $\tau$ :)}\\
  &\implies \phi(\tau)\in T^\ast &\text{inductive hypothesis}\\
  &\implies T^\ast\vdash\sigma &\text{EG}\\
  &\implies \sigma\in T^\ast &\text{completeness of $T^\ast$}
\end{align*}

This completes the proof. $\square$.

We remark that the :) follows from the definition of the Henkin/Herbrand model. Since we don't have control over the length of the term $\tau$, we had to do our induction over the complexity of $\sigma$ instead of the length of $\sigma$.

The completeness theorem has many consequences, one of which is to greatly simplify our terminology.

* Semantic validity is equivalent to syntactic validity.
* Semantic implication is equivalent to syntactic implication.
* Semantic consistency is equivalent to syntactic consistency.

As a result we rarely need to discern between the semantic and syntactic notions. Another simple but powerful consequence is the following.

**Compactness Theorem**. If every finite subset of $T$ has a model, then $T$ has a model.

*Proof*. It suffices to show that if every finite subset of $T$ is syntactically consistent, then $T$ is syntactically consistent. Taking the contrapositive, we must show that if $T$ is syntactically inconsistent then some finite subset of $T$ is syntactically inconsistent. This is clear from the fact that proofs are finite: if $T$ proves a contradictory sentence $\alpha\wedge\neg\alpha$, then the proof used just finitely many sentences of $T$, so there exists a finite subset $T_0\subset T$ that proves a $\alpha\wedge\neg\alpha$ too. $\square$

The compactness theorem is a powerful tool for generalizing proofs about finite objects into proofs about infinite objects.

**Corollary**. Suppose $T$ has arbitrarily large finite models. Then $T$ has infinite models.

*Proof*. Let $\sigma_n$ be the sentence which says that there exist $n$ distinct elements of the universe. That is, $\sigma_n$ says that $\exists x_1\cdots\exists x_n\bigwedge x_i\neq x_j$. Let $T'$ be the theory $T\cup\set{\sigma_n:n\in\mathbb N}$. Then every finite subset of $T'$ is consistent by our hypothesis. As a consequence $T'$ is consistent. Any model of $T'$ is a model of $T$ and is infinite. $\square$

This simple idea can also be used to derive the following consequences of compactness. The first is key in the theory of *nonstandard arithmetic*, where one studies models of number theory with infinite elements, and the second fact is key in *nonstandard analysis* where one studies models of analysis with infinitesimal elements.

**Corollary**. Let $T$ be the theory of the natural numbers, that is, the set of sentences true in the structure $(\mathbb N;+,\times,0,1,\lt)$. There is a model of $T$ with an element $N$ such that $n\lt N$ for all $n\in\mathbb N$.

**Corollary**. Let $T$ be the theory of the real numbers, that is, the set of sentences true in the structure $(\mathbb R;+,\times,0,1,\lt)$. There is a model of $T$ with an element $\epsilon$ such that for all $0\lt r\in\mathbb R$ we have $0\lt\epsilon\lt r$.

We will leave the proofs as exercises.

### 21. More applications of compactness

For the next result, recall that the theory of simple graphs is the theory of a single binary relation $\sim$ which is irreflexive and transitive. Further recall that a graph $G$ is *bipartite* if it can be partitioned into subsets $P,Q$ such that no two vertices of $P$ are adjacent and no two vertices of $Q$ are adjacent. For example, a hexagon is bipartite but a heptagon is not.

**Corollary**. Let $G$ be a graph such that every finite subset of $G$ is bipartite. Then $G$ is bipartite.

*Proof*. Let the language $\mathcal L$ consist of $\sim$ together with constant symbols $c_x$ for every $x\in G$ together with unary relation symbols $P$ and $Q$. Let the theory $T$ consist of the following axioms:

* $c_x\neq c_{x'}$ whenever $x\neq x'$
* $c_x\sim c_{x'}$ whenever $x\sim x'$
* $c_x\not\sim c_{x'}$ whenever $x\not\sim x'$
* $P,Q$ is a partition
* $P,Q$ have no edges within them

Then every finite subset of $T$ is consistent. Indeed, if $T_0$ is a finite subset of $T$, then $T_0$ mentions a certain subset $G_0\subset G$. The induced subgraph corresponding to $G_0$ is bipartite and thus gives rise to a model of $T_0$.

By the compactness theorem, $T$ has a model, $G'$. Observe that $G$ is a subgraph of $G'$ via the function which sends any $x\in G$ to the interpretation of $c_x$ in $G'$. Since $G'$ is bipartite, it follows that $G$ is bipartite. $\square$.

For each theory $T$ there is a corresponding class of models of $T$. We will say that a class $\mathcal C$ of structures is *axiomatizable* if there exists a theory $T$ such that the models of $T$ are precisely the elements of $\mathcal C$. It is natural to ask whether every (reasonable) class of srtuctures is axiomatizable. Our next result says that the answer is no.

Recall that a graph is *connected* if for any two vertices $x,y$, there exists a path from $x$ to $y$. That is, for any $x,y$ there is a sequence of vertics $x_1,\ldots,x_n$ such that $x\sim x_1\sim x_2\sim\cdots\sim x_n=y$.

**Corollary**. The class of connected graphs is not axiomatizable.

*Proof*. Suppose there exists a theory $T$ such that the models of $T$ are exactly the connected graphs. Expand the language with two new constant symbols $a,b$. Let $\sigma_n$ be the sentence which says there is no path from $a$ to $b$ of length $n$. Let $T'$ be the theory $T\cup\set{\sigma_n:n\in\omega}$. Then any finite subset $T_0\subset T'$ is consistent. Indeed, if $N$ is the largest number such that $\sigma_N$ occurs in $T_0$, then a graph consisting of a single path of length $N+1$ from $a$ to $b$ gives a model of $T_0$. It follows from the compactness theorem that $T'$ is consistent and hence has a model. But any model of $T'$ is disconnected, because there cannot be a path from $a$ to $b$. Hence we have shown that there is a disconnected model of $T$, a contradiction. $\square$

**Corollary**. The class of well-orders is not axiomatizable.

*Proof*. Suppose there exists a theory $T$ such that the models of $T$ are exactly the well-orders. Expand the language with new constant symbols $c_n$ for $n\in\omega$. Let $\sigma_n$ be the sentence which says that $c_n\lt\ldots\lt c_0$. Let $T'$ be the theory $T\cup\set{\sigma_n:n\in\omega}$. Then any finite subset $T_0\subset T'$ is consistent. Indeed, if $N$ is the largest number such that $\sigma_N$ occurs in $T_0$, then the structure $(\omega,\lt)$ together with a decreasing sequence of interpretations of $c_0,\ldots,c_n$ is a model of $T_0$. It follows from the compactness theorem that $T'$ is consistent and hence has a model. But any model of $T'$ is ill-founded, because the interpretations of the $c_n$ form an infinite decreasing sequence. Hence we have shown that there is an ill-founded model of $T$, a contradiction. $\square$

Recall we have shown that theories with arbitrarily large finite models have infinite models. It is natural to ask what cardinalities will occur. Our final corollary addresses this question with the most generous possible answer.

**Lowenheim--Skolem Theorem**. Suppose $T$ is a theory in a language $\mathcal L$ and $T$ has an infinite model. Then for any cardinal $\kappa\geq\abs{\mathcal L}\cdot\aleph_0$, $T$ has a model of cardinality $\kappa$.

*Proof*. We prove the theorem in two parts: a downwards direction and an upwards direction. To begin with downwards direction, we will prove that if $T$ has an infinite model then $T$ has a model of size $\abs{\mathcal L}\cdot\aleph_0$. Reading the proof of the completeness theorem, we see that the Henkin/Herbrand model $\mathcal H$ happens to have precisely this size. Indeed, it is constructed from terms, which are finite strings of elements of the given countable language.

For the upwards direction, assume $T$ has a model of size $\abs{\mathcal L}\cdot\aleph_0$ and let $\kappa\geq\abs{\mathcal L}\cdot\aleph_0$ be given. Expand the language to include $\kappa$ many constant symbols $c_\alpha$ for $\alpha\lt\kappa$. Let $T'=T\cup\set{c_\alpha\neq c_\beta\mid\alpha\neq\beta}$. Then any finite subset $T_0\subset T'$ is consistent. Indeed, $T_0$ mentions just finitely many of the constant symbols $c_\alpha$, and we can intrepret them as arbitrary elements of the given model of $T$. It follows from the compactness theorem that $T'$ is consistent, and so has a model. The resulting model must have cardinality at least $\kappa$. If it has cardinality greater than $\kappa$, we can use the downwards direction of the theorem to produce a model of cardinality exactly $\kappa$. $\square$

The Lowenheim--Skolem theorem has the mind-bending consequence that if ZFC is consistent, then ZFC has a countable model. Since we know that ZFC implies there exist uncountable sets, we appear to have reached a paradox: an uncountable object is contained in a countable object. The resolution to this apparent contradiction is that the countable model only believes its sets are uncountable because it lacks the bijections to prove they are countable. These bijections do exist but externally to the model.

### 22. Complete theories

Previously we said that a theory $T$ is complete if it is consistent, and for every sentence $\sigma$ either $\sigma\in T$ or $\neg\sigma\in T$.

For example, if $\mathcal A$ is any structure then the theory $T=Th(\mathcal A)$ consistening of all sentences $\sigma$ such that $\mathcal A\models\sigma$ is a complete theory. This follows simply from the definition of $\models$. Thus the theory of arithmetic $Th(\mathbb N,+,\times)$ and the theory of analysis $Th(\mathbb R,+,\times)$ are complete theories.

In accordance with common practice, we also say that $T$ is complete if the set of logical consequences of $T$ is complete. That is, $T$ is *complete* if it is consistent and for every sentence $\sigma$ either $T\models\sigma$ or $T\not\models\sigma$.

For example, if $T$ is the theory which says that $G$ is a group with exactly $7$ elements, then $T$ is complete. (One shows in a standard algebra class that there is only one such group.)

On the other hand, most theories are not complete. For example the theory of infinite linear orders (is there a last element? consider $(0,1)$ versus $(0,1]$), the theory of infinite abelian groups (are all elements divisible by 2? consider $\mathbb Z$ versus $\mathbb Q$), and set theory (does CH hold?).

In these examples, we can find sentences $\sigma$ such that $T\cup\set{\sigma}$ has a model, so $\neg\sigma$ is not a consequence of $T$, and $T\cup\set{\neg\sigma}$ has a model, so $\sigma$ is not a consequence of $T$.

But how can one show that a given theory $T$ is complete? In general this can be a challenging problem, but in the rest of this section, we will give one relatively easy tool to prove that at theory is complete. We first need several new definitions.

**Definition**. Structures $\mathcal A,\mathcal B$ are *isomorphic* if there is a bijection $\phi\colon A\to B$ such that for every function symbol $f$ we have $f^{\mathcal A}(a)=b\iff f^{\mathcal B}(\phi(a))=\phi(b)$ and for every relation symbol $R$ we have $R^{\mathcal A}(a)\iff R^{\mathcal B}(\phi(a))$.

**Definition**. Structures $\mathcal A,\mathcal B$ are *elementarily equivalent* if they satisfy the same sentences: $\mathcal A\models\sigma\iff\mathcal B\models\sigma$. In other words, the two structures are models of the same complete theory.

It is clear that if structures $\mathcal A,\mathcal B$ are isomorphic then they are elementarily equivalent. However the converse is false, since for example if $T$ is any complete theory with infinite models then $T$ has models of distinct cardinalities. This means that structures can have properties that are not described by first-order logic!

In light of the example in the previous paragraph, it is natural to ask whether a complete theory can have distinct models of the same cardinality. In general this is not the case, but when it is true we give it a name. 

**Definition**. Let $T$ be a theory and let $\kappa$ be a cardinal. Then $T$ is called *$\kappa$-categorical* if all models of $T$ of cardinality $\kappa$ are isomorphic to one another.

The following is the most famous example of a categorical theory. The theory of dense linear orders without endpoints consists of the theory of linear orders (irreflexivity, transitivity, trichotomy) plus the axioms $\forall x\forall y\exists z x\lt y\rightarrow x\lt z\lt y$ and $\forall x\exists y\exists z y\lt x\lt z$. Thus the rational order is an example of a dense linear order without endpoints.

**Proposition**. The theory $T$ of dense linear orders without endpoints is $\aleph_0$-categorical.

*Proof sketch*. Let $\mathcal A,\mathcal B$ be two countable models $T$. Let $a_n$ enumerate $A$ and let $b_n$ enumerate $B$. We can recursively construct an isomorphism using the "back-and-forth" method. Initially let $\phi(a_0)=b_0$. Next assume $\phi$ has been defined on $a_0,\ldots,a_n$ and $\phi^{-1}$ has been defined on $b_0,\ldots,b_n$. We then define $\phi$ on $a_{n+1}$ and $\phi^{-1}$ on $b_{n+1}$ by mapping them to the interval required to preserve the order relations. $\square$

Note that the theory of dense linear orders without endpoints is not $\kappa$-categorical for $\kappa=2^{\aleph_0}$. For example $\mathbb R$ and $\mathbb R\setminus\set{0}$ are dense linear orders without endpoints that are not isomorphic to one another.

Next we describe an example of a theory that is $\kappa$-categorical for some uncountable $\kappa$. A group is called torsion-free if it satisfies $\forall x x\neq0\rightarrow nx\neq 0$. A group is called divisible if it satisfies $\forall x\exists y nx=y$. The torsion-free divisible abelian groups are simply direct sums of copies of $\mathbb Q$. 

**Proposition.** The theory $T$ of torsion-free divisible abelian groups is $\aleph_1$-categorical.

*Proof*. Any torsion-free divisible abelian group $G$ can be made into a rational vector space by defining $\frac mng=h$ iff $mg=nh$. Note that divisibility is used to show there is such an $h$, and torsion-free is used to show that $h$ is unique. Now any two uncountable vector spaces over a countable field must have the same dimension, and therefore are isomorphic to one another. $\square$

The following result shows the connection between categorical and complete theories.

**Vaught Test Thoerem**. Let $T$ be a consistent theory in a finite language with no finite models. If $T$ is $\kappa$-categorical for some $\kappa$, then $T$ is complete.

*Proof*. Suppose that $T$ is $\kappa$-categorical but not complete. Then there is a sentence $\sigma$ such that both $T\cup\set{\sigma}$ and $T\cup\set{\neg\sigma}$ are consistent. By the Lowenheim--Skolem theorem, there are models $\mathcal A,\mathcal B$ of $T\cup\set{\sigma},T\cup\set{\neg\sigma}$ respectively, of cardinality $\kappa$. This contradicts that $T$ is $\kappa$-categorical. $\square$

**Corollary**. The theory of dense linear orders without endpoints is complete. In particular, $(\mathbb Q,\lt)$ and $(\mathbb R,\lt)$ are elementarily equivalent.

**Corollary**. The theory of torsion-free divisible abelian groups is complete. In particular, $(\mathbb Q,+)$ and $(\mathbb R,+)$ are elementarily equivalent.

A famous theorem of Morley states that a theory $T$ is $\kappa$-categorical for some $\kappa\geq\aleph_1$ if and only if $T$ is $\aleph_1$-categorical. This means that there are just two types of categoricity, countable and uncountable.

### 23. Definability and absoluteness

Consider the structure $(\mathbb N,+,0)$, and compare it with the structure $(\mathbb N,+)$. The second structure has a reduced language, but is it really weaker in the sense that fewer concepts are expressible?

**Definition**. Let $\mathcal A$ be a structure. An $n$-ary relation $R\subset A^n$ is *definable* in $\mathcal A$ if there is a formula $\phi(x_1,\ldots,x_n)$ such that $(a_1,\ldots,a_n)\in R\iff\mathcal A\models\phi[x_i=a_i]$. A function $f\colon A^n\to A$ is definable if its graph is a definable $n+1$-ary relation. Finally an element $c\in A$ is definable if $\set{c}$ is a definable unary relation.

For example, if $\mathcal A=(\mathbb N,+)$. Then the constant $0$ is definable using $x+x=x$, and $\lt$ is definable using $\exists z x+z=y$.

**Definition**. Let $T$ be an $\mathcal L$-theory, and $\phi$ a formula. Then the corresponding *expansion by definitions* of $T$ is the theory $T\cup\set{\phi(x_1,\ldots,x_n)\iff R(x_1,\ldots,x_n}$, where $R$ is a new $n$-ary relation symbol.

If $T'$ is an expansion by definitions of $T$, then $T,T$ prove exactly the same sentences of the original language. Moreover if $\phi$ is any formula of the expanded language then $T$ proves it is equivalent to a formula of the original language. Finally, if $\mathcal A$ is any model of $T$ then $\mathcal A$ can be expanded to a model of $T'$.

In the rest of this section we study definability in models of set theory. That is, we will return to our favorite theory ZFC and its fragments. Something potentially confusing happens when we study models of set theory that didn't happen in other theories: we can try use a set with its native $\epsilon$ relation as a model of set theory.

**Definition**. Let $A$ be any set. Then $A$ gives rise to a *set model* $(A;\epsilon)$ with domain $A$ and binary relation $\epsilon$.

When we work with set models, we elide the structure notation $\mathcal A=(A;\epsilon)$ and simply write $A$. Of course most set models will not satisfy all ZFC, but some subtheory of ZFC. For instance, every set model satisfies the Axiom of Extensionality.

One of the most useful set models is the set HF of hereditarily finite sets, also denoted $V_\omega$. Observe that HF satisfies all of ZFC except the Axiom of Infinity. Similarly the model $HC$ consisting of the hereditarily countable sets satisfies all of ZFC 

When $A,B$ are set models and $A\subset B$, both models believe they are talking about some of the same objects (they share the elements of $A$ in common), but they may disagree about properties of these objects. For example $\omega\subset HF$, the two models agree on which object is the empty set, and disagree on whether $\epsilon$ is a linear order. An even worse example is $\set{3,4,5,\ldots}$, which disagrees with HF about which object is the empty set!

**Definition**. Let $A\subset B$ be sets. A formula $\phi(x_1,\ldots,x_n)$ is *absolute* between $A$ and $B$ if for all substitution functions $s\colon V\to A$ we have $\mathcal A\models\phi[s]\iff\mathcal B\models\phi[s]$.

Which formulas are absolute between which set models? This is a complicated question in general, but there is a large class of formulas that is absolute between any two set models which are transitive. Recall that a set $A$ is *transitive* if $b\in a\in A$ implies $b\in A$.

**Definition**. A formula $\phi$ is said to be a *$\Delta_0$-formula* if its quantifiers are bound, that is, every occurrence of $\exists$ is of the form $\exists y\in z$ and every occurrence of $\forall$ is of the form $\forall y\in z$.

For example, the proposition that $x$ is an ordered pair may be expressed as a $\Delta_0$-formula. One needs to say $\exists y,z\in\bigcup x x=\langle y,z\rangle$.

On the other hand, the proposition that $x$ is a power set of another set cannot (apparently) be expressed as a $\Delta_0$ formula.

**Theorem**. If $A,B$ are transitive sets and $A\subset B$, then for any $\Delta_0$-formula $\phi$ we have that $\phi$ is absolute between $A$ and $B$.

*Proof*. We use induction on the complexity of $\phi$. If $\phi$ is atomic then it is of the form $x=y$ or $x\in y$. In each case the statement holds because both sets are using the true equality and element relations.

If $\phi$ is $\neg\alpha$ then the inductive hypothesis for $\alpha$ clearly gives the corresponding statement for $\phi$. A similar argument holds for the binary connectives.

If $\phi$ is $\exists y\in z\alpha$ and the statement is true of $\alpha$ then we have:

\begin{align*}
A\models \exists y\in z\alpha(x,y,z)
  &\iff \exists a\in A A\models \alpha(x,a,z)\wedge a\in z\\
  &\iff \exists a\in B B\models \alpha(x,a,z)\wedge a\in z\\
  &\iff B\models \exists y\in z\alpha(x,y,z)
\end{align*}

Here in the backwards direction we are using transitivity to say that if $a\in B$ and $a$ is required to be in $z\in A$, then $a\in A$. $\square$

## Part III: Computability theory

### 24. Computability

Suppose we are working over the set model HF. Informally, we say that $A$ is *decidable* if there is a procedure that decides given $x$ whether or not $x\in A$. In other words, there should be an algorithm or computer program which takes input $x$ and halts and outputs Yes if $x\in A$ and halts and outputs No if $x\notin A$.

For example, if $\phi$ is a $\Delta_0$-formula. Let $A=\set{x\in HF\mid \phi(x)}$ be the  corresponding $\Delta_0$-definable subset. Then $A$ is very simple in the sense that there is a natural decision procedure to decide whether or not $x\in A$. One simply steps through the formula testing its conditions, and each time one encounters a bounded quantifier, one must undertake just a finite search.

On the other hand, there are sets that are intuitively computable but not $\Delta_0$-definable. For example, let $A$ be the set of even natural numbers. Then there is cleary a decision procedure for $A$: given $x$ first check whether it is totally ordered and transitive, then mark off elements in pairs until you have $0$ or $1$ left over. But $A$ is not $\Delta_0$-definable. To see this, note that if it were then since $\omega$ is transitive it would be definable in $\omega$. But using compactness, $\omega$ has an elementary extension with an automorphism that moves $A$. Thus $A$ is not definable in $\omega$, and hence it is not $\Delta_0$-definable in HF.

**Definition**. A formula $\phi$ is $\Sigma_1$ if it is of the form $\exists y\alpha$, where $\alpha$ is $\Delta_0$. A formula $\phi$ is $\Pi_1$ if it is of the form $\forall y\alpha$, where $\alpha$ is $\Delta_0$. (We may also allow iterated existentials or iterated universals.)

**Definition**. A subset $A$ of HF is $\Delta_1$ definable if it is both $\Sigma_1$-definable and $\Pi_1$-definable.

(In fact there is a whole hierarchy of Sigma, Pi, and Delta definability, but this is all we will need for now.)

For example, the set $A$ of even natural numbers is a $\Delta_1$-definable subset of HF. We have already said that the property of being a natural number is $\Delta_0$-definable in HF. Thus the formula $\alpha(n,e)$ which says "$n$ is a natural number and $e$ is the set of even numbers $\lt n$" is $\Delta_0$. Then $x\in A$ if and only if $\exists n,e\alpha(n,e)\wedge x\in e$, and $x\in A$ if and only if $\forall n,e\alpha(n,e)\wedge x\in n\rightarrow x\in e$.

Like the $\Delta_0$-formulas, the $\Delta_1$-decidable sets enjoy a degree of absoluteness.

**Proposition**. Let $A,B$ be transitive sets and $A\subset B$. If $\phi$ is a $\Sigma_1$ sentence and $A\models\phi$ then $B\models\phi$. If $\phi$ is a $\Pi_1$ sentence and $B\models\phi$ then $A\models\phi$. If $\phi$ is $\Sigma_1$, $\psi$ is $\Pi_1$, and both $A,B$ model $\phi\leftrightarrow\psi$, then $\phi,\psi$ are absolute between $A$ and $B$.

Like the $\Delta_0$-definable sets, the $\Delta_1$-definable sets are decidable, but by a more complex procedure. Suppose that $A$ is defined both by $\exists y\alpha(x,y)$ and by $\forall y\beta(x,y)$, where $\alpha,\beta$ are $\Delta_0$-formulas. Then $A^c$ is defined by $\exists y\neg\beta(x,y)$. Given an input $x$, we run through all possible values of $y$ and each time check whether $\alpha(x,y)$ holds and whether $\neg\beta(x,y)$ holds. Since $A$ and $A^c$ are complementary, one of these must eventually occur, at which point we can say whether $x\in A$ or $x\in A^c$. Note that this procedure will have to terminate, but our description provides no insight as to when.

Conversely, if a set $A$ is decidable by some procedure, then $A$ should be $\Delta_1$-definable. To see this note that each run of the procedure should leave some record of its behavior. Thus we can say that $x\in A$ iff there exists a code for a run of the procedure on input $x$ that halted and output Yes. And we can say that $x\in A$ iff for all codes for a run of the procedure on input $x$, if the code halted, then the output was Yes.

**Church-Turing Thesis**. A set is decidable by a procedure (in a finite amount of time, with finitary operations, without resource limitations) if and only if it is $\Delta_1$-definable.

In other words, all "reasonable" notions of being decidable by a procedure end up being equivalent to one another. The list of equivalent notions is long and includes decidable by a Turing machine, decidable by a python program, definable by recursion, and so forth. The point is that all of these possible choices lead to the same robust notion. For our class we will stick with $\Delta_1$-definable as the official definition.

**Definition**. A subset $A$ of HF is *decidable* if it is $\Delta_1$-definable.

The class of decidable sets has many nice properties.

**Proposition**. The decidable sets of HF are closed under boolean operations and bounded quantification.

*Proof*. It suffices to show that $\Delta_1$-definitions are closed under negation, conjunction, disjunction, and bounded quantification.

Complementation is clear because $\Sigma_1$ and $\Pi_1$ are dual to one another. For disjuctions observe that $\exists x\alpha(x)\wedge\exists x\beta(x)$ is equivalent to $\exists x\exists y\alpha(x)\wedge\beta(y)$, and similarly for $\forall$. Yet another similar argument holds for conjuctions.

For bounded quantification, we will show that $\Sigma_1$ is closed under bounded quantification. The argument for $\Pi_1$ is similar, and the fact for $\Delta_1$ follows. For this, first observe that $\exists x\in y\exists z\alpha$ is equivalent to $\exists z\exists x\in y\alpha$ which is clearly $\Sigma_1$. Next we claim that $\forall x\in y\exists z\alpha$ is equivalent to $\exists u\forall x\in y\exists z\in u\alpha$. The backward implication is trivial. For the forward implication we create a set $u$ which contains a witness $z_x$ for all possible $x\in y$. $\square$

### 25. Computable functions and recursion

**Definition**. Let $f$ be a function from HF to HF. Then $f$ is *computable* if its graph is decidable.

The Church--Turing thesis implies that we can informally say that $f$ is computable if and only if there is a procedure which, given any input $x$, halts and outputs $f(x)$. To see this equivalence, first if the graph of $f$ is decidable then given $x$ we can search through all possible values $y$ until we find one with $(x,y)\in f$ and then we can halt and output $y$. Conversely if there is such a procedure for evaluating $f$ then given $(x,y)$ we can decide whether $(x,y)\in f$ by calculating $f(x)$ and asking whether $f(x)=y$.

The simplest example of a computable function is the characteristic function $\chi_A$ of any decidable set $A$. Indeed $(x,i)\in\chi_A$ if and only if $i=1$ and $x\in A$ or else $i=0$ and $x\notin A$. This statement is a boolean combination of $\Delta_1$-formulas.

Another example of a computable function is the cardinality function $f(x)=\abs{x}$. Here $\abs{x}=y$ if and only if $y\in\omega$ and there exists a bijection between $x$ and $y$, and $\abs{x}=y$ if and only if $y\in\omega$ and every injection from $x$ to $y$ is a surjection.

Some more interesting examples of computable functions are $+,\cdot$. However to prove this we will need the recursion theorem. You may recall that we have proved the classical recursion theorm and the transfinite recursion theorem. What we need is the computable version of the recursion theorem.

**Theorem**. If $G\colon\mathbb N^{\lt\omega}\to\mathbb N$ is computable, then there exists a computable function $F\colon\mathbb N\to\mathbb N$ such that $F(n)=G(F\restriction n)$.

*Proof idea*. The ordinary recursion theorem implies that the function $F$ exists. To see that $F$ is computable observe that $F(n)=y$ if and only if there exists a finite partial function $f$ obeying the recursion and satisfying $f(n)=y$, and $F(n)=y$ if and only if for all finite partial functions $f$ obeying the recursion if $n$ is in the domain then $f(n)=y$. Thus the graph of $F$ is $\Delta_1$-definable. $\square$

Thus the well-known enumerations such as $n!$, the $n$th Fibonacci number, as well as $+,\cdot$ are computable because they are defined recursively by computable rules. There is also a version of the recursion theorem along $\in$, so that functions such as the cardinality and rank functions may be defined recursively.

Another application of the recursion theorem is the following.

**Proposition**. Let $A$ be the set consisting of all pairs $\phi,\sigma$, where $\phi$ is a code for a $\Delta_0$-formula and $\sigma$ is a substitution function, such that $HF\models\phi[\sigma]$. Then $A$ is decidable.

The idea of the proof is to use the partial order of subformulas, and then to define a function $f$ which maps inputs $\phi,\sigma$ to values $T,F$ by recursion. The recursive definition $G$ is simply a formalizing our definition of satisfaction.

### 26. Undecidable sets

We have given numerous examples of decidable sets and computable functions. What kinds of things are not decidable? We first begin with the following.

**Theorem**. There exists a set which is $\Sigma_1$-definable but not $\Delta_1$-definable.

This theorem is hardly surprising, since otherwise we would probably not have given different names to the concepts $\Delta_1$ and $\Sigma_1$. To prove this we will first show that there is a $\Sigma_1$ set which is universal in the sense that it is of maximum complexity among the $\Sigma_1$ sets. We will then prove that a universal $\Sigma_1$ set cannot be $\Delta_1$.

**Lemma**. There exists a $\Sigma_1$-definable set $U\subset HF^2$ such that for every $\Sigma_1$-definable set $A\subset HF$ there exists $r\in HF$ such that $A=\set{x\mid (r,x)\in U}$.

*Proof of Lemma*. Let $V$ be the set of all triples $(\phi,x,y)$ where $\phi$ is a code for a $\Delta_0$-formula and $HF\models\phi(x,y)$. Then we have shown $V$ is $\Delta_1$. Next let $U$ be the set of all pairs $(\phi,x)$ such that $\exists y(\phi,x,y)\in V$. Then $U$ is clearly $\Sigma_1$.

Now if $A$ is any $\Sigma_1$ set, then $A$ is defined by $x\in A$ if and only if $\exists y\phi(x,y)$ for some $\phi$. Thus $A$ is precisely $\set{x\mid(\phi,x)\in U}$, as desired. $\square$

To prove the theorem, we once again return to the diagonalization idea of Cantor and Russell.

*Proof of Theorem*. Let $U$ be a universal $\Sigma_1$ set. Let $D=\set{x\in HF\mid (x,x)\notin U}$. Then $D$ fails the conclusion of the Lemma, since it disagrees with every horizontal section of $U$. Thus $D$ is not $\Sigma_1$. However the definition of $D$ is clearly $\Pi_1$. It follows that $HF\setminus D$ is a $\Sigma_1$ set which is not $\Pi_1$ and in particular not $\Delta_1$, as desired. $\square$

While the universal set the first place one would look for an example of an undecidable set, it is not very natural in the sense that it would not arise in practice. We next introduce one of the most naturally occuring examples of an undecidable set.

In the following result, fix any model computation you like, and fix some way of coding programs in that model as elements of HF. For example if you like python programs, you can code the symbols of python as natural numbers, and code a whole program as a finite sequence of natural numbers. Now some python programs halt, and others run forever. We let $H\subset HF$ consist of the set of codes for programs that halt.

**Theorem**. The set $H$ of codes for halting programs is undecidable.

*Proof*. Let $A$ be a $\Sigma_1$ set which is not $\Delta_1$. Let $\phi$ be a $\Delta_0$-formula such that $x\in A$ if and only if $\exists y\phi(x,y)$. For each $x$ let $h_x$ be a code for the program which searches through all possible $y\in HF$ until it finds one such that $\phi(x,y)$. Then $x\in A$ if and only if $h_x\in H$. Thus if $H$ were $\Delta_1$ then so would $A$ be $\Delta_1$, a contradicton. $\square$

In this proof we defined a function $r\colon HF\to HF$ with the property that $x\in A\iff r(x)\in H$. Such a funcion is called a *reduction* from $A$ to $H$, and it implies that the complexity of $H$ is no simpler than that of $A$. If one wishes to prove that a given set is undecidable, the most common proof technique is to find a reduction from some known undecidable set to the given set.

### 27. Decidability in logic, incompleteness

In this section we apply our understanding of diagonalization and undecidability in the setting of logical proof. The result will be Godel's incompleteness theorems.

Recall that if $T$ is a theory then its deductive closure is the set $\bar T=\set{\sigma\mid T\vdash\sigma}$. Most theories that we have described are decidable, but the deductive closure may or may not be.

For example it is not difficult to decide whether or not a given sentence $\sigma$ is in ZFC, but it is much more decide whether $\sigma$ is a theorem of ZFC. OF course ZFC is very powerful, so this may not be too surprising. But we can study the same questions about deductive closure in the context of much simpler theories.

**Definition**. Core set theory, or CST, is the theory consisting of the Axiom of Extensionality, Axiom of Pairing, Axiom of Union, Axiom of Comprehension, and the Axiom of Foundation.

This theory may seem weak compared to ZFC, but it is strong enough to do finite set theory plus induction. It is also possible to work Peano Arithmetic, the usual axioms of the natural numbers with $+,\cdot$ including the induction scheme.

**First incompleteness theorem**. If $T$ is any consistent extension of CST then $\bar T$ is undecidable.

In our proof of the first incompleteness theorem, we once again return to a diagonalization argument. This time we will need to "represent" subsets of HF inside $T$ itself.

**Proposition**. Every element $a\in HF$ is $\Delta_0$-definable. That is, there is a $\Delta_0$-formula $\delta_a(x)$ such that $x=a\iff\delta_a(x)$.

The propostion says that we don't need to add terms for elements of HF, we can already represent these elements in the language.

**Definition**. Given a theory $T$ of $\in$, a formula $\phi$, and an element $a\in HF$, we will say that $T\vdash\phi(\langle a\rangle)$ if and only if $T\vdash\exists x\delta_a(x)\wedge\phi(x)$. CHECK

**Definition**. Let $T$ be any theory of $\in$ and let $A\subset HF$. Then $A$ is *representable* in $T$ if there is a formula $\phi$ such that $a\in A$ if and only if $T\vdash\phi(\langle a\rangle)$.

**Proposition**. Let $T$ be a consistent extension of CST. Then every $\Delta_0$-definable set is representable in $T$.

*Proof*. We will prove that for any $\Delta_0$-formula, we have $CST\vdash\phi(\langle a\rangle)$ if and only if $HF\models\phi[a]$. For atomic and negated atomic formulas $x\in y$, $x\notin y$, $x=y$, and $x\neq y$ are proved by induction on the rank of the elements $a,b$ that are plugged in for $x,y$. For general $\Delta_0$-formulas $\phi$ we use induction on the complexity of $\phi$. The boundedness of quantifiers is key because they reduce to conjuctions or disjunctions of atomics. $\square$

The claim that $CST\vdash\phi(\langle a\rangle)$ if and only if $HF\models\phi[a]$ fails for arbitrary formulas since for instance the negation of the Axiom of Infinity is true in HF but not provable from CST.

**Proposition**. Let $T$ be a consistent extension of CST. Then every $\Delta_1$-definable set is representable in $T$.

*Proof*. Let $A$ be a $\Delta_1$-definable subset of HF, and let $\alpha,\beta$ be $\Delta_0$-formulas such that $a\in A$ iff $\exists y\alpha(a,y)$ iff $\forall z\beta(a,z)$. Note that we cannot use either of these two expressions directly to represent $A$, because they may be true without being witnessed in HF (that is, they may be witnessed by nonstandard elements). Instead we let $\psi(x)$ be the formula:

\begin{equation*}
\exists y\left[\alpha(x,y)\wedge\forall z \mathrm{rk}(z)\lt \mathrm{rk}(y)\rightarrow\beta(x,z)\right]
\end{equation*}

We claim that $a\in A\iff T\vdash\psi(\langle a\rangle)$. First assume that $a\in A$. Then there is $y\in HF$ with the desired property. Since the inner portion of the sentence is $\Delta_0$, the previous proposition implies $T$ proves $\psi(\langle a\rangle)$.

Conversely assume that $a\notin A$. We claim that $CST\vdash\neg\psi(\langle a\rangle)$, that is,

\begin{equation*}
\forall y\left[\neg\alpha(\langle a\rangle,y)\vee\exists z \mathrm{rk}(z)\lt \mathrm{rk}(y)\wedge\neg\beta(\langle a\rangle,z)\right]
\end{equation*}

Indeed first find $z$ such that $CST\vdash\neg\beta(\langle a\rangle,\langle z\rangle)$. Next given any $y$, if $y\in HF$ then the first clause holds, and if not then the second clause holds. Now since $T$ is a consistent extension of CST, we conclude $T\not\vdash\psi(\langle a\rangle)$. $\square$

We are now ready to prove the final step of the first incompleteness theorem.

**Theorem**. Suppose $T$ is a theory such that every $\Delta_1$-definable subset of HF is representable in $T$. Then $\bar T$ is undecidable.

*Proof*. Let $U=\set{(\phi,a)\mid T\vdash\phi(\langle a\rangle)}$. Then since every $\Delta_1$-definable set is representable in $T$, every $\Delta_1$-definable set  appears as a cross-section of $U$, namely $\set{a\mid (\phi,a)\in U}$. We say that $U$ is universal for $\Delta_1$ sets.

Now if $\bar T$ were decidable then $U$ would be decidable and hence $\Delta_1$-definable. Thus the diagonal set $D=\set{x\mid (x,x)\notin U}$ would be $\Delta_1$-definable. This is a contradiction because $D$ does not appear as a cross-section of $U$. $\square$

This completes the proof of the first incompleteness theorem. We can rephrase the first incompleteness theorem as follows.

**Corollary**. If $T$ is any consistent, decidable extension of CST then $T$ is incomplete.

To see that this result follows from the first incompleteness theorem, note that if $T$ were complete then we would have $\bar T=T$.

The corollary is rather stunning, since it implies mathematicians will never know all truths about sets or arithmetic. We can't simply add axioms to ZFC (such as CH etc) to obtain a decidable theory which can prove or disprove all statements.

The corollary provides conditions under which there exists a sentence that is neither provable nor disprovable from $T$. However it does not provide an example of such a sentence $\sigma$. The second incompleteness theorem gives an explicit and relevant example of such a sentence $\sigma$.

**Second incompleteness theorem**. If $T$ is any consistent, decidable extension of CST then, and $\sigma$ is the sentence which asserts that $T$ is consistent, then $T\not\vdash\sigma$.

*Proof idea*. It is possible to formalize consistency and provability in CST. It is further possible to construct a diagonal sentence $\tau$ which asserts in the formalization that "$T\not\vdash\tau$", that is, there is no proof from $T$ of $\tau$ itself. We omit the details—it is like the liar paradox statement "this sentence is false", but with truth replaced by provability. Then $T\vdash\tau$ implies $T\not\vdash\tau$ and vice versa. This is a contradiction! $\square$

<script type='text/x-mathjax-config'>
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [['$','$'], ['\\(','\\)']],
      processEscapes: true
    },
    TeX: {
      Macros: {
        set: ["{\\left\\{ #1 \\right\\}}", 1],
        abs: ["{\\left| #1 \\right|}", 1],
        lt: ["<"]
      }
    }
  });
</script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML'></script>
