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
* In general, an ordinal is equal to the collection of ordinals that came before it. Thus the Von Neumann ordinals will be extended into the infinite by setting $\omega={0,1,2,3,...}$, $\omega+1=\\{0,1,2,3,...,\omega\\}$ and so on. Infinity plus one!
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
* Replacement Axiom: 
* Once again, the replacement axiom is an axiom scheme.
* Theorem. For any sets A,B we can construct the cartesian product AxB.
* For example, suppose we have constructed the set N of natural numbers. Then we can construct the cartesian product NxN. We can further construct the less than binary relation on N. If we have already constructed the + and x operations, we can further construct functions such as f(n)=n^2+2n+5.

### 4. More relations, well orders

* We have introduced functions as relations but there are several other special types of relations.
* Order relations: Like the &lt; relation on R.
* Def: A (strict) linear order is a binary relation R on a set X satisfying the axioms transitive, irreflexive, and trichotomy
* Equivalence relations: Like equality, congruence, similarity, isomorphism.
* Def: An equivalence relation is a binary relation R on a set X satisfying the axioms transitive, reflexive, and symmetric.
* Isomorpism of linear orders: ...
* For example, on R &lt; and &gt; are isomorphic. However on [0,1), &lt; and &gt; are not isomorphic.
* Examples of linear orders: most number sets such as N, Z, Q, R, and the induced ordering on any subset of these.
* The key example in set theory is the ordering of the ordinals as introduced above. The $\in$ relation is a linear order.
* 

### 5. Ordinals

* ...

## Part II: Model theory


## Part III: Computability theory


<script type='text/x-mathjax-config'>
  MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']], processEscapes: true}});
</script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML'></script>
