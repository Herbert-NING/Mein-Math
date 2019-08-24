
# Naive Set Theory by Paul R. Halmos

ISBN 879-7-5062-9217-7/O608

---

## Contenet

| Section |                                                           | Page  |
| :-----: | :-------------------------------------------------------: | :---: |
|         |                    [Preface](#Perface)                    |   V   |
|    1    |     [The axiom of extension](#the-axiom-of-extension)     |   1   |
|    2    | [The axiom of specification](#the-axiom-of-specification) |   4   |
|    3    |            [Unordered pairs](#unordered-pairs)            |   8   |
|    4    |    [Unions and intersection](#unions-and-intersection)    |  12   |
|    5    |     [Complements and powers](#complements-and-powers)     |  17   |
|    6    |              [Ordered pairs](#ordered-pairs)              |  22   |
|    7    |                  [Relations](#relations)                  |  26   |
|    8    |                  [Functions](#functions)                  |  30   |
|    9    |                   [Families](#families)                   |  34   |
|   10    |    [Inverses and composites](#inverses-and-composites)    |  38   |
|   11    |                    [Numbers](#numbers)                    |  42   |
|   12    |           [The peano axiom](#the-peano-axioms)            |  46   |
|   13    |                        Arithmetic                         |  50   |
|   14    |                           Order                           |  54   |
|   15    |                    The axiom of choice                    |  59   |
|   16    |                       Zorn's lemma                        |  62   |
|   17    |                       Well ordering                       |  66   |
|   18    |                   Transfinite recursion                   |  70   |
|   19    |                      Ordinal numbers                      |  74   |
|   20    |                  Sets of ordinal numbers                  |  78   |
|   21    |                    Ordinal Arithmetic                     |  81   |
|   22    |              The Schrönder-Bernstein theorem              |  86   |
|   23    |                      Countable sets                       |  90   |
|   24    |                    Cardinal arithmetic                    |  94   |
|   25    |                     Cardinal Numbers                      |  99   |
|         |                           Index                           |  102  |
FIXME:COMPLETE THE LINKS

---

## Perface

>The student who gets interested in set theort for its own sake should know, however, that there is much more to the subject than there is in this book. One of themost beautiful sources od set-theoretic wisdom is still Hausdorff's *Set Thoery*. A recent and highly readable addition to the lieterature, with an extensive and up to date bibliography, is *Axiomatic set theory* by Suppes.

To be honst, nothing is here.

## The axiom of extension

One thing that the development will not include is a definition of sets. We know it by the ordinary, human, intuitive understanding.  
Set, as they are usually conceived, have *elements or members*.  
The principal of concept of set theory, the one that in completely axiomatic studies is the principal primitice(undefined) concept, is that of *belonging*. If $x$ belongs to $A$, we shall write
$$x\epsilon A$$
*The version of the Greek letter epsilon is so often used to denote belonging. Then the most authors use$\ \varepsilon$when they need the fifth letter of the Greek alphabet.*  
One more elementart relation between the sets is *equality*. For that we write  
$$A=B$$
that fact tha A and B are not equal is expressed by  
$$ A\not ={B}.$$
Then we can get a most basic property of sets.
>**Axiom of extension** Two sets are equal if and only if they have the same element.

*With greater pertentiousness and less clarity: a set is determined by its extension.*

If $A$ and $B$ are sets and if every element of $A$ is an element of $B$.We say that A is *a subset* of $B$, or $B$ includes $A$, and we write
$$A\subset B$$  
or  
$$ B\supset A.$$  
By the way, the wording of the definition implies that $(A\subset A)$, we described it *reflexive*(NOTE, equaltiy is also reflxive). If $A$ and $B$ are both sets such that $(A\subset B)\land (A\not ={B})$, we use the word *proper*(proper subset, proper inclusion). If $A,B,C$ are sets such that $(A\subset B)\land(B\subset C),$ then $A\subset C$, which is described by saying *transitive*.  
If $A$ and $B$, are sets such that $(A\subset B)\land(B\subset A)$,then $A$ and $B$ have same elements therefore, by the Axiom of extension, $A=B$. The fact also describes that set inclusion is *antisymmetric* (Equality is always *symmetric*).  
Hence the Axiom of extension can also be described by
$$ A=B\Leftrightarrow (A\subset B)\land(B\subset A).$$

## The axiom of specification  

All the basic principles of set theory, expect only the axiom of extension, are designed to make new sets out of old ones. The first and most important of these basic principle of set manufacture says roughly speaking, that anything intelligent one can assert about the elements of a set specifies is subset namely, the subset of those elements about which the assertion is ture.
>Warning: a box that contains a hat and nothing else is not the samething as a hat.**The analogy between sets and boxes has many weak points, but sometimes it gives a helpful picture of the facts.**

All that is lacking for the precise general formulation tha underlies the example above is a definition of *sentence*. But here is only a quick and informal one. There are two basic types of sentences, namely, assertions of belonging  
$$ x\ \epsilon\  A$$  
and assertions equality,  
$$ A = B .$$
all other sentences are obtained from such atomic sentences by repeated applications of usual logical operators, subject only to minimal courtesies of grammar and unambiguity.  
For a more explicit (and longer) definition, it is nessary to append to it a list "usuall logical operators" and the rules of syntax. As following *and, or, not, if_then_, if and only if, for some, for all*.
We can use the rules of sentence construction and the logical operator, new sentence to construct.
>**Axiom of specification** To every set $A$ and to every condition $S(x)$ there corresponds a set $B$ whose elements are exactly those elements $x$ of $A$ for which $S(x)$ holds.

Where condition is just a sentence. And from Axiom of extension and Axiom of specification it is easy to find that $B$ is unique. To indicate the way $B$ is obtained from $A$ and from $S(x)$ it is customary to write  
$$B = \{x\ \epsilon:S(x)\}.$$  
To obtain an amusing and instructive application of the axiom of specification, consider, in the tole of $S(x)$, the sentence
$$not\ (x\ \epsilon\ x).$$
For convencience we write "$x\ \epsilon' \ x$".  
It foloows that, whatever the set $A$ may be, if $B = \{x\ \epsilon\ A:x\ \epsilon' \ x\}$, then, for all $y$,
$$ y\ \epsilon\ B\ if\ and\ only\ if (y\ \epsilon\ A \ and\ y\ \epsilon' \ y)\tag{$*$}$$

Can it be that $B\ \epsilon \ A$? We procedd to prove that the answer is no.  
Indeed, if $B\ \epsilon\ A$, then either $B\ \epsilon\ B$ also or else $B\ \epsilon '\ B$. With the $(*)$ we can easliy find that the two situtation are obviously impossible. Then we have $B\ \epsilon '\ A$.  
The most interesting part of the conclusion is that there always exists something (namely B), that does not belong to $A$. The set $A$ in this arugument was quite arbitrary. We have proved, in other word, that  
$$ nothing\ contains\ everything$$  
or, more spectacularly,
$$there\ is \ no \ universe.$$
>In older (pre-axiommatic) approaches to set theory, the existence of a universe was taken for granted, and the argument in the preceding paragraph was know as the *Russel paradox*.The moral is that it is impossible, especially in mathmatics, to get someting for nothing. To specify a set, it is not enhough to pronoice some magic words (which may form a sentence such that as " $x\ \epsilon' x$ "); it is nessary also to have at hand a set to whose elements the magic words apply.

## Unordered pairs

For all that has been said so far, we might have been operating in a vacuum. For the disscuion, let we now officially assume that
$$there\ exists\ a \ set.$$
Obviously there exists no elements at all. Indeed, if $A$ is a set, applying the axiom of specification with condition "$x\not ={x}$" (or, for that matter, with any other universally false sentence). The result is the set without any element at all. The axiom of extension implies that the set is unique.The usual symbol for the set is  
$$\varnothing$$  
and called the *empty set*.  
The empty ser is a subset of every set, or, in other words, $\varnothing \subset A$ for every $A$.  

The set theory develop so far is still a prettu poor thing; for all we know that there is only one set and that one is empty. Are there enough sets to ensure that every set is an element of some set (maybe 2, 3, 4 or more)? The following principle is a good beginning for this.
>**Axiom of pairing.** For any two sets there exists a set that they both belong to.  

One consequence (in favt an equivalent formulation) of the axiom of pairing is that for any two sets there exists a set thath contains both of them and nothing else. Indeed, if $a$ and $b$ are sets, and if $A$ is a set such that  $a\ \epsilon\ A$ and $b\ \epsilon\ B$, then we can apply the axiom of specification to $A$ with sentence "$x=a\ or\ x=b$". The result would be  
$$\{x\ \epsilon A :x=a\ or\ x= b\},$$  
and that set, clealy, contains just $a$ and $b$. The axiom of extension implies that there is only one set with the property. The usal symbol for that set is  
$$\{a,b\}$$  
the set is called the *pair* (or *unordered pair*).  
If $a$ is a set, we may form the unordered pair $\{a,a\}$. That unordered pair is  denoted by  
$$\{a\}$$  
and is called the *singleton* of $a$; it is uniquely characterized by the statement that it has $a$ as its only element. Thus, for instance, $\varnothing$ and $\{\empty\}$ are very different sets.

## Unions and intersection

If $A$ and $B$ are sets, it is natural to wish to unite their elements into one comperhensive set. One way of describing such a comprehensive set is to require it to all the elements that belong to at least one of the two numbers of the pair $\{A,B\}$. This formluation suggests a sweeping generalizetion of itself; surely a similar sonstruction should apply to arbitrary collections of sets and not just to pairs of them. What is wanted,  
>**Axiom of unions.** For every collection of sets there exists a set that contains all the elements that belong to at least one set of the given collection.

Here it is again: for every collection $\Theta$ there exists a set $U$ such that if $x\ \epsilon\ X$ for some $X$ in $\Theta$, then $x\ \epsilon\ U.$  
Also we can use the axion of specification to form the set  
$$ \{x\ \epsilon\ U: \ x\ \epsilon\ X\ for \ some\ X \ in\ \Theta\}.$$
Then we can change the notation and call the new set $U$ , so
$$U=\{x : \ x\ \epsilon\ X\ for \ some\ X \ in\ \Theta\}.$$
The set $U$ is called the *union* of the collection $\Theta$ of sets (note that the axiom of extension guatantees its uniqueness).

For this time we only considerate the simplest facts.
$$\bigcup\ \{X:X\ \epsilon\ \varnothing\} =\varnothing$$
and  
$$\bigcup\ \{X:X\ \epsilon\{A\}\}=A.$$

And for the case, where are only two sets, we have the notation
$$\bigcup\ \{X:X\ \epsilon\ \{A,B\}\} = A\cup B.$$
The general definition of unions implies in the special case that $x\ \epsilon\ A \cup B$ if and only if $x$ belongs to either $A$ or $B$ or both; it follows that
$$A\cup B = \{x:x\ \epsilon\ A\ or\ x\ \epsilon\ B\}.$$
Here are some easily proved facts about the unions of pairs:
$$
\begin{array}{c}{A \cup \varnothing=A} \\ {A \cup B=B \cup A \text { (commutativity), }} \\ {A \cup(B \cup C)=(A \cup B) \cup C(\text {associativity})} \\ {A \cup A=A \text { (idempotence) }} \\ {A \subset B \text { if and only if } A \cup B=B}\end{array}
$$
Every student of mathematics should prove these things for himself at least once in his life.  

And equally simpl but quite suggestive fact is that
$$
\{a\}\cup\{b\}=\{a,b\}.
$$
What this suggests is the way to generalize pairs.  Specifically, we write
$$
\{a, b, c\}=\{a\} \cup\{b\} \cup\{c\}.
$$
Without misunderstanding it can be proved that
$$
\{a, b, c\}=\{x : x=a \text { or } x=b \text { or } x=c\}
$$
we know now that for every three sets there exists a set that contains them and nothing else, which could be called (*unordered*) *triple* formed by them. THe extension of the notation and terminology thus introduved to more terms is obvious.

Ther formation of unions has many points of similarity with another theoretic operation. If $A$ and $B$ are sets, the *intersection* of $A$ and $B$ is the set $A\cap B$ defined by
$$
A\cap B = \{x\ \epsilon\ A:x\ \epsilon\ B\}
$$
The definition is symmetric in $A$ and $B$ even if it looks otherwise; we have
$$
A\cap B = \{x\ \epsilon\ B:x\ \epsilon\ A\}
$$
and, in fact, since $x\ \epsilon A\cap B$ if and only if $x$ belongs to both $A$ and $B$, it follows that  
$$
A \cap B=\{x : x \in A \text { and } x \in B\}.
$$
The basic facts about intersections, as well as their proofs, are similar to the basic facts about unions:
$$
\begin{array}{c}{A \cap \varnothing=\varnothing} \\ {A \cap B=B \cap A} \\ {A \cap(B \cap C)=(A \cap B) \cap C} \\ {A \cap A=A} \\ {A \subset B \text { if and only if } A \cap B=A}\end{array}
$$

Pairs of sets with an empty intersection occur frequently enough to justift the use of special word: if $A\cap B = \varnothing$, the sets $A$ and $B$ are called *disjoint*.  
Two useful facts about unions and intersections involve both the operations at the same time:
$$
\begin{array}{l}{A \cap(B \cup C)=(A \cap B) \cup(A \cap C)} \\ {A \cup(B \cap C)=(A \cup B) \cap(A \cup C)}\end{array}
$$
These infentities are called the *distributive laws.*

The formation of the intersection of two sets $A$ and $B$, or, we might as well say, the formation of the intersection of a pair $\{A,B\}$ of sets, is a special case of a much more general operation. The existence of the general operation of intersection depends on the fact that for each non-empty collection of sets there exists a set that contains exactly those elements that belong to every set of the given collection. In other words: for each collection $\Theta$, other than $\varnothing$, there exists a set $V$ such that $x\ \epsilon \ V$ if and only if $x\ \epsilon\ X$ for every $X$ in $\Theta$. To prove this assetion, let $A$ be any particular set in $\Theta$ (this step is justified by the fact that $\Theta\not ={\varnothing}$) and write
$$
V=\{x \in A : x \in X \text { for every } X \text { in } \Theta\}
$$
The dependence of $V$ on the arbitrary choice of $A$ is illusory; in fact
$$
V=\{x : x \in X \text { for every } X \text { in } \Theta\}
$$
The set $V$ is called the *intersection* of collection $\Theta$ of sets; the axiom of extension guarantees its uniqueness.

## Complements and powers

If $A$ and $B$ are sets, the *difference* between $A$ and $B$, more often kown as the *relative complement* of $B$ in $A$, is the set $A-B$ defined by
$$
A-B=\left\{x\ \epsilon\ A : x\  \epsilon^{\prime}\ B\right\}.
$$
In order to record the baisc facts about complementation as simply as possible, we assume nevertheless (in this section only) that all the sets to be moentioned are subsets of one and the same sets $E$ and that all complements (unless otherwise specified) are formed relative to that $E$. In such situation (and there are quite common) it is easier to remember the underlying set $E$ than to keep writing it down, and this makes it possible to simplift the notation. An often use symbol for the temporarily (as opposed to relative) complement $A$ is $A'$.  
Then we can get some basic facts about complementation in terms of this symbol:
$$
\begin{array}{c}{\left(A^{\prime}\right)^{\prime}=A} \\ {\varnothing^{\prime}=E, \quad E^{\prime}=\varnothing} \\ {A \cap A^{\prime}=\varnothing, \quad A \cup A^{\prime}=E} \\ {A \subset B \text { if and only if } B^{\prime} \subset A^{\prime}}\end{array}
$$
The most important statements about complements are the so-called *De Morgan laws*:
$$
(A \cup B)^{\prime}=A^{\prime} \cap B^{\prime}, \quad(A \cap B)^{\prime}=A^{\prime} \cup B^{\prime}
$$
This fact is somtimes referred to as the *principle of duality for sets*.

If $A$ and $B$ are sets, the *symmetric difference* (or *Boolean sum*) of $A$ and $B$ is the set $A+B$ defined by
$$
A+B=(A-B)\cup (B-A).
$$
This operation is commutative and associative.  
This may be the right time to straighten out a trivial but occasionally puzzling part of the theory of intersections. Recall, to begin with, that intersections were defined for non-empty collection only. The reason is that the same approach to the empty collection does not define a set. There is nothing to be done about this; it is just a fact of life.
If we strict out attention to subsets of a particular set $E$, as we temporarily paragraph appears to go away. The point is that in that case we can define the intersection of a collection $\Theta$ (of subsets of $E$) to be the set  
$$
\{x \in E : x \in X \text { for every } X \text { in } \Theta\}.
$$
This is nothing recolutionary; for each non-empty collection, the new definition agrees with the old one. The difference is in the way the old and the new difinitions treat the empty collection; according to the new definition $\bigcap_{x\ \epsilon\ \varnothing} X$ is equal to $E$. The difference is just a matter of language. A little reflection reveals that the "new" defintion offered for the intersection of a collection $\Theta$ of subsets of $E$ is really the same as the old definition of the intersection of the collection $\Theta\cup\{E\}$, and the latter is never empty.

We have been considering the subsets of a set $E$, do those subsets themselves constitute a set? The following principle guarantees that the answer is yes.
>**Axiom of powers.** For each set there exists a collection of sets that contains among its elements all the subsets of the given set.

In other words, if $E$ is a set, then there exists a set (collection)  $\mathcal{P}$ such that if $X\subset E$, then $X\ \epsilon\ \mathcal{P}$.  
The set $\mathcal{P}$ described above may be larger than wanted; it may contain elements other than the subsets of $E$. This is easy to remedy; just apply the axiom of specification to form the set $\{X\ \epsilon\ \mathcal{P}:X\subset E\}$. Since, for every $X$, a necessary and sufficient condition that $X$ belong to this set is that $X$ be a subset of $E$, it follows that if we change notation and call this set $\mathcal{P}$ again, then
$$
\mathcal{P} = \{X:X\subset E\}.
$$
The set $\mathcal{P}$ is called the *power set* of $E$; the axiom of extension guarantees its uniqueness. The dependence of $\mathcal{P}$ on $E$ is denoted by writing $\mathcal{P}(E)$ instead of just $\mathcal{P}$.  
Beacause the set $\mathcal{P}(E)$ is very big in comparsion with $E$, it is not easy to give example. If $E = \varnothing$, the situtaion is clear enough; the set $\mathcal{P}(\varnothing)$ is the singeleton $\{\varnothing\}$. The power sets of singletons and pairs are also easily describable; we have  
$$
\mathcal{P}(\{a\}) = \{\varnothing,\{a\}\}.
$$
and  
$$
\mathcal{P}(\{a,b\}) = \{\varnothing,\{a\},\{b\},\{a,b\}\}.
$$
The power set of a triple has 8 elements. The reader can probably guess (and is hereby challenged to prove) the generalization that includes all these statements: the power set of a finite set with, say $e$ elements has $2^n$ elements. The occurrence of $n$ as an exponent (the $n-th$ power of 2) has something to do with the reason why a power set bears its name.  

If $\Theta$ is a collection of subsets of a set $E$ (that is, $\Theta$ is s subcollection of $\mathcal{P}(E)$), then write
$$
\mathfrak{D} = \{X\ \epsilon\ \mathcal{P}(E):X'\ \epsilon\ \Theta\}.
$$  
To be certain that the condition used in the defintion of $\mathfrak{D}$ is a sentence in the precise technical sense, it must be rewritten in something like the form  
$$
\text { for some } Y\left[Y \epsilon \ \Theta \text { and for all } x\left(x \ \epsilon\  X \text { if and only if }\left(x \ \epsilon\  E \text { and } x\ \epsilon^{\prime}\ Y\right)\right)\right]
$$
Similar comments often apply when we wish to use defined abbreviations
instead of logical and set-theoretic primitives only. The translation rarely
requires any ingenuity and we shall usually omit it. It is eustomary to
denote the union and the intersection of the collection $\mathfrak{D}$ by the symbols
$$
\bigcup_{X\ \epsilon\ \Theta}X'\ \text{and} \ \bigcap_{X\ \epsilon \ \Theta}X'
$$
In this notation the general forms of the *De Morgan laws* become
$$
\left(\bigcup_{X\ \epsilon\ \Theta}X\right)' = \bigcap_{X\ \epsilon\ \Theta}X'
$$
and
$$
\left(\bigcap_{X\ \epsilon\ \Theta}X\right)' = \bigcup_{X\ \epsilon\ \Theta}X'
$$

## Ordered pairs

What dose it mean to arrange the element of a set $A$ in some ordered?  
The moral is this: we may not know precisely what it means to order the elements of a set $A$. But with each order we can associate a set $\Theta$. If $A=\{a,b\}$ and if, in the desired order, $a$ comes first, then $\Theta=\{\{a\},\{a,b\}\}$.
The *ordered pair* of $a$ and $b$, with *first coordinate* $a$ and *second coordinate* $b$, is the set $(a,b)$ defined by  
$$
(a,b)=\{\{a\},\{a,b\}\}.
$$
However convincing the motivation of this definition may be, we must still prove that the result has the main property that an ordered pair must have to deserve its name. We must be sure that if $(a,b)$ and $(x,y)$ are ordered pairs and if $(a,b)=(x,y)$, then $a=b$ and $b=y$, which is not difficult to find.  

If $A$ and $B$ are sets, does there exist a set that contains all the ordered pair $(a,b)$ with $a$ in $A$ and $b$ in $B$? The answer is yes. All the ordered pair is the element of the set $\mathcal{P}(\mathcal{P}(A\cup B))$; in other words $(a,b)\ \epsilon\ \mathcal{P}(\mathcal{P}(A\cup B))$ whenever $a\ \epsilon A,\ b\ \epsilon B$.  
Once that is konwn, it is a routine matter to apply the axiom of specification and the axiom of extension to produce the unique set $A\times B$ that consists exactly of the ordered pairs $(a,b)$ with $a$ in $A$ and $b$ in $B$. This set is called the *Cartesian product* of $A$ and $B$; it is characterized the fact that  
$$
A\times B=\{x:x=(a,b)\ for\ some\ a\ in\ A\ and\ for\ some\ b\ in\ B\}.
$$
The Cartesian product of two sets is a set of ordered pairs (that is, a set each of whose elements is an ordered pair), and the same is true of every subset of a Cartesian product. It is of technical imprtance to know that we can go in the converse direction also: every set of ordered pairs is a subset of the Cartesian product of two sets.  
In other word: if $R$ is a set such that every elements of $R$ is an ordered pair, then there exists two sets $A$ and $B$ such that $R\subset A\times B$. Suppose indeed that $x\ \epsilon\ R$, so that $x=\{\{a\},\{a,b\}\}$ for some $a$ and for some $b$. It is easly to find that for all $a$ and $b$, they both belong to $\bigcup \bigcup R$. Then just apply axiom of specification to prudce the sets
$$
A=\{a:for\ some\ b\ ((a,b)\ \epsilon\ R)\}
$$
and  
$$
B=\{b:for\ some\ a\ ((a,b)\ \epsilon\ R)\}
$$
These sets are called the projections of $R$ onto the first and second coordinates respectively.  
However important set theory may be now, when it began some scholars considered it a diesease from which, it was to be hope, mathematics would soon recover. For this reason may set-theoretic considerarions were called pathological, and the word lives on in mathematical usage; it often refers to something the speaker does not like. The explicit definition of an ordered pair $((a,b)=\{\{a\},\{a,b\}\}).$ is frequently relegated to pathological set theory. For the benefit of those who think that in this case the name is deserved, we note that the definition has served its purpose by now and will never be used again. We need to know that ordered pairs are determined by and uniquely determine their first and second coordinates, that Cartesian products can be formed, and that every set of ordered pairs is a subset of some Cartesian product; which particular approach is used to achieve these ends is immaterial.

## Relations

Using ordered pairs, we can formulate the mathematical thoery of relation in set-theoretic language. By a relation we mean here something like marriage. More explicitly, what we shall call a relation is sometimes called a *binary* relation.  
We may not know what a relation is, but we do know what a set is, and the preceding considerations establish a close connection between relations and sets.  The simplest thing to do is to define a relation to be corresponding set. This is what we do; we hereby define a *relation* as a set of ordered pairs.  
Explicitly: a set $R$ is a relation if each element of $R$ is an ordered pair; this means, of course, that if $z\ \epsilon\ R$, then there exist $x$ and $y$ so that $z=(x,y)$. If $R$ is a relation, it is sometimes convenient to express the fact that $(x,y)\ \epsilon\ R$ by writing  
$$
x\ R\ y
$$
and saying, as in everyday language, that $x$ stands in the relation $R$ to $y$.  
In the theory of relations these sets are known as the *domain* and the *range* of $R$ (abbrevited $\mathrm{dom}\ R$ and $\mathrm{ram}\ R$); we recall that they are defined by
$$
\mathrm{dom}\ R = \{x:for\ some\ y\ (x\ R\ y)\}.
$$
and
$$
\mathrm{ran}\ R = \{y:for\ some\ x\ (x\ R\ y)\}.
$$
A relation in a set is an *equivalence relation* if it is reflexive, symmetric, and transitive.  
There is an intimate connection between eq
TODO: 28页,不是我说,真看不懂 暂时不管 看下一张去了

## Functions

If $X$ and $Y$ are sets, a *function* from (or *on*) $X$ *to* (or *into*) $Y$ is a relation such that dom $f=X$ and such that for each $x$ in $X$ there is a unique elements $y$ in $Y$ with $(x,y)\ \epsilon\ f$. The uniqueness condition can be formulated explicitly as follows: if $((x,y)\ \epsilon\ f)\land((x,z)\ \epsilon\ f)\Rightarrow (y=z).$  
For each $x$ in $X$, the unique $y$ in $Y$ such that $(x,y)\ \epsilon\ f$ is denoted by $f(x)$.  
*Attention: in other book, this concept usually is called with "mapping".*  
The symbol  
$$
f:X\to Y
$$
is sometimes used as an abbreviation for "$f$ is a function from $X$ to $Y$".The set of all functions from $X$ to $Y$ is a subset of the power set $\mathcal{P}(X\times Y)$; it will be denoted by $Y^X$.  
For relations in general, and hence for functions in particular, we have defined the concepts of domain and range. The domain of a funtion $f$ from $X$ into $Y$ is, by definition, equal to $X$, while its range need not be equal to $Y$. If the range of $f$ is equal to $Y$, we say that $f$ maps $X\ onto\ Y$. If $A$ is a subset of $X$, we may want to consider the set of all those elemengts $y$ of $Y$ which there exists an $x$ in the subset $A$ such that $f(x)=y$. This subset of $Y$ is called the *image* of $A$ under $f$ and is frequently denoted by $f(A)$.  
If $X$ is a subser of a set $Y$, the funcion $f$ defined by $f(x)=x$ for each $x$ in $X$ is called the $inclusion map$ of $X\ into\ Y$. The inclusion map of $X$ into $X$ is called the *indentity map* on $X$.  
A function that always maps distinct elements onto distinct elements is called *one-to-one* (usually a *one-to-one correspondence*).  

## Families

There are occasions when the range of a function is deemed to be more important than the function itself.  
Suppose, for instance, that $x$ is a function from a set $I$ to a set $X$. An element of the domain $I$ is called *index*, $I$ is called the *index set*, the range of the function is called an *indexed set*, the function it self is called a *family*, and the calue of the function $x$ at an index $i$, called a *term* of the family, is denoted by $x_i$. Thus, for instance, the phrase "a family $\{A_i\}$ of subsets of $X$" is usually understood to refer to a function $A$, from some set $I$ of indices, into $\mathcal{P}(X)$.  
If $\{A_i\}$ is a family of subsets of $X$, the union of the range of the family is called the union of the family $\{A_i\}$, the standard notation for it is
$$
\bigcup_{i \in I} A_{i} \text { or } \bigcup_{i} A_{i}
$$
The algebraic laws satisfied by the operation of union for pairs can be generalized to arbitrary unions suppose, for instance, that $\{I_j\}$ is a family of sets with domain $J$, say; write $K=\bigcup_hI_j$, and let $\{A_k\}$ be a family of sets with domain $K$. It is then not difficult to prove that  
$$
\bigcup_{k\ \epsilon \ K} A_k=\bigcup_{j\ \epsilon\ J}(\bigcup_{i\ \epsilon\ I_j}A_i).
$$
An empty union makes sense (and is empty), but an empty intersection does not make sense. Thus, for instance, if $\{A_i\}$ is a non-empty family of sets, the intersection of the range of the family is called the intersection of the family $\{A_i\}$, or the intersection of the sets $\{A_i\}$; the standatd notation for it is  
$$
\bigcap_{i\ \epsilon \ I} A_i\ \ \ \text{or}\ \ \ \bigcap_i A_i,
$$
according as it is or is not important to emphasize the index set $I$. (By a "non-empty family" we mean a family whose domain $I$ is not empty.)  
It is normal and not of much interest with algebraic indentities, that we can find, if $\{A_i\}$ is a family of subsets of $X$ and $B\subset X$,then
$$
B\cap\bigcup_iA_i=\bigcup_i(B\cap A_i)
$$
and  
$$
B\cup\bigcap_iA_i=\bigcap_i(B\cup A_i).
$$

Explanation of notation: a symbol such as $\bigcup_{i,j}$ is an abbreviation for $\bigcup_{(i,j)\ \epsilon\ I\times J}$  
TODO: 集族的笛卡尔积后面一段我又不知道他在说什么了.

## Inverses and composites

A correspondence between the elements of $X$ and the elements of $Y$ does always induce a well-behaved correspondence between the subsets of $X$ and the subsets of $Y$, not forward, by the formation of images, but backward, by the the formation of inverse images. Given a function $f$ from $X$ to $Y$, let $f^{-1}$, the inverse of $f$, be the function from $\mathcal{P}(Y)$ to $\mathcal{P}(X)$ such that $B\subset Y$, then
$$
f^{-1}(B)=\{x\ \epsilon X:f(x)\ \epsilon\ B\}.
$$
TODO: SECTION  10 P38  

## Numbers

*How much is two? More generall, are wo to define numbers?*  
First of all, we can consider a set $X$ and let us form the collection $P$ of all unrodered unumber pairs $\{a,b\}$. In some way, we can find it so tempting to define twoness as the common property of all the sets in the collection $P$. Obviously, it is mathmatical nosense. We should have a proposed definition without using vague expression.  
And now the trouble is that our present modified proposal depends on $P$. and hence ultimately on $X$. At best the proposal defines twoness for subsets of X.  

There are two way out.  
ONE is to abandon the restricition to a particulat set and to consider instead all possible unordered pairs $\{a,b\}$. This can be done but we do not do this here.
Before we show the way to define the twoness, it would be helpful if we can know hoe would a mathmatician define a meter -- the procedure analogous, which have two steps. First is to select an object whose length can be considered as one meter. Then we form the set of all objects in the universe that are of same length, and define the set as the set so formed. Then we can comment that to determine whether two object, and does not depend on having a precise definition of length.  

Motivated by the consideration, and we have earlier defined 2 as some particualt set with exactly two elements.  
How was that standrad set selected? How should other such standard sets for otheer numbers be selected? There is no compelling mathmatical reason for preferring one answer to this question to another; the whole thing is largely a matter of taste. Everything is just a selection.  
>**But actually the selection should presumably be guided by considerations of simplicity and economy.**  

z.B. to motivatethe particular selection that is usually made, suppose that a number, say 7, has alredy been defined as a set (with seven elements). How, in this case, should we define 8? Where, in other words, can we find a set consisting of exactly eight elements? Can we use 7 to adjoin? A reasonable answer to define 8 is the set consisting of the seven elements of 7, together with 7. Note that according to this proposal each number will be equal to the set of its own predecessors.

Exactly we can define for every set $x$ its *successor* $x^+$ to be the set obtained by adjoining $x$ to the elements of x; d.h.
$$
x^+=x\cup\{x\}.
$$
(frequent denoted by $x'$).

Now we are ready to define the natural numbers. In defining 0 to be a set with zero elements (with nothing). We have no chioce, that we must werite
$$
0=\varnothing
$$
If every natural number is to be equal to the set of its predecessors, we have no chioce in defining 1, or 2, or 3, we must write  
$$
\begin{aligned}
    &1=0^+(=\{0\}),\\
    &2=1^+(=\{0,1\}),\\
    &3=2^+(=\{0,1,2\}),\\
\end{aligned}
$$
etc.  
From what we has been said so far it does not follow that the construction of successors can be carried out ad infinitium within ont and the same set. What we need is a new set-theoretic principle.
>**Axiom of infinity** There exists a set containing 0 and containing the successor of each of its elements.

Altough we have not yet given a precise definition of infinity but it seems reasonable that sets such as the ones that the axiom of infinity describes deserve to be called infinite.  
In language the axiom of infinity simply says that there exists a successor set $A$. Since the intersection of every (non-empty) family of successor sets is a successor sets itself, the intersection of all the successor sets included in $A$ is a successor set $\omega$. The minimality property so established uniquely characterizes $\omega$; the axiom of extension guarantees that there can be only one successor set that is included in every other successor set. A *natural number* is,by definition, an element of the minimal successor set $\omega$. This definition of natural of natural numbers is the rigorous counterpart of the intuitive description according to which they consisit of 1, 2, 3, "and so on". TODO: MAYBE SOMETHING ABOUT THE MISS UNDERSTANDING>  
*This slight feeling of discomfort that reader may experience in connection with the definition of natural number is queite common and in most case temporary. The trouble is that, as once before, the object defined has some irrelevant structure, which seems to get in the way. We want to be told that the successor of 7 is 8, but to be told 7 is a subset of 8 is very disturbing. We shall make use of this superstructure of natural numbers jsut long enough to derive their most important natural properties; after that superstructure may safely be forgotten.*  

## The peano axioms

Now there is a minor digression.whose purpose of the digression is to make fleeting contact with the arithmetic theory of natural numbers.  
The most important thing we know about the set $\omega$ of all natural numbers is that it is the unique successor set that is a subset of every successor set. To say that $\omega$ is a suvvessor set means that  
$$
0\ \epsilon\ \omega \tag{I}
$$
(where, of course, $0\ =\ \varnothing$), and that
$$
if\ n\ \epsilon\ \omega, \ then\ n^+\ \epsilon\ \omega \tag{II}
$$
and
$$
if\ S\ \subset \omega,\ if\ 0\ \epsilon \ S,\ and\ if\ n^+\ \epsilon \ S \ whenever\ n\ \epsilon\ S,\ then\ S=\omega \tag{III}
$$
Proterty (III) is known as the priciple of mathmatical induction.  
And we shall now add to this list of properties of $\omega$ two others:  
$$
n^+\not ={0}\ for \ all\ n\ in\ \omega\tag{IV}
$$
and
$$
{ if }\  n \ and\  m \ { are\ in\ } \omega, \ { and\ if\ } n^{+}=m^{+}, \  {then }\ n=m\tag{V}
$$
The proof of (IV) is quite trival; since $n^+$ always contains $n$, and since 0 is empty, it is clear that $n^+$ is differnt from 0.  
FIXME: there are two statment from which i cant find any PUNKT. S.47  
We are now ready to prove (V). Suppose indeed that $n$ and $m$ are natrual numbers and that $n^+=m^+$. Since $n\ \epsilon \ n^+$, it follows thath $n\ \epsilon\ m^+$, and hence that either $n\ \epsilon\ m$ or $n=m$. If $n\not ={m}$, then we must have $n\ \epsilon\ m$ and $m\ \epsilon\ n$.Since, by(ii), $n$ is transitive, it follows that $n\ \epsilon\ n$. Since, however, $n\subset n,$ this contradicts(i), and the proof is complete.  
The assertion (I)-(V) are known as the **Peano axiom**; they used to be considered as the fountainhead of all mathematical knowledge. With them it is possible to define integers, rational numbers, real numbers, and complex numbers, and to derive their usual arithmetic and analytic properties.  
Induction is ofren used not only to prove things but also to define things. For a induction the principle of mathematical indution does indeed prove, easily, that there can be at most one function satisfying all the stated conditions, but is does not establish the existence of such a function, then what is need is the following result.
>**Recursion theorem.** If $a$ is an element of a set $X$, and if $f$ is a funtion from $X$ into $X$, then there exists a function $u$ from $\omega$ into $X$ such that $u(0) = a$ and such that $u(n^+)=f(u(n))$ for all $n$ in $\omega$.  

TODO: HERE SHOULD BE A PROOF.  
An application of the recursion theorem is  called definition by induction.

## Arithemetic

The introduction of addition for natural numbers is a typical example of definition by induction.  
FIXME: I DONT WANT TO USE THE PROOF HERE, MAYBE THE PROOF IN BOOK BY TAO IS A BETTER CHOICE.  

## Order

The theory of order plays an important role. The only thing to remember is that the primary motivation comes from the familiat properties of "less than or equal to" and not "less than". There is no profound reason.  
A relation $R$ in a set $X$ is called *antisymmetric*, if for every $x$ and $y$ in $X$ the simultaneous validity of $x\ R\ y$ and $y\ R\ x$ implies that $x=y$. A *partial order* (or sometimes simply an *order*) in a set $X$ is a reflexive, antisymmetric, and transitive relation in $X$. Thus a partial order in $X$ may be defined as a relation $\leqq$ in $X$ such that, for all $x, y$ and $z$ in $X$, we have (i) $x\leqq x$, (ii) if $x\leqq y$ and $y\leqq x$, then $x=y$, and (iii) if $x\leqq y$ and $y\leqq z$, then $x\leqq z$. If for every $x$ and $y$ in $X$ either $x\leqq y$ or $y\leqq x$, then $\leqq$ is called *total* order. A totally ordered set is frequent ly called a *chain.*  
A *partially ordered* set is a set together with a partial order in it. A precise formulation of this "togertherness" goes as follows: a partially ordered setis an ordered pair $(X,\leqq)$, whew $X$ is a set and $\leqq$ is a partial order in $X$. Follwoing custom, we shal often sat something like "let $X$ be a partially ordered sets," when what we really mean is thing like "let $X$ be the domain of a partial order."  
We also have the note $<$. And the connection between $\leqq$ and $<$ can be generalized to arbitrart relations. z.B. for given relation $\mathcal{R}$ in a set $X$, we can define a relation $\mathcal{S}$ in $X$ by writing $x\ \mathcal{S}\ y$ in case $x\ \mathcal{R} \ y$ but $x\not ={y}$, and vice versa. To have an abbreviated way of refering to the passage from $\mathcal{R}  \text{to}\ \mathcal{S}$ and back, we shall say that $\mathcal{S}$ is the *strict* relation corresponding to $\mathcal{R}$, and $\mathcal{R}$ is the *weak* relation coresponding to $\mathcal{S}$.  
If $X$ is a partially ordered set, and if $a\ \epsilon \ X$, the set $\{x\ \epsilon\ X:x<a\}$ is the *initial segment* determined by $a$; we shall denote it by $s(a)$, and the set $\{x\ \epsilon\ X:x\leqq a\}$ is the *weak segment* determined by $a$, which denoted by $\bar{s}(a)$.  
Then we can have the concept *least (smallest, first)*, *greatest (larges, last)*. By the way it is of great importance to distinguish the least elements and minimal ones because of the difference definition of order.  
We can also define that the *lower bound*, *upper bound*, *greatest lower bound* and *least upper bound* with $\inf E,\ \sup E$, where $E$ is a set.

## The axiom of choice

For the deepest result oredered sets we need a new set-theoretic tool; we interrupt the development of the theory of order long enhough pich up the tool.  
It is not difficult to find that $X\times Y$ is not empty, where $X$ and $Y$ are nonempty sets. The preceding remarks consitute the case $n =1$ and $n =2$ of the following assertion: if $\{X_i\}$ is a finite sequence of sets, for $i$ in $n$, say, then a necessary and sufficient condition that their Cartesian product be empty is that at least one of them be empty. The assertion is very easy to prove by induction on $n$.  
But the generalization to infinite damilies of the non-trivial part of the assertion in the preceding paragraph (necessity) is the following inmprtant priciple of set theory.
>**Axiom of choice** The Cartesian product of a non-empty family of non-empty sets is non-empty.  

In other words: if $\{X_i\}$ is a family of non-empty sets indexed by a non-empty set $I$, then there exists a family $\{x_i\},i\ \epsilon \ I,$ such that $x_i\ \epsilon \ X_i$ for each $i$ in $I$.  
Suppose that $\Theta$ is a non-empty collection of non-empty sets. We can convert $\Theta$ into an indexed set, just by using the collection $\Theta$ it self. And the axiom of choice then says that the Cartesian product of the sets of $\Theta$ has at least one element. Conclusion: there exists a function $f$ with domain $\Theta$ such that if $A\ \epsilon\ \Theta$, then $f(A)\ \epsilon\ A$. In intuitive language the funtion $f$ can be described as a simultaneous choice of an element from each of many sets; this is the reason for the name of the axiom.  
TODO:P60 DI 2 DUAN

As an illustration of the use of the axiom of choice, consider the assertion that if a set is infinite then it has a subset equivalent to $\omega$.  
An informal augument might run as follows. If $X$ is infinite, then, in particulat, it is not empty (that is, it is not equicalent to 0); henve it has an element, say $x_0$. Since $X$ is not equivalent to 1, the set $X-\{x_0\}$ is not empty; hence it has an element, say $x_1$. Repeat this qrgument ad infinitum; the nex step, for instance, is to say that $X-\{x_0,x_1\}$ is not empty, and, therefore, it has an element, say $x_2$. The result is an infinite sequence $\{x_n\}$ of distinct elements of $X$; Q.E.D.  
This sketch of a proof at least has the virtue of being honest about the most important idea behind it; the act of choosing an element from a non-empty set was repeated infinitely often. For our purposes it is advisable to take a longer look:  


.
