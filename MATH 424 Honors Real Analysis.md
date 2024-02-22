>This is the notes for the basic of calculus based on Professor Eugene Lerman's lecture notes of MATH 424 Honors Real Analysis at UIUC. In case of broken down preview, download the markdown or see the [[MATH 424 Honors Real Analysis.pdf|pdf]].


Reference:
>Introduction to Analysis, Rosenlicht
>Analysis I and Analysis II, Terence Tao

# Chapter 1 Skipped
# Chapter 2 The real number system

## 2.1 Field properties
>[!important] Def (Field)
>A set of numbers that satisfies the following properties is a field $F$ equipped with two operations $\cdot : \: F \times F \rightarrow F,(x,y)\mapsto x+y$ and $+:\:F \times F \rightarrow F, (x,y) \mapsto x \cdot y$:
>1) (COMMUTATIVITY) $\forall a,b \in F$, $a + b = b+a$ and $a \cdot b = b \cdot a$.
>2) (ASSOCIATIVITY) $\forall a,b,c \in F$, $(a+b)+c = a+(b+c)$ and $(a \cdot b) \cdot c = a \cdot (b \cdot c)$
>3) (DISTRIBUTIVITY) $\forall a,b,c \in F$, we have $a \cdot (b+c) = a \cdot b + b \cdot c$.
>4) (EXISTENCE OF IDENTITY AND ZERO) There are distinct elements $0$ and $1$ of $F$ s.t. $\forall a \in F$, $a + 0 = a$ and $a \cdot 1 = a$.
>5) (EXISTENCE OF INVERSES) $\forall a \in F$, there is an element of $F$, denoted $-a$, s.t. $a + (-a) = 0$, and for all non zero $a \in F$, there is an element of $F$, denoted $a^{-1}$ s.t. $a \cdot a^{-1} = 1$.
>And we say $(F,\: +,\:\cdot ,\: 0,\: 1\: )$ is a field.

### Field properties
#TODO 


$\mathbb{R}$ is a special field because it is **ordered** and **complete**, so we introduce the concept of order...
## 2.2 Order

>[!important] Def (Ordered field)
>An ordered field is a field $F$ with a subset $P \subseteq F$ (positive)  s.t.
>1) $0$ $\notin$ $P$.
>2) For any $a,b \in P$, $a+b$, $a \cdot b$ $\in P$.
>3) For any $a \in F$, $a \neq 0$, then either $a \in P$ or $-a \in P$. i.e, $F/ \{0\} = P \cup -P$, where $-P \coloneqq \{-x:\: x \in P\}$

Remark: $\mathbb{C}$ is not ordered. (see [[#^c28092|proof]])

>[!important] Def (Inequality)
>If $(F,P)$ is an ordered field, then there are relations $<, \leq$ ($>, \geq$) defined by
>$$ a < b \iff a - b \in P$$
>$$ a \leq b \iff a = b\: or\: a < b$$
>where $a,b \in F$
### Order properties
**O1** (Trichotomy) If $a,b \in \mathbb{R}$, then one and only one of the following statements is true:
$$\begin{align*}
a > b \\
a = b\\
a < b
\end{align*}$$
Proof:
	If we apply part iii) of order properties to $a,b$, then either $a-b \in P$, $a-b = 0$, or $a - b \in -P$, which is exactly what we want.

**O2** (Transitivity) If $a > b$ and $b > c$ then $a > c$.
**O3** If $a>b$ and $c > d$ then $a+c > b+d$.
**O4** If $a > b > 0$
#TODO 
Consequently, we have: 
1) $a \leq b$ $\iff$ $-b \leq -a$
2) $\forall a$, $a^2 \geq 0$
3) If $a \in P$, $b\in -P$, then $ab \in -P$
proof:
	 Note that $0 \leq a \iff a \in P\cup \{0\}$
	 i) $a \leq b \iff 0 \leq b - a = -(a-b) \iff -b \leq -a$ 
	 ii) If $a = 0$, $a^2 = 0 \geq 0$. If $a > 0, \:a\cdot a = a^2 \in P$. 
	 If $a < 0, \: -a \in P$, which implies that $(-a)^2 = a^2 \in P$ $\implies$ $a^2 > 0$.
	 iii) Note that $-(ab) = a \cdot (-b) \in P$, so $ab \in -P$.

Corollary: $\mathbb{C}$ is not an ordered field
proof: 
	Suppose that it is, then $1 = 1 \cdot 1 > 0 \implies -1 < 0$, but $-1 =( \sqrt{-1})^2 > 0$, contradiction. ^c28092

We can then define the **absolute value**
>[!important] Def (Absolute value)
>For any $a \in \mathbb{R}$, the absolute value $|a|$ is defined by 
>$$|a| = \begin{cases} a,\:\:\:\:\:\:\: a \geq 0 \\ -a, \:\:\: o.w. \end{cases}$$

>[!note] Properties of absolute value
>We define the function $| \:\cdot\:|: \: \mathbb{R} \rightarrow [0, \infty)$, $a \mapsto |a|$ to be the absolute value of $a$ with the following properties:
>1) $\forall a, |a| \geq 0$
>2) $|ab| = |a||b|$
>3) $|a^2| = |a|^2$
>Note that ii) directly implies iii) by taking $a = b$.

Proof: trivial

**Lemma** (Triangle Inequality) $\forall a, b \in \mathbb{R}$, $|a+b| \leq |a|+|b|$
Proof:
	For $x \in \mathbb{R}$, we have $x \leq |x|$. Thus for $a, b \in \mathbb{R}$, $a \leq |a|,$ $b \leq |b|$. By O3, we have $a + b \leq |a| + |b|$. Similarly, $-a \leq |a|$, $-b \leq |b|$ and $-a-b = -(a+b) \leq |a| + |b|$. Note that for any $x,y \in \mathbb{R}$, $x\ \leq y$ and $-x \leq y$ implies that $|x| \leq y$, thus $|a+b| \leq |a| + |b|$

**Corollary** $||a| - |b|| \leq |a-b|$
Proof:
	$|a| = |a-b+b| \leq |a-b|+|b| \implies |a|-|b| \leq |a-b|$. Similarly, $|b|-|a| \leq |b-a| = |a-b|$, so $||a| - |b|| \leq |a-b|$
	

>[!note] Def (Distance/ metric ...)
>There is a function $d: \mathbb{R} \times \mathbb{R} \rightarrow [0, \infty)$ defined by $d(a,b) = |a-b|$ that makes $\mathbb{R}$ a metric space.

## 2.3 Least upper bound Properties
>[!important] Def (Bounded from above)
>A subset $S \subseteq \mathbb{R}$ is **bounded from above** if $\exists \:a \in \mathbb{R}$ s.t. $s \leq a, \forall s \in S$. Any such $a$ is an **upper bound** of $S$. 

>[!important] Def (Least Upper Bound/ Supremum)
>Suppose $S \subseteq \mathbb{R}$ is bounded from above, then a number $a \in \mathbb{R}$ is a least upper bound if the following two conditions are satisfied:
>1) $a$ is an upper bound of $S$
>2) If $b$ is an upper bound of $S$, then $a \leq b$.
>We denote $a = sup(S) = lub(S)$. If $S$ is not bounded from above, then we say $sup(S) = \infty$.

>[!note] Completeness Axiom of LUB
>Any nonempty subset $S \subseteq \mathbb{R}$ bounded from above has a l.u.b.

Similarly, we can define a lower bound and greatest lower bound/ infimum for $S$, where $\inf(S) = -\sup(-S)$, and $-S = \{-s\:|\:s \in S\}$. 
So does the completeness axiom work for lower bound.

**Lemma 2.3.1** $\forall x \in \mathbb{R}$, $\exists \: n \in \mathbb{R}$ s.t. $x < n$.
Proof:
	Suppose not, then $\exists \: x_0 \in \mathbb{R}$ s.t. $n \leq x_0$, $\forall n \in \mathbb{R}$. By Completeness, $a = \sup(\mathbb{R})$ exists and is not equal to $\infty$. Then $\forall n, n+1 \leq a$. But then $\forall n, n \leq a - 1$, contradicting that $a$ is a l.u.b.

**Corollary 2.3.2** $\forall x \in \mathbb{R}$, $\exists \: n \in \mathbb{R}$ s.t. $\frac{1}{n} < \varepsilon$.
Proof:
	By 2.1, $\exists \: n \in \mathbb{N}$ s.t. $\frac{1}{\varepsilon} < n$. 

**Corollary 2.3.3** $\forall x\in \mathbb{R}$, $\exists n \in \mathbb{Z}$ s.t. $n \leq x \leq n + 1$.
Proof:
	#TODO 
	
**Consequence** $\forall a \in \mathbb{R}, a \geq 0$, if for all $\delta > 0, a < \delta$, then $a = 0$.
Proof:
	If $a > 0$, $\exists \:n \in \mathbb{N}$ s.t. $\frac{1}{n} < a$, contradiction.

**Theorem 2.3.4** ($\mathbb{Q}$ is dense in $\mathbb{R}$) $\forall x \in \mathbb{R}, \forall \varepsilon > 0, \exists\:r \in \mathbb{Q}$ s.t. $|x - r| < \varepsilon$. 
Proof:
	We fix $x, \varepsilon > 0$. By 2.2, $\exists \: N \in \mathbb{N}$ s.t. $\frac{1}{N} < \varepsilon$. By 2.3, $\exists\: n \in \mathbb{Z}$ s.t. $n < Nx \leq n + 1$. So $\frac{n}{N} \leq x < \frac{n+1}{N}$, so $0 \leq x < \frac{1}{N} \leq \varepsilon$ by choice of $N$. Thus $|x - \frac{n}{N}| < \varepsilon$, where $\frac{n}{N}$ is the desired rational $r$.

# Chapter 3 Metric spaces

## 3.1 Metric space
>[!important] Def (Metric Space)
>A metric space is a set $E$ together with a function $d:\: E \times E \rightarrow [0, \infty)$ s.t. $\forall x,y \in E$
>1) $d(x,y) = 0 \iff x = y$
>2) $d(x,y) = d(y,x)$
>3) $d(x,z) \leq d(x,y) + d(y,z)$ (Triangle Inequality)

The metric space is a pair $(E, d)$, where $d$ is called the metric.
ex. 
1) $(E = \mathbb{R}, d = |x-y|)$
2) $(E: any\:set, d = \begin{cases} 1, x\neq y\\ 0, x = y\end{cases})$
3) $(E = \mathbb{C}, d((x+iy),(u+iy)) = |(x+iy)-(u+iv)| = \sqrt{(x-u)^2 - (y-v)^2}$, and we define $d_2(x,y) = \sqrt{\sum_{i=1}^n(x_i-y_i)^2}$  ^034b7e
4) $(E = \mathbb{R},  d_1(x,y) = \sum|x_i-y_i|)$, $d_1$ is also called the Taxi/ Manhattan metric. Also, we define $d_{\infty}(x,y) = max\{|x_1-y_1|, \cdots, |x_n-y_n|\}$
Remark: If $(E,d)$ is a metric space, $\tilde{E} \subseteq E$, then $(\tilde{E}, \tilde{d} = d|_{\tilde{E} \times \tilde{E}})$ is also a metric space.

>[!important] Def ($l^2$ norm)
>The $l^2$ norm on $\mathbb{R}^n$ is the function $\Vert \:\cdot\: \rVert_2 :  \mathbb{R}^n \rightarrow [0,\infty)$ $\lVert x \rVert_2 = \sqrt{\sum x_i^2}$. 
>Note: the $l^2$ norm is actually the distance from the point to the origin. Also, recall the definition of [[#^034b7e|d2]] and we see $d_2(x,y) = \lVert x - y\rVert_2$

**Cauchy-Schwarz Inequality** $\forall x,y \in \mathbb{R}$, $|\sum x_iy_i| \leq \lVert x\rVert_2 \cdot \lVert y\rVert_2$
Proof:
	If either $x = 0$ or $y=0$, then we have $0 \leq 0$. Now suppose $x\neq 0, y \neq 0$. Then $\forall \alpha \in \mathbb{R}$, we have $x - \alpha y= (x_1-\alpha y_1,\cdots, x_n - \alpha y_n)$. By definition of norm there is $0 \leq \lVert x - \alpha y \rVert^2 = \sum(x_i - \alpha y_i)^2 = \sum(x_i^2 - 2\alpha x_i y_i + \alpha^2 y_i^2) = \lVert x \rVert^2 - 2 \alpha \sum x_iy_i + \alpha^2 \lVert y \rVert^2$. Now we take $\alpha = \pm\frac{\lVert x \rVert}{\lVert y \rVert}$, then the inequality becomes $0 \leq \lVert x \rVert^2 \pm 2 \frac{\lVert x \rVert}{\lVert y \rVert} \sum x_iy_i \pm{(\frac{\lVert x \rVert}{\lVert y \rVert})}^2 \lVert y \rVert^2 = 2 \lVert x \rVert^2 \mp 2 \frac{\lVert x \rVert}{\lVert y \rVert} \sum x_iy_i$
	And we have $\pm \sum x_iy_i \leq \lVert x \rVert\lVert y \rVert$, and thus $|\sum x_iy_i| \leq \lVert x\rVert_2 \cdot \lVert y\rVert_2$.

$d_2$: the Euclidean metric
**Theorem 3.1 (Triangle Inequality for $d_2$)** $\forall x, y \in \mathbb{R}^n$, $\Vert x + y \rVert_2 \leq \lVert x \rVert_2 + \lVert y \rVert_2$. Consequently, $\forall x,y,z \in \mathbb{R}^n$, $d_2(x,z) \leq d_2(x,y) + d_2 (y,z)$
Proof:
1) $\Vert x + y \rVert^2 = \sum(x_i+y_i)^2 = \sum(x_i^2+2x_iy_i+y_i^2) \leq \lVert x \rVert^2 + 2\lVert x\rVert \lVert y \rVert + \lVert y \rVert^2 = (\lVert x \rVert + \lvert y \rVert)^2$ (the inequality part comes from Cauchy-Schwarz).
2) $d(x,z) = \lVert x - z \rVert_2 = \lVert (x-y) + (y-z) \rVert \leq \lVert x-y \rVert + \lVert y-z \rVert = d(x,y) + d(y,z)$.

**Corollary 3.1.2** $(\mathbb{R}^n, d_2)$ is a metric space.
Proof:
	By Theorem 3.1 we've proven the triangle inequality for $d_2$. Now if $d_2(x,y) = 0$, then $\sqrt{\sum(x_i-y_i)^2)} = 0$, which implied that $x_i-y_i=0, \forall i$, thus $x=y$. $d_2(x,y) = \sqrt{\sum(x_i-y_i)^2)} = \sqrt{\sum(y_i-x_i)^2)} = d_2(y,x)$, which ends our proof.

## 3.2 Open and closed sets
Now we continue our discussion about metric space by introducing a new concept, the open/closed ball.
>[!important] Def (Open ball and closed ball)
>Let $(E,d)$ be a metric space, an **open ball** centered at $x \in E$ of radius $r>0$ is the set $B_r(x) \equiv B(x,r) := \{y\in E| d(x,y) < r\}$. 
>Similarly, a **closed ball** centered at $x \in E$ of radius $r>0$ is the set $\overline{B_r(x)} \equiv \overline{B(x,r)} := \{y\in E| d(x,y) \leq r\}$. 

ex
1) $E = \mathbb{R}^2, d = d_2$. 
2) $E = \mathbb{R}^2, d = d_{\infty} = \max\{|x_1-y_1|,|x_2-y_2|\}$, $B_r(0) = \{y \in \mathbb{R}^2 |y_1| < r,|y_2| < r\}$, and this is a square of side length $r$.
3) $E  = [0,2]$, $d(x,y) = |x-y|$, $B_1(2) = (1,2]$
4) $E$: a set, $d(x,y) = \begin{cases}1, \:\:x\neq y\\ 0, \:\:x=y\end{cases}$. $B_2(x) = E$, $B_1(x) = \{x\}$

>[!important] Def (Open set)
>A subset $U$ of a metric space $(E,d)$ is open if $\forall x \in U, \exists r > 0$ s.t. $B_r(x) \subseteq U$.

Ex. $E = \mathbb{R}$, $U = (a,b)$, $d = \min\{|a-x|,|b-x|\}$

>[!important] Def (Closed set)
>A subset $C$ of a metric space $(E,d)$ is closed if the complement of $C$, $C^c = E\setminus C := \{x\in E| x \notin C\}$ is open.

Ex. $E = \mathbb{R}$, $C = [0,1]$.
Remark: $[0,1) \in \mathbb{R}$ is neither closed nor open. 

**$E, \varnothing$ are both open and closed**

>[!note] Theorem 3.2.1
> Let $(E,d)$ be a metric space, then
>1) $\forall$ collection $\{U_i\}_{i \in I}$ of open sets in $E$, $\cup_{i \in I}U_i$ is open.
>2) $\forall \:k$, $\forall$ open sets $U_1,...,U_k, \:U_1 \cup ...\cup U_k$ is open, i.e., **finite** union of open sets are open. 
>3) Open balls are open.

Proof:
	1) Suppose $x \in \cup_{i \in I} U_i$, then $x \in U_{i0}$ for some $i_0 \in I$. Since $U_i$ is open, $\exists\:r > 0$ s.t. $B_r(x) \subseteq U_{i0} \subseteq \cup U_i$.
	2) Suppose $U_1,...,U_k$ are open and $x \in \cap_{i=1}^k U_i$. Then $\forall i$, $\exists r_i > 0$ s.t. $B_{ri}(x) \subseteq U_i$. Let $r = \min\{r_1,...,r_k\}$, then $B_r(x) \subseteq \cap_{i=1}^kU_i$.
	3) Given $y \in B_r(x)$, $d(x,y) = r$. We have $\delta = r - d(x,y) > 0$. Then $\forall z \in B_{\delta}(x)$, $d(x,z) \leq d(x,y) + d(y,z) < d(x,y) + \delta = d(x,y) + (r - d(x,y)) = r$. So $z \in B_r(x)$ and $B_{\delta}(x) \subseteq B_r(x)$, $B_r(x)$ is open. (see Figure 3.2.1 below). 
					       ![[Fig 2.2.1.jpeg | 200]] 
							       Figure 3.2.1
Remark: we need the number of intersections in (2) to be finite. If not, the infimum can be 0. Consider $E = \mathbb{R}$, $d(x,y) = |y-x|, U = (-\frac{1}{n},\frac{1}{n})$. Then $\cup U_n = \{0\}$. But under the standard metric, any open ball centered at 0 _must_ contain some number greater than and less than 0, which is a contradiction.

Remark. An **open rectangle** in $\mathbb{R}^n$ is a set $U = (a_1 \times b_1)\times  (a_2 \times b_2)\times \cdots  \times(a_n \times b_n), a_i < b_i$, $i = 1,2,\cdots, n$.
It is open. $\forall x  = (x_1,\cdots,x_n) \in U$, let $r = \frac{1}{2}\min\{|a_i-x_i|,|b_i-x_i|\}$, then $B_r(x) \subseteq U$. 
Similarly, $F = [a_1 \times b_1]\times [a_2 \times b_2]\times \cdots \times[a_n \times b_n]$ is closed.

>[!important] Def (bounded)
>A subset $\varnothing \neq S \subseteq E$ of a metric space $(E,d)$ is bounded if $\exists x \in E, r> 0$ s.t. $S \subseteq B_r(x)$.

Ex. $[a,b)$ is bounded, $x = 0, r = \max\{|a|,|b|\} + 1$, while $[0,\infty)$ is not.
Ex. $E = \{a\} \neq \varnothing$ s.t. $d(x,y) = \begin{cases}1, x\neq y\\ 0, x = y\end{cases}$. Then for all $U \subseteq E$, for any $x \in E$, we have $U \subseteq B_2(x)$.
Remark. $\{d(x,s)|s \in S\}$ is bounded above by $r$.
Remark. Any subset of a bounded metric space $E$ is bounded.

>[!note] Theorem 3.2.2 
>Suppose $\varnothing \neq S \subseteq \mathbb{R}$ is closed and bounded. Then inf $S$, sup $S$ exist and are in $S$

Proof:
	We show that sup$S$ exists and sup$S \in S$. Since $S$ is bounded, $S$ is bounded from above. Since also $S \neq \varnothing$, $L = \sup S$ exists. If $L \notin S$, then $L \in \mathbb{R}\setminus S$, which is open. But then $\exists r > 0$ s.t. $B_r(L) = (L-r, L+r) \subseteq \mathbb{R}\setminus S$, so we have $(L,\infty) \subseteq \mathbb{R}\setminus S$ and $(L - r,\infty) \subseteq \mathbb{R}\setminus S$. Hence, for all $s \in S$, $s \leq L-r < L - \frac{r}{2}$, which means that $L - \frac{r}{2}$ is also a lower bound, contradicting that $L$ is the supremum.
	For inf$S$, argue for $-S$.

## 3.3 Convergent sequences

>[!important] Def (Sequence)
>A sequence in a set $E$ is a function $S: \mathbb{N} \rightarrow E$.
>Notation: $S = \{S_i\}_{i=1}^{\infty} = \{s_1,...,s_n,...\}$ or just $(s_n)$.
 
>[!important] Def (Convergent)
>Let $(E,d)$ be metric space and $(S_n)$ a sequence. We say $S_n$ converges to $L \in E$ if $\forall \varepsilon > 0$, $\exists N\in \mathbb{N}$ s.t. for all $n > N$, $d(s_n,L) < \varepsilon\equiv s_n \in B_{\varepsilon}(L)$.
>We write $S_n \rightarrow L$ or $\lim_{n \rightarrow \infty} S_n = L$ and we say $S_n$ is convergent, $L$ is a limit of $S_n$.
>

Ex. $E = \mathbb{R}$, $S_n = \frac{1}{n}$, $S_n \rightarrow 0$. *proof:* Given $\varepsilon > 0$, $\exists N\in \mathbb{N}$ s.t. $\frac{1}{\varepsilon} < N$. Then for all $n > N$, we have $\frac{1}{n} < \frac{1}{N} < \varepsilon$.

**Lemma 3.3.1** A sequence $\{S_n\}$ in $(E,d)$ converges to $L \iff \forall$ open set $U \subseteq E$ with $L \in U$, $\exists N \in \mathbb{N}$ s.t. for all $n > N$, $s_n \in U$.
Proof: 
	($\impliedby$) $\forall \varepsilon, B_{\varepsilon}(L)$ is open, so $\exists N \in \mathbb{N}$ s.t. $\forall n > N$, $s_n \in B_{\varepsilon}(L)$, i.e., $d(s_n, L) < \varepsilon$. 
	($\implies$) Suppose $S_n \rightarrow L$ and $U$ is an open set with $L \in U$. Since $U$ is open, $\exists \:r > 0$ s.t. $B_r(L) \subseteq U$. Since $S_n \rightarrow L$, $\exists N  = N(r)$ s.t. for all $n > N$, $s_n \in B_r(L) \subseteq U$.

**Lemma 3.3.2** Convergent sequences are bounded.
Proof:
	Suppose $S_n \rightarrow L$ in a metric space $(E,d)$. Since $S_n \rightarrow L$, $\exists \: N \in \mathbb{N}$ s.t. $\forall n > N$, $s_n \in B_r(L)$. Let $r = \max\{d(s_1,L),...,d(s_N,L),1\} + 1$. Then $s_n \in B_r(L)$ for all $n$.

**Proposition** Let $S_n$ be a sequence in the metric space $(E,d)$. If $S_n \rightarrow L_1$ and $S_n \rightarrow L_2$, then $L_1 = L_2$.
Proof:
	We have $N,N'$ s.t. $\forall n > N, d(s_n,L_1) < \varepsilon/2, d(s_n,L_2) < \varepsilon/2$. Thus for $n > \max\{N,N'\},$$d(L_1,L_2) \leq d(L_1,s_n) + d(L_2, s_n) = \varepsilon/2\cdot2 = \varepsilon$. 
	
**Proposition** Suppose $S_n \rightarrow L$, ${S_{nk}}$ is a subsequence of $S_n$. Then $S_{nk} \rightarrow L$.
Proof:
	Let $𝑠_{𝑛_𝑘}$ denote a subsequence of $𝑠𝑛$. Note that $𝑛_𝑘≥k$ for all 𝑘. This easy to prove by induction: in fact, $𝑛_1≥1$ and $𝑛_𝑘≥𝑘$ implies $𝑛_{𝑘+1}>𝑛_𝑘≥𝑘$ and hence $𝑛_{𝑘+1}≥𝑘+1$. Let lim$𝑠_𝑛=L$ and let $𝜖>0$. Then there exists $𝑁$ so that $𝑛>𝑁$ implies $|𝑠_𝑛−L|<𝜖$. Now $𝑘>𝑁⟹𝑛_𝑘>𝑁$$⟹|s_{n_k}−L|<𝜖$. Therefore: $\lim_{𝑘→∞}𝑠_{𝑛_𝑘}=L$.

**Lemma 3.3.3** Suppose $C$ is closed in $(E,d)$, $\{S_n\}$ a sequence in $C$ ($\forall n, s_n \in C$) and $s_n \rightarrow L$. Then $L \in C$.
			Conversely, if $\forall$ convergent $\{s_n\}$ in $C$, lim$s_n \in C$, then $C$ is closed.
Proof:
	($\implies$) Suppose $C$ is closed, $\{S_n\}$ is a sequence in $C$ and $s_n \rightarrow L$. Suppose $L\notin C$, then $\exists r > 0$ s.t. $B_{r}(L) \subseteq E\setminus C$ since $E\setminus C$ is open. Since $s_n \rightarrow L$, $\exists N \in \mathbb{N}$ s.t. $s_n \in B_r(L)$ for all $n > N$, contradiction, since $s_n \in L$ and $B_r(L) \cap C = \varnothing$.  
	($\impliedby$) We prove the contrapositive.  Suppose $C$ is not closed, then $E \setminus C$ is not open. $\implies \exists p \in E \setminus C$ s.t. $\forall r > 0$, $B_r(p)\not\subset E \setminus C$, $B_r(p) \cap C \neq \varnothing$. In particular, $\forall n \in \mathbb{N}$, $\exists x_n \in B_{1/n}(p) \cap C$. Then $\{x_n\}$ is a sequence with $d(x_n,p) < \frac{1}{n}$. Given $\varepsilon > 0, \exists N$ s.t. $\frac{1}{N} < \varepsilon$. Hence for all $n > N$, $d(x_n,p) < \frac{1}{n} < \frac{1}{N} < \varepsilon$, which suggests that $x_n \rightarrow p \notin C$. So we prove that if $C$ is not closed, then $\exists$ a sequence $\{x_n\} \subseteq C$ with $x_n \rightarrow p \notin C$.
 
**Proposition** Suppose $\{a_n\},\{b_n\}$ are two sequences in $\mathbb{R}$, $a_n \rightarrow a$, $b_n \rightarrow b$. Then
1) $a_n + b_n \rightarrow a + b$
2) $a_n \cdot b_n \rightarrow a \cdot b$
3) $\forall c \in \mathbb{R}$, $ca_n \rightarrow ca$
4) If $b \neq 0$ and $b_n \neq 0$ for all $n$, then $\frac{a_n}{b_n} \rightarrow \frac{a}{b}$
5) If $a_n \leq b_n$ for all $n$, then $a \leq b$.
#TODO 
Proof:
	For (2), take it with the fact that convergent sequences are bounded and take $\varepsilon = \varepsilon/2M$, where $M$ is and upper bound for both of the sequence.

>[!important] Def (Inferior, Closure, Boundary)
>Let $(E,d)$ be a metric space, $S \subseteq E$ a subset, then:
>Interior$(S) \equiv S^{\circ} = \cup_{O\subseteq S} O$, where $O$ is an open set, is the largest open set contained in $S$.
>Closure$(S) \equiv \overline{S} \equiv \cap_{S\subseteq C} C$, where $C$ is a closed set, is the smallest closed set containing $S$.
>Boundary$(S) \equiv \overline{S}\setminus C^{\circ} = \delta S$.

Ex. $E = \mathbb{R}, d(x,y) = |x-y|, S = \mathbb{Q}$. $\forall\:q\in\mathbb{Q}$, $\forall r > 0$, $B_r(q) = (q-r,q+r)\cap(\mathbb{R}\setminus \mathbb{Q}) \neq \varnothing$. So $\not\exists r$ s.t. $B_{r}(q) \subseteq \mathbb{Q}$. Thus $\mathbb{Q}^{\circ} = \varnothing$. $\overline{\mathbb{Q}} = \mathbb{R}$. $\delta S = \mathbb{R}$.
Ex. $E = \{-1,0,1\}\subseteq\mathbb{R}, d(x,y) = |x-y|$. $B_1(0) = \{0\}$. $B_1(0)$ is open and closed. $\overline{B_1(0)} = B_1(0)$. But $\{y \in E\: |\: d(y,0) \leq 1\} = E$.

>[!note] Theorem
>Let $(E,d)$ be a metric space, $S\subseteq E$, then
>1) $S^{\circ} = \{x \in S | \exists \varepsilon > 0,\:s.t.\:B_{\varepsilon}(x) \subseteq S\}$, $\varepsilon > 0$
>2) $E\setminus \overline{S} = (E\setminus S)^{\circ}$
>3) $\overline{S} = \{x\in E| \exists\:a\:sequence \{s_n\}\subseteq S\:with\:s_n\rightarrow x\}$
>4) $\delta S = (E\setminus S^{\circ}) \cap (E\setminus(E\setminus S^{\circ}))$
>5) $E = S^{\circ}\sqcup \delta S \sqcup (E\setminus S)^{\circ}$. $E$ is the disjoint union of the interior of $S$, boundary of $S$, and exterior of $S$.

Ex. $S = \{\frac{1}{n}|n\in\mathbb{N}\} \subseteq \mathbb{R}$. $S^{\circ} = \varnothing, \overline{S} = S \cap \{0\}, \delta S = \overline{S}\setminus S^{\circ} = S \cup \{0\}, Ext(S) = (\mathbb{R}\setminus S)^{\circ} = \mathbb{R} \setminus\overline{S}$
Proof:
	1) Suppose $x \in S^{\circ}$. Since $S^{\circ}$ is open, $\exists r > 0$ s.t. $B_r(x)\subseteq S^{\circ} \subset S \implies$ $x \in \{x'\in S|\exists r>0\: s.t.\:B_r(x')\subseteq S\}$. Then $\exists r\:s.t. B_r(x) \subseteq S$. Note that $B_r(x)$ is an open set, so we have open sets $\subseteq S^{\circ}, x \in S$.
	2) $E\setminus \overline{S} = E \setminus \cap_{C\:closed, S \subseteq C}C = \cup_{E\setminus C\: open,E\setminus C\subseteq E\setminus S}(E\setminus C) = \cup_{O\:open, O \subseteq E\setminus S} O= (E\setminus S)^{\circ} = Ext(S)$
	3) Suppose $x \in \overline{S}$, then $E\setminus \overline{S} = (E\setminus S)^{\circ}$. If $x \notin (E\setminus S)^{\circ}$, then $\forall r,\:B_r(x)\nsubseteq E\setminus S$. Then $\forall r,\:B_r(x) \cup S \neq \varnothing$, so $\forall r, \exists S_r \in B_r(x) \cup S)$. Let $r = \frac{1}{n}$, then $\forall n, S_n \in B_{1/n}(x) \cap S$ and $S_n \rightarrow x$. Conversely, if $\{S_n\}\subseteq S, S_n \rightarrow x$, then $x = \lim S_n \in \overline{S}$ since $\{S_n\}\subseteq \overline{S}$ and $\overline{S}$ is closed.
	4) $\delta S = \overline{S}\setminus S^{\circ} = \overline{S}\cap (E\setminus S^{\circ}) = (E\setminus(E\setminus S^{\circ})) \cap (E\setminus S^{\circ}) =(2)= (E\setminus Ext(S)) \cap (E \setminus S^{\circ})$
	5) $E = (E\setminus \overline{S}) \sqcup \overline{S} = (E\setminus S)^{\circ} \sqcup (\delta S) \sqcup (S^{\circ})$

### Monotone sequences in $\mathbb{R}$
>[!!note] Def (increasing/ decreasing sequence)
>A sequence $\{a_n\} \subseteq \mathbb{R}$ is increasing if $a_1 \leq a_2 \leq \cdots \leq a_n \cdots$. Similarly, $\{a_n\} \subseteq \mathbb{R}$ is decreasing if $a_1 \geq a_2 \geq \cdots \geq a_n \cdots$. Note that the constant sequence is both increasing and decreasing.

>[!note] Def (monotone sequence)
>A sequence is monotone if it is increasing or decreasing.

>[!important] Theorem (Bounded monotone sequences converges)
>Any bounded monotone sequences in $\mathbb{R}$ converges.

Proof:
	Suppose $\{a_n\}$ is increasing and bounded. Then $S = \{a_n | n \in \mathbb{N}\}$ is bounded above. Since $\mathbb{R}$ is complete, $L := \sup S$ exists. We claim that $a_n \rightarrow L$. To see this, notice that for all $\varepsilon > 0, L - \varepsilon < L \implies \exists N\: s.t. \: L - \varepsilon \leq a_n \leq L$ for $n \geq N$,  then$L - \varepsilon \leq a_N \leq a_n \leq L \implies a_n \in B_{\varepsilon}(L)$.
	For the cases when the sequence is bounded from below, we argue that for infimum.

>[!important] Def (Divergent)
>A sequence $\{a_n\}\subseteq \mathbb{R}$ diverges to $+\infty$ if $\forall M \in \mathbb{R}, \exists N \in \mathbb{N}$ s.t. for all $n > N$, $a_n > M$.  A sequence $\{b_n\}\subseteq \mathbb{R}$ diverges to $-\infty$ if $\forall M \in \mathbb{R}, \exists N \in \mathbb{N}$ s.t. for all $n > N$, $a_n < M$.  

>[!note] Theorem 
>A monotone sequence in $\mathbb{R}$ either converges or diverges to $\pm\infty$

Proof:
	If $\{a_n\}$ is increasing and not bounded, it diverges to $+\infty$. 

### lim sup and lim inf
Remark: Suppose $\{S_n\},\{T_n\}$ are two bounded sequences, $T \subseteq S$. then $\sup T \leq \sup S,\: \inf T \geq \inf S$.
Proof: 
	Suppose $\{S_n\}$ is a sequence bounded above. Then $V_N := \sup\{S_n|n\geq N\}$ exists and since $\{S_n| n\geq N + 1\}\subseteq \{S_n|n\geq N\}$, $V_{N+1} \leq V_N, \forall N$, so $\{V_n\}$ is monotone, hence either converges or diverges to infinity. 

>[!important] lim sup and lim inf
>Let $\{S_n\}$ be a sequence bounded above. Then $\forall N$, $V_N:=\sup\{S_n|n\geq N\}$. We define
>$$\lim \sup S_n := \lim V_n = \lim_{n\rightarrow \infty} \sup\{S_n|n\geq N\}$$
>which may be infinity or a number.
>Similarly, if the sequence is bounded below, we define
>$$\lim \inf S_n := \lim V_n = \lim_{n\rightarrow \infty} \inf\{S_n|n\geq N\}$$ 

Ex. $S_n = (-1)^n, V_N = \sup \{(-1)^n|n\geq N\} = 1$. $S_n = -n, V_N = \sup \{-n|n \geq N\} = -N, V_N \rightarrow -\infty$
Remark. $\inf\{S_n | n \geq N\} \leq S_N \leq \sup\{S_n | n \geq N\}$
Remark. Given $\{S_n\}$ not bounded above, $\sup\{S_n | n \geq N\} = + \infty$. $\lim \sup S_n := + \infty$. Similar definition for lim inf. 
	Ex. $S_n = (-1)^nn$, $\lim \sup S_n = +\infty, \lim \inf S_n = -\infty$

>[!note] Theorem
>Let $\{S_n\}$ be a sequence in $\mathbb{R}$
>1) If $\{S_n\} \rightarrow \pm \infty$ or converges, then $\lim \inf S_n = \lim S_n = \lim \sup S_n$.
>2) If $\lim \inf S_n = \lim \sup S_n$ (could be $\pm \infty$), then $\lim \inf S_n = \lim S_n = \lim \sup S_n$.

Proof:
	1) Let $L = \lim S_n$. Then $\forall \varepsilon > 0, \exists N$ s.t. $\forall n \geq N, |S_n - L| < \varepsilon/2$, or, equivalently, $L - \varepsilon/2 < L < L + \varepsilon/2$. Then $\forall M \geq N,$ $L - \varepsilon < L - \varepsilon/2 \leq \inf\{S_n | n\geq M\} \leq \sup\{S_n | n\geq M\}\leq L + \varepsilon/2 < L + \varepsilon$. Hence we have $\lim \inf S_n = L = \lim\sup S_n$.
	2) If $\lim \inf S_n = L = \lim\sup S_n$, then $\forall \varepsilon > 0, \exists N$ s.t. for all $M \geq  N$, $L - \varepsilon < \inf\{S_n|n\geq M\} \leq S_M \leq \sup\{S_n|n \geq M\} < L + \varepsilon \implies S_n \rightarrow L$

## 3.4 Completeness

>[!important] Def (Cauchy Sequences)
>A sequence $\{S_n\}$ in a metric space $(E,d)$ is Cauchy if $\forall \varepsilon > 0, \exists N$ s.t. $\forall n,m > N, d(s_n,s_m) < \varepsilon$

**Lemma 3.4.1** Any convergent sequence $\{S_n\}$ in $(E,d)$ is Cauchy.
Proof: Suppose $s_n \rightarrow L$ in $(E,d)$, then given $\varepsilon > 0, \exists N$ s.t. for $n> N, d(s_n,L) < \varepsilon/2$. For $n,m > N$, $d(s_n,s_m) \leq d(s_n,L) + d(s_m,L) = \varepsilon/2\cdot 2 = \varepsilon$.
Ex. $S_n = \sum_{k=1}^n\frac{1}{k}, \lim S_n = \sum_{k=1}^{\infty}\frac{1}{k}$. Claim: it is not Cauchy. 
	$s_{2n} - s_n = \frac{1}{n+1} + \cdots + \frac{1}{n+n}\geq \frac{1}{2n}+\cdots + \frac{1}{2n} = \frac{1}{2}$. Hence $\nexists N$ s.t. for $2n,n >N, |s_{2n}-s_n| < 1/2$. It is not epsilon-close.

Remark. There are $(E,d)$ where Cauchy sequence need not have a limit in $E$.
	Consider $E = \mathbb{R}\setminus\{0\}, d = |x-y|$. Then $S_n = \frac{1}{n} \rightarrow L = 0 \in \mathbb{R}$, but $L \notin \mathbb{R}\setminus \{0\}$

>[!note] Def (Completeness) 
>A metric space $(E,d)$ is complete if every Cauchy sequences converges.

We want to show that. 1) $\mathbb{R},\mathbb{R}^n$ are complete. 2) Any subset of a complete metric space is complete.
(see below)

**Lemma 3.4.2** Let $(E,d)$ be a metric space and $\{S_n\}$ a Cauchy sequence in $E$. Then $\{S_n\}_{n \in \mathbb{N}}$ is bounded.
Proof:
	Since it is a Cauchy sequence, $\exists N$ s.t. for $m,n \geq N, d(s_n,s_m) < 1$. Let $r = \max\{d(s_1,s_n),\cdots d(s_{N-1},s_N),1\} + 1$, then $\forall k, d(s_n,s_k) < r$.

**Lemma 3.4.3** Suppose $\{S_n\}$ is a Cauchy sequence and $\{S_{n_k}\}$ is a convergent subsequence with $S_{n_k} \rightarrow L$. Then $S_n \rightarrow L$ as well.
Proof:
	Since $S_{n_k} \rightarrow L$, $\forall \varepsilon > 0, \exists k$ s.t. $d(S_{n_l},L)<\varepsilon /2, \forall l > k$. Since $\{S_n\}$ is a Cauchy sequence. Then $\exists N$ s.t. for $n,m > N, d(s_n,s_m) \leq \varepsilon / 2$. Then for $n > \max\{N,k\} = M$, $d(s_n,s_{n_M})\leq \varepsilon/2$ since $n_M \geq M \geq N$ and $d(s_{n_M}, L) < \varepsilon/2$. Then $d(s_n,L) \leq d(s_n,s_{n_M}) + d(s_{n_M},L) = \varepsilon$

**Lemma 3.4.4** Any closed subsets $C$ of a complete metric space $(E,d)$ is complete.
Proof:
	Let $\{S_n\}$ be a Cauchy sequence in $E$ with respect to metric $d$. Then $\{S_n\}$ is a Cauchy sequence in $E$. Since $E$ is complete, $\{S_n\}$ converges to some limit $L \in E$. Since $\{S_n\}\subseteq C$ and $C$ is closed, we have $L \in C$ and thus $C$ is complete.

We then show that $\mathbb{R},\mathbb{R}^n$ are complete. Let's start with $\mathbb{R}$.

>[!note] Theorem (Bolzano–Weierstrass in $\mathbb{R}$)
>Let $\{S_n\}$ be a bounded sequence in $\mathbb{R}$, $L = \lim\sup S_n$. Then there is a subsequence $\{S_{n_k}\}$ s.t. $S_{n_k} \rightarrow L$.

Proof:
	Let $V_N:=\sup\{s_n|n\geq N\}$, then by definition $L = \lim_{N\rightarrow \infty} V_N$. Then $\forall \varepsilon >0, \exists k$ s.t. $N\geq k \implies L - \varepsilon < V_N < L + \varepsilon$. Also, $\exists i$ s.t. $L - \varepsilon < s_i \leq V_N < L + \varepsilon$. 
	When $\varepsilon = 1$, $\exists K_1$ s.t. for $n_1\geq K_1$,  $L - 1 < s_{n_1}<L+1$
	When $\varepsilon = 1/2$, $\exists K_2$ s.t. for $n_2\geq K_2$,  $L - 1/2 < s_{n_2} \leq V_{n_2}<L+1/2$
	If we replace $K_2$ by $\max\{K_2,n_1+1\}$, we may assume that $n_2 \geq K_2 > n_1$.
	Then continuing the construction we will get a sequence $n_1 < n_2 < \cdots < n_k < n_{k+1}<\cdots$ so that $L - 1/k < s_{n_k} < L + 1/k$, $\forall k$, hence $s_{n_k} \rightarrow L$. 
	*Note: 1/k comes from the construction of $\varepsilon = 1/k$*

**Corollary 3.4.6** $(\mathbb{R},d)$ is complete.
Proof:
	Let $\{S_n\} \subseteq \mathbb{R}$ be Cauchy. Then by Lemma 3.4.2, it is bounded. By Bolzano–Weierstrass $\{S_n\}$ has a convergent subsequence $\{S_{n_k}\}$. By Lemma 3.4.3, $S_n\rightarrow \lim S_{n_k} \in \mathbb{R}$.

Now recall some useful metric in $\mathbb{R}^n$: 
$d_2(x,y) := \sqrt{\sum_i (x_i - y_i)^2}$
$d_1(x,y) := \sum_i |x_i-y_i|$
$d_{\infty}(x,y) = \max_{1\leq i \leq n}|x_i-y_i|$

**Lemma 3.4.7** $(\mathbb{R}^n,d_1)$ is complete.
Proof:
	Let $x^{(k)} = \{(x^{(k)}_1,x^{(k)}_2,\cdots x^{(k)}_n)\}_{k=1}^{\infty}$ be a Cauchy sequence in $\mathbb{R}^n$ with respect to $d_1$. Note that $\forall j$ we have $|x_j-y_j|\leq \sum_{i=1}^n|x_i-y_i| = d_1(x,y)$ for all $x,y\in\mathbb{R}^n$. Hence $\forall j$, $\exists N$ s.t. $k,l > N \implies \varepsilon > d_1(x^{(k)}, x^{(l)}) \geq |x_j^{(k)}-x_j^{(l)}|$, so $\{x_1^{(k)}\}, \cdots, \{x_n^{(k)}\}$ are a convergent sequences in $\mathbb{R}$. Since $\mathbb{R}$ is complete, $\forall j, \exists L_j$ s.t. $x_j^{(k)}\rightarrow L_j$. Hence $\exists N_j$ s.t. $k > N_j \implies |x^{(k)}_j \rightarrow L_j| < \varepsilon / n$. Then $\forall N > \max\{N_1,\cdots, N_n\}$
		$$d((L_1,L_2,\cdots,L_n), x^{(k)}) = \sum_{j=1}^n|L_j - x_j^{(k)}| < \frac{\varepsilon}{n} + \frac{\varepsilon}{n}+\cdots \frac{\varepsilon}{n} =\varepsilon$$
		Hence $x^{(k)}\rightarrow L = (L_1,\cdots,L_n) \in \mathbb{R}^n$ with respect to $d_1$ and thus complete.

>[!note] Theorem (Bolzano–Weierstrass in $\mathbb{R}^n$)
>Let $\{s_n\}$ be a bounded sequence in $\mathbb{R}^n$, then $\{s_n\}$ has a convergent subsequence.

Proof:
	Let $\{x^{m}\}$ be a bounded sequence in $\mathbb{R}^n$. The sequence $\{x^{m}_1\}$ of first components of the terms of $\{x^m\}$ is a bounded real sequence, which has a convergent subsequence $\{x^{mk} _1\}$. Let $\{x^{mk}\}$ be the corresponding subsequence of $\{x^m\}$. Then the sequence $\{x^{mk}_2 \}$ of second components of $\{x^{mk}\}$ is a bounded sequence of real numbers, so it too has a convergent subsequence, and we again have a corresponding subsequence of $\{x^{mk}\}$(and therefore of $\{x^m\}$), in which the sequences of first and second components both converge. Continuing for $n$ iterations, we end up with a subsequence $\{z^m\}$ of $\{x^m\}$ in which the sequences of first, second, ..., $n$th components all converge, and therefore the subsequence $\{z^m\}$ itself converges in $\mathbb{R}^n$.


>[!note] Def (Norm)
>A norm on $\mathbb{R}^n$ is a function $\mathbb{R}^n\rightarrow \mathbb{R}, x \mapsto \lVert x \rVert$ so that
>1) $\lVert x \rVert \geq 0$ and $\lVert x \rVert = 0 \iff x = 0$
>2) $\lambda$$\lVert x \rVert = \lambda \lVert x \rVert, \forall \lambda \in \mathbb{R}, x\in\mathbb{R}^n$
>3) $\lVert x + y \rVert \leq \lVert x \rVert + \lVert y \rVert$

**Lemma 3.4.8** Let $\lVert \cdot \rVert: \mathbb{R}^n\rightarrow \mathbb{R}$ be a norm. Then $d: \mathbb{R}^n\times \mathbb{R}^n \rightarrow [0,\infty)$, $d(x,y) = \lVert x - y \lVert$ is a metric.

>[!note] Def (Equivalent norm and metric)
>Two norms $\lVert \cdot \rVert, \lVert \cdot \rVert'$ are equivalent on $\mathbb{R}^n$ if $\exists c_1,c_2 > 0$ s.t. $\forall x\in\mathbb{R}^n$
>$$c_1 \lVert x \rVert \leq \lVert x \rVert' \leq c_2\lVert x \rVert$$
>two metrics $d,d'$ are equivalent on a set $E$ if $\exists c_1,c_2 > 0$ s.t. $\forall x,y \in E$
>$$c_1d(x,y)\leq d'(x,y)\leq c_2d(x,y)$$
>Note that $c_1,c_2$ here are constants.

**Theorem 3.4.9** $\frac{1}{n}\lVert x \rVert_1 \leq \lVert x \rVert_{\infty} \leq \lVert x \rVert_2 \leq \lVert x \rVert_1$ for all $x \in \mathbb{R}^n$
Proof:
	Fix $x \in \mathbb{R}^n$, then $\lVert x \rVert_{\infty} = \max\{|x_1|,\cdots,|x_n|\}$, so $\exists j$ s.t. $\lVert x \rVert_{\infty}=|x_j|$. But then $|x_j| = \sqrt{x_j^2} \leq \sqrt{x_i^2} = \lVert x \rVert_2$. $(\lVert x \rVert)^2 = \sum_j |x_j|^2 \leq (\sum_j |x_j|)^2 = (\lVert x \rVert_1)^2$, so we have $\lVert x \rVert_2 \leq \lVert x \rVert_1$.
	$n\lVert x \rVert_{\infty} = |x_j| + |x_j| + \cdots + |x_j| \geq |x_1| + |x_2| + \cdots + |x_n| = \lVert x \rVert_1$, which ends our proof.
Remark. Suppose $\lVert \cdot \rVert, \lVert \cdot \rVert'$ are two equivalent norms, then  $\exists c_1,c_2 > 0$ s.t. $\forall z\in\mathbb{R}^n$, $c_1 \lVert z \rVert \leq \lVert z \rVert' \leq c_2\lVert z\rVert$. Then $\forall x,y \in \mathbb{R}^n$, $\forall x\in\mathbb{R}^n$, $c_1 \lVert x-y \rVert \leq \lVert x-y \rVert' \leq c_2\lVert x-y \rVert$, so the two metric $d = \lVert x-y \rVert$, $d' = \lVert x-y \rVert'$ are equivalent.

**Lemma 3.4.10** Suppose $d,d': E \rightarrow [0,\infty)$ are two equivalence metric.
1) $\{S_n\}$ a Cauchy sequence with respect to $d \iff \{S_n\}$ is a Cauchy sequence with respect to $d'$.
2) $\{S_n\} \subseteq E$ converges with respect to $d \iff \{S_n\}$ converges with respect to $d'$.
Proof:
	1) Since $d,d'$ are equivalent, $\exists c_1,c_2 > 0$ s.t. $c_1d(x,y) \leq d'(x,y) \leq c_2d(x,y), \forall x,y$. Suppose $\{S_n\}$ is a Cauchy sequence with respect to $d$. Then given $\varepsilon > 0$, $\exists N$ s.t. $n,m \geq M \implies d'(s_n,s_m) < c_1\varepsilon$, and then $n,m \geq N$, $d(s_n,s_m) \leq \frac{1}{c}d'(s_n,s_m) < c_1 d'(s_n,s_m) < c_1< \frac{1}{c_1}c_1\varepsilon = \varepsilon$. The converse is similar.
	3) #TODO 

**Corollary 3.4.11** $(\mathbb{R}^n,d_2), (\mathbb{R}^n,d_{\infty})$ are complete: Cauchy sequences converge.
Proof:
	Suppose $d: \mathbb{R}^n\times \mathbb{R}^n\rightarrow [0,\infty)$ is a metric equivalent to $d_1$, and $\{S_n\}$ is a Cauchy sequence with respect to $d$. Then $\{S_n\}$ is a Cauchy sequence with respect to $d_1$, hence converges, hence converges with respect to $d$. Since $d_2,d_{\infty}$ are equivalent to $d_1$, we are done.

#### *Topology
Recall if $(E,d)$ is a metric space, then we have a notion of an open set 
$O: E$ is open $\iff \forall x \in O, \exists r(x) = r >0$ s.t. $B_{r(x)}(x) \subseteq O$. 
We prove 3 properties of open sets: 1) $\varnothing, E$ are open. 2) If $O,O'$ are open then so is $O \cap O'$. 3) If $\{O_{\alpha}\}_{\alpha \in A}$ is a collection of open sets, then $\cup_{\alpha \in A} O_{\alpha}$ is open.

>[!note] Def (Topology)
>A topology $\mathcal{T}$ on a set $X$ is a collection of subset of $X$ (so $\mathcal{T} \subseteq \mathbb{P}(X)$,where $\mathbb{P}(X)$ is the power set) whose elements are called "open sets" s.t.
>1) $\varnothing, X \in \mathcal{T}$
>2) If $O,O'\in \mathcal{T}$, then  $O \cap O' \in \mathcal{T}$. 
>3) $\forall\{O_{\alpha}\}_{\alpha \in A} \subseteq \mathcal{T}$, then $\cup_{\alpha \in A}O_{\alpha}\in\mathcal{T}$.

Note: $\mathbb{R}^n$ comes with the standard topology and metric $(d_2)$
Note: the "open set" here does not necessarily have anything to do with metric.

We proved: if $(E,d)$ is a metric space, then there is a topology $\mathcal{T}_d$ with associated to $d$.

>[!note] Def (Topological space)
>A topological space is a pair $(X,\mathcal{T})$, where $\mathcal{T}$ is a topology on a set $X$.

**Lemma 3.4.12** Let $d, d'$ be two equivalent metric on a set $E$, then $\mathcal{T}_d = \mathcal{T}_{d'}$, i.e., they give rise to the same topology.
Proof:
	It's enough to show that $\mathcal{T}_d \subseteq \mathcal{T}_{d'}$, then by the same argument $T_{d'} \subseteq T_d$.
	Since $d,d'$ are equivalent, $\exists c > 0$ s.t. $cd(x,y)\leq d'(x,y), \forall x,y$. Suppose $O \subseteq \mathcal{T}_d$ an open set, then $\forall x \in O, \exists r(x)$ s.t. $B_{r(x)}^d(x) \subseteq O$. If $y \in B_{cr}^{d'}(x)$ (another ball risen by $d'$ centered at $x$). then $cr > d'(x,y) (def\:of\:y \in B_{rc}^{d'}(x)) \geq cd(x,y) \implies d(x,y) < r \implies y \in B_{r(x)}^d(x)$ 
	$\implies B_{rc}^{d'}(x) \subseteq B_{r(x)}^d(x) \subseteq O$. Since $x$ is arbitrary, $O \in \mathcal{T}_{d'}$, which gives $\mathcal{T}_d\subseteq \mathcal{T}_{d'}$

>[!note] Def (Convergent sequence in a topological space)
>Let $(X,\mathcal{T})$ be a topological space, $\{S_n\}\subseteq X$ a sequence. Then $S_n \rightarrow L\in X$ if $\forall$ open set $U \subseteq X$ with $L \in U$, $\exists N$ s.t. $n > N \implies S_n\in U$.

Exercise: If $\mathcal{T} = \mathcal{T}_d$ for some metric $d$, then the two notions of convergence agree.

**Corollary 3.4.13** Let $E$ be a set, $d,d'$ two equivalent metric, then $S_n \rightarrow L\in E$ with respect to $d$ $\iff S_n \rightarrow L \in E$ with respect to $d'$. 

## 3.5 Compactness
*note: def different from the book*

>[!note] Def (Open cover)
> Let $(X,\mathcal{T})$ be a topological space, $K \subseteq X$ a subset, then an open cover of $K$ is a collection of open sets $\{O_{\alpha}\}_{\alpha \in A} \subseteq \mathbb{P}(X)$ s.t. $K \subseteq \cup_{\alpha \in A}O_{\alpha}$. 
>

Ex. $\{(n,n+2)\}_{n \in \mathbb{Z}}$ is an open cover of $\mathbb{R}$
Ex. $(E,d)$ metric space, $\{B_{1-1/n}(x)\}_{n\in \mathbb{N}}$ is an open cover in $\mathbb{R}$. 

>[!important] Def (Compactness)
>A subset $K$ of a topological space $(X,\mathcal{T})$ is compact if for every open cover $\{U_{\alpha}\}_{\alpha \in A}$ of $K$, $\exists n,\alpha_1,...\alpha_n \in A$ s.t. $K \subseteq U_{\alpha_1} \cup \cdots \cup U_{\alpha_n}$

*Any open over has a finite open subcover that covers the subset*

Ex. any finite set $\{x_1,...,x_n\}$ is compact. if $\{U_{\alpha}\}_{\alpha \in A}$ is an open cover, then $\forall i$, $\exists \alpha_i$ s.t. $x_i \in U_{\alpha_i}$ and then $\{x_1,...,x_n\} \subseteq U_{\alpha_1} \cup \cdots \cup U_{\alpha_n}$
Counter(?) example: $\mathbb{R}$ is not compact: $\{(n,n+2)\}_{n \in \mathbb{Z}}$ is an open cover with no finite subcover.
Counter(?) example 2: $\mathbb{N} \subseteq \mathbb{R}$ is not compact. $\{U_i = (i-1/2,i+1/2)\}_{i \in\mathbb{N}}$ is an open cover of $\mathbb{N}$ no finite subcover.
Counter(?) example 3: $E$ = a set. $d(x,y) = 1$ for $x \neq y$. This is the "discrete metric". Then every set is bounded. If $K \subseteq E$ is a set, then $\{\{x\}\}_{x \in K}$ is an open cover of $K$. So $K$ is compact $\implies K$ is finite.

Remark. to prove compactness is to prove an open subcover.

**Lemma 3.5.1** Let $(X,\mathcal{T})$ be a topological space, $K \subseteq X$ compact, $C \subseteq X$ closed. Then $K \cap C$ is compact.
Proof:
	Suppose $\{U_{\alpha}\}_{\alpha \in A}$ is an open cover of $K \cap C$. Then $X \setminus C \cup \{U_{\alpha}\}_{\alpha \in A}$ is an open cover of $K$. Since $K$ is compact, $\exists \alpha_1,\cdots,\alpha_n$ s.t. $K \subseteq (K\setminus C) \cup U_{\alpha_1} \cup \cdots \cup U_{\alpha_n}$,$(K = (K \cap C) \cup (K \setminus C) \subseteq (X\setminus C) \cup (X\setminus C) \cup_{\alpha \in A}U_{\alpha}$) which implies that $K\cap C \subseteq U_{\alpha_1} \cup \cdots \cup U_{\alpha_n}$, and we are done.

**Theorem 3.5.2** Let $(E,d)$ be a metric space. If $K \subseteq E$ is compact, then $K$ is closed and bounded.
Proof:
	($K$ is bounded) Choose any $x \in E$, then $E = \cup_{n=1}^{\infty}B_n(x)$, so $\{B_n(x)\}_{n=1}^{\infty}$ is an open cover of $K$. So $\exists n_1 < n_2 < \cdots < n_k$ s.t. $K \subseteq B_{n1}(x) \cap \cdots \cap B_{nk}(x) = B_{nk}(x)$
	($K$ is closed)    If $K = E$, we are done, $K$ is closed since $\varnothing = E\setminus K$ is open. If $K \neq E$, let $x \in E \setminus K$, then $K \subseteq E \setminus \{x\}$. $U_r = E \setminus \overline{B_r}(x)$ is open for all $r$. Now consider the union. $\cup_{r > 0}(E \setminus \overline{B_r}(x)) = E \setminus \cap_{r>0}\overline{B_r}(x) = E \setminus \{x\} \supseteq K$ $\implies \{U_r\}_{r > 0}$ is an open cover of $K$. Since $K$ is compact, $\exists r_1<\cdots<r_k$ s.t. $K \subseteq U_{r1}\cup \cdots \cup U_{rk} = E \setminus (\overline{B_{r1}}(x)\cap \cdots \cap \overline{B_{rk}}(x)) = E \setminus \overline{B_{r1}}(x)$ (since it is closed) $\implies B_{r1}(k)\cap K = \varnothing \implies E\setminus K$ is open.
*The converse is false by simply taking any metric that is bounded: d = min(|x-y|,1), R: closed and bounded, but not compact. Since every singletons $\{x\}$ is closed and open, there is no finite subcover of any infinite set*.
Remark. In $(\mathbb{R}^n,d_2)$ a metric space is compact $\iff$ it is closed and bounded

Remark. In general, compact sets need not be closed.
Ex. $X =\{a,b\}, \mathcal{T} = (X,\varnothing, \{a\})$. $K = \{a\}$ is compact (finite) but not closed since $X \setminus K = \{b\}\notin \mathcal{T}$
Note that singletons are compact since they are finite.

**Theorem 3.5.3** Let $X$ be a topological space, $K_1 \supseteq K_2 \supseteq \cdots \supseteq K_n \supseteq \cdots$ a sequence of compact sets, then $K = \cap_{n=1}^{\infty}K_n \neq \varnothing$ (and compact: since the intersection sets in $K_1$)
 Note: $X = \mathbb{R}, K_n = [0,\infty), \cap_{n\geq 1}K_n = \varnothing$. $U_n = (0,1/n), \:\:\cap U_n = \varnothing$. Such examples don't hold because they are not closed.

**Theorem 3.5.4** Let $X$ be a topological space, $K_1 \supseteq K_2 \supseteq \cdots \supseteq K_n\supseteq\cdots$ sequences of nonempty nested closed compact sets. Then $\cap_{i=1}^{\infty}K_i \neq \varnothing$.
Proof:
	Suppose $\cap_{i=1}^{\infty}K_i = \varnothing$. Then $E = E\setminus \cap_{i=1}^{\infty}K_i =\cup_{i=1}^{\infty}(E \setminus K_i)$. We get an open cover $\{E\setminus K_n\}_{n=1}^{\infty}$ of $E$ and of $K_1$. Since $K_1$ is compact, $\exists n_1 < n_2 <\cdots < n_l$ s.t. $K \subseteq (E\setminus K_1) \cup \cdots \cup (E\setminus K_{n_l}) = E \setminus\cap_{i=1}^{l}K_{n_i} = E \subseteq K_{n_l}$. But $K_{n_l}\subseteq K_1$, contradiction.


>[!important] Def (Sequentially compact)
>A subset $K$ of a topological space is sequentially compact if every sequence in $K$ has a convergent subsequence whose limit is in $K$.

Ex 3.5.1. Suppose $K\subseteq \mathbb{R}^n$ is closed and bounded. Then $K$ is sequentially compact:  
Proof:
	Every bounded sequence $\{s_n\}$ in $K$ has a convergent subsequence $\{s_{n_k}\}$ by Bolzano-Weierstrass since $K$ is bounded. Since $K$ is closed, $L = \lim_{n\rightarrow \infty}\{s_{n_k}\} \in K$.  ^7302cd

**Lemma 3.5.5** Suppose $(E,d)$ is a metric space and $K \subseteq E$ is compact, then $K$ is sequentially compact.
Proof:
	Let $\{S_n\}$ be a sequence in $K$. We argue that (1) $\exists x \in K$ s.t. $\forall \varepsilon > 0, \{n|s_n \in B_{\varepsilon}(x)\}$ is infinite, and this (1) implies that there is a subsequence #question  $\{S_{n_k}\}$ that converges to $x$. Take $\varepsilon = 1, 1/2,1/3\cdots$ and find $n_1<n_2<\cdots <n_k\cdots$ s.t. $S_{n_k} \in B_{1/n}(x)$. To see (1), suppose it is false. Then $\forall x \in K$, $\exists \varepsilon = \varepsilon(x)$ s.t. $\{n | s_n \in B_{\varepsilon(x)}(x)\}$ is finite. Then $\{B_{\varepsilon(x)}(x)\}_{x \in K}$ is an open cover of $K$. Since $K$ is compact, $\exists x_1,\cdots x_l \in K$ s.t. $K \subseteq B_{\varepsilon(x_1)}(x_1) \cap \cdots \cap B_{\varepsilon(x_l)}(x_l)$. But then $\{n| s_n\in B_{\varepsilon(x_1)}(x_1)\cup\cdots \cup B_{\varepsilon(x_l)}(x_l)\}$ is finite, a contradiction.


>[!important] Def (Totally bounded)
>A subset $K$ of a metric space $(E,d)$ is totally bounded if $\forall s > 0$, $\exists x_1,\cdots, x_n \in K$ s.t. $K \subseteq B_{\varepsilon}(x_1)\cap \cdots \cap B_{\varepsilon}(x_n)$. i.e., $\forall \varepsilon > 0$, $K$ can be covered by finitely many balls of radius $\varepsilon$.

**Lemma 3.5.6** Suppose $(E,d)$ is a metric space, $K \subseteq E$ sequentially compact. Then $(K,d)$ is complete and totally bounded.
Proof: 
	Suppose $\{S_n\} \in K$ is Cauchy. Since $K$ is sequentially compact, $\{S_n\}$ has a convergent subsequence and since $\{S_n\}$ is Cauchy, $\{S_n\}$ converges to $L=$ lim $S_{n_k}$ #question . Suppose $K$ is not totally bounded, then $\exists \varepsilon > 0$ s.t. $K$ cannot be covered by finitely many $\varepsilon$ balls $\implies$ $\exists x_1 \in K$ s.t. $K\setminus B_{\varepsilon}(x_1) \neq \varnothing$. Then $\exists x_2 \in K \setminus B_{\varepsilon}(x_1)$ s.t. $K \setminus (B_{\varepsilon}(x_1) \cup B_{\varepsilon}(x_2)) \neq \varnothing$.... $\exists x_n \in K \setminus (B_{\varepsilon}(x_1) \cup \cdots \cup B_{\varepsilon}(x_{n-1}))$ s.t. $K \setminus (B_{\varepsilon}(x_1) \cup \cdots \cup B_{\varepsilon}(x_{n-1}))\neq \varnothing$ (\*). We get a sequence $\{x_n\}$ in $K$ with $d(x_n,x_m) \geq \varepsilon$ for all $n \neq m$. Then $\{x_n\}$ has no Cauchy subsequence $\implies \{x_n\}$ has no convergent subsequences. This contradicts sequential compactness.
	\*: This is a recursive definition, $\{x_n\}$ is infinite.

**Lemma 3.5.7** Let $(E,d)$ be a metric space, $K \subseteq E$ complete and totally bounded, then $K$ is compact. 
Proof:
	Suppose $\exists$ an open cover $\{U_{\alpha}\}_{\alpha \in A}$ of $K$ with no finite subcover. Since $K$ is totally bounded, $K$ can be covered with finitely many balls of radius 1. $\implies \exists x_0 \in K$ s.t. $B_1(x_0)$ cannot be covered by finitely many $U_{\alpha}$. There is a finite cover of $K$ by balls of radius $1/2 \implies$ $\exists x_1$ s.t. $B_{1/2}(x_1)\cap B_1{x_0} \neq \varnothing$ and $B_{1/2}(x_1)$ cannot be covered by finitely many $U_{\alpha}$. Proceeding this way we get a sequence $x_0,x_1,\cdots,x_n,\cdots$  s.t. $B_{1/2^n}(x_n) \cap B_{1/2^{n-1}}(x_{n-1})$, and each $B_{1/2^n}(x_n)$ cannot be covered by finitely manny $U_{\alpha}$s. Then $d(x_n, x_{n+k}) \leq d(x_n,x_{n+1}) + d(x_{n+1}, x_{n+2}) + \cdots + d(x_{n+k-1},x_{n+k})  < \frac{1}{2^{n-1}} (1 + \frac{1}{2} + \cdots + \frac{1}{2^k}) < \frac{1}{2^{n-2}}$Thus $\{x_n\}$ is Cauchy. Since $K$ is complete, $x_n \rightarrow y$ for some $y \in K$. Since $\{U_{\alpha}\}_{\alpha\in A}$ is a cover, $\exists \alpha_0$ s.t. $y \in U_{\alpha_0}$. Since $U_{\alpha_0}$ is open, $\exists r > 0$ s.t. $B_r(y_0) \subseteq U_{\alpha_0}$. Since $x_n \rightarrow y$, $\exists n$ s.t. $x_n \in B_{r/2}(y)$ and $\frac{1}{2^n} < \frac{r}{2}$. $B_{1/2^n}(x_n) \subseteq B_r(y) \subseteq U_{\alpha_0}$. But according to the construction of $B_{1/2^n}(x_n)$, we get a contradiction.

>[!note] Summary
>For a subset $K$ of a metric space, (1)$\implies$ (2), (2)$\implies$ (3), (3)$\implies$ (1), thus TFAE:
>1) $K$ is compact
>2) $K$ is sequentially compact
>3) $K$ is compete and totally bounded.

>[!Note] Theorem (Heine-Borel)
>A subset $K$ of $\mathbb{R}^n$ is compact $\iff K$ is closed and bounded.

Proof:
	($\implies$) is true for any metric space.
	($\impliedby$) Suppose $K$ is closed and bounded, then by [[#^7302cd|Ex 3.5.1]], $K$ is sequentially compact and hence compact.

Ex. $\mathbb{R}, d=\min(1, |x-y|)$. $(\mathbb{R},d)$ is bounded but not totally bounded since it's complete but not compact. $B_{1/2}^d(x)=(x-1/2,x+1/2), \forall x$ and $\mathbb{R}$ cannot be covered by finitely many balls of radius $1/2$. Thus only in $(\mathbb{R},d_2)$ or ($d_1$ or $d_{\infty}$) bounded $\implies$ totally bounded.


# Chapter 4 Continuous functions
## 4.1 Continuity
>[!important] Def (Continuous at a point)
>Let $(E,d)$, $(E',d')$ be two metric space. A function $f: E \rightarrow E'$ is continuous at $p \in E$ if $\forall \varepsilon > 0$, $\exists \delta > 0$ so that $\forall x \in E$, $d(x,p) < \delta \implies d'(f(x),f(p)) < \varepsilon$. i.e. $f(B_{\delta}^d(p)) \subseteq B_{\varepsilon}^{d'}(f(p))$

Remark. think of "$\delta-\varepsilon$ close"

>[!important] Def (Continuous function)
>A function $f: E \rightarrow E'$ is continuous if it is continuous at every point $p$ of $E$.

Ex 1. $(E,d)$ a metric space, $q \in E$ a point, $f: E \rightarrow \mathbb{R},\: f(p) = d(p,q)$. Then $f$ is continuous at every $p \in E$: $|f(x) - f(p)| = |d(x,q) - d(p,q)| \leq d(x,q)$. So $\forall \varepsilon > 0, d(x,p) < \varepsilon \implies |f(x) - f(p)| < \varepsilon = \delta$.
Ex 2. $f: \mathbb{R} \rightarrow \mathbb{R}, f(x) = \begin{cases} 1, x\:\:rational\\ 0,x\:\:irrational\end{cases}$ is not continuous at any $p \in \mathbb{R}$. To see this, $\forall p \in \mathbb{R}, \delta > 0, B_{\delta}(p) = (p-\delta,p+\delta)$ contains both rationals and irrationals. If $p$ is rational, then $f(p) = 1$ and $\forall \delta > 0$, $\exists x \in B_{\delta}(1)$ s.t. $f(x) = 0$. Then for all $\varepsilon < 1$ (1/2, for example), no matter which $\delta$ we choose, $|x-p| < \delta \not\implies |f(x) - 1| < 1/2$. Similar problem happens if $f(p) = 0$.

>[!note] Theorem 4.1.1
>$f: (E,d) \rightarrow (E',d')$ is continuous $\iff \forall U \subseteq E', U$ open, $f^{-1}(U)$ is open.

Proof:
	($\implies$) Suppose $f$ is continuous, $U \subseteq E'$ open, then $\forall p \in f^{-1}(U)$, $f(p) \in U \implies \exists \varepsilon > 0$ s.t. $B_{\varepsilon}(f(p))\subseteq U$. Since $f$ is continuous at $p$, $\exists \delta > 0$ s.t. $f(B_{\delta}(p))\subseteq B_{\varepsilon}(f(p))$, which implies that $f(B_{\delta}(p))\subseteq U$, and thus $B_{\delta}(p)\subseteq f^{-1}(U)$. Since $p \in f^{-1}(U$) is arbitrary, $f^{-1}(U)$ is open.
	($\impliedby$) Suppose $\forall U \subseteq E', U$ open, $f^{-1}(U)$ is open. Given $p \in E$ and $\varepsilon > 0$, $B_{\varepsilon}(f(p))$ is open in $E$. Since $p \in f^{-1}(f(p))\subseteq f^{-1}(B_{\varepsilon}(f(p)))$ and $f^{-1}(B_{\varepsilon}(f(p)))$ is open, $\exists \delta > 0$ s.t. $f(B_{\delta}(p))\subseteq B_{\varepsilon}(f(p))$ and $f$ is continuous at $p$. 


**Corollary 4.1.2** $f: (E,d) \rightarrow (E',d')$ is continuous $\iff\forall C \subseteq E'$, $C$ closed, $f^{-1}(C)$ is closed.

>[!note] Def (Continuous function )
>A map/function $f: (X, \mathcal{T})\rightarrow (X', \mathcal{T}')$ between two topological spaces is continuous if $\forall U \in \mathcal{T}'$, $U$ open, $f^{-1}(U) \in \mathcal{T}$. i.e., preimages of open sets are open.

Remark. Theorem 4.1.1 says that the notion of continuity of a map depends only on the topologies:
If $d_1,d_2$ are two metrics s.t. $\mathcal{T}_{d_1} = \mathcal{T}_{d_2}$, $d_1',d_2'$ are two metrics s.t. $\mathcal{T}_{d_1'} = \mathcal{T}_{d_2'}$. Then $f: (E, d_1) \rightarrow (E', d_1')$ is continuous iff  $f: (E, d_2) \rightarrow (E', d_2')$ is continuous.

**Theorem 4.1.3** The composite of two continuous maps is continuous. If $f: (X, \mathcal{T}_X) \rightarrow (Y, \mathcal{T}_Y),$$g: (Y, \mathcal{T}_Y) \rightarrow (Z, \mathcal{T}_Z)$ are continuous, then $g\circ f : (X, \mathcal{T}_X)\rightarrow (Z, \mathcal{T}_Z)$ is continuous.
Proof:
	Suppose $W \subseteq Z$ is open, then $g^{-1}(W) \subseteq Y$ is open $\implies f^{-1}(g^{-1}(W))$ is open in $X$. But $f^{-1}(g^{-1}(W)) = (f\circ g)^{-1}(W)$, so $(f\circ g)^{-1}(W)$ is open in $X$ and hence $f\circ g$ is continuous.

**Theorem 4.1.4** Images of compact sets under continuous functions are compact.  If $f: X \rightarrow Y$ is continuous and $K \subseteq X$ is compact, then $f(X) \subseteq Y$ is compact.
Proof: 
	Let $\{U_{\alpha}\}_{\alpha \in A}$ be an open cover of $f(K)$, then $\{f^{-1}(U_{\alpha})\}_{\alpha \in A}$ is an open cover of $K$. Since $K$ is compact, $\exists \alpha_1 \cdots \alpha_n$ s.t. $K \subseteq f^{-1}(U_{\alpha_1}) \cup \cdots \cup f^{-1}(U_{\alpha_n})$ $\implies f(K) \subseteq U_{\alpha_1}\cup \cdots \cup U_{\alpha_n}$ and $f(K)$ is compact.

**Corollary 4.1.5** Let $(E,d)$ be a metric space, $X$ a topological space, $K\subseteq X$ compact and $f: X \rightarrow E$ is continuous, then $f(k)$ is complete, totally bounded, sequentially compact and closed. 

**Corollary 4.1.6** Suppose $X$ is a topological space, $f: X \rightarrow \mathbb{R}$ continuous and $K \subseteq X$ compact, then $\exists x_1,x_2\in X$ s.t. $\forall x\in X$, $f(x_1)\leq f(x) \leq f(x_2)$. i.e., $f$ achieves maximum and minimum on $X$. 
Proof:
	$f(K)$ is closed and bounded in $\mathbb{R}$, hence $\exists x_1,x_2 \in\mathbb{R}$ s.t. $f(x_1) = \inf (f(K)), f(x_2) = \sup(f(K))$

## 4.2 Continuity and Limits
>[!note] Def (Cluster point of a topological space)
>Let $X$ be a topological space, $S \subseteq X$ a subspace, then $x\in X$ is a cluster point of  $S$ if $\forall$ open set $U$ with $x\in U, (U\setminus \{x\})\cap S$ is nonempty. If $E$ is a metric space, $x$ is a cluster point of $S$ iff $\exists$ a sequence $\{S_n\} \subseteq S\setminus\{x\}$ s.t. $s_n \rightarrow x$.

Ex. $S = \{0\} \cup [1,2] \subseteq \mathbb{R}$, $d(x,y) = |x-y|$. 0 is not a cluster point. Every $x \in [1,2]$ is a cluster point of $S$.

>[!note] Def (Cluster point of a metric space)
>Suppose $(E,d)$, $(E',d')$ are metric spaces, $A \subseteq E$, $f: A \rightarrow E'$, $p$ is a cluster point of $A$. Then 
>$$\lim_{x \rightarrow p}f(x) = q$$
>If $\forall \varepsilon > 0$, $\exists \delta > 0$ s.t. $x \in A\cap B_{\delta}(p), x \neq p, d'(f(x),q) < \varepsilon$

Remarks. 
(1) $p\in A$ is not necessary. i.e., $f(p)$ need not be defined.
(2) Even if $p \in A$ we are requiring $f(p) =\lim_{x\rightarrow p}f(x)$
Ex. $f:\mathbb{R}\rightarrow \mathbb{R}, f(x) = 1, x=0,f(x) = 0, o.w.$ Then $\lim_{x \in \rightarrow 0} f(x)= 0 \neq 1 = f(0)$.

**Lemma 4.2.1** $E,E'$ metric spaces, $p$ cluster point of $E$. Then $f: E \rightarrow E'$ is continuous at $p \iff$ $\lim_{x \rightarrow p} f(x) = f(p)$.
Proof:
	#TODO 
	Note that if $p$ is not a cluster point, then $\exists r$ s.t. $B_r(p)\setminus \{p\}\cap E = \varnothing$. i.e. $B_r(p) = \{p\}$. And then any $f: E \rightarrow E'$ is continuous at $p$. 

**Theorem 4.2.2** $E,E'$ metric spaces, $f: E \rightarrow E'$ is continuous at $p \in E$ $\iff \forall$ sequences $\{S_n\} \in E$ with $S_n \rightarrow p$, we have $f(s_n) \rightarrow f(p)$.
Proof:
	($\implies$) Suppose $S_n \rightarrow p$ and $f$ is continuous. Then given $\varepsilon > 0$, $\exists \delta > 0$ s.t. $d(x,p) < \delta \implies d'(f(x),f(p)) < \varepsilon$. Since $S_n \rightarrow p$, $\exists N$ s.t. if $n \geq N$, $d(x,p) < \delta \implies d'(f(x),f(p)) < \varepsilon \implies f(p) \rightarrow f(x)$
	($\impliedby$) We prove the contrapositive. Suppose $f$ is not continuous at $p$. We construct $\{S_n\}$ s.t. $S_n \rightarrow p$ but $f(S_n) \not\rightarrow f(p)$. Since $f$ is not continuous at $p$, $\exists \varepsilon_0 > 0$ s.t. $\forall \delta > 0$, $\exists x_r \in B_{\delta}(p)$ with $f(x_r)\notin B_{\varepsilon_0}(f(p))$. Let $S_n = x_{1/n}$. Then $s_n \in B_{1/n}(p)$ (hence $s_n \rightarrow p$) and $f(s_n)\notin B_{\varepsilon_0}(f(p))$  (hence $f(s_n) \not\rightarrow f(p)$)

**Theorem 4.2.3** Suppose $f,g: (E,d) \rightarrow \mathbb{R}$ are continuous at $p \in E$. Then $f + g, f\cdot g$ are continuous at $p$. If $g(p) \neq 0$, $f/g$ is also continuous.
Proof:
	Suppose $S_n \rightarrow p$, then $f(s_n) \rightarrow f(p), g(s_n)\rightarrow g(p)$. Hence $(f+g)(s_n) = f(s_n) + g(s_n)$ $\rightarrow f(p) + g(p) \implies f+g$ is continuous. Other proofs are similar.

**Theorem 4.2.4** Suppose $f = (f_1,\cdots,f_n): E \rightarrow \mathbb{R}^n$ is a function, $p \in E$. Then $f$ is continuous at $p \iff f_1\cdots f_n$ are all continuous at $p$.
Proof:
	A sequence $t_k = (t_k^{(1)}, \cdots, t_n^{(n)}) \rightarrow \mathbb{R}^n$ converges to $q = (q_1,\cdots, q_n) \in \mathbb{R}^n \iff$ $t_k^{(k)} \rightarrow q^{(i)}, i = 1,2, \cdots n.$ 

#### Uniform continuity
>[!note] Def (Uniformly continuous)
>$f: (E,d) \rightarrow (E',d')$ is uniformly continuous if $\forall \varepsilon > 0$, $\exists \delta = \delta_{\varepsilon} > 0$ s.t. 
>$$d(x,p) < \delta \implies d'(f(x),f(p))< \varepsilon, \forall x,p$$

Ex. $f(x) = x^2$. $f: [0,\infty) \rightarrow \mathbb{R}$ is not uniformly continuous. 
Proof: $|f(x) - f(y)| = x^2-y^2= |x-y| |x+y| \geq 2\cdot \min(x,y)\cdot |x-y|$. There for $\forall \delta$ if $x,y > \frac{1}{\delta}$ and $|x-y| = \delta / 2$. We have $|f(x) - f(y)| \geq 2 \cdot \frac{1}{\delta}\cdot \frac{\delta}{2} = 1$. 

**Lemma 4.2.5** Suppose $f: E \rightarrow E'$ is uniformly continuous, then for any Cauchy sequences $\{S_n\}$ in $E$, $f(s_n)$ is Cauchy.
Proof:
	Since $f$ is uniformly continuous, $\forall \varepsilon > 0$, $\exists \delta$ s.t. $d(x,y) < \delta \implies d'(f(x),f(p)) < \varepsilon$. Fix $\varepsilon > 0$ and choose $\delta$. Since $\{S_n\}$ is Cauchy, $\exists N$ s.t. $n,m \geq N \implies d(s_n,s_m) < \delta$. And then $d'(f(s_n),f(s_m)) < \varepsilon$.
	
Ex. $f: (0,1) \rightarrow \mathbb{R}, f(x) = \sin(1/x)$. Claim: $f$ is not uniformly continuous. Reason: $S_n = \frac{1}{\pi /2 + n\pi} \rightarrow 0$,not in $(0,1)$ but still Cauchy. $f(s_n) = \sin(\frac{\pi}{2} + n\pi ) = (-1)^n$. So $f$ is not uniformly continuous.

**Theorem 4.2.6** Suppose $f: E \rightarrow E'$ is continuous and $E$ is compact, then $f$ is uniformly continuous. 
Proof:
	Given $\varepsilon$ we want $\delta = \delta_{\varepsilon}$ s.t. $d(x,y) < \delta \implies d(f(x),f(y)) < \varepsilon$. Since $f$ is continuous, $\forall x$, $\exists \delta_x$ s.t. $d(x,y) < \delta_x \implies d'(f(x),f(y)) < \varepsilon/2$. $\{B_{\delta_{x/2}}(x)\}_{x \in E}$ is an open cover of $E$ $\implies \exists n,x_1,\cdots, x_n$ s.t. $E = B_{\delta_{x1}/2} \cup \cdots \cup B_{\delta_{x_n}/2}(x_n)$. Let $\delta = \min(\delta x_1/2,\cdots \delta x_n/2)$. Suppose $d(p,q) < \delta$. Then $q \in B_{\delta x_i /2}(x)$ for some $i$. Then $d(p,x_i) \leq d(p,q) + d(q,x_i) < \delta + \delta_ {x_1}/2 \leq \delta_{x_i}$. $p \in B_{\delta_{x_i}}(x_i)$. Since $p,q \in B_{\delta_{x_i}}(x_i)$, $d'(f(p),f(q)) \leq d'(f(p), f(x_i)) + d'(f(x_i),f(p)) < \varepsilon /2 + \varepsilon /2 = \varepsilon$. 

>[!note] Def (Pointwise continuity)
>$\{f_n:(E,d)\rightarrow (E',d')\}_{n=1}^{\infty}$ sequence of functions between two metric spaces. The sequence $\{f_n\}$ converges pointwise to $f: E\rightarrow E'$ if $\forall p \in E$, $f_n(p) \rightarrow f(p)$

Pointwise limit of continuous functions need not be continuous.

>[!note] Def (Uniform convergence)
>$\{f_n:(E,d)\rightarrow (E',d')\}_{n=1}^{\infty}$a  sequence of functions between two metric spaces, $A \subseteq E$ a subspace. $f_n \rightarrow f$ uniformly on $A$ if $\forall \varepsilon > 0$, $\exists N$ s.t. $n\geq N \implies d'(f_n(p), f(p)) < \varepsilon, \forall p \in A$. 
>Equivalently, $\forall \varepsilon > 0$, $\exists N$ s.t. $n \geq N \implies \sup\{d'(f_n(p),f(p))|p\in A\} < \varepsilon$. $\lim_{n\rightarrow \infty} \sup \{d'(f_n(p),f(p))|p\in A\} = 0$

Ex. $f_n(x) = x^n, f_n : [0,1]\rightarrow [0,1]$ on $A = [0,a]$. $a < 1$, $f_n$ converges uniformly. Check $\sup\{|x^n-0|: 0 \leq x \leq a\} = a^n \rightarrow 0$. $\{f_n\}$ converges to 0 on $[0,1)$ but not uniformly, $\sup\{|x^n-0|: 0 \leq x \leq 1\} = 1 \not\rightarrow 0$
Ex. $f_n(x) = \frac{nx}{1 + n^2x^2}, f_n: \mathbb{R}\rightarrow\mathbb{R}$. Since $f_n(0) = 0, \forall n$, and for $x \neq 0, |\frac{nx}{1+n^2x^2}| \leq |\frac{nx}{n^2x^2}| = \frac{1}{n|x|}_{n\rightarrow \infty}\rightarrow0$. Note that $f_n(\frac{1}{n}) = \frac{n/n}{1+n^2/n^2}=\frac{1}{2}\not\rightarrow 0$, so $\{f_n\}$ is not uniformly convergent.

>[!note] Def (Uniformly Cauchy)
>A sequence of functions $\{f_n: E \rightarrow E'\}_{n \in \mathbb{N}}$ is uniformly Cauchy on $A \subseteq E$ if $\forall \varepsilon > 0, \exists N$ with $n,m \geq N \implies \sup\{ d'(f_n(x),f_m(x))|x\in A\} < \varepsilon$

**Theorem** Let $\{f_n: E \rightarrow E'\}_{n\in\mathbb{N}}, E'$ complete, then $\{f_n\}$ converges uniformly on $A$ $\iff \{f_n\}$ is uniformly Cauchy.
Proof:
	($\implies$) Suppose $f_n \rightarrow f$ uniformly on $A$. Then $\forall \varepsilon > 0, \exists N$ s.t. for $n\geq N$, $\sup\{d'(f_n(x),f(x))|x\in A\} < \varepsilon/3$. Then $\forall n,m \geq N$, $\forall x \in A$, $d'(f_n(x),f_m(x))\leq d'(f_n(x), f(x)) + d'(f_m(x),f(x)) < \varepsilon/3 + \varepsilon/3$, which suggests that $\sup\{d'(f_n(x),f_m(x))|x\in A\} \leq \frac{2}{3}\varepsilon < \varepsilon$.
	($\impliedby$) Suppose $\{f_n\}$ is uniformly Cauchy on $A$. Then $\forall x \in A, \{f_n(x)\}$ is Cauchy. Since $E'$ is complete, we can define $f: A \rightarrow E'$ by $f(x) = \lim_{n\rightarrow\infty}f_n(x)$. We now argue: $f_n \rightarrow f$ is uniformly on $A$.  Recall that $\forall x \in E', h: E' \rightarrow [0,\infty), h(p) = d'(x,p)$ is continuous. Since $\{f_n\}$ is uniformly Cauchy on $A$, given $\varepsilon > 0, \exists N$ s.t. if $m,n \geq N$, then $\sup\{ d'(f_n(x),f_m(x))|x\in A\} < \varepsilon/2$. Fix $n \geq N$, then $d'(f_n(x), f(x)) = d'(f_n(x), \lim_{m \rightarrow \infty}f_m(x)) = \lim_{m \rightarrow \infty}d'(f_n(x),f_m(x)) \leq$$\sup_{m \geq n} d'(f_m(x), f_n(x))$$< \varepsilon$. Hence $\forall n \geq N, \sup\{d'(f_n(x), f(x))| x\ \in A\} \leq \varepsilon/2 < \varepsilon$.

**Theorem** Uniform limit of continuous functions is continuous.
Proof:
	Suppose $\{f_n: E \rightarrow E'\}$ converges uniformly on all of $E$. Fix $p \in E$, we prove that $f$ is continuous on $p$. For $\forall x \in E, \forall n \in \mathbb{N}$, $d'(f(p), f(x))\leq d'(f(p), f_n(p)) + d'(f_n(p),f_n(x)) + d'(f_n(x), f(x))$.  Given $\varepsilon > 0$, we want to show: $\exists \delta > 0$ s.t. if $d(x,p) < \delta$, then $d'(f(x),f(p)) < \varepsilon$. Since $f_n \rightarrow f$ converges uniformly, $\exists N$ s.t. for $n \geq N$, $d'(f_n(y), f(y)) < \varepsilon /3, \forall y \in E$. Since $f_N$ is continuous at $p$, $\exists \delta > 0$ s.t. if $d(x,p) < 0, d'(f_N(x),f_N(p)) < \varepsilon/3$. Then $\forall x$ with $d(x,p) < \delta$,
	$d'(f(p), f(x))\leq d'(f(p), f_n(p)) + d'(f_n(p),f_n(x)) + d'(f_n(x), f(x)) < \varepsilon/3+\varepsilon/3+\varepsilon/3 = \varepsilon$

>[!note] Def (Bounded function)
>Let $(E,d), (E',d')$ be two metric spaces, a function $f: E \rightarrow E'$ is bounded if $f(E) \subseteq E'$ is bounded.
>Notation: $C(E,E') = \{f: E\rightarrow E'| f\:bounded\:and\:continuous\}$

Exercise. if $f,g: E\rightarrow E'$ are bounded, then $\{d'(f(x),g(x))| x\in E\}$ is bounded. Define $D: C(E,E')\times C(E,E')\rightarrow [0,\infty)$ by $D(f,g) = \sup\{d'(f(x),g(x))| x \in E\}$
Exercise. $D$ is a metric. Then $f_n \rightarrow f$ in $(C(E,E'),D) \iff f_n \rightarrow f$ uniformly convergent.




# Chapter 5 Differentiation


# Chapter 6 Riemann Integrals


# Chapter 7 Interchange of limit operations

