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
>2) $\forall \:k$, $\forall$ open sets $U_1,...,U_k, \:U_1 \cap ...\cap U_k$ is open, i.e., **finite** intersection of open sets are open. 
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
Non-example: $\mathbb{R}$ is not compact: $\{(n,n+2)\}_{n \in \mathbb{Z}}$ is an open cover with no finite subcover.
Non-example 2: $\mathbb{N} \subseteq \mathbb{R}$ is not compact. $\{U_i = (i-1/2,i+1/2)\}_{i \in\mathbb{N}}$ is an open cover of $\mathbb{N}$ no finite subcover.
Non-example 3: $E$ = a set. $d(x,y) = 1$ for $x \neq y$. This is the "discrete metric". Then every set is bounded. If $K \subseteq E$ is a set, then $\{\{x\}\}_{x \in K}$ is an open cover of $K$. So $K$ is compact $\implies K$ is finite.

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
	Let $\{S_n\}$ be a sequence in $K$. We argue that (1) $\exists x \in K$ s.t. $\forall \varepsilon > 0, \{n|s_n \in B_{\varepsilon}(x)\}$ is infinite, and this (1) implies that there is a subsequence #question  $\{S_{n_k}\}$ that converges to $x$ ==(there are infinite points around $x$, equivalent to $x$ is a cluster point)==. Take $\varepsilon = 1, 1/2,1/3\cdots$ and find $n_1<n_2<\cdots <n_k\cdots$ s.t. $S_{n_k} \in B_{1/n}(x)$. To see (1), suppose it is false. Then $\forall x \in K$, $\exists \varepsilon = \varepsilon(x)$ s.t. $\{n | s_n \in B_{\varepsilon(x)}(x)\}$ is finite. Then $\{B_{\varepsilon(x)}(x)\}_{x \in K}$ is an open cover of $K$. Since $K$ is compact, $\exists x_1,\cdots x_l \in K$ s.t. $K \subseteq B_{\varepsilon(x_1)}(x_1) \cap \cdots \cap B_{\varepsilon(x_l)}(x_l)$. But then $\{n| s_n\in B_{\varepsilon(x_1)}(x_1)\cup\cdots \cup B_{\varepsilon(x_l)}(x_l)\}$ is finite, a contradiction.


>[!important] Def (Totally bounded)
>A subset $K$ of a metric space $(E,d)$ is totally bounded if $\forall s > 0$, $\exists x_1,\cdots, x_n \in K$ s.t. $K \subseteq B_{\varepsilon}(x_1)\cap \cdots \cap B_{\varepsilon}(x_n)$. i.e., $\forall \varepsilon > 0$, $K$ can be covered by finitely many balls of radius $\varepsilon$.

**Lemma 3.5.6** Suppose $(E,d)$ is a metric space, $K \subseteq E$ sequentially compact. Then $(K,d)$ is complete and totally bounded.
Proof: 
	Suppose $\{S_n\} \in K$ is Cauchy. Since $K$ is sequentially compact, $\{S_n\}$ has a convergent subsequence and since $\{S_n\}$ is Cauchy, $\{S_n\}$ converges to $L=$ lim $S_{n_k}$(See Lemma 3.4.3). Suppose $K$ is not totally bounded, then $\exists \varepsilon > 0$ s.t. $K$ cannot be covered by finitely many $\varepsilon$ balls $\implies$ $\exists x_1 \in K$ s.t. $K\setminus B_{\varepsilon}(x_1) \neq \varnothing$. Then $\exists x_2 \in K \setminus B_{\varepsilon}(x_1)$ s.t. $K \setminus (B_{\varepsilon}(x_1) \cup B_{\varepsilon}(x_2)) \neq \varnothing$.... $\exists x_n \in K \setminus (B_{\varepsilon}(x_1) \cup \cdots \cup B_{\varepsilon}(x_{n-1}))$ s.t. $K \setminus (B_{\varepsilon}(x_1) \cup \cdots \cup B_{\varepsilon}(x_{n-1}))\neq \varnothing$ (\*). We get a sequence $\{x_n\}$ in $K$ with $d(x_n,x_m) \geq \varepsilon$ for all $n \neq m$. Then $\{x_n\}$ has no Cauchy subsequence $\implies \{x_n\}$ has no convergent subsequences. This contradicts sequential compactness.
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
Ex. $f:\mathbb{R}\rightarrow \mathbb{R}, f(x) = 1, x=0,f(x) = 0, o.w.$ Then $\lim_{x \rightarrow 0} f(x)= 0 \neq 1 = f(0)$.

**Lemma 4.2.1** $E,E'$ metric spaces, $p$ cluster point of $E$. Then $f: E \rightarrow E'$ is continuous at $p \iff$ $\lim_{x \rightarrow p} f(x) = f(p)$.
Proof:
	#TODO 
	Note that if $p$ is not a cluster point, then $\exists\: r$ s.t. $B_r(p)\setminus \{p\}\cap E = \varnothing$. i.e. $B_r(p) = \{p\}$. And then any $f: E \rightarrow E'$ is continuous at $p$. 

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

### Uniform continuity
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

**Theorem 4.3.1** Let $\{f_n: E \rightarrow E'\}_{n\in\mathbb{N}}, E'$ complete, then $\{f_n\}$ converges uniformly on $A$ $\iff \{f_n\}$ is uniformly Cauchy.
Proof:
	($\implies$) Suppose $f_n \rightarrow f$ uniformly on $A$. Then $\forall \varepsilon > 0, \exists N$ s.t. for $n\geq N$, $\sup\{d'(f_n(x),f(x))|x\in A\} < \varepsilon/3$. Then $\forall n,m \geq N$, $\forall x \in A$, $d'(f_n(x),f_m(x))\leq d'(f_n(x), f(x)) + d'(f_m(x),f(x)) < \varepsilon/3 + \varepsilon/3$, which suggests that $\sup\{d'(f_n(x),f_m(x))|x\in A\} \leq \frac{2}{3}\varepsilon < \varepsilon$.
	($\impliedby$) Suppose $\{f_n\}$ is uniformly Cauchy on $A$. Then $\forall x \in A, \{f_n(x)\}$ is Cauchy. Since $E'$ is complete, we can define $f: A \rightarrow E'$ by $f(x) = \lim_{n\rightarrow\infty}f_n(x)$. We now argue: $f_n \rightarrow f$ is uniformly continuous on $A$.  Recall that $\forall x \in E', h: E' \rightarrow [0,\infty), h(p) = d'(x,p)$ is continuous. Since $\{f_n\}$ is uniformly Cauchy on $A$, given $\varepsilon > 0, \exists N$ s.t. if $m,n \geq N$, then $\sup\{ d'(f_n(x),f_m(x))|x\in A\} < \varepsilon/2$. Fix $n \geq N$, then $d'(f_n(x), f(x)) = d'(f_n(x), \lim_{m \rightarrow \infty}f_m(x)) = \lim_{m \rightarrow \infty}d'(f_n(x),f_m(x)) \leq$$\sup_{m \geq n} d'(f_m(x), f_n(x))$$< \varepsilon$. Hence $\forall n \geq N, \sup\{d'(f_n(x), f(x))| x\ \in A\} \leq \varepsilon/2 < \varepsilon$.

**Theorem 4.3.2** Uniform limit of continuous functions is continuous.
Proof:
	Suppose $\{f_n: E \rightarrow E'\}$ converges uniformly on all of $E$. Fix $p \in E$, we prove that $f$ is continuous on $p$. For $\forall x \in E, \forall n \in \mathbb{N}$, $d'(f(p), f(x))\leq d'(f(p), f_n(p)) + d'(f_n(p),f_n(x)) + d'(f_n(x), f(x))$.  Given $\varepsilon > 0$, we want to show: $\exists \delta > 0$ s.t. if $d(x,p) < \delta$, then $d'(f(x),f(p)) < \varepsilon$. Since $f_n \rightarrow f$ converges uniformly, $\exists N$ s.t. for $n \geq N$, $d'(f_n(y), f(y)) < \varepsilon /3, \forall y \in E$. Since $f_N$ is continuous at $p$, $\exists \delta > 0$ s.t. if $d(x,p) < 0, d'(f_N(x),f_N(p)) < \varepsilon/3$. Then $\forall x$ with $d(x,p) < \delta$,
	$d'(f(p), f(x))\leq d'(f(p), f_n(p)) + d'(f_n(p),f_n(x)) + d'(f_n(x), f(x)) < \varepsilon/3+\varepsilon/3+\varepsilon/3 = \varepsilon$

>[!note] Def (Bounded function)
>Let $(E,d), (E',d')$ be two metric spaces, a function $f: E \rightarrow E'$ is bounded if $f(E) \subseteq E'$ is bounded.
>Notation: $C(E,E') = \{f: E\rightarrow E'| f\:\text{bounded\:and\:continuous}\}$

Exercise. if $f,g: E\rightarrow E'$ are bounded, then $\{d'(f(x),g(x))| x\in E\}$ is bounded. 
Define $D: C(E,E')\times C(E,E')\rightarrow [0,\infty)$ by $D(f,g) = \sup\{d'(f(x),g(x))| x \in E\}$
Exercise. $D$ is a metric. 
Then $f_n \rightarrow f$ in $(C(E,E'),D) \iff f_n \rightarrow f$ uniformly convergent.
 $\{f_n\}_{n\in\mathbb{N}}$ is Cauchy in $(C(E,E'),D) \iff \{f_n\}_{n\in\mathbb{N}}$ uniformly Cauchy.

**Theorem** If $E'$ is a complete metric space, then $(C(E,E'),D)$ is complete.
If $\{f_n\}_{n \in\mathbb{N}}$ is Cauchy in $C(E,E'),D$, then by Theorem 4.3.1 it is uniformly Cauchy. Then by 14.1 $\{f_n\}_{n\in\mathbb{N}}$ converges uniformly to $f: E\rightarrow E'$, since the convergence is uniform, $f$ is continuous. Moreover each $f_n$ is bounded and $f_n \rightarrow f$ uniformly, so $f$ is bounded (check that), so $f = \lim f_n \in C(E,E')$

## 4.3 Connectedness revisited

>[!note] Def (Connectedness)
>A subset $Y$ of a topological space $X$ is connected if  $\forall U, V \subseteq X$, $U,V$ open with $Y \subseteq U \cup V$ and $(Y \cap U)\cap (Y \cap V) = \varnothing$, then either $Y \subseteq U$ or $Y \subseteq V$.

In particular a space $X$ is connected if $X = U \cup V, U \cap V = \varnothing \implies X = U$ or $X = V$.

Non Example: $Y=[0,1/2)\cup(1/2,1] \subseteq \mathbb{R}$, standard topology, $Y$ is not connected: $U = (-\infty, 1/2), V = (1/2,\infty)$. $U\cap V = \varnothing, Y \subseteq U\cup V$, but neither $Y \subset U$ or $Y \subset V$.


>Def (Subspace topology)
>Suppose $(X, \mathcal{T})$ is a topological space, $A \subseteq X$ is a subspace. A subspace topology $\mathcal{T}_A$ on $A$ is $\mathcal{T}_A = \{U \cap A | U\text{\:open\:in}\:X\}$
>(a) $\mathcal{T}_A$ is a topology
>(b) If $d$ is a metric on $X$, and $d_A = d|_{A \times A}$. Then $\mathcal{T}_{d_A} = (\mathcal{T}_d)_A$
>
>*Connect this with the definition of connectedness*

Proof
(a) It contains $\varnothing$ and $A$ since $\varnothing = \varnothing \cap \mathcal{T}$ and $A = A \cap X$, and $\varnothing, X$ are elements of $\mathcal{T}_A$. Suppose $U_1, U_2,\cdots\subseteq \mathcal{T}$ are open sets. 
Notice that $(U_1\cap Y)\cap (U_2\cap Y)\cap\cdots\cap(U_n\cap Y)=(U_1\cap U_2 \cap \cdots \cap U_n) \cap Y\subseteq \mathcal{T}_Y$. For arbitrary intersections, we have $\cup_{\alpha\in A}(U_{\alpha}\cap Y)=(\cup_{\alpha \in A}U_{\alpha})\cap Y\subseteq \mathcal{T}_Y$. 
(b) Suppose $U \subseteq \mathcal{T}_{d_A}, U$ open, we will show that $U \subseteq (\mathcal{T}_d)_A$. And then we show the converse. Since $U$ is open, $\forall x \in U, \exists \varepsilon > 0$ s.t. $B_{\varepsilon}^{d_A}(x) \subseteq U$. Since $d_A = d$, it is also an open ball in $(\mathcal{T}_d)_A$ intersecting $A$. Hence, $B_{\varepsilon}^{d_A}(x) = B_{\varepsilon}^{d}(x) \cap A$, and we can write $U$ as a union of intersections of open sets in $E$ with $A$, hence $U$ is open in the subspace topology $(\mathcal{T}_d)_A$.
Conversely, suppose that $U \subseteq (\mathcal{T}_d)_A$. Then there exists an open set $U = V \cap A$. For all $x\in V, \exists \varepsilon > 0$ s.t. , $B_{\varepsilon}^d(x) \subseteq V$. Since $U = V \cap A$, we have $B_{\varepsilon}^{d_A}(x) = B_{\varepsilon}^d(x) \cap A \subseteq U$. Therefore, $U$ is open in $(\mathcal{T}_d)_A$.

#ToReview  
**Theorem** $[0,1]$ with standard topology is connected.
Proof:
	Suppose $[0,1] = U \cup V, U, V\subseteq [0,1]$ open and $U \cap V = \varnothing$. We may assume that $0 \in U$. We argue that $V = \varnothing$. Let $S = \{x \in [0,1]\:|\:[0,x]\subseteq U\}$. Since $U$ is open, $0 \in U$, $\exists r > 0$ s.t. $[0,r) \subseteq U$. And then $[0,r/2]\subseteq U$. So $S$ is nonempty and contains some $x > 0$. Let $c = \sup S$. Then $c \leq 1$ and $c > 0$ since $\exists x > 0, x\in S$.
	Claim 1: $[0,c) \subseteq U$. If $y \in [0,c)$, then $y < c = \sup S \implies \exists z$ s.t. $y \leq z < c \implies [0,z] \subseteq U\implies$ $[0,y] \subseteq [0,z] \subseteq U \implies y \in U$.
	Claim 2: $c \in U$. If not, $c \in V$. Since $V$ is open, $\exists \delta > 0$ s.t. $(c-\delta, c+\delta) \cap [0,1] \subseteq V$. $\implies c - \delta/2 \in V$. But $c - \delta/2 < c$ and $[0,c) \subseteq U$. But $U \cap V = \varnothing$, contradiction. $\therefore [0,c) \cup \{c\} = [0,c] \subseteq U$ 
	We now argue $c = 1$. If $c \neq 1, c < 1 \implies c \in (0,1)$. Since $(0,1), U$ are open, $(0,1) \cap U$ is open. $\exists \varepsilon > 0$ s.t. $(c-\varepsilon, c + \varepsilon) \subseteq (0,1) \cap U$. $[0,c+ \varepsilon) = [0,c] \cap (c-\varepsilon, c + \varepsilon)\subseteq U$. $\implies [0,c + \varepsilon/2] \subseteq U$, which contradicts that $c = \sup S$, $\therefore [0,1]$ is connected.

## 4.5 Continuous functions on a connected metric space
**Theorem 4.5.1** Suppose $f: X \rightarrow Y$ is continuous, $X$ is connected, then $f(X) \subseteq Y$ is connected.
Proof:
	Suppose $U,V \subseteq Y$ are open, $f(X) \subseteq U \cup V$, $(f(X) \cap U) \cap (f(X) \cap V) = \varnothing$. [Def of Connectedness] We argue that either $f(X) \subseteq U$ or $f(X) \subseteq V$. Since $f(X) \subseteq U \cup V, X = f^{-1}(U)\cup f^{-1}(V)$ since $f$ is continuous.[preimage of open sets of a continuous function is open] Since $(f(X) \cap U)\cap (f(X) \cap V) = \varnothing$, $f^{-1}(U) \cap f^{-1}(V) = \varnothing$. Since $X$ is connected, $X = f^{-1}(U)$. But then $f(X) \subseteq U$ (or $f(X) \subseteq V$). 

*Note that here the $f^{-1}$ refers to the forward function not inverse function!*

**Corollary 4.5.2** $\forall a,b \in \mathbb{R}, a< b, [a,b]$ is connected.
Proof:
	$f(t) = ta+ (1-t)b, t \in [0,1]$ is a surjective continuous map $f:[0,1] \rightarrow [a,b]$. 

>[!note] Def (Path-connected)
>A space $X$ is path connected if $\forall p,q \in X$, $\exists$ a continuous function $\gamma: [0,1]\rightarrow X$ s.t. $\gamma(0) = p$,$\gamma(1) = q$.
In this case, we say $\gamma$ is a path from $p$ to $q$.

Ex. $\mathbb{R}^n$ is path-connected. $\forall p,q \in \mathbb{R}^n$, $\gamma(t) = tp + (1-t)q$ is a continuous path from $p$ to $q$.

>[!note] Def (Convex)
>A subset $X \subseteq \mathbb{R}^n$ is convex if $\forall p, q\in X$, $tp + (1-t)q \in X, \forall t \in [0,1]$

Remark. Convex sets are path connected. In particular, closed and open balls in $\mathbb{R}^n$ (w.r.t. $d_1,d_2,d_{\infty}$) are all convex, and thus path-connected.
Ex. $X = \{(x,y) \in \mathbb{R}^2: xy \geq 0\}$ is path connected but not convex. 

*If U $\subseteq \mathbb{R}^n$ is open, then path components of U are open.* 

**Theorem 4.5.2** $X$ is path connected $\implies$ $X$ is connected
Proof:
	Suppose $X$ is path-connected, $U,V \subseteq X$ open, $U \cup V = X$. $U \cap V \neq \varnothing$. Suppose by contradiction that both $U \neq \varnothing$ and $V \neq \varnothing$. Then $\exists \gamma : [0,1]\rightarrow X$ s.t. $\gamma (0) \in U, \gamma(1) \in V$. But then $[0,1] = \gamma^{-1}(U\cup V) = U ^{-1} \cup V^{-1}$, and thus $0 \in \gamma^{-1}(U), 1 \in \gamma^{-1}(V)$ and $\gamma^{-1}(U) \cap \gamma^{-1}(V) = \varnothing$. This contradicts the connectedness of $[0,1]$. 

**Lemma 4.5.3** For $Y \subseteq\mathbb{R}$, $Y$ is connected $\iff Y$ is convex: $\forall y_1,y_2 \in Y, y_1 \neq y_2, [y_1,y_2]\in Y$. (Hence for $Y \subseteq \mathbb{R}$, connected $\iff$ path connected) 
Proof:
	($\impliedby$) If $y_1,y_2 \in Y, [y_1,y_2] \subseteq Y$, then $Y$ is path connected hence connected.
	($\implies$) Suppose $Y$ is connected, and $\exists y_1,y_2 \in Y$ with $[y_1,y_2] \not\subseteq Y$. Then $\exists z \in [y_1,y_2]$ s.t. $z \notin Y \implies Y \subseteq (-\infty, z) \cup (z, \infty)$ and $y_1 \in (-\infty, z) \cap Y$, $y_2 \in(z, \infty) \cap Y$, but this contradicts connectedness.

**Theorem 4.5.4 (Intermediate Value Theorem)**  Suppose $X$ is connected, $f: X \rightarrow \mathbb{R}$ is continuous. Then $\forall y_1,y_2 \in f(x)$ with $y_1 < y_2, [y_1,y_2] \subseteq f(X)$. In particular, $\forall y \in \mathbb{R}$ with $y_1 < y < y_2$, $\exists x \in X$ s.t. $f(x) = y$
Proof: 
	Since $f$ is continuous and $X$ is connected, $f(X) \subseteq \mathbb{R}$ is connected. Now apply Lemma 4.5.3. #question

Ex. Suppose $f:[0,1]\rightarrow [0,1]$, then $f$ has a fixed point: $\exists x \in [0,1]$ s.t. $f(x) = x$.
Proof: Consider $g(x) = f(x) - x$. $g(0) = f(0) \in [0,1]\implies f(x) \geq 0$. $g(1) = f(1) - 1 \leq 0$. Since $g$ is continuous and $[0,1]$ is connected, $\exists x \in [0,1]$ s.t. $0 = g(0) = f(x) - x$.

Ex of $A \subset \mathbb{R}$ which is connected but not path-connected: Let $B = \{(x,\sin\frac{1}{x}) | x > 0\}$. Since $f:[0,\infty) \rightarrow B, f(x) = (x, \sin\frac{1}{x})$ is continuous and surjective, $B$ is path-connected. Let $A = (\{0\}\times [-1,1]) \cup B$ (secretly $A = \bar{B}$ the closure of $B$)
Proof: 
Claim 1: A is connected
Suppose not, then $\exists U_1,U_2 \subseteq \mathbb{R}^2$ open sets, s.t. $A \subseteq U_1 \cup U_2, (A \cap U_1) \cap (A \cap U_2) = \varnothing$, and $A \cap U_1, A \cap U_2 \neq \varnothing$. Since $C = \{0\}\times [-1,1], B$ are connected, $C\subseteq U_1$ and then $B\subseteq U_2$, or $C\subseteq U_2$ and $B \subseteq U_1$. Say $C \subseteq U_1$. Since $U_1\subseteq \mathbb{R}^2$ is open, $\exists r>0$ s.t. $B_r((0,0)) \subseteq U_1$. But $B_r((0,0)) \cap B \neq \varnothing,\quad r\not\Rightarrow B\cap U_1 \neq\varnothing$. Contradiction.  
Claim 2: A is not path-connected
Suppose $A$ is path connected, then $\exists \gamma:[0,1]\rightarrow A$ with $\delta(0) = (0,0) \in C, \delta(1) \in B$. Since $\gamma(0) \in C, \gamma^{-1}(C) \neq \varnothing$. Since $B = \{(x,y) \in\mathbb{R}^2|x>0\}\cap A$, $B$ is open in $A\implies \gamma^{-1}(B)$ is open in $[0,1]$. 
#TODO 

**Theorem 4.5.5** If $U \subseteq \mathbb{R}^n$ is connected and open, then $U$ is path-connected.
Proof:
Define $\sim$ on $U$ by $x \sim y \iff x,y$ can be connected by a path. We check that it is an equivalence relation. Then equivalence classes of $\sim$ are disjoint.
Check equivalence:
(Reflexivity) Consider the map $\gamma: [0,1]\rightarrow X, \gamma(t) = x, \forall t \in [0,1]$. Note that it is continuous since the preimage of any open sets of $X$ is either $[0,1]$ or $\varnothing$, both of which are open, and thus the map is continuous. 
(Symmetry) Suppose $x \sim y$, we want to show that $y \sim x$. Since $x \sim y$, $\exists \gamma(t)$ with $\gamma(0) =x$ and $\gamma(1) = y$. Now consider $\gamma'(t) = \gamma(1-t)$ for $t\in [0,1]$, and it is continuous by the hint. Now we have $\gamma'(0) = \gamma(1-0) = \gamma(1) = y, \gamma'(1) = \gamma(1-1) = \gamma(0) = x$. Therefore we find a continuous map with $\gamma'(0) = y, \gamma'(1) = x$, thus $y\sim x$.
(Transitivity) Suppose $x \sim y, y \sim z$, we want to show that $x \sim z$. Since $x \sim y, y \sim z$, $\exists \gamma_1:[0,1]\rightarrow X, \gamma_2:[0,1]\rightarrow X$ continuous satisfying the requirements of $\sim$. Now define $\gamma:[0,2]\rightarrow X$ by 	
$$\gamma(t) = \begin{cases}\gamma_1(2t), t \in [0,\frac{1}{2}\\
			\gamma_2(2t-1), t \in [\frac{1}{2}, 1] \end{cases}$$and by HW 6 Q2 $\gamma(t)$ is continuous. Note that $\gamma(0) = \gamma_1(0) = x$, $\gamma(1) = \gamma_2(2\cdot 1 -1) = \gamma_2(1) = z$, thus $x\sim z$.

Claim: Any equivalence classes $V$ of $\sim$ is open.
Proof: given $x\in V, \exists r > 0$ s.t. $B_r(x) \subseteq U$. But any point $y \in B_r(x)$ can be connected to $x$ by a path $\implies B_r(x) \subseteq V\implies V$ is open. Since $U$ is connected, there can only be one equivalence class, so $U$ is path-connected.

# Chapter 5 Differentiation
## 5.1 Derivative
>[!note] Def (Differential)
>Let $U \subseteq \mathbb{R}$ open, $f: U \rightarrow \mathbb{R}, f$ is differentiable at $a \in U$ ($f$ has a derivative at $a$) if $\lim _{x\rightarrow a} \frac{f(x)-f(a)}{x-a}$ exists.
>If $f$ is differentiable at $a$, we write $f'(a)$ or $\frac{\text{d}f}{\text{d}x}(a)$

Ex. $U = \mathbb{R}, f(x) = x$. Then $\lim_{x \rightarrow a} \frac{f(x)-f(a)}{x-a} = \frac{x-a}{x-a} = 1$, thus $f(x)$ is differentiable.
Ex. Same $U, f(x) = c, c$ constant is differentiable.
Ex. $U = \{x\in\mathbb{R}: x \neq 0\}, f(x) = 1/x$. Then for all $a \in U, \lim_{x \rightarrow a} \frac{f(x)-f(a)}{x-a} = \frac{1}{x-a} (\frac{1}{x} - \frac{1}{a}) = -\frac{1}{a^2}$

Note: $\forall u,v \in\mathbb{R}, n \in \mathbb{N}, u^n - v^n = (u-v) (u^{n-1} + u^{n-2}v+ \cdots+ uv^{n-2} + v^{n-1})$  

Ex. $U = (0,\infty), f(x) = x^{1/n}, n\in\mathbb{N}$, $f'(a) = \lim_{x \rightarrow a} \frac{f(x)-f(a)}{x-a} = \frac{1}{x-a}(x^{1/n} - a^{1/n}) =  \frac{x^{1/n} - a^{1/n}}{x^{1/n} - a^{1/n}(x^{{n-1}/n} + x^{{n-2}/n}a^{1/n} + \cdots)} = \lim_{x\rightarrow a} \sum_{k=1}^{n-1}(x^{\frac{n-1-k}{n}}a^{k/n})^{-1}$ $= n(a^{\frac{n-1}{n}})^{-1} = \frac{1}{n}a^{1/n-1}$ 

Equivalence expression of $f(x)$ is differentiable at $a$:
1) $\lim_{h\rightarrow 0} \frac{f(a+h) - f(a)}{h}$ exists.
2) $\exists f'(a) \in\mathbb{R}$ s.t. $\lim_{x \rightarrow a} = \frac{f(x) - f(a) - f'(a)(x-a)}{x-a}=0$

**Lemma 5.1.1** If $f: U \rightarrow \mathbb{R}$ is differentiable at $a$, then it is continuous at $a$.
Proof:
	Suppose $f'(a) = \lim_{x \rightarrow a} \frac{f(x)-f(a)}{x-a}$ exists, then $\lim_{x\rightarrow a} f(x) = \lim_{x\rightarrow a}f(a) + \frac{f(x)-f(a)}{x-a}(x-a)= f(a) + \lim_{x\rightarrow a}\frac{f(x)-f(a)}{x-a} \cdot \lim_{x\rightarrow a}(x-a)$
	$=f(a) + 0\cdot f'(a) = f(a)$

**Lemma 5.1.2** Suppose $f$ is differentiable at $a$ and $g$ is differentiable at $f(a)$, then $g\circ f$ is differentiable at $a$ and $(g\circ f)'(a) = g'(f(a))\cdot f'(a)$
Proof:
	Define $h(y) = \begin{cases}\frac{g(y) - g(f(a))}{y-f(a)},&y\neq f(a)\\	g'(f(a)), \:\:\:\:&y = f(a)\end{cases}$
	Then $h$ is continuous at $a$ since $\lim_{y\rightarrow f(a)}h(y) = g'(f(a))$. Moreover, $\lim_{x\rightarrow a}\frac{g(f(x)) - g(f(a))}{x-a} = \lim_{x\rightarrow a} h(f(x))\cdot \frac{f(x)-f(a)}{x-a} = h(f(a))\cdot f'(a) = g(f(a))\cdot f'(a)$

**Lemma 5.1.3** Suppose $f(a) \neq 0$ and $f$ is differentiable at $a$, then $k(x) = \frac{1}{f(x)}$ is differentiable at $a$ and $k'(a) = -\frac{1}{(f(a))^2}f'(a)$
Proof:
	$k(x) = (g\circ f)(x)$ where $g(y) = \frac{1}{y}$

## 5.2 Rules of Differentiation
**Theorem 5.2.1** Suppose $f,g$ are differentiable at $a$ and $c\in\mathbb{R}$ a constant, then $f+g,f\cdot g,cf$ are differentiable at $a$. If $g(a) \neq 0, f/g$ is also differentiable at $a$. Moreover,
1) $(cf)'(a) = cf'(a)$
2) $(f+g)'(a) = f'(a) + g'(a)$
3) $(f\cdot g)'(a) = f'(a)g(a) + f(a)g'(a)$
4) $(f/g)'(a) = \frac{f'(a)g(a) - f(a)g'(a)}{(g(a))^2}$ if $g(a) \neq 0$.
Proof:
Since $c=0$, (3)$\implies$ (1); (3) + 5.1.3 $\implies$ (4) since $f/g=f\cdot \frac{1}{g}$.
(2) $(f+g)'(a) =\lim_{x\rightarrow a}\frac{(f+g)(x) - (f+g)(a)}{x-a} = \lim_{x\rightarrow a}(\frac{f(x) - f(a)}{x-a} + \frac{g(x) - g(a)}{x-a}) = f'(a) + g'(a)$
(3) $(f\cdot g)'(a) = \lim_{x\rightarrow a}\frac{f(x)g(x) -f(x)g(a) + f(x)g(a) - f(a)g(a) }{x-a} = \lim_{x\rightarrow a}f(x) \frac{g(x) - g(a)}{x-a} + g(x) \frac{f(x) - f(a)}{x-a}$ 
$= f(a) g'(a) + f'(a)g(a)$

**Theorem 5.2.2** Suppose $f$ is differentiable at $a$ and $f$ achieves an extremum at $a$, then $f'(a) = 0$
Proof:
We prove the theorem when $a$ is a local maximum. Then $\exists \varepsilon>0$ s.t. for $x \in (a-\varepsilon,a+\varepsilon)$, i) if $x\in(a-\varepsilon, a), \frac{f(x)-f(a)}{x-a}\geq 0$, ii) for $x\in(a, a+\varepsilon), \frac{f(x)-f(a)}{x-a}\leq 0$. ii) implies that $\lim_{x\nearrow a}\frac{f(x)-f(a)}{x-a}\geq 0$ and $\lim_{x\searrow a}\frac{f(x)-f(a)}{x-a}\leq 0$ . But $\lim_{x\rightarrow a}\frac{f(x)-f(a)}{x-a}$ exists and equals $f'(a)$, thus $f'(a) \geq 0, f'(a) \leq 0$, so $f'(a) = 0$.
 
## 5.3 Mean Value Theorem

>[!important] Theorem (Rolle's Theorem)
>$f:[a,b]\rightarrow\mathbb{R}$ continuous differentiable on $(a,b)$, $f(a) = f(b)$. Then $\exists c \in (a,b)$ so that that $f'(c) = 0$

Proof:
	Since $[a,b]$ is compact, $f$ achieves max and min on $[a,b]$ if a point $c \in (a,b)$ is extremal, we are done. Otherwise, the external points are in $\{a,b\}$ and then $f$ is constant, hence $f'(c) = 0, \forall c\in (a,b)$

>[!important] Theorem (Mean Value Theorem)
>Suppose $f:[a,b] \rightarrow \mathbb{R}$ is continuous, differentiable on $(a,b)$. Then $\exists c \in (a,b)$ s.t. 
>$$f'(c) = \frac{f(b) - f(a)}{b-a}$$

Note: This is Rolle's theorem if $f(a) = f(b)$
Proof of MVP:
	Let $h(x) = \frac{f(b)- f(a)}{b-a}\cdot (x-a)$. Note: $h'(x) = \frac{f(b)-f(a)}{b-a}, \forall x$. Let $g(x) = f(x) - h(x)$. then $g(a) = f(a) - h(a) = f(a)$. $g(b) = f(b) - \frac{f(b) - f(a)}{b-a}\cdot (b-a) = f(a)$. By Rolle's Theorem applied to $g(x)$ we get: $\exists c \in (a,b)$ so that $0 = g'(c)$. But $g'(c) = f'(c) - h'(c) = f'(c) - \frac{f(b) - f(a)}{b-a}$. Thus $\exists c \in (a,b)$ s.t. $f'(c) = \frac{f(b) - f(a)}{b-a}$. 

**Corollary 5.3.1** Suppose $f: (a,b) \rightarrow \mathbb{R}$ is differentiable and $f'(x)= 0, \forall x \in (a,b)$. Then $f$ is constant.
Proof:
	If $f$ is not constant, $\exists x_1,x_2 \in (a,b), x_1 < x_2$ s.t. $f(x_1) \neq f(x_2)$. By Mean Value Theorem $\exists c\in (a,b)$ s.t. $f'(c) = \frac{f(x_2)-f(x_1)}{x_2-x_1} \neq 0$. Contradiction.

**Corollary 5.3.2** Let $f,g: (a,b)\rightarrow \mathbb{R}$ differentiable, $f'(x) = g'(x), \forall x$. Then $\exists c \in \mathbb{R}$ s.t. $f(x) = g(x) + c$
Proof:
	$(f-g)'(x) = f'(x) - g'(x) = 0$. By 5.3.1, $h(x) = f(x) - g(x)$ is constant.

Ex. Suppose $f: \mathbb{R} \rightarrow \mathbb{R}$ is a function, suppose $\exists \alpha >1$ s.t. $|f(x) - f(y)| \leq |x-y|^{\alpha}$ for all $x,y \in\mathbb{R}$. Then $f$ is constant.
Proof: 
	It's enough to prove that $f$ is differentiable and that $f'(a)=0, \forall a$. So fix $a \in\mathbb{R}, \forall x \neq a$ $|\frac{f(x) - f(a)}{x-a}-0| = \frac{|f(x) - f(a)|}{|x-a|}\leq |x-a|^{\alpha - 1}$. Given $\varepsilon > 0$, let $\delta = \varepsilon^{1/(\alpha-1)}$. Then, for $x\neq a$, $|x-a| < \delta \implies\delta^{\alpha - 1}=\varepsilon > |x-a|^{\alpha - 1} \geq |\frac{f(x) - f(a)}{x-a} - 0|$. $\therefore \lim_{x\rightarrow a}\frac{f(x) - f(a)}{x-a} = 0$

**Lemma 5.3.3** Suppose $f:(a,b)\rightarrow \mathbb{R}$ is differentiable and $f'(x)$ is bounded. then $f$ is uniformly continuous.
Proof:
	Let $M$ be an upper bound for $\{|f'(x)|: x \in (a,b)\}$. By the Mean Value Theorem, $\forall x, y\in(a,b), x< y, \exists c\in (x,y)$ s.t. $\frac{f(y)-f(x)}{y-x} = f'(c) \implies \frac{|f(y)-f(x)|}{|y-x|} = |f'(c)| \leq M$ 
	$\implies |f(y) - f(x)| \leq M|y-x|$. Hence given $\varepsilon >0$, let $\delta = \varepsilon/M$, then $|y-x| < \varepsilon/M \implies |f(y) - f(x)| \leq M|y-x|\leq M\cdot \varepsilon/M = \varepsilon$

Remark. $f(x) = \sqrt{x}$ is continuous on $[0,1]$ hence uniformly continuous on $[0,1]$ since $[0,1]$ is compact. Hence it's uniformly bounded on $(0,1)$, but $f(x) = 1/(2\sqrt{x})$ is not bounded on $(0,1)$

**Theorem 5.3.4** Suppose $f:(a,b)\rightarrow \mathbb{R}$ is differentiable on $(a,b)$, then:
1) $f'(x) > 0, \forall x\implies f$ is strictly increasing
2) $f'(x) < 0, \forall x\implies f$ is strictly decreasing
3) $f'(x) \geq 0, \forall x\iff f$ is nondecreasing
4) $f'(x) \leq 0, \forall x\iff f$ is non increasing
Proof of (3):
	($\implies$) Suppose $f'(z) \geq 0,  \forall z \in (a,b),x,y\in(a,b),x<y$, then $\exists c\in(x,y)$ s.t. $\frac{f(y)-f(x)}{y-x} = f'(c)\geq 0$ $\implies f(y) - f(x) = (y-x)f'(c) \geq 0$
	($\impliedby$) If $f$ is nondecreasing then $\forall x<y, \frac{f(y)-f(x)}{y-x}\geq 0 \implies f'(y)\geq 0, \forall y$.  
Remark. strictly increasing $\not\implies f'(x) > 0$ 

>[!note] Theorem (Inverse Function Theorem)
>Suppose $f:(a,b)\rightarrow(c,b)$ is a continuous bijection, $x_0\in(a,b)$, $f$ is differentiable at $x_0$ and $f'(x_0)\neq 0$. Then $f^{-1}:(c,d)\rightarrow (a, b)$ is differentiable at $y_0 = f(x_0)$ and
>$$(f^{-1})'(y_0) \cdot f'(x_0) = 1, (\text{i.e.} (f^{-1})'(y_0) = \frac{1}{f'(x_0)})$$

Remark. the content of the theorem is that $f^{-1}$ is differentiable at $y_0$. the formula then follows from $f^{-1}(f(x)) = x$ (chain rule) $\implies (f^{-1})'(f(x_0))\cdot f'(x_0) = 1$
To prove the Inverse Function Theorem we will need to know that $f^{-1}$ is a continuous at all points of $(c,d)$

**Lemma 5.3.5** Let $(S,d), (S',d')$ be metric spaces, $S$ compact, $f:S \rightarrow S'$ continuous bijection. Then $f^{-1}: S'\rightarrow S$ is continuous. 
Proof:
	$g:=f^{-1}$ is continuous $\iff \forall$ closed sets $C \subseteq S, g^{-1}(C)$ is closed. Now, since $g = f^{-1}, g^{-1}(C) = f(C)$. Since $C\subseteq S$ is closed, $C$ is compact. $f$ continuous $\implies f(C)$ is compact. But $S'$ is a metric space, and compact subsets of metric space are closed, so $f(C)$ is closed. $\therefore g=f^{-1}$ is continuous.

Proof of IVT:
	We first argue that $f^{-1}$ is continuous. Given $y_0 \in (c,d), x_0 = f^{-1}(y_0) \in (a,b)\implies \exists \varepsilon >0$ s.t. $[x_0-\varepsilon, x_0+\varepsilon] \subseteq (a,b)$. Since $[x_0-\varepsilon, x_0+\varepsilon]$ is compact, $f:[x_0-\varepsilon, x_0+\varepsilon]\rightarrow f([x_0-\varepsilon, x_0+\varepsilon])$ has a continuous inverse. In particular $f^{-1}$ is continuous at $y_0 = f(x_0) \subseteq f([x_0-\varepsilon, x_0+\varepsilon])$.
	We now argue: $\lim_{y \rightarrow y_0}\frac{f^{-1}(y) - f^{-1}(y_0)}{y - y_0}$ exists and is equal to $\frac{1}{f'(x_0)}$. It is enough to show $\forall$ sequence $\{y_n\} \subseteq (c,d)\setminus \{y_0\}$ with $y_n \rightarrow y_0$, $\lim_{n\rightarrow \infty}\frac{f^{-1}(y_n)-f^{-1}(y_0)}{y_n-y_0}$ exists and equals $\frac{1}{f'(x_0)}$. Let $x_n = f^{-1}(y_n)$. Since $f^{-1}$ is continuous, $x_n = f^{-1}(y_n) \rightarrow f^{-1}(y_0) = x_0$. Therefore, $$\lim_{n\rightarrow \infty}\frac{f^{-1}(y_n) - f^{-1}(y_0)}{y_n-y_0} = \lim_{n\rightarrow \infty}\frac{x_n-x_0}{f(x_n)-f(x_0)} = \frac{1}{f'(x_0)}$$
	 and we are done.

Ex. $f(x) = \sin(x), x\in(-\pi/2,\pi/2), g(y) = f^{-1}(y) = \arcsin(y)$. $g'(\sin(x)) = \frac{1}{f'(x)} = \frac{1}{\cos(x)} = \frac{1}{\cos(\arcsin(y))} = \frac{1}{\sqrt{(1-y^2)})}$

$f$ is infinitely differentiable if $f$ is $k$-times differentiable for all $k \geq 1$

Notation. $C^k(a,b)=\{f(a,b)\rightarrow\mathbb{R}|f\: \text{is}\:k-\text{times\:differentiable\:and}f^{(k)}\:\text{is\:continuous}\}$
$C^{\infty}(a,b)=\{f(a,b)\rightarrow\mathbb{R}|f\in C^k(a,b) \:\text{for all\:} k\} = \cap_{k=1}^{\infty}C^k(a,b)$

## 5.4 Taylor's Theorem

>[!important] Theorem (Taylor's Theorem)
>Let $U\subseteq\mathbb{R}$ be an open interval, $f:U\rightarrow \mathbb{R}\:n$-times differentiable. Fix $a \in U$, then $\forall x \in U, \exists c \in$ between $a$ and $x$ s.t. 
>$$f(x)=\sum_{k=0}^{n-1}\frac{f^{(k)}(a)}{k!}(x-a)^k+\frac{f^{(n)}(c)}{n!}(x-a)^n$$ 

Proof:
	#TODO

Note. If $n=1$, we have $f(x) = \frac{f^{(0)}(a)}{0!}(x-a)^0+\frac{f'(c)}{1!}(x-a)^1 = f(a)+f'(c)(x-a)$ for c between $x,a$, i.e. $f'(c) = \frac{f(x) - f(a)}{x-a}$, which is MVT.
Note that also $f^{(n)} = 0 \not\Rightarrow f(x)$ is constant. 
Ex. $f(x) = \begin{cases}e^{-1/x}, x>0\\0, \:\:\:\:\:\:\:\:o.w.\end{cases}$ 
Since $\lim_{x\rightarrow 0}e^{-1/x}= \lim_{x\rightarrow 0^+}\frac{1}{e^{1/x}} = 0$, $f$ is continuous at $0$. $f'(0) = \lim_{x\rightarrow 0^+}\frac{e^{-1/x}-0}{x-0} = \lim_{x\rightarrow 0^+}\frac{1}{xe^{1/x}} = -\lim_{y\rightarrow\infty}\frac{y}{e^y} = \lim_{y\rightarrow\infty}\frac{1}{e^y}=0$ (L'Hopital) $f$ is differentiable at $0$ and $f'(0)=0$. Induction on $n \implies f$ is $n$-times differentiable at $0$ and $f^{(n)}=0$, and thus $f$ is $C^{\infty}$ and $f^{(n)}=0,\forall n$. 

**Corollary 5.4.1** Suppose $f\in C^{\infty}(-a,a)$ and $\exists M,C >0$ s.t. $\forall k \in \mathbb{N}, \forall x \in (-a,a)$, $|f^{(k)}(x)| \leq MC^k$.
Then $\forall x \in (-a,a), f(x) = \sum_{k=0}^{\infty}\frac{f^{(k)}(0)}{k!}(:=\lim_{N\rightarrow \infty}\sum_{k=0}^{N}\frac{f^{(k)}(0)}{k!}x^k)$

Ex. $f(x) = \sin x, f'(x) = \cos x, f''(x) = -\sin x...$ all derivatives satisfy $|f^{(n)}(x)|\leq 1, \forall x$, so $M=C=1$. (Cor 5.4.1) $\sin(x) = \sum_{k=0}^{\infty}\frac{\sin^{(k)}(0!)}{k!} = \sum_{n=0}^{\infty}\frac{(-1)^n}{(2n+1)!}x^{2n+1}$ 

Remark. We can replace $(-a,a)$ with $(x_0-a,x_0+a)$, then $f(x) = \sum_0^{\infty}\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k$
Proof:
	By Taylor's Theorem, $f'(x) - s_N(x) \equiv f(x) - \sum_{k=0}^N\frac{f^{(k)}(0)}{k!}x^k = \frac{f^{(N+1)}(c)}{(N+1)!}x^{N+1}$ for some $c$ between 0 and $x$. By assumption, $|f(x) - s_N(x)| = \frac{f^{(N+1)}(c)}{(N+1)!}|x|^{N+1} \leq \frac{M\cdot C^{N+1}}{(N+1)!}a^{N+1}$ 
	Claim: $\lim_{N\rightarrow \infty}\frac{MC^{N+1}}{(N+1)!}a^{N+1} = 0$
	Proof of claim: Let $b_N = \frac{MC^Na^N}{N!}$, note that $b_N > 0$. Then $\frac{b_{N+1}}{b_N} = \frac{N!M(Ca)^{N+1}}{(N+1)!M(ca)^N} = \frac{ca}{N+1} \rightarrow 0$ as $N\rightarrow 0$ $\implies \exists N_0$ s.t. for $\forall n \geq N_0, \frac{b_{n+1}}{b_n}\leq 1/2$, i.e., $b_{n+1}\leq \frac{1}{2}b_n$ $\implies \forall k, b_{n+k}\leq \frac{1}{2}b_{n+(k-1)}\leq \cdots \leq \frac{1}{2^k}b_n$ $\implies \lim_{N\rightarrow \infty}b_N = 0$
	
Note. The claim implies $s_N(x) \rightarrow f(x)$ uniformly, so we are done.

Ex. $f(x) = \cos(x)$. Since $|f^{(k)}(x)|\leq 1, \forall k$, 5.4.1 implies that $\cos(x) = \sum_{k=0}^{\infty}\frac{\cos^{(k)}(0)}{k!}x^k = \sum_{k=0}^{\infty}\frac{(-1)^n}{(2n)!}x^{2n}$ for all $x$

>[!note] Def (Real analytic)
>A function $f$ is real analytic on an open set $U \subseteq \mathbb{R}$ if $f$ is infinitely differentiable on $U$ and $\forall a \in U, \exists \delta >0$ s.t. $f(x) = \sum_{k=0}^{\infty}\frac{f^{(k)}(a)}{k!}(x-a)^k, \forall x\in (a-\delta, a+\delta)$

Ex. $f(x) = \sin(x),\cos(x),e^x,$ polynomials...
$f(x) = \begin{cases}e^{-1/x^2}, x\neq 0\\ 0, x=0\end{cases}$ is not real analytic at 0 since $f^{(n)}(0)=0,\: \forall n$ but $f(x) \not\equiv 0$ for $x$ near 0.

A function $f\in C^{\infty}(U)$ with the property that $f^{(k)}(a) = 0, \forall k, (a \in U$ fixed) is called **flat** at $a$.

Ex. $f(x) = \frac{1}{1+x}$ is real analytic on $\mathbb{R}\setminus\{-1\}$
proof:
	Recall that $(q-1)(1+q+\cdots +q^k) = q^{n+1}-1 \implies \sum_{k=0}^{\infty}q^n = \frac{1^{n+1}-1}{q-1}\rightarrow_{n\rightarrow \infty}\frac{1}{1-q}$ if $|q| < 1$. Thus for $q$ with $|q| < 1, \sum_{n=0}^{\infty}q^n = \frac{1}{1-q} \implies \sum_{n=0}^{\infty}(-1)^nq^n = \frac{1}{1+q}$. Now for $a \neq -1$, we have
	$\frac{1}{1+x} = \frac{1}{1+a+x-a} = \frac{1}{1+a}\cdot \frac{1}{1+\frac{x-a}{a+1}} = \frac{1}{1+a}\cdot \sum_{n=0}^{\infty}\frac{(-1)^n(x-a)^n}{(a+1)^n}$ if $|\frac{x-a}{a+1}| < 1$. Thus $\forall a, \forall x$ with $|x-a| < |a+1|, \frac{1}{x+1} = \sum_{n=0}^{\infty}\frac{(-1)^n}{(1+a)^{n+1}}(x-a)^n$ and one can show that $f^{(k)}(a) = \frac{(-1)^k}{(1+a)^{k+1}}k!$

# Chapter 6 Riemann Integrals

## 6.1 Darboux Integral

Notation $f:[a,b]\rightarrow \mathbb{R}$ bounded function, $S \subseteq[a,b]$ a subset ($S \neq \varnothing$). $M(f,S):=\sup\{f(x)|x\in S\}, m(f,S):= \inf\{f(x)|x\in S\}$.
Note. If $S$ is an interval of length $l, f|_S \geq 0$ we expect $m(f,S)\cdot l \leq \int_{S}f(x)ds \leq M(f.S)\cdot l$
    
>[!note] Def (Partition, Darboux sum)
>(i) (Partition) A partition $\mathcal{P}$ of an interval $[a,b]$ is a finite strictly increasing sequence $a = t_0 < t_1 < \cdots t_{n-1} < t_n = b$
>(ii) The upper Darboux sum $U(f,\mathcal{P})$ of $f:[a,b]\rightarrow\mathbb{R}$ w.r.t. $\mathcal{P}$ is $$U(f,\mathcal{P}) := \sum_{k=1}^n M(f,[t_{k-1},t_k])\cdot (t_k-t_{k-1})$$
>(iii) The lower Darboux sum $L(f,\mathcal{P})$ of $f:[a,b]\rightarrow\mathbb{R}$ w.r.t. $\mathcal{P}$ is $$L(f,\mathcal{P}) := \sum_{k=1}^n m(f,[t_{k-1},t_k])\cdot (t_k-t_{k-1})$$

Ex. $f(x) = x+1,[a,b]=[1,3], \mathcal{P} = 1 = t_0 < 2 = t_1 < 3 = t_2$.
$U(f,P) = 3\cdot(2-1)+4\cdot(3-2) = 7, L(f,P) = 2\cdot (2-1) + 3\cdot (3-2) = 5$

Note. For any partition $P = a = t_0 < t_1 < \cdots < t_n = b$, 
$U (f,P) \leq \sum_{i=1}^n M(f,[a,b])\cdot (t_i-t_{i-1}) = M(f,[a,b])(b-a)$ 
$L (f,P) \geq \sum_{i=1}^n m(f,[a,b])\cdot (t_i-t_{i-1}) = L(f,[a,b])(b-a)$ 
Thus for all partition $P$, we have $m(f,[a,b])\cdot (b-a)\leq L(f,P)\leq U(f,P) \leq M(f,[a,b])(b-a)$. Hence the sets $\{U(f,P)| P \text{ is a partition of [a,b]}\}$, $\{L(f,P)| P \text{ is a partition of [a,b]}\}$
are bounded.
We can define $U(f) = \inf\{U(f,P)| P\text{ is a partition})\}, L(f) = \sup\{L(f,P)| P\text{ is a partition}\}$ 

>[!note] Def (Darboux integrable)
>A function $f:[a,b]\rightarrow\mathbb{R}$ is (Darboux) integrable if $U(f) = L(f)$. In this case we define 
>$$\int_a^b f(x)dx := L(f) = U(f)$$

Remark. We'll prove shortly that $L(f) \leq U(f)$. Hence to prove integrability it's enough to show $U(f) \leq L(f)$.
Ex. $f:[0,1]\rightarrow\mathbb{R}, f(x) = \begin{cases} 1,\:x\:irrational\\ 0, \:x\:rational\end{cases}$. Then for all $S \subseteq [0,1], M(f,S) = 1, m(f,S) = 0$ $\implies \forall P, L(f,P) = 0, U(f,P) = 1$. 
$\implies L(f) = \sup\{L(f,P)| P\text{ a partition}\} = 0$. $U(f) = \sup\{U(f,P)| P\text{ a partition}\} = 1$. 
Hence $f$ is not (Darboux) integrable.

Ex. $f(x) = x$ on $[0,b]\: (b>0), P = \{0=t_0 < t_1 < \cdots < t_n = b\}$. $U(f,P) = \sum_{k=1}^n M(f,[t_{k-1},t_k])\cdot (t_k, t_{k-1}) = \sum_{k=1}^n t_k (t_k - t_{k-1})$. Similarly, $L(f,P) = \sum_{k=1}^n t_{k-1}(t_k - t_{k-1})$.
In particular let $P_n$ be the partition with $t_k = \frac{kb}{n}$, Then $U(f,P_n) = \sum_{k=1}^n \frac{kb}{n}\cdot (\frac{kb}{n} - \frac{(k-1)b}{n})$ 
$= \sum_{k=1}^n \frac{kb}{n}\cdot\frac{b}{n} = \frac{b^2}{n^2}\sum_{k=1}^n k = \frac{b^2}{n^2} \frac{n(n+1)}{2} = \frac{b^2}{2}\frac{n+1}{n}$. Similarly, $L(f,P_n) = \frac{b^2}{2}\cdot\frac{n-1}{n}$.
Since $U(f) = \inf\{U(f,P)\} \leq U(f,P_n) = \frac{b^2}{2}\cdot \frac{n+1}{n}$. $U(f) \leq \lim_{n\rightarrow\infty}\frac{b^2}{2}\cdot\frac{n+1}{n}=\frac{b^2}{2}$
Similarly $L(f) = \sup\{L(f,P)\} \geq L(f,P_n) = \lim_{n\rightarrow\infty}\frac{b^2}{2}\cdot \frac{n-1}{n} = \frac{b^2}{2}$. 
$\implies \frac{b^2}{2}\leq L(f) \leq U(f) \leq \frac{b^2}{2} \implies L(f) = U(f) = \frac{b^2}{2}, \therefore \int_0^b xdx = \frac{b^2}{2}$.

More generally "sauce" argument gives:
Suppose $f:[a,b]\rightarrow\mathbb{R}$ is bounded, $\{P_n\},\{Q_n\}$ are sequence of partitions of $[a,b]$ s.t. the limits $\lim_{n\rightarrow \infty} U(f,P_n), \lim_{n\rightarrow \infty} L(f,Q_n)$ exists and are equal. Then
(i) $f$ is integrable and
(ii) $\int_a^b L(f,Q_n) = \lim_{n\rightarrow \infty}U(f,P_n)$

Now cope with $L(f) \leq U(f)$
**Lemma 6.1.2** Let $f:[a,b]\rightarrow \mathbb{R}$ be bounded, $P,Q$ two partitions of $[a,b]$ with $P \subseteq Q$. Then
$$L(f,P) \leq L(f,Q) \leq U(f,Q) \leq U(f,P)$$
proof:
	We prove that $L(f,P) \leq L(f,Q)$, The other proof is similar. It's sufficient to consider the case when $Q$ has one more point than $P$. That is, $P = \{a=t_0< t_1 < \cdots < t_n = b\}$, $Q = \{a=t_0< t_1 <\cdots <t_k < u< t_{k+1} < \cdots t_n = b\}$. Then $L(f,Q) - L(f,P) = m(f,[t_k,u])(u-t_k) + m(f,[u, t_{k+1}])(t_{k+1}-k) - m (f, [t_k,t_{k+1}])(t_{k+1}-t_k)$ $= (m(f,[t_k,u]) - m(f,[t_k,t_{k+1}]))(u-t_k) + m(f,[u,t_{k+1}]) - m(f, [t_k,t_{k+1}])\cdot (t_{k+1} - u) \geq 0$ 
	Since $m(f,[t_k,u])\geq m(f,[t_k,t_{k+1}])$, $m(f,[u,t_{k+1}])\geq m(f,[t_k,t_{k+1}])$

**Corollary 6.1.3** Suppose $f:[a,b]\rightarrow\mathbb{R}$ is bounded, $P,Q$ two partitions of $[a,b]$, then $L(f,P) \leq U(f,Q)$
proof:
	$P,Q \subseteq P \cup Q$. Hence by 6.1.2 $L(f,P) \leq L(f, P\cup Q)\leq U(f, P\cup Q)\leq U(f, Q)$

**Theorem 6.1.4** $f:[a,b]\rightarrow\mathbb{R}$ bounded. Then $L(f) \leq U(f)$.
proof:
	$\forall$ two partitions $P,Q$ of $[a,b]$, $L(f,P) \leq U(f,Q)\implies L(f) :=\sup L(f,P) \leq U(f,Q)$ for any $Q$. Which implies that $L(f)=\sup L(f,P) \leq \inf U(f,Q) = U(f)$

>[!note] Cauchy criterion for integrability
>Suppose $f:[a,b]\rightarrow \mathbb{R}$ is bounded. then $f$ is integrable on $[a,b]\iff \forall\varepsilon > 0, \exists$ a partition $P$ of $[a,b]$ s.t. 
>$$U(f,P) - L(f,P) < \varepsilon$$ 

proof:
	$(\implies)$ Since $f$ is integrable, $U(f) = L(f)$. Since $U(f) = \inf_P U(f,P), L(f) = \sup_PL(f,P), \exists$ partitions $P_1,P_2$ s.t. $U(f,P_1) < U(f) + \varepsilon/2, L(f,P_2) \geq L(f) - \varepsilon/2$. Let $P = P_1 \cup P_2$. Then
	$U(f,P) \leq U(f,P_1) \leq U(f) + \varepsilon/2$, $L(f,P)\geq L(f, P_2) \geq L(f) - \varepsilon/2$. Then $U(f,P) - L(f,P) \leq U(f) - L(f) + \varepsilon = \varepsilon$ since $L(f) = U(f)$
	($\impliedby$) Suppose $\forall \varepsilon > 0, \exists P$ s.t. $U(f) -L(f) \leq \varepsilon$. Then $U(f) \leq U(f, P) = U(f,P) - L(f,P)+L(f,P) \leq L(f,P) + \varepsilon \leq L(f) + \varepsilon$. $\implies \forall \varepsilon >0$, we have$(0 \leq )U(f) - L(f) \leq \varepsilon \implies U(f) = L(f)$ and $f$ is integrable.

**Def (Mesh)** The mesh of a partition $P = t_0 < t_1 < \cdots <t_n$ is mesh$(P) = \max\{t_i - t_{i-1}|i = 1,2,\cdots n\}$, 

>[!note] Def (Riemann Sum)
>Let $f:[a,b]\rightarrow\mathbb{R}$ be a bounded function, $P = \{a = t_0 < t_1 <\cdots < t_k = b\}$ a partition of $[a,b]$. Choose $x_k \in [t_{k-1},t_k],\forall k$. The corresponding Riemann sum is 
>$$S:= \sum_{k=1}^n f(x_k)\cdot (t_k - t_{k-1})$$

>[!note] Def (Riemann Integrable)
>A (bounded) function $f:[a,b]\rightarrow\mathbb{R}$ is Riemann integrable if $\exists R \in\mathbb{R}$ s.t. $\forall \varepsilon > 0, \exists \delta > 0$ with two properties that $\forall$ partition $P$ with mesh$(P) < \delta, \forall$ Riemann sum $S$ of $f$ associated with $P$,$$|S-R| < \varepsilon$$
>$R$ is called the Riemann integral of $f$.

**Theorem 6.1.5** A bounded function $f:[a,b]\rightarrow\mathbb{R}$ is Riemann integrable $\iff f$ is Darboux integrable. the value of the two integrals agree.
proof: #TODO postponed...

## 6.2 Properties of Integrals

**Theorem 6.2.1** Every monotonic function $f:[a,b]\rightarrow\mathbb{R}$ is integrable.
proof:
	We consider the case where $f$ is weakly increasing. Since $f(a) \leq f(x) \leq f(b), \forall x \in [a,b], f$ is bounded. We argue that $\forall \varepsilon >0, \exists$ a partition $P$ of $[a,b]$ s.t. $U(f,P) - L(f,P) < \varepsilon$. Let $P_n = t_0 = a < t_1 <\cdots < t_n = b$ where $t_k:= a + \frac{b-a}{n}k$. 
	Then $U(f,P_n) = \sum \sup(f|_{[t_k,t_{k-1}]}) \cdot (t_k - t_{k-1}) = \sum_{k=1}^n f(t_k) \cdot \frac{b-a}{n}$. 
	Similarly, $U(f,P_n) = \sum_{k=1}^n f(t_{k-1})\cdot \frac{b-a}{n}$. Hence
	$U(f,P_n) - L(f,P_n) = \frac{b-a}{n}\sum_{k=1}^n (f(t_k) - f(t_{k-1}))$
	$=\frac{b-a}{n}((f(t_1)-f(t_0)) + (f(t_2) - f(t_1)) + \cdots + (f(t_n) - f(t_{n-1})) = \frac{b-a}{n} (f(b) - f(a))$
	Now given $\varepsilon > 0$ choose $n$ s.t. $\frac{(b-a)(f(b) - f(a))}{n} < \varepsilon$, then $U(f,P_n) - L(f,P_n) < \delta$ and we are done by Cauchy criteria for integrability.
 
**Theorem 6.2.2** Every continuous function $f:[0,1]\rightarrow\mathbb{R}$ is integrable.
proof:
	Since $[a,b]$ is compact, $f$ is uniformly continuous: $\forall \varepsilon> 0, \exists \delta >0$ s.t. $|x-y| < \delta \implies$ $|f(x) - f(y)| < \frac{\varepsilon}{b-a},\forall x,y \in [a,b]$. Let $P$ be a partition of $[a,b]$ with mesh$(P) < \delta$. Now $\forall k, \exists x_k,y_k\in[t_{k-1},  t_k]$ s.t. $f(x_k) = \sup\{f(x)| x\in [t_{k-1},t_k]\}$ and $f(y_k) = \inf\{f(x)| x\in [t_{k-1},t_k]\}$. Then $M(f, [t_{k-1},  t_k]) - m(f, [t_{k-1},  t_k]) = f(x_k) - f(y_k) <\frac{\varepsilon}{b-a}$ since $|x_k-y_k| \leq |t_k - t_{k-1}| < \delta$. Therefore $U(f,P) - L(f,P) = \sum_{k=1}^n  (M(f, [t_{k-1},  t_k]) - m(f, [t_{k-1},  t_k])) \cdot (t_k - t_{k-1})$ $\leq \sum_{k} \frac{\varepsilon}{b-a} \cdot (t_k - t_{k-1}) =\frac{\varepsilon}{b-a} \cdot (b-a) =\varepsilon$. By Cauchy's criteria, $f$ is integrable.  

**Theorem 6.2.3** Suppose $f, g:[a, b]\rightarrow \mathbb{R}$ are bounded and integrable
(i) $\forall c \in \mathbb{R}$ of is integrable and $\int_a^b c f=c \int_a^b f$
(ii) $f+g$ is integrable and $\int_a^b(f+g)=\int_a^b f+\int_a^b g$.

Remark. Theorem says astounded integrable functions form a vector space and (b) : $\int_a^b$ : integrable functions $\rightarrow \mathbb{R}, f \mapsto \int_a^b f$ to linear.
proof:
	It's enough to prove (i) for $c>0$ and for $c=-1$ :
	if $c<0, c=(-1)|c|$ and then $\int_a^b c f=\int_a^b(-1)|c| f=(-1) \int_a^b|c| f = (-1)(-c) \int_a^b f=c \int_a^b f$
	If $c=0, c f=0$ and then $\int_a^b 0 \cdot f=0=0 \cdot \int_a^b f$.
	If $c=-1, \sup (-f|_{[t_k, t_{k-1}]})=-\inf(f|_{[t_k, t_{k-1}]}), \inf (-f|_{[t_k, t_{k-1}]})=-\sup(f|_{[t_k, t_{k-1}]})$, $\forall[t_k, t_{k-1}] \leq[a, b]$
	$\implies\forall$ partition $P$ of $(a, b)$
$$
\begin{gathered}
U(-f, p)=-L(f, p) \\
L(-f, p)=-U(f, P) \\
\Rightarrow U(-f)=\inf _p( U(-f, p))=\inf _p(-L(f, P))=-\sup _p L(f, P)=-L(f).
\end{gathered}
$$
	Similarly $L(-f)=-U(f)$. $\Rightarrow-f$ is integrable and $\int_a^b(-f)=-\int_a^b f$.
	If $c>0$, $\sup \{cf(x)|_{[t_k, t_{k-1}]}\}=c \sup (f(x)|_{[t_k, t_{k-1}]})$, $\inf \{cf(x)|_{[t_k, t_{k-1}]}\}=c \inf (f(x)|_{[t_k, t_{k-1}]})$
$$
\Rightarrow U(c f, P)=c \cdot U(f, p), \quad L(c f, P)=c L(f, P) \forall P
$$
$$
\Rightarrow U(c f)=c U(f)=c L(f)=L(c f)
$$
	$\Rightarrow c f$ is integrable and $\int_a^b c f=c \int_a^b f$.
	For (ii): Since $f,g$ are integrable, $\forall \varepsilon> 0, \exists$ partition $P_1,P_2$ s.t. 
	$U(f,P_1)-L(f,P_1) < \varepsilon/2, U(g,P_2) -L(g,P_2) < \varepsilon/2$ (Cauchy Criteria). Let $P = P_1 \cup P_2$, then $U(f,P) - L(f,P) < \varepsilon/2, U(f,P) - L(f,P) < \varepsilon /2$. Note that $\forall S \subseteq [a,b], \forall x\in S$, 
	$(f+g)(x) = f(x) + g(x) \leq \sup(f|_S) + \sup(g|_S) \implies \sup ((f+g)|_S) \leq \sup(f|_S) + \sup(g|_S)$
	Similarly, $\inf ((f+g)|_S) \geq \inf(f|_S) + \inf(g|_S) \implies$ $L(f+g,P) \geq L(f,P) + L(g,P), U(f+g, P) \leq U(f,P) + U(g,P)$.
	$U(f+g,P) - L(f+g,P)<\varepsilon/2 + \varepsilon/2 = \varepsilon$ and by Cauchy's criteria it is integrable.

**Theorem 6.2.4** Suppose $a<b<c, \quad f:[a, c] \rightarrow \mathbb{R}$ is bounded and $f\mid(a,b)$, $f \mid(b, c)$ are integrable. Then $f$ is integrable and $\int_{[a, c]} f=\int_{[a, b]} f+\int_{[b, c]} f \text {. }$
proof:
	Given $\varepsilon>0, \exists$ partitions $P_1$ of $[a, b]$. $P_2$ of $[b, c]$ So that $U\left(f, P_1\right)-L\left(f, P_1\right)<\varepsilon / 2$ and $U\left(f_1 P_2\right)-L\left(f_1 P_2\right)<\varepsilon / 2$. Let $P=P_1 \cup P_2$. Then $\left.U(f, P)=U\left(f, P_1\right)+U\left(f, P_2\right), L (f, P\right)=L\left(f, P_1\right)+L\left(f, P_2\right)$. Hence $U(f, P)-L(f, P)<\varepsilon / 2+\varepsilon / 2=\varepsilon$ $\Rightarrow f$ in integrable on $[a, c]$.
	Furthermore
$$
\begin{aligned}
& \int_{[a, c]} f=U(f) \leq U(f, P)=U\left(f, p_1\right)+U\left(f, P_2\right) \\
& <L\left(f, P_1\right)+\varepsilon / 2+L\left(f, P_2\right)+\varepsilon / 2 \leqslant \int_{[a, b]} f+\int_{\left[b, c\right]} f+\varepsilon \text {. } \\
&
\end{aligned}
$$
	Similarly, $\int_{[a, c]} f \geq L(f, P)=L\left(f, P_1\right)+L\left(f, P_2\right) \geq\left(U\left(f, P_1\right)-\varepsilon / 2\right)+\left(U\left(f, P_2\right)-\varepsilon / 2\right)$
$$
\begin{aligned}
& \geqslant\left(\int_{[a, b]} f-\varepsilon / 2\right)+\left(\int_{[b, c]} f-\varepsilon / 2\right)=\left(\int_{[a, b]} f+\int_{[c, d]} f\right)-\varepsilon \\
\Rightarrow \quad \mid \int_{[a, c]} f & -\left(\int_{\{a, b]} f+\int_{[b, c]} f\right) \mid<\varepsilon \quad \forall \varepsilon . \\
=\quad \int_{[a, c]} f & =\int_{[a, b]} f+\int_{[b, c]} f .
\end{aligned}
$$

Remark: At this point, given $f:[a, b] \rightarrow \mathbb{R}$, integrable, we can define
(\*) $\int_b^a f(x) d x=-\int_{[a, b]} f$. And then $\int_a^b f(x) d x+\int_b^c f(x) d x=\int_a^c f(x) d x$ even if $b$ in not between $a$ and $c$ (provided $f$ is integrable on the three relevant intervals).
WARNING $\int_a^b f(x) d x$ is then not an integral of a function; it's the integral of the 1 -form $f(x) d x$, It's an oriented integral. Forms are discussed in MATH 425.

**Theorem 6.2.5** Suppose $f:[a, b]\rightarrow[c, d]$ is integrable $g:[c, d] \rightarrow \mathbb{R}$ continuous. Then $h(x):=g(f(x))$ is integrable on $[a, b]$
proof:
	By Cauchy's criteria it's enough to show that $\forall \varepsilon > 0, \exists$ a partition $P = \{a = t_0<t_1<\cdots < t_n = b\}$ of $[a,b]$ s.t. $U(h) - L(h) < \varepsilon$. 
	1. Let $K = \sup\{|g(y)|:y\in[c,d]\}$
	2. Choose any $\varepsilon' s.t. 0 < \varepsilon' <  \frac{\varepsilon}{2k+(b-a)}$.
	3. Since $[c,d]$ is compact, $g:[c,d]\rightarrow \mathbb{R}$ is uniformly continuous $\implies \exists \delta$ s.t. $\delta < \varepsilon'$ and $|s-t| < \delta \implies |g(s) - g(t)|  < \varepsilon'$.
	4. Since $f$ is integrable, $\exists$ a partition $P = \{a = t_0 < t_1 <\cdots < t_n = b\}$ of $[a,b]$ s.t. $U(f,P) - L(f,P) < \delta^2$. We now argue that $P$ is the desired partition.
	Notation: For any $\varphi:[a,b]\rightarrow\mathbb{R}, \varphi$ bounded, set $M_i(\varphi) = \sup\{\varphi|_{[t_{i-1},t_i]}\}, m_i(\varphi) = \inf\{\varphi|_{[t_{i-1},t_i]}\}$.
	Let $A = \{k \in \{1,2,\cdots,n\}|M_k(f) - m_k(f) < \delta\}, B = \{k \in \{1,2,\cdots,n\}|M_k(f) - m_k(f) \geq \delta\}$. Then $\forall i \in A, \forall x,y \in [t_{i-1},t_i], |f(x) - f(y)| \leq M_i(f) -m_i(f) < \delta$.
	And then $|g(f(x)) - g(f(y)) | < \varepsilon'$ $\implies M_i(g\circ f) - m_i(g\circ f)\leq \varepsilon' \implies$ $\sum_{i \in A}(M_i(g\circ f) - m_i(g \circ f))(t_i - t_{i-1})\leq\varepsilon'\sum_{i\in A}(t_i - t_{i-1}) \leq \varepsilon'(b-a)$. 
	If $i \in B$ then $\frac{1}{\delta}(M_i(f) - m_i(f)) \geq 1$, $\sum_{i \in B}(M_i(f) - m_i(f))(t_i - t_{i-1}) \leq$ $\sum_{i \in B}\frac{1}{\delta}(M_i(f) - m_i(f))(t_i - t_{i-1}) \leq \frac{1}{\delta}(U(f,P) - L(f,P))\leq \frac{1}{\delta}\cdot\delta^2 = \delta < \varepsilon'$. 
	Since $M_i(g\circ f) - m_i(g\circ f) \leq 2k,\forall i$, $$\sum_{i \in B}(M_i(g\circ f) - m_i(g\circ f))(t_i - t_{i-1}) \leq 2K\sum_{i \in B}(t_i - t_{i-1}) < 2K \varepsilon'$$Hence $U(g\circ f,P) - L(g\circ f,P)$ 
	$= \sum_{i \in A}(M_i(g\circ f) - m_i(g\circ f))(t_i - t_{i-1}) + \sum_{i \in B}(M_i(g\circ f) - m_i(g\circ f))(t_i - t_{i-1})$ 
	$< \varepsilon'(b-a) + 2k\varepsilon' = \varepsilon'((b-a)+2k) < \varepsilon$

Note: $g$ has to be continuous. Consider $f = \begin{cases}1/q, x=p/q,\:gcd(p,q)=1\\0, x \:\text{is irrational} \end{cases}$ . $g = \begin{cases}1, x>0\\0, x \leq 0 \end{cases}$ . $g$ is integrable on any interval, but $g\circ f = \begin{cases} 1, x\:\text{is rational}\\0,x\:\text{is irrational}\end{cases}$ is NOT integrable.

**Theorem 6.2.6** If $f, g:[a, b] \rightarrow \mathbb{R}$ are integrable and $f(x) \leq g(x)\quad \forall x$. Then $\int_{[a, b]} f \leqslant \int_{[a, b]} g$
proof:
	For any partition $P, U(f, P) \leqslant U(g, P)$. Hence $U(f)=\inf _p U(f, P) \leq U(f, P) \leq U(g, P) \quad \forall P$
$$
\Rightarrow \int_{[a, b]} f=\inf _P U(f, P) \leqslant \inf _P U(g, P)=\int_{[a, b]} g .
$$

**Corollary 6.2.7** If $f:[a, b] \rightarrow \mathbb{R}$ is integrable, so is $|f|$. Moreover $\left|\int_{[a, b]} f\right| \leqslant \int_{[a, b]}|f|$.
proof: 
	Since $g(x)=|y|$ is continuous, $|f|(x)=(g \circ f)(x)$ is integrable by 6.2.5. Since
	$-|f(x)| \leq f(x) \leq |f(x)|\forall x,-|f| \leq f \leq|f| .$ By 6.2.6, $|\int_{a}^{b} f(x) \, dx| \leq \int_{a}^{b} |f(x)| \, dx$ 

**Corollary 6.2.8** (i) $\forall$ integrable function $q:[a,b]\rightarrow\mathbb{R},q^2$ is integrable. (ii) If $f, g:[a, b] \rightarrow \mathbb{R}$ are integrable, then so is $f \cdot g$.
proof:
	(i) Since $h(y)=y^2$ is continuous, $q^2=h \circ q$ is integrable
	(ii) $f \cdot g=\frac{1}{4}((f+g)^2 -(f-g)^2)$, $f, g$ integrable $\Rightarrow f \pm g$ are integrable $-(f+g)^2,(f-g)^2$ are integrable $\implies f\cdot g$ is integrable.


## 6.3 Fundamental Theorem of Calculus

>[!important] Theorem (Fundamental theorem of calculus, version 1)
>Suppose $g:[a, b] \rightarrow \mathbb{R}$ continuous, $g, f_{(a, b)}$ is differentiable, and $g^{\prime}$ is bounded and integrable on $[a, b]$. Then
>$$
\int_{[a, b]} g^{\prime}\left(=\int_a^b g^{\prime}(x) d x\right)=g(b)-g(a) \text {. }
$$

proof 
Fix a partition $P=\left\{a=t_0<t_1<\ldots<t_{n-1}<t_h=b\right\}$.
By Mean Value Theorem $\forall k \quad \exists x_k \in\left[t_k, t_{k-1}\right]$ so that
$$
g^{\prime}\left(x_k\right)=\frac{g\left(t_k\right)-g\left(t_{k-1}\right)}{t_k-t_{k-1}}
$$
ie. $\quad g^{\prime}\left(x_k\right)\left(t_k-t_{k-1}\right)=g\left(t_k\right)-g\left(t_{k-1}\right)$
$\Rightarrow \quad \forall k$
$$
m\left(g^{\prime},\left(t_{k-1}, t_k\right)\right)\left(t_k-t_{k-1}\right) \leqslant \underbrace{g^{\prime}\left(x_k\right)\left(t_k-t_{k-1}\right)}_{g\left(t_k\right)-g\left(t_{k-1}\right)} \leqslant M\left(g^{\prime},\left[t_{k-1}, t_k\right]\right) \cdot\left(t_k-t_{k-1}\right)
$$
$$
L\left(g^{\prime}, P\right)=\sum_k m\left(g^{\prime},\left[t_{k-1}, t_k\right)\right)\left(t_k-t_{k-1}\right) \leq \sum_{k=1}^n\left(g^{\prime}\left(t_k\right)-g\left(t_{k-1}\right)\right)=g(b)-g(a)
$$
similarly
$$
U(g^{\prime}, p)=\sum_k M(g^{\prime},[t_{k-1}, t_k])(t_k-t_{k-1}) \geq \sum_{k=1}^n\left(g(t_k)-g (t_{k-1}\right)) =g(b)-g(a)
$$
Hence $\quad \int_{[a,b]} g^{\prime}=\sup _p L\left(g^{\prime}, P\right) \leqslant g(b)-g(a)$
$$
\int_{[a, b]} g^{\prime}=\inf _p u\left(g^{\prime}, p\right) \geq g(b)-g(a)
$$
Therefore,
$$
\int_{[a, b]} g^{\prime}=g(b)-g(a)
$$


**Corollary 6.3.1 (Integration by parts)** Suppose $f:[a, b] \rightarrow \mathbb{R}$ are continuous, differentiable on $[a, b]$ and $f^{\prime}, g^{\prime}$ are integrable on $[a, b]$. Then$\int_{[a, b]} f \cdot g^{\prime}=(f(b) g(b)-f(a) g(a))-\int_{[a, b]} f^{\prime} \cdot g$
proof
$(f \cdot g)^{\prime}=f^{\prime} \cdot g+f \cdot g^{\prime}$
Since $f^{\prime}, g{\prime}, f, g$ are integrable so is $(f g)^{\prime}$.
By FTC version 1
$$
\begin{aligned}
f(b) g(b)-f(a) g(a) & =\int_{[a, b]}(f g)^{\prime}=\int_{[a, b]}\left(f^{\prime} g+f g^{\prime}\right) \\
& =\int_{[a, b]} f^{\prime} \cdot g+\int_{[a, b]} f \cdot g^{\prime} .
\end{aligned}
$$

>[!important] Theorem (Fundamental theorem of calculus, version 2)
> Suppose $f:[a, b] \rightarrow \mathbb{R}$ is (bounded and) integrable. Then $F(x):=\int_a^x f(u) d u$ is continuous.
> Moreover, if $f$ is continuous at $x_0 \in(a, b)$ Then $F$ is differentiable at $x_0$ and$$
F^{\prime}\left(x_0\right)=f\left(x_0\right) \text {. }
$$

proof
Since $f$ is bounded $\exists M>0$ s.t. $|f(x)| \leq M \quad \forall x \in[a, b]$. We argue first that $F$ is uniformly continuous.
For any $x, y \in(a, b), x<y$
$$
\begin{aligned}
& |F(y)-F(x)|=\left|\int_a^y F-\int_a^x F\right|=\left|\int_a^x F+\int_x^y F-\int_a^x F\right| \\
& =\left|\int_{[x, y]} F\right| \leq \int_{[x, y]}|F| \leq \int_{[x, y]} M=M(y-x)=M|y-x| .
\end{aligned}
$$
$\therefore F$ is (uniformly) continuous	
We now argue that $F$ differentiable at $x_0$ and that $F^{\prime}\left(x_0\right)=f\left(x_0\right)$, ie
$$
\lim _{h \rightarrow 0}\left|\frac{1}{h}\left(F\left(x_0+h\right)-F\left(x_0\right)\right)-f\left(x_0\right)\right|=0
$$
Note: $f\left(x_0\right)=\frac{1}{h} \cdot f\left(x_0\right) \cdot\left(\left(x_0+h\right)-x_0\right)=\frac{1}{h} \int_{x_0}^{x_0+h} f\left(x_0\right) d x$
$$
\begin{aligned}
\Rightarrow \quad&\left |\frac{1}{h}\left(F\left(x_0+h\right)-F\left(x_0\right)\right)-f\left(x_0\right)\right|=\left|\frac{1}{h}\left(\int_a^{x_0+h} f-\int_a^{x_0} f\right)-f\left(x_0\right)\right| \\
&=\left|\frac{1}{h}\left(\int_{x_0}^{x_0+h} f-\frac{1}{h} \int_{x_0}^{x_0+h} f\left(x_0\right)\right)\right|=\left|\frac{1}{h} \int_{x_0}^{x_0+h}\left(f(u)-f\left(x_0\right)\right) d u\right| \\
&\leq\left|\int_{x_0}^{x_0 \pm h} \frac{\left|f(u)-f\left(x_0\right)\right|}{|h|} d u\right| \leqslant \sup \left\{\left|f(u)-f\left(x_0\right)\right| \mid u+\left(x_0+|h\left|, x_0-\right| h\right|)\right\}
\end{aligned}
$$
Since $f$ is continuous at $x_0, \forall \varepsilon>0 \quad \exists \delta>0$ s.t.
$$
\left|u-x_0\right|<\delta \Rightarrow\left|f(u)-f\left(x_0\right)\right|<\varepsilon / 2
$$
Therefore it $|h-0|<\delta$ then
$$
\begin{aligned}
& \left|\frac{1}{h}\left(E\left(x_0+h\right)-F\left(x_0\right)\right)-f\left(x_0\right)\right| \leqslant \varepsilon / 2<\varepsilon . \\
\Rightarrow & \lim _{h \rightarrow 0}\left|\frac{1}{h}\left(F\left(x_0+h\right)-F\left(x_0\right)\right)-f\left(x_0\right)\right|=0 .
\end{aligned}
$$

Example. $f(x)=1 / x$ is continuous on $(0, \infty)$.
$\Rightarrow F(x):=\int_1^x \frac{1}{u} d u$ is differentiable on $(0, \infty)$.

Moreover $F^{\prime}(x)=1 / x>0 \Rightarrow F:(0, \infty)\rightarrow\mathbb{R}$ is strictly increasing

## 6.4 The logarithmic and exponential functions

>[!note] Def ($\ln x, \exp x$)
 $\ln (x):=F(x)=\int_1^x \frac{1}{u} d u$
Since $F(x)$ is strictly m creasing and $F^{\prime}(x) \neq 0$, it has a differentiable inverse: We define $\exp (y)=F^{-1}(y)$.
since
>$$
\begin{aligned}
& \frac{d}{d y}\left(F^{-1}(y)\right)=\frac{1}{F^{\prime}}\left(F^{-1}(y)\right) \quad \text { and since} \quad F^{\prime}(x)=1 / x \\
& \frac{d}{d y}(\exp (y))=\frac{1}{1 / \exp (y)}=\exp (y) .
\end{aligned}
>$$
>Since $\ln (1)=\int_1^1 \frac{d u}{u}=0, \quad \exp (0)=1$.


**Lemma 6.4.1**
(i)   $\ln (x y)=\ln (x)+\ln (y)$
(ii)  $\ln \left(\frac{1}{y}\right)=-\ln (y)$ 
(iii) $\ln \left(x^n\right)=n \ln (x)\quad \forall n \in \mathbb{Z}_i$ 

Proof 
(i) By the chain rule$$
\frac{d}{d x}(\ln (x y)-\ln x)=\frac{1}{x y} \cdot \frac{d}{d x}(x y)-\frac{1}{x}=\frac{1}{x y} \cdot y-\frac{1}{x}=0 \text {. }
	$$$\Rightarrow \quad \ln (x y)-\ln x=c$ for some $c \in \mathbb{R}$.
Since $\ln (1)=0, \quad c=\ln (1 \cdot y)-\ln (1)=\ln (y)$.
$$
\therefore \quad \ln (x y)-\ln (x)=\ln (y) \quad \text { and (i) follows. }
$$
(ii) $0=\ln 1=\ln \left(y \cdot \frac{1}{y}\right)=\ln y+\ln \left(\frac{1}{y}\right) \Rightarrow \ln (1 / y)=-\ln (y)$.
(iii) For $n>0$, (iii) follows from (i) by induction.
if $n<0, \quad \ln \left(x^n\right)=\ln \left(\left(x^{-1}\right)^{-n}\right)=(-n) \ln \left(\frac{1}{x}\right)=(-n) \cdot(-1) \ln x=n \ln x$

Note: Since $\ln (2)>\ln (1)=0, \ln \left(2^n\right)=n \ln 2 \rightarrow+\infty$ $\ln :(1, \infty) \rightarrow[0, \infty)$ is onto by the intermediate value theorem.
Since $\ln \left(\frac{1}{x}\right)=-\ln x, \ln :(0,1]\rightarrow(-\infty, 0]$ is also onto
$\therefore \ln :(0, \infty) \rightarrow \mathbb{R}$ is onto
$\therefore$ domain of exp $=(\ln )^{-1}$ is all of $\mathbb{R}$.

Note $\quad \ln (\exp (x) \exp (y))=\ln (\exp x)+\ln (\exp (y))=x+y$
$$
\begin{aligned}
& \Rightarrow \exp (x) \cdot \exp (y)=\exp (x+y) \\
& \Rightarrow \exp (-x) \exp (x)=\exp (-x+x)=\exp (0)=1 . \Rightarrow \exp (-x)=\frac{1}{\exp (x)} .
\end{aligned}
$$

>[!note] Def ($x^{\alpha}$)
>For $x>0$ we define $x^\alpha:(0, \infty) \rightarrow \mathbb{R}$ by
>$$
x^\alpha=\exp (\alpha \ln (x))
>$$
Note: for $\alpha \in \mathbb{N}, \quad x^\alpha=\exp (n \ln (x))=\exp \left(\ln \left(x^n\right)\right)=x^n$
So this new definition agrees with the older one if $\alpha$ is a natural number.

**Theorem 6.4.2** 
(i)   $x^\alpha \cdot x^\beta=x^{\alpha+\beta}$
(ii)  $\frac{x^\alpha}{x^\beta}=x^{\alpha-\beta}$
(iii) $\left(x^\alpha\right)^\beta=x^{\alpha \beta}$
(iv) $(x y)^\alpha=x^\alpha y^\alpha \quad$  
(v)  $\frac{d}{d x}\left(x^\alpha\right)=\alpha x^{\alpha-1}$
(vi) $\frac{d}{d \alpha} x^\alpha=\ln x \cdot x^\alpha$

Proof
(i)   $x^\alpha x^\beta=\exp (\alpha \ln x) \exp (\beta \ln x)=\exp ((\alpha+\beta) \ln (x))=x^{\alpha+\beta}$
(ii)  $\frac{1}{x^\beta}=\frac{1}{\exp (\beta \ln (x))}=\exp (-\beta \ln x)=x^{-\beta}$
(iii)
$$
\begin{aligned}
\left(x^\alpha\right)^\beta & =(\exp (\alpha \ln (x)))^\beta=\exp [\beta \ln (\exp (\alpha \ln (x)))] \\
& =\exp (\beta \cdot(\alpha \ln x))=x^{\alpha \beta}
\end{aligned}
$$(iv)$$
\begin{aligned}
& (x y)^\alpha=\exp (\alpha \ln (x y))=\exp (\alpha \ln x+\alpha \ln y) \\
& =\exp (\alpha \ln x) \cdot \exp (\alpha \ln y)=x^\alpha \cdot y^\alpha .
\end{aligned}
$$(v)  $\frac{d}{d x}\left(x^\alpha\right)=\frac{d}{d x} \exp (\alpha \ln x)=\exp (\alpha \ln x) \cdot \frac{d}{d x}(\alpha \ln x)=x^\alpha \cdot \alpha \cdot \frac{1}{x}=\alpha x^{\alpha-1}$.
(vi) $\frac{d}{d \alpha}\left(x^\alpha\right)=\frac{d}{d \alpha} \exp (\alpha \ln x)=\exp (\alpha \ln x) \cdot(\ln x)=\ln x \cdot x^\alpha$.

Remark Define $e:=\exp (x)$. Then
$$
\begin{gathered}
e^\alpha=\exp (\alpha \ln (e))=\exp (\alpha) \quad \forall \alpha \text {, ie } \\
\exp (x)=e^x .
\end{gathered}
$$

**Lemma 6.4.3** $\lim _{n \rightarrow \infty}\left(1+\frac{1}{n}\right)^n=e$.
Proof 
$(1+1 / n)^n=\exp (n \ln (1+1 / n))$. Since $\exp (x)$ is continuous
$$
\begin{aligned}
\Rightarrow & \lim _{n \rightarrow \infty}(1+1 / n)^n=\exp \left(\lim _{n \rightarrow \infty}(n \ln (1+1 / n))\right) \\
\lim _{n \rightarrow \infty} n \ln (1+1 / n)= & \lim _{h \rightarrow \infty} \frac{\ln (1+1 / n)}{1 / n}=\lim _{h \rightarrow 0} \frac{\ln (1+h)-\ln (1)}{h}=\left.\left(\frac{d}{d n} \ln (x)\right)\right|_{n=1}=\frac{1}{1}\\
\Rightarrow &\lim _{n \rightarrow \infty}\left(1+\frac{1}{n}\right)^n=e^{\lim _{n \rightarrow \infty} n \ln (1+1 / n)}=e^1=e_0
\end{aligned}
$$

>[!note] Theorem (Change of variables)
>Suppose $I, J$ are open intervals $u: I \rightarrow J$ is differentiable and $u$ is continuous (i.e. $u \in C^1(I)$ )
Suppose $f: J \rightarrow \mathbb{R}$ is continuous. Then $\forall a, b \in I$
>$$
\int_a^b(f \circ u)(x) u^{\prime}(x) d x=\int_{u(a)}^{u(b)} f(u) d u \text {. }
$$

Proof 
Since $f \circ u$, $u^{\prime}$ are continuous, $(f \circ u) \cdot u^{\prime}$ is continuous on $I$, hence integrable. Fix $c \in I$ and define $F(y)=\int_c^y f(t) d t$
Then by the fundamental theorem of calculus, version 2$, F$ is differentiable and $F^{\prime}(y)=f(y) \quad \forall y \in J$.
Let $g:=F \circ u$. By the chain rule
$$
\begin{aligned}
& g^{\prime}(x)=F^{\prime}(u(x)) \cdot u^{\prime}(x)=f(u(x)) \cdot u^{\prime}(x) \\
\Rightarrow \quad & \int_a^b(f \circ u)(x) \cdot u^{\prime}(x) d x=\int_a^b g^{\prime}(x) d x=g(b)-g(a) \\
= & F(u(b))-F(u(a))=\int_c^{u(b)} f(t) d t-\int_c^{u(a)} f(t) d t \\
= & \int_{u(a)}^{u(b)} f(t) d t .
\end{aligned}
$$


# Chapter 7 Interchange of limit operations

## 7.1 Integration and differentiation of sequences of functions

Example. Consider $f_n:[0,2]\rightarrow\mathbb{R},f_n(x) = \begin{cases}n, \frac{1}{n}\leq 2 \leq \frac{2}{n}\\0,\quad\text{o.w.}\end{cases}$ . Then $\lim_{n\rightarrow\infty}\int_{0}^2f_n(x) dx =1$. But $f_n(x)\rightarrow 0, \forall x\in[0,2]$. So $\lim_{n\rightarrow\infty}\int_{0}^2f_n\neq \int_{0}^2(\lim f_n)$. 

Example. $\exists$ a sequence of integrable function $f_n:[0,1] \rightarrow \mathbb{R}$ s.t. $f(x)=\lim _{n \rightarrow \infty} f_n(x)$ is not integrable.
Construction:
$Q \cap[0,1]$ in countable, so $\exists$ a bijection $\mathbb{N}\rightarrow \mathbb{Q} \cap[0,1], n \mapsto r_n$.
Now define $f_{n} :[0,1] \rightarrow \mathbb{R}$$$
f_n(x)= \begin{cases}1 & x=r_1, \ldots r_n \\ 0 & \text { otherwise }\end{cases}
$$Each $n$ is integrable. But $\lim _{n \rightarrow \infty} f_n(x)= \begin{cases}1 & x \in Q \cap[0,1] \\ 0 & x \notin Q \cap[0,1]\end{cases},$ which is not integrable


**Theorem 7.1.1** Suppose $\left\{f_n:[a, b] \rightarrow \mathbb{R}\right\}$ is a sequence of integrable functions and suppose $f_n \rightarrow f$ uniformly. Then $f$ is integrable and $\quad \int_{[a, b]} f=\lim _{n \rightarrow \infty} \int_{[a, b]} f_0$
Recall $f_n \rightarrow f$ uniformly on $[a, b]$ if $\forall \varepsilon>0 \quad \exists N$ s.t.
$$
(*) \sup _{x \in[a, b]}\left|f_n(x)-f(x)\right|<\varepsilon \quad \forall n \geq N_0 .
$$
Proof 
	Pick a partition $P$ of $[a, b]$ so that
$$
U\left(f_N, P\right)-L\left(f_{N,} P\right)<\varepsilon
$$
Then, $\forall i$$$
\begin{aligned}
& \sup _{[t_i, t_{i+1}]} f \leq \sup _{\left[t_{i}, t_{i+1}\right]}\left(f_N-f\right)+\sup _{\left[t_i, t_{i+1}\right]} f_N \\
& \Rightarrow U(f, P) \equiv U\left(f-f_N, P\right)+U\left(f_N, P\right) \\
& \leqslant \varepsilon \cdot(b-a)+U\left(f_N, P\right) \\
&
\end{aligned}
$$Similarly
$$
L(f, P) \geq L\left(f_N, P\right)+(-\varepsilon) \cdot(b-a)
$$
Hence
$$
U(f, P)-L(f, P) \leqslant 2 \varepsilon \cdot(b-a)+\varepsilon
$$
$\Rightarrow f$ is integrable.
Finally $\left|\int_{[a, b]} f-\int_{[a, b]} f_n\right| \leq \int_{[a, b]}\left|f-f_n\right|$
$$
\begin{aligned}
& \leq\left(\operatorname{sup}_{[a, b]}\left|f(x)-f_n(x)\right|\right) \cdot(b-a)  \xrightarrow[n \rightarrow \infty]{ } 0 \\
&\therefore \quad \lim _{n \rightarrow \infty} \int_{[a, b]} f_n =\int_{[a, b]} f(=\int_{[a, b]}(\lim f)).
\end{aligned}
$$


**Theorem 7.1.2** Suppose $\left\{f_n:(a, b) \rightarrow \mathbb{R}\right\}_{n \in \mathbb{N}}$ is a sequence of $C^f$ functions and suppose $\left\{f_n^{\prime}\right\}_{k \in N}$ converges uniformly to some function $g$.
Assume further $\exists c \in(a, b)$ at $\left\{f_n(c)\right\}$ converges.
The $\left(f_n\right)$ converges piece-wise to a differentiable function $f$ and $f^{\prime}=$ g. (i.e. $\left.\lim _{n \rightarrow \infty}\left(f_n^{\prime}\right)=\left(\lim f_n\right)^{\prime}\right)$

Proof 
By the fundamental theorem of calculus
$$
f_n(x)-f_n(c)=\int_c^x f_n^{\prime}(t) d t
$$

By 7.1.1
$$
\int_c^x f_n^{\prime}(t) d t \rightarrow \int_c^x g(t) d t \text {. }
$$
Since $f_n(x)=f_n(c)+\int_c^x f_n^{\prime}(t) d t$
Then $f(x):=\lim _{n \rightarrow \infty} f_n(x)$ exist and equals $\lim _{n \rightarrow \infty} f_n(c)+\int_c^x g(t) d t$.
$$
f(c)=\lim _{n \rightarrow \infty} f_n(c)+\int_c^c g(t) d t=0
$$and
$$
\begin{aligned}
& f(x)-f(c)=\int_c^x g(t) d t . \\
& \text { F.T.C v2 } \Rightarrow \\
& f^{\prime}(x)=\frac{d}{d x}\left(\int_c^x g(t) d t\right)=g(x)\left(=\lim _{n \rightarrow \infty} f_n^{\prime}(x)\right) .
\end{aligned}
$$

**Theorem 7.1.3** Suppose $a<b, c<d, f$ is continuous on
$$
S=[a, b] \times(c, d) \equiv\left\{(x, y) \in \mathbb{R}^2 \mid a \leq x \leq b, c<y<d\right\} \text {. }
$$
Assume $\forall x, y \mapsto f(x, y)$ is differentiable and the function $(x, y) \rightarrow \frac{\partial f}{\partial y}(x, y)$ is continuous on $S$
Then$$
F:(c, d) \rightarrow \mathbb{R} \quad F(y)=\int_a^b f(x, y)  d x \text { is differentiable }
$$
and $\quad F^{\prime}(y)=\int_a^b \frac{\partial f}{\partial y}(x, y) d x$
i.e. $\quad \frac{d}{d y}(\int_a^b f(x, y) d y)=\int_a^b \frac{\partial f}{\partial y}(x, y) d x$.
Proof 
Note first that the definition of $F(y)$ makes sense:
Since $f$ is continuous, $\forall y \quad x\mapsto f(x, y)$ is integrable.
To prove that $F$ is differentiable at $y \in(c, d)$ we need to show: $\forall \varepsilon>0 \quad \exists \delta>0$ so that if $0<|h|<\delta$ then
$$
\begin{aligned}
& \left|\frac{1}{h}(F(y+h)-F(y))-\int_a^b \frac{\partial f}{\partial y}(x, y) d x\right|<\varepsilon \\
& \frac{1}{h}(F(y+h)-F(y))=\int_a^b \frac{1}{h}(f(x, y+h)-f(x, y)) d x
\end{aligned}
$$
M. V. T. $\Rightarrow \forall x \quad \exists y_{h, x}$ between $y+h$ and $y$ s.t.
$$
f(x, y+h)-f(x, y)=((y+h)-y) \cdot \frac{\partial f}{\partial x}(x,y_{h, x})
$$
ie $\frac{1}{h}(F(y+h)-F(y))=\int_a^b \frac{\partial f}{\partial x}\left(x, y_{h, x}\right) d x$ 
Pick $h_0$ sufficiently small, s.t. $\left[y-h_0, y+ h_0\right] \subseteq (c, d)$
Since $\frac{\partial f}{\partial y}(x, y)$ is uniformly continuous on $[a, b] \times\left[y-h_0, y+h_0\right]$
Therefore, given $\varepsilon > 0, \exists \delta$  s.t.
$$
\left|\frac{\partial f}{\partial x}\left(x, y_{h, x}\right)-\frac{\partial f}{\partial y}(x, y)\right|<\varepsilon /(b-a) \text { if }|h|<\delta
$$

And then
$$
\begin{aligned}
& \quad\left|\frac{1}{h}(F(y+h)-F(y))-\int_a^b \frac{\partial f}{\partial y}(x, y) d x\right| \\
& =\left|\int_a^b\left(\frac{\partial f}{\partial y}(x, y_{h, x})-\frac{\partial f}{\partial y}(x, y)\right) d x\right| \leq \int_a^b\left|\frac{\partial f}{\partial y}(x,y_{h, x})-\frac{\partial f}{\partial y}(x, y)\right| d x \\
& <(b-a) \cdot \frac{\varepsilon}{b-a}=\varepsilon .
\end{aligned}
$$

**Theorem 7.1.4** $R=[a, b] \times[c, d]$, $U$ open set in $\mathbb{R}^2$ containing $R$. $f: U \rightarrow \mathbb{R}$ continuous, $\frac{\partial f}{\partial x}: U \rightarrow \mathbb{R}$ exists and is continuous.
Then $F(x):=\int_c^d f(x, y) d y$ is differentiable on $(a, b)$ and
$$
F^{\prime}(x)=\frac{d}{d x}\left(\int_c^d f(x, y) d y\right)=\int_c^d \frac{\partial f}{\partial x}(x, y) d y \text {. }
$$

Proof 
Fix $x\in(a, b)$. We want to show
$$
\lim _{h \rightarrow 0} \frac{1}{h}(F(x+h)-F(x))=\int_c^d \frac{\partial f}{\partial x}(x, y) d y
$$
Since $\frac{\partial f}{\partial x}$ is continuous on $R$ and $R$ is compact, $\frac{\partial f}{\partial x}$ is uniformly continuous, $\Rightarrow \forall \varepsilon>0 \quad \exists \delta>0$ so that
$$
d_2\left((x, y),\left(x^{\prime}, y^{\prime}\right)\right)<\delta \Rightarrow\left|\frac{\partial f}{\partial x}(x, y)-\frac{\partial f}{\partial x}\left(x^{\prime}, y^{\prime}\right)\right|<\frac{\varepsilon}{d-c}
$$

By Mean Vale Theorem, $\forall(x, y) \in U \quad \forall h$ sufficiently small, $\exists \xi=\xi(x, y, h)$ between $x$ and $x+h$ so that
$$
\frac{f(x+h, y)-f(x, y)}{(x+h)-x}=\frac{\partial f}{\partial x}(\xi, y)
$$
Therefore if $|h|<\delta, \quad d_2((\xi, y),(x, y)) \leq|h|<\delta$ and then 
$$
\begin{aligned}
& \left|\frac{1}{h} F(x+h, y)-F(x)-\int_c^d \frac{\partial f}{\partial x}(x, y) d y\right|= \\
= & \left|\frac{1}{h}\left(\int_c^d f(x+h, y) d y-\int_c^d f(x, y) d y\right)-\int_c^d \frac{\partial f}{\partial x}(x, y) d y\right| \\
= & \left|\int_c^d\left(\frac{f(x+h, y)-f(x, y)}{h}-\frac{\partial f}{\partial x}(x, y)\right) d y\right| \\
\leqslant & \int_c^d\left|\frac{\partial f}{\partial x}(\xi, y)-\frac{\partial f}{\partial x}(x, y)\right| d y \leqslant \int_c^d \frac{\varepsilon}{d-c} d y=\varepsilon
\end{aligned}
$$

Example. Compute $\int_0^\pi e^{\cos (x)} \cos (\sin x) d x$
Solution
We'll use: $\forall z \in \mathbb{C} \quad e^{\bar{z}}:=\sum_{n=0}^{\infty} \frac{z^n}{h !}$ exists and $\frac{d}{d z}\left(e^z\right):=\lim _{h \rightarrow 0} \frac{e^{z+h}-e^2}{h}$ also exists and equals $e^z$.

Consequently for any differentiable function $f:(a, b) \rightarrow \mathbb{C}$, $\frac{d}{d x} e^{f(x)}=e^{f(x)} \cdot f^{\prime}(x)$. This can also be proved using.
$$
e^{f(x)}=e^{R e f(x)} \cdot e^{i \operatorname{lm}(f(x))}
$$

Now let $I(b)=\int_0^\pi e^{b \cos x} \cos (b \sin x) d x$
Since $\cos (u)$ is even, $\quad e^{b \operatorname{\cos x}} \cos (b \sin x)$ is an even function of $x$
$$
\begin{aligned}
& \Rightarrow I(b)=\frac{1}{2} \int_{-\pi}^\pi b \cos x \cos (b \sin x) d x=\frac{1}{2} \int_0^{2 \pi} b \cos x \cos (b \sin x) d x \\
& e^{b e^{i x}}=e^{b(\cos x+i \sin x)}-e^{b \cos x} \cdot e^{i b \sin x}=e^{b \cos x} \cdot(\cos (b \sin x)+ \\
& i \sin (b \sin x)) \\
& \Rightarrow b \cos x \cdot \cos (b(\sin x))=\operatorname{Re}\left(e^{b e^{i x}}\right) \\
& \Rightarrow I(b)=\operatorname{Re}\left(\frac{1}{2} \int_0^{2 \pi} e^{b e^{i x}} d x\right) \\
& \frac{d}{d x} \int_0^{2 \pi} e^{b\left(e^{i x}\right)} d x=\int_0^{2 \pi} \frac{\partial}{\partial b}\left(e^{b\left(e^{i x}\right)}\right) d x \\
& =\int_0^{2 \pi} e^{b e^{i x}} \cdot \frac{\partial}{\partial b}\left(b e^{i x}\right) d x=\int_0^{2 \pi} e^{b e^{i x}} \cdot e^{i x} d x \\
&
\end{aligned}
$$
Note that$$
\begin{aligned}
& \frac{\partial}{d x}\left(e^{b e^{i x}}\right)=e^{b e^{i x}} \cdot \frac{\partial}{\partial x}\left(b e^{i x}\right)=e^{b e^{i x}} \cdot i b \cdot e^{i x} \\
& \begin{aligned}
& \frac{d}{d b}\left(\int_0^{2 \pi} \frac{1}{2} e^{b e^{i x}} d x\right)=\frac{1}{2 i} \int_{-0}^{2 \pi} \frac{d}{d x}\left(e^{b e^{i x}}\right) d x=\left.\frac{1}{2 i}\left(e^{b e^{i x}}\right)\right|_0 ^{2 \pi} \\
&=\frac{1}{2 i}\left(e^{b e^{2 \pi}}-e^{b e^0}\right)=\frac{1}{2}\left(e^b-e^{-b}\right)=0 \\
& \Rightarrow \frac{d}{d b}|I|=0 \\
& \Rightarrow \int_0^\pi e^{\cos (x)} \cos (\sin x) d x=I(1)=I(0)=\int_0^\pi e^{0 \cos x} \cos (0 \sin x) d x \\
&=\int_0^\pi d x=\pi .
\end{aligned}
\end{aligned}
$$

**Aside: Improper integrals.**
Supple $f: \mathbb{R} \rightarrow \mathbb{R}$ is integrable on every interval $(a, b)$.

Then we define
$$
\int_a^{\infty} f:=\lim _{b \rightarrow \infty} \int_a^b f \text { if the limit exists }
$$

Similarly
$$
\int_{-\infty}^b f=\lim _{a \rightarrow-\infty} \int_a^b f \text { if the emit exists }
$$
and $\quad \int_{-\infty}^{\infty} f=\lim _{\substack{a \rightarrow-\infty \\ b \rightarrow+\infty}} \int_a^b f^a$ if the limit exist
WARNING
$$
\lim _{a \rightarrow+\infty} \int_{-a}^a \sin (x) d x=\lim _{a \rightarrow+\infty} 0 \text { but }
$$
$\int_{-\infty}^{\infty} \sin (x) d x$ does not exit.

Note: if $f: \mathbb{R} \rightarrow \mathbb{R}$ is integrable on $[ a, b]$ at $f(x)=0$ for $x \notin[a, b]$, then $\int_{-\infty}^{\infty} f=\int_{[a, b]} f$.

