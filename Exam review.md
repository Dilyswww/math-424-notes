> This is the collection of important definitions, theorems, corollaries,  and proof techniques introduced in the MATH 424 class used for exam review. Proofs of statements will not be included.

# Midterm 1
## Real number system

An ordered field is a field $F$ with a subset $P \subseteq F$ (positive)  s.t.
1) $0$ $\notin$ $P$. 
2) For any $a,b \in P$, $a+b$, $a \cdot b$ $\in P$. 
3) For any $a \in F$, $a \neq 0$, then either $a \in P$ or $-a \in P$. i.e, $F/ \{0\} = P \cup -P$, where $-P \coloneqq \{-x:\: x \in P\}$
Equivalently, these properties holds:
1) $a \leq b$ $\iff$ $-b \leq -a$
2) $\forall a$, $a^2 \geq 0$ * -> $\mathbb{C}$ is unordered*
3) If $a \in P$.  $b\in -P$, then $ab \in -P$

Lemma 
$\forall x \in \mathbb{R}$, $\exists \: n \in \mathbb{R}$ s.t. $x < n$.

Corollary  
$\forall x \in \mathbb{R}$, $\exists \: n \in \mathbb{R}$ s.t. $\frac{1}{n} < \varepsilon$.

Consequence
$\forall x \in \mathbb{R}, x \geq 0$ s.t. $x < \varepsilon, \forall \varepsilon > 0$, then $x = 0$.

Theorem ($\mathbb{Q}$ is dense in $\mathbb{R}$) 
$\forall x \in \mathbb{R}, \forall \varepsilon > 0, \exists\:r \in \mathbb{Q}$ s.t. $|x - r| < \varepsilon$. 

## Metric space

Def (Open ball)
Let $(E,d)$ be a metric space, an **open ball** centered at $x \in E$ of radius $r>0$ is the set $B_r(x) \equiv B(x,r) := \{y\in E| d(x,y) < r\}$. 

Def (Closed ball)
Similarly, a **closed ball** centered at $x \in E$ of radius $r>0$ is the set $\overline{B_r(x)} \equiv \overline{B(x,r)} := \{y\in E| d(x,y) \leq r\}$. 

Def (Open set)
A subset $U$ of a metric space $(E,d)$ is open if $\forall x \in U, \exists r > 0$ s.t. $B_r(x) \subseteq U$.

Def (Closed set)
A subset $C$ of a metric space $(E,d)$ is closed if the complement of $C$, $C^c = E\setminus C := \{x\in E| x \notin C\}$ is open.

$E, \varnothing$ are both open and closed

Given $(E,d)$ metric space, 1)$\forall$ collection $\{U_i\}_{i \in I}$ of open sets in $E$, $\cup_{i \in I}U_i$ is open. 2) $\forall \:k$, $\forall$ open sets $U_1,...,U_k, \:U_1 \cup ...\cup U_k$ is open, i.e., finite intersections of open sets are open. 3) Open balls are open.

Def (Convergent)
Let $(E,d)$ be metric space and $(S_n)$ a sequence. We say $S_n$ converges to $L \in E$ if $\forall \varepsilon > 0$, $\exists N\in \mathbb{N}$ s.t. for all $n > N$, $d(s_n,L) < \varepsilon\equiv s_n \in B_{\varepsilon}(L)$.
We write $S_n \rightarrow L$ or $\lim_{n \rightarrow \infty} S_n = L$ and we say $S_n$ is convergent, $L$ is a limit of $S_n$.

Lemma 
Assume a sequence $\{S_n\}$ in $(E,d)$ converges to $L \iff \forall$ open set $U \subseteq E$ with $L \in U$, $\exists N \in \mathbb{N}$ s.t. for all $n > N$, $s_n \in U$.

Lemma
Convergent sequences are bounded.

Proposition (Limit is unique)
Let $S_n$ be a sequence in the metric space $(E,d)$. If $S_n \rightarrow L_1$ and $S_n \rightarrow L_2$, then $L_1 = L_2$.

Proposition
Suppose $S_n \rightarrow L$, ${S_{nk}}$ is a subsequence of $S_n$. Then $S_{nk} \rightarrow L$.

Lemma
Suppose $C$ is closed in $(E,d)$, $\{S_n\}$ a sequence in $C$ ($\forall n, s_n \in C$) and $s_n \rightarrow L$. Then $L \in C$. Conversely, if $\forall$ convergent $\{s_n\}$ in $C$, lim$s_n \in C$, then $C$ is closed.

Def (Inferior, Closure, Boundary)
Let $(E,d)$ be a metric space, $S \subseteq E$ a subset, then:
Interior$(S) \equiv S^{\circ} = \cup_{O\subseteq S} O$, where $O$ is an open set, is the largest open set contained in $S$.
Closure$(S) \equiv \overline{S} \equiv \cap_{S\subseteq C} C$, where $C$ is a closed set, is the smallest closed set containing $S$.
Boundary$(S) \equiv \overline{S}\setminus C^{\circ} = \delta S$.

Theorem
Let $(E,d)$ be a metric space, $S\subseteq E$, then
1) $S^{\circ} = \{x \in S | \exists \varepsilon > 0,\:s.t.\:B_{\varepsilon}(x) \subseteq S\}$, $\varepsilon > 0$
2) $E\setminus \overline{S} = (E\setminus S)^{\circ}$
3) $\overline{S} = \{x\in E| \exists\:a\:sequence \{s_n\}\subseteq S\:with\:s_n\rightarrow x\}$
4) $\delta S = (E\setminus S^{\circ}) \cap (E\setminus(E\setminus S^{\circ}))$
5) $E = S^{\circ}\sqcup \delta S \sqcup (E\setminus S)^{\circ}$. $E$ is the disjoint union of the interior of $S$, boundary of $S$, and exterior of $S$.

Def (increasing/ decreasing sequence)
A sequence $\{a_n\} \subseteq \mathbb{R}$ is increasing if $a_1 \leq a_2 \leq \cdots \leq a_n \cdots$. Similarly, $\{a_n\} \subseteq \mathbb{R}$ is decreasing if $a_1 \geq a_2 \geq \cdots \geq a_n \cdots$. Note that the constant sequence is both increasing and decreasing.

Def (monotone sequence)
A sequence is monotone if it is increasing or decreasing.

Theorem (Bounded monotone sequences converges)
Any bounded monotone sequences in $\mathbb{R}$ converges.

Theorem 
A monotone sequence in $\mathbb{R}$ either converges or diverges to $\pm\infty$

Fact
Suppose $\{S_n\},\{T_n\}$ are two bounded sequences, $T \subseteq S$. then $\sup T \leq \sup S,\: \inf T \geq \inf S$.

Let $\{S_n\}$ be a sequence bounded above. Then $\forall N$, $V_N:=\sup\{S_n|n\geq N\}$. We define
$$\lim \sup S_n := \lim V_n = \lim_{n\rightarrow \infty} \sup\{S_n|n\geq N\}$$
which may be infinity or a number.
Similarly, if the sequence is bounded below, we define
$$\lim \inf S_n := \lim V_n = \lim_{n\rightarrow \infty} \inf\{S_n|n\geq N\}$$ 
Theorem
1) If $\{S_n\} \rightarrow \pm \infty$ or converges, then $\lim \inf S_n = \lim S_n = \lim \sup S_n$.
2) If $\lim \inf S_n = \lim \sup S_n$ (could be $\pm \infty$), then $\lim \inf S_n = \lim S_n = \lim \sup S_n$.

Def (Cauchy Sequences)
A sequence $\{S_n\}$ in a metric space $(E,d)$ is Cauchy if $\forall \varepsilon > 0, \exists N$ s.t. $\forall n,m > N, d(s_n,s_m) < \varepsilon$

Lemma
Any convergent sequence $\{S_n\}$ in $(E,d)$ is Cauchy.

Def (Completeness) 
A metric space $(E,d)$ is complete if every Cauchy sequences converges.

Lemma
Let $(E,d)$ be a metric space and $\{S_n\}$ a Cauchy sequence in $E$. Then $\{S_n\}_{n \in \mathbb{N}}$ is bounded.
 
Lemma
Suppose $\{S_n\}$ is a Cauchy sequence and $\{S_{n_k}\}$ is a convergent subsequence with $S_{n_k} \rightarrow L$. Then $S_n \rightarrow L$ as well.

Lemma
Any closed subsets $C$ of a complete metric space $(E,d)$ is complete.

some useful metric in $\mathbb{R}^n$: 
$d_2(x,y) := \sqrt{\sum_i (x_i - y_i)^2}$
$d_1(x,y) := \sum_i |x_i-y_i|$
$d_{\infty}(x,y) = \max_{1\leq i \leq n}|x_i-y_i|$

Theorem (Bolzano–Weierstrass in $\mathbb{R}$)
Let $\{s_n\}$ be a bounded sequence in $\mathbb{R}$, $L = \lim\sup s_n$. Then there is a subsequence $\{s_{n_k}\}$ s.t. $s_{n_k} \rightarrow L$.

Theorem (Bolzano–Weierstrass in $\mathbb{R}^n$)
Let $\{s_n\}$ be a bounded sequence in $\mathbb{R}^n$, then $\{s_n\}$ has a convergent subsequence.

Def (Equivalent norm and metric)
Two norms $\lVert \cdot \rVert, \lVert \cdot \rVert'$ are equivalent on $\mathbb{R}^n$ if $\exists c_1,c_2 > 0$ s.t. $\forall x\in\mathbb{R}^n$
$c_1 \lVert x \rVert \leq \lVert x \rVert' \leq c_2\lVert x \rVert$
two metrics $d,d'$ are equivalent on a set $E$ if $\exists c_1,c_2 > 0$ s.t. $\forall x,y \in E$
$c_1d(x,y)\leq d'(x,y)\leq c_2d(x,y)$

Theorem
$\frac{1}{n}\lVert x \rVert_1 \leq \lVert x \rVert_{\infty} \leq \lVert x \rVert_2 \leq \lVert x \rVert_1$ for all $x \in \mathbb{R}^n$

Def (Topology)
A topology $\mathcal{T}$ on a set $X$ is a collection of subset of $X$ (so $\mathcal{T} \subseteq \mathbb{P}(X)$,where $\mathbb{P}(X)$ is the power set) whose elements are called "open sets" s.t.
1) $\varnothing, X \in \mathcal{T}$
2) If $O,O'\in \mathcal{T}$, then  $O \cap O' \in \mathcal{T}$. 
3) $\forall\{O_{\alpha}\}_{\alpha \in A} \subseteq \mathcal{T}$, then $\cup_{\alpha \in A}O_{\alpha}\in\mathcal{T}$.

Def (Topological space)
A topological space is a pair $(X,\mathcal{T})$, where $\mathcal{T}$ is a topology on a set $X$.

Lemma 
Let $d, d'$ be two equivalent metric on a set $E$, then $\mathcal{T}_d = \mathcal{T}_{d'}$, i.e., they give rise to the same topology.

Def (Convergent sequence in a topological space)
Let $(X,\mathcal{T})$ be a topological space, $\{S_n\}\subseteq X$ a sequence. Then $S_n \rightarrow L\in X$ if $\forall$ open set $U \subseteq X$ with $L \in U$, $\exists N$ s.t. $n > N \implies S_n\in U$.

Corollary 
Let $E$ be a set, $d,d'$ two equivalent metric, then $S_n \rightarrow L\in E$ with respect to $d$ $\iff S_n \rightarrow L \in E$ with respect to $d'$. 

Def (Open cover)
Let $(X,\mathcal{T})$ be a topological space, $K \subseteq X$ a subset, then an open cover of $K$ is a collection of open sets $\{O_{\alpha}\}_{\alpha \in A} \subseteq \mathbb{P}(X)$ s.t. $K \subseteq \cup_{\alpha \in A}O_{\alpha}$. 

Def (Compactness)
A subset $K$ of a topological space $(X,\mathcal{T})$ is compact if for every open cover $\{U_{\alpha}\}_{\alpha \in A}$ of $K$, $\exists n,\alpha_1,...\alpha_n \in A$ s.t. $K \subseteq U_{\alpha_1} \cup \cdots \cup U_{\alpha_n}$

Any finite set $\{x_1,...,x_n\}$ is compact

Lemma 
Let $(X,\mathcal{T})$ be a topological space, $K \subseteq X$ compact, $C \subseteq X$ closed. Then $K \cap C$ is compact.

Theorem 
Let $(E,d)$ be a metric space. If $K \subseteq E$ is compact, then $K$ is closed and bounded.

Remark. In $(\mathbb{R}^n,d_2)$ a metric space is compact $\iff$ it is closed and bounded
Remark. In general, compact sets need not be closed.

Theorem
Let $X$ be a topological space, $K_1 \supseteq K_2 \supseteq \cdots \supseteq K_n \supseteq \cdots$ a sequence of compact sets, then $K = \cap_{n=1}^{\infty}K_n \neq \varnothing$ (and compact: since the intersection sets in $K_1$)

Theorem
Let $X$ be a topological space, $K_1 \supseteq K_2 \supseteq \cdots \supseteq K_n\supseteq\cdots$ sequences of nonempty nested closed compact sets. Then $\cap_{i=1}^{\infty}K_i \neq \varnothing$.

Def (Sequentially compact)
A subset $K$ of a topological space is sequentially compact if every sequence in $K$ has a convergent subsequence whose limit is in $K$.

Def (Totally bounded)
A subset $K$ of a metric space $(E,d)$ is totally bounded if $\forall s > 0$, $\exists x_1,\cdots, x_n \in K$ s.t. $K \subseteq B_{\varepsilon}(x_1)\cap \cdots \cap B_{\varepsilon}(x_n)$. i.e., $\forall \varepsilon > 0$, $K$ can be covered by finitely many balls of radius $\varepsilon$.

For a subset $K$ of a metric space, TFAE: 1) $K$ is compact 2) $K$ is sequentially compact 3) $K$ is compete and totally bounded.

Fact
Suppose $K\subseteq \mathbb{R}^n$ is closed and bounded. Then $K$ is sequentially compact

Lemma
Suppose $(E,d)$ is a metric space and $K \subseteq E$ is compact, then $K$ is sequentially compact.

Lemma
Suppose $(E,d)$ is a metric space, $K \subseteq E$ sequentially compact. Then $(K,d)$ is complete and totally bounded.

Lemma
Let $(E,d)$ be a metric space, $K \subseteq E$ complete and totally bounded, then $K$ is compact. 

Theorem (Heine-Borel)
A subset $K$ of $\mathbb{R}^n$ is compact $\iff K$ is closed and bounded.

## Continuous functions

Def (Continuous at a point)
Let $(E,d)$, $(E',d')$ be two metric space. A function $f: E \rightarrow E'$ is continuous at $p \in E$ if $\forall \varepsilon > 0$, $\exists \delta > 0$ so that $\forall x \in E$, $d(x,p) < \delta \implies d'(f(x),f(p)) < \varepsilon$. i.e. $f(B_{\delta}^d(p)) \subseteq B_{\varepsilon}^{d'}(f(p))$

Theorem
$f: (E,d) \rightarrow (E',d')$ is continuous $\iff \forall U \subseteq E', U$ open, $f^{-1}(U)$ is open.

Corollary
$f: (E,d) \rightarrow (E',d')$ is continuous $\iff\forall$  $C \subseteq E'$, $C$ closed, $f^{-1}(C)$ is closed.

 Def (Continuous function )
A map/function $f: (X, \mathcal{T})\rightarrow (X', \mathcal{T}')$ between two topological spaces is continuous if $\forall U \in \mathcal{T}'$, $f^{-1}(U) \in \mathcal{T}$. i.e., preimages of open sets are open.

Remark
The composite of two continuous maps is continuous. If $f: (X, \mathcal{T}_X) \rightarrow (Y, \mathcal{T}_Y),$$g: (Y, \mathcal{T}_Y) \rightarrow (Z, \mathcal{T}_Z)$ are continuous, then $g\circ f : (X, \mathcal{T}_X)\rightarrow (Z, \mathcal{T}_Z)$ is continuous.

Theorem
Images of compact sets under continuous functions are compact.  If $f: X \rightarrow Y$ is continuous and $K \subseteq X$ is compact, then $f(X) \subseteq Y$ is compact.

Corollary
Let $(E,d)$ be a metric space, $X$ a topological space, $K\subseteq X$ compact and $f: X \rightarrow E$ is continuous, then $f(k)$ is complete, totally bounded, sequentially compact and closed. 

Corollary
Suppose $X$ is a topological space, $f: X \rightarrow \mathbb{R}$ continuous and $K \subseteq X$ compact, then $\exists x_1,x_2\in X$ s.t. $\forall x\in X$, $f(x_1)\leq f(x) \leq f(x_2)$. i.e., $f$ achieves maximum and minimum on $X$. 

Def (Cluster point of a topological space)
Let $X$ be a topological space, $S \subseteq X$ a subspace, then $x\in X$ is a cluster point of  $S$ if $\forall$ open set $U$ with $x\in U, (U\setminus \{x\})\cap S$ is nonempty. If $E$ is a metric space, $x$ is a cluster point of $S$ iff $\exists$ a sequence $\{S_n\} \subseteq S\setminus\{x\}$ s.t. $s_n \rightarrow x$.

Def (Cluster point of a metric space)
Suppose $(E,d)$, $(E',d')$ are metric spaces, $A \subseteq E$, $f: A \rightarrow E'$, $p$ is a cluster point of $A$. Then 
$\lim_{x \rightarrow p}f(x) = q$, if $\forall \varepsilon > 0$, $\exists \delta > 0$ s.t. $x \in A\cap B_{\delta}(p), x \neq p, d'(f(x),q) < \varepsilon$.

Lemma
$E,E'$ metric spaces, $p$ cluster point of $E$. Then $f: E \rightarrow E'$ is continuous at $p \iff$ $\lim_{x \rightarrow p} f(x) = f(p)$.

Theorem
Suppose $f,g: (E,d) \rightarrow \mathbb{R}$ are continuous at $p \in E$. Then $f + g, f\cdot g$ are continuous at $p$. If $g(p) \neq 0$, $f/g$ is also continuous.

Theorem
Suppose $f = (f_1,\cdots,f_n): E \rightarrow \mathbb{R}^n$ is a function, $p \in E$. Then $f$ is continuous at $p \iff f_1\cdots f_n$ are all continuous at $p$.

Def (Uniformly continuous)
$f: (E,d) \rightarrow (E',d')$ is uniformly continuous if $\forall \varepsilon > 0$, $\exists \delta = \delta_{\varepsilon} > 0$ s.t. 
$$d(x,p) < \delta \implies d'(f(x),f(p))< \varepsilon, \forall x,p$$

Lemma
Suppose $f: E \rightarrow E'$ is uniformly continuous, then for any Cauchy sequences $\{S_n\}$ in $E$, $f(s_n)$ is Cauchy.

Theorem
Suppose $f: E \rightarrow E'$ is continuous and $E$ is compact, then $f$ is uniformly continuous. 

Def (Pointwise continuity)
$\{f_n:(E,d)\rightarrow (E',d')\}_{n=1}^{\infty}$ sequence of functions between two metric spaces. The sequence $\{f_n\}$ converges pointwise to $f: E\rightarrow E'$ if $\forall p \in E$, $f_n(p) \rightarrow f(p)$

Def (Uniform convergence)
$\{f_n:(E,d)\rightarrow (E',d')\}_{n=1}^{\infty}$a  sequence of functions between two metric spaces, $A \subseteq E$ a subspace. $f_n \rightarrow f$ uniformly on $A$ if $\forall \varepsilon > 0$, $\exists N$ s.t. $n\geq N \implies d'(f_n(p), f(p)) < \varepsilon, \forall p \in A$. 
Equivalently, $\forall \varepsilon > 0$, $\exists N$ s.t. $n \geq N \implies \sup\{d'(f_n(p),f(p))|p\in A\} < \varepsilon$. $\lim_{n\rightarrow \infty} \sup \{d'(f_n(p),f(p))|p\in A\} = 0$

Def (Uniformly Cauchy)
A sequence of functions $\{f_n: E \rightarrow E'\}_{n \in \mathbb{N}}$ is uniformly Cauchy on $A \subseteq E$ if $\forall \varepsilon > 0, \exists N$ with $n,m \geq N \implies \sup\{ d'(f_n(x),f_m(x))|x\in A\} < \varepsilon$

Theorem
Let $\{f_n: E \rightarrow E'\}_{n\in\mathbb{N}}, E'$ complete, then $\{f_n\}$ converges uniformly on $A$ $\iff \{f_n\}$ is uniformly Cauchy.

Theorem
Uniform limit of continuous functions is continuous.

Def (Bounded function)
Let $(E,d), (E',d')$ be two metric spaces, a function $f: E \rightarrow E'$ is bounded if $f(E) \subseteq E'$ is bounded.
Notation: $C(E,E') = \{f: E\rightarrow E'| f\:bounded\:and\:continuous\}$


