# Math 502 course notes

Based largely on our textbook Ken Kunen, *The Foundations of Mathematics*.

## Part I: Set theory

### 1. Introduction and foundational logic

* There is a circular relationship between logic and set theory
* We will start with just enough logic to talk about set theory, and then return to logic again in the second part.
* Logical symbols: and, or, not, implies, iff, for all, there exists, and variables
* Non-logical symbols: the relations, functions, and constant symbols used in a given context. Examples include less than, plus, times, 0.
* Sentences versus formulas 
* The axiomatic method: for any area of study, we first choose a universe of discourse and an appropriate collection of non-logical symbols. We then write down a collection of axioms that govern how the symbols behave. Finally we try to prove theorems using only the axioms.
* Example 1: geometry
* Example 2: group theory
* Example 3: arithmetic
* Our main example will be set theory. Set theory is important for two key reasons. First it is a foundational theory, meaning all of the above theories can be studied inside of set theory. Second it allows us to study the idea of infinity, since after all we know there are infinite sets.
* In set theory the universe of discourse consists of all possible sets. The only non-logical symbol will be the binary set membership relation $\in$. The remaining set relations and operations will be definable from this one alone.
* BIG IDEA: In particular everything is a set, even the elements of a set! Thus the universe really consists of hereditary sets.

### 2. Extensionality, pairing, union; also separation

* Set theory is officially the axioms for the set membership relation $\in$.
* There are many additional set relations and operations, but these can all be defined in terms of $\in$. For example consider subset, union, intersection, and empty set.
* Draw some sample models
* The axioms of set theory must at least get the hereditarily finite sets right.
* Empty Set Existence Axiom: not officially necessary, but let's just start with this.
* Extensionality Axiom: This axiom distinguishes set theory from other types of collections (lists, multisets). 
* Pairing Axiom:
* Union Axiom:
* Proposition: there exists a nonempty set
* Proposition: there exists a set with more than one element
* Proposition: there exists a set with more than two elements
* In general, one can see how all sets involving {} and $\emptyset$ may be created
* Comprehension Axiom: Allows to form subsets. This justifies the use of the set-builder notation {z in x \| phi(z)}.
* Naive comprehension {z \| P(z)} leads to two problems: the use of non-logical phrases such as "the least natural number that can be defined in fewer than 20 words", and Russell's paradox. The modern comprehension axiom is also called the separation axiom.
* The comprehension axiom is really an axiom scheme. Thus set theory officially has infinitely many axioms.

### 3. Natural numbers, relations, functions, replacement

* We have promised that set theory is somehow the theory of everything, meaning all other objects of mathematical study can be regarded as sets. Perhaps the most important objects in mathematics are natural numbers. How can these be regarded as objects in the universe of sets?
* Von Neumann ordinals: an ordinal is a counting number (as opposed to a quantity measuring number). Define 0, 1, 2, 3, etc as particular hereditarily finite sets.
* We have also promised that set theory is somehow the theory of the infinite, meaning we can study different kinds of infinity using sets. The axiom of infinity will allow us to count into the infinite.
* In general, an ordinal is equal to the collection of ordinals that came before it. Thus the Von Neumann ordinals will be extended into the infinite by setting $\omega$={0,1,2,3,...}, $\omega+1$={0,1,2,3,...,$\omega$} and so on. Infinity plus one!
* Thus we have a successor function $S(\alpha)$ or $\alpha+1$ is equal to $\alpha\cup\\{\alpha\\}$. 
* Another of the most important mathematical objects is a function. You may have seen the definition of a function as a set of ordered pairs (input,output).
* Ordered pair: (a,b) is defined to be { {a}, {a,b} }. We have to check this "works". Observe that other more naive attempts don't work.
* Binary relation: any set whose elements are ordered pairs. If R is a set of ordered pairs (a,b) then we write aRb to mean that (a,b) is an element of R. Example: less than
* Function: 
* In elementary mathematics, we usually teach that a function is a formula or rule. But in formal mathematics, a function is really its graph.
* Domain and range: these concepts are valid for binary relations (and in particular for functions). Note both the domain and range of R are subsets of UUR.
* Injective, surjective, and bijective: ...
* Cartesian product: Most binary relations, and thus most functions, are constructed as a subset of a cartesian product AxB = {(a,b) \| a in A, b in B}.
* In order to show that the cartisian product exists, we actually need a new axiom!
* Replacement Axiom: For each logical formula phi(x,y) satisfying phi(x,y) and phi(x,y') implies y=y', the following is an axiom: For all A, there exists B which is the image of phi restricted to the domain A.
* Once again, the replacement axiom is an axiom scheme.
* Theorem. For any sets A,B we can construct the cartesian product AxB.
* Proof: First, for each b in B we can use replacement with phi(x,y) being "(x,b)=y" and domain A to construct each Ax{b}. Then use replacement with phi(x,y) being "Ax{x}=y" to construct the set {Ax{b} | b in B}. Finally apply union to this to get AxB.
* For example, suppose we have constructed the set N of natural numbers. Then we can construct the cartesian product NxN. We can further construct the less than binary relation on N. If we have already constructed the + and x operations (which we'll do still later), we can further construct functions such as f(n)=n^2+2n+5.

### 4. More relations, well-orders

* We have introduced functions as relations but there are several other special types of relations.
* Order relations: Like the &lt; relation on R.
* Def: A (strict) linear order is a binary relation R on a set X (meaning both the domain and range are contained in X) satisfying the axioms transitive, irreflexive, and trichotomy
* Equivalence relations: Like equality, congruence, similarity, isomorphism.
* Def: An equivalence relation is a binary relation R on a set X satisfying the axioms transitive, reflexive, and symmetric.
* Isomorpism of linear orders: ...
* For example, on R &lt; and &gt; are isomorphic. However on [0,1), &lt; and &gt; are not isomorphic.
* Examples of linear orders: most number sets such as N, Z, Q, R, and the induced ordering on any subset of these.
* The key example in set theory is the ordering of the ordinals as introduced above. The $\in$ relation is a linear order.
* What is an ordinal really? In addition to being a linear order, one key property is that it only has ...'s that go to the right.
* Def: A relation R on a set X is called well-founded if for all nonempty subsets Y of X, Y has an R-minimal element (an element y in Y such that for all z in Y it's not true that zRy).
* Def: A well-founded relation that is also a linear order is called a well-order.
* Examples: None of Z,Q,R are well-orders, but N and ordinals are.
* Theorem: A relation R is a well-order iff there is no infinite R-descending sequence.
* Proof: -&gt; Note that an infinite R-descending sequence has no R-minimal element. &lt;- If R is not well-founded and X has no R-minimal element, pick any x(0) in X and recursively choose x(n+1) in X such that x(n+1) R x(n).
* (Later we will make the concepts "infinite", "recursively", and "choose" formal.)

### 5. Ordinals

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

### 6. More ordinals

* We have defined a set alpha to be an ordinal if it is well-ordered by $\in$ and a transitive set. We have shown the ordinals are a proper class that is itself well-ordered by $\in$ and transitive.
* The ordinal successor operation: $S(\alpha)$ or $\alpha+1$ = $\alpha \cup \\{\alpha\\}$. In principal this may be carried out on any set, but it is most useful on ordinals because then it always produced another ordinal.
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
  * For this, suppose $f\colon\alpha\cong\beta$. We wish to show that f is the identity function. If it isn't the identity function, then there exists $\xi\in\alpha$ which is the first point moved by $f$. (Use the well-foundedness of $\alpha$ here.) If $f(\xi)=\mu&lt;\xi$ then we would also have $f(\mu)=\mu$, contradicting that f is injective. On the other hand if $f(\xi)=\mu&gt;\xi$ then nothing can possibly map to $\xi$, contradicting that $f$ is surjective.
  * We next show the existence portion of the theorem, which will be seen to have an inductive flavor.
  * Let R be a well-ordered relation on A. For each $a\in A$ let pred(a) denote the set of R-predecessors of A. Define a set of "good" elements by G={a:pred(a) is isomorphic to an ordinal}. Using the uniqueness proved above, and the axiom of replacement, we may define a function on G by f(a)=the unique ordinal such that pred(a) is isomorphic to f(a). We now make a series of observations:
    * G is an R-initial segment of A, since if $a\mathrel{R}b\in G$ and $pred(b)\cong\beta$ we can restrict this isomorphism to $pred(a)$.
    * f is an order-preserving map from G into the ordinals, meaning that $aRb$ implies $f(a)\in f(b)$.
    * f(G) is an initial segment of the ordinals, since if $\beta\in\alpha=f(a)$ then there is an isomorphism of pred(a) with $\alpha$ carrying some b to $\beta$, and then $f(b)=\beta$.
  * It follows that the range of f IS an ordinal, call it $\xi$. To complete the proof, it is enough to show that G=A. If this is not the case, then let a be the minimum element of $A\setminus G$. Then pred(a) is exactly G, and it follows that f is an isomorphism of pred(a) with $\xi$. The definition of G now means that $a\in G$ after all, a contradiction!
* Whew!  
* Lexicographic ordering.

## Part II: Model theory

## Part III: Computability theory

<script type='text/x-mathjax-config'>
  MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']], processEscapes: true}});
</script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML'></script>
