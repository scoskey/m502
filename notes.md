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
* Proof: First, for each b in B we can use replacement with phi(x,y) being "(x,b)=y" and domain A to construct each Ax{b}. Then use replacement with phi(x,y) being "Ax{x}=y" to construct the set {Ax{b} \| b in B}. Finally apply union to this to get AxB.
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
* Proof: $\rightarrow$ Note that an infinite R-descending sequence has no R-minimal element. $\leftarrow$ If R is not well-founded and X has no R-minimal element, pick any x(0) in X and recursively choose x(n+1) in X such that x(n+1) R x(n).
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
  * For this, suppose $f\colon\alpha\cong\beta$. We wish to show that f is the identity function. If it isn't the identity function, then there exists $\xi\in\alpha$ which is the first point moved by $f$. (Use the well-foundedness of $\alpha$ here.) If $f(\xi)=\mu<\xi$ then we would also have $f(\mu)=\mu$, contradicting that f is injective. On the other hand if $f(\xi)=\mu>\xi$ then nothing can possibly map to $\xi$, contradicting that $f$ is surjective.
  * We next show the existence portion of the theorem, which will be seen to have an inductive flavor.
  * Let R be a well-ordered relation on A. For each $a\in A$ let pred(a) denote the set of R-predecessors of A. Define a set of "good" elements by G={a:pred(a) is isomorphic to an ordinal}. Using the uniqueness proved above, and the axiom of replacement, we may define a function on G by f(a)=the unique ordinal such that pred(a) is isomorphic to f(a). We now make a series of observations:
    * G is an R-initial segment of A, since if $a\mathrel{R}b\in G$ and $pred(b)\cong\beta$ we can restrict this isomorphism to $pred(a)$.
    * f is an order-preserving map from G into the ordinals, meaning that $aRb$ implies $f(a)\in f(b)$.
    * f(G) is an initial segment of the ordinals, since if $\beta\in\alpha=f(a)$ then there is an isomorphism of pred(a) with $\alpha$ carrying some b to $\beta$, and then $f(b)=\beta$.
  * It follows that the range of f IS an ordinal, call it $\xi$. To complete the proof, it is enough to show that G=A. If this is not the case, then let a be the minimum element of $A\setminus G$. Then pred(a) is exactly G, and it follows that f is an isomorphism of pred(a) with $\xi$. The definition of G now means that $a\in G$ after all, a contradiction!
* Whew!

### 7. Ordinals and induction

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
* The transfinite recursion principle: Let G(x) be a proper class function (defined by a function-like formula phi(x,y)). Then there is a proper class function F(x) such that for every alpha we have F(alpha)=G(F\|alpha).
* The proof is similar to the proof of the classical recursion principle, and it relies on the principle of induction plus replacement. We will content ourselves with a summary in the case of G(s)=n s\|n.
  * We want to build the function F(n)=n!. We do this by building a sequence of approximations F\_n. Each function F\_n has domain n={0,...,n-1} and behaves like the usual factorial.
  * We prove by induction that for each n, there exists a unique function F\_n with the property described above. The base case is trivial. The inductive step is true because we can define f\_n+1 (n) = nf\_n(n-1), and check this is unique.
  * We finally let F(n)=F\_n+1 (n). This is the desired item.
* The general theorem is proved by: (1) substitute whatever G is into the proof, (2) at limit stages obtain F\_lambda by taking a union of the previous F\_beta's.
* We can finally make sense of the intuitive idea of doing something iteratively. This will be of fundamental importance to our study of the infinite.
* Example: epsilon\_0.
* Example: transitive closure: Define U^nz inductively, and then tc(z)=UU^nz.

### 8. Power set and cardinality

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
* We say that \|A\|$\leq$\|B\| if there is an injection, \|A\|=\|B\| if there is a bijection, and \|A\|&lt;\|B\| if there is an injection but no bijection.
* Note that so far we have told you how cardinality works, but not what cardinality is. We will remedy this later.
* Cantor's theorem. If A is any set, then \|A\|&lt;\|P(A)\|.
* Proof.
  * The function i(a)={a} is an injection from A to P(A).
  * Now suppose that f is any function from A to P(A). We will show that some subset D of A is not in the range of f. Thus f is not a bijection. Since f was arbitrary this proves the theorem.
  * The definition of D is { a in A : a notin f(a) }. This is called a diagonalizer.
  * Example: suppose f(a)={b,c,z}, f(b)={a,b,c,d}, f(c)={a,d,e,g,h}, f(d)={d,w,z}, .... Then we would let D = {a, c, ...}. This is guaranteed not to be in the range because it differs from every f(x) on the subject of x.
  * Formally, suppose towards a contradictoin that D is in the range and let f(a)=D. Then ask whether a in D (it implies a notin D) and whether a notin D (it implies a in D).
* Corollary. There are infinitely many distinct cardinalities, and infinitely many distinct uncountable cardinalities. For example, omega, P(omega), P(P(omega)), etc.
* Corollary. The digit spaces 2^N^, N^N^, and R are uncountable. The first space is exactly P(omega), and the first space embeds into the latter two.
* But what is the exact cardinality of N^N^ and R?
* Cantor-Schroder-Bernstein theorem. If \|A\|$\leq$\|B\| and \|B\|$\leq$\|A\| then \|A\|=\|B\|.
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

### 9. Cardinals

* Previously we defined the behavior of \|A\| in terms of injections and bijections. But what exactly is \|A\|?
* One of the earliest definitions of \|A\| was the set of all sets that are in bijection with A. Thus 3 is the set of all 3-element sets. But this object is a class not a set.
* Once we again use the idea of representatives, so \|A\| will be a particular set of size A (if possible). And once again we turn to the ordinals.
* Def: An ordinal alpha is called a cardinal if it isn't in bijection with any lower ordinal.
* Ex: 0,1,2,... are all ordinals that are cardinals. omega is also a cardinal. But as we have seen, omega^2^ and so on are not cardinals.
* Def: If A is any set then \|A\| = a cardinal kappa such that there is a bijection between A and kappa. Note that if this exists it must be unique.
* Ex: This supports standard calculations like \|{divisors of 10}\|=4.
* Ex: If A is a countable set, then \|A\|=omega.
* Question: What is \|R\|?
* In principle, there may be sets A which are not in bijection with any ordinals/cardinals. In such a case \|A\| cannot be defined to be an ordinal or any particular object. Thus to approach cardinals in this way we need an axiom.
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
* Prop. If kappa is an infinite cardinal then |kappa x kappa|=|kappa|
* Proof. We must show kappa x kappa is injectible into kappa. Assume it is true for every alpha&lt;kappa. Let R be the usual increasing boxes ordering of kappa x kappa. Then every initial segment of R is contained in some alpha x alpha, and hence injectible into alpha. It follows that R is injectible into kappa. (If it weren't then kappa would be injectible into some initial segment of R and hence into some alpha&lt;kappa contradicting it is a cardinal.)
* Continuing this logic one can determine that even iterated ordinal exponentiation etc does not increase cardinality. In particular the countable ordinals extend inconceivably far before finally being dominated by aleph1.
* Ordinal exponentiation vs cardinal exponentiation

### 10. Axiom of choice

* We have said that the axiom of choice allows us to regard all cardinals as special ordinals that are not in bijection with any smaller ordinal. But what does the axiom say exactly?
* Axiom of Choice: If F is a set of nonempty sets which are pairwise disjoint, then there exists a set C such that \|C cap A\|=1 for all A in F.
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
* Cor. For any sets A,B, we have \|A\|$\leq$\|B\| or \|B\|$\leq$\|A\| (or both).
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

### 11. Cardinal arithmetic

* We have defined arithmetic for ordinals and explored some of its properties.
* Assuming AC, we can define an arithmetic of cardinals as well. We use context and hinting to distinguish between ordinal and cardinal arithmetic!
  * kappa + lambda = \|kappa + lambda\| as ordinals
  * kappa x lambda = \|kappa x lambda\| as ordinals
  * kappa^lambda^ = \| Fun(lambda, kappa) \|
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
* Then d disagrees with every f\_xi somewhere, completing the contradiction and the proof.

## Part II: Model theory

## Part III: Computability theory

<script type='text/x-mathjax-config'>
  MathJax.Hub.Config({tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']], processEscapes: true}});
</script>
<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.2/MathJax.js?config=TeX-AMS_HTML'></script>
