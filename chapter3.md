Understanding Analysis - Chapter 3 <br>
Basic Topology of \mathbb{R}
================
Rosie Sun <br>
2026-11-01


# 3.2 Open and Closed Sets

### 3.2.2 Let $A = \\{(-1)^n + 2/n: n = 1, 2, 3, ...\\}$ and $B = \\{x \in \mathbb{Q}: 0 < x < 1\\}$.

#### (a) What are the limit points?

A: The limit points are 1 and -1.

B: The limit points are [0, 1].

#### (b) Is the set open? Closed?

A: Neither. $A$ is not closed because -1 is a limit point not in $A$. $A$ is not open because it is countable. Specifically, 2 is in $A$ but $V_\epsilon(2)$ is not in $A$. 

B: Neither. $B$ is not closed because it does not contain all the limit points (0, 1, and the irrationals). $B$ is not open because for any element in $B$, its neighborhood contains irrationals.

#### (c) Does the set contain any isolated points?

A: Yes. Every element of $A$ is an isolated point except 1. 

B: No. Every element of $B$ is a limit point of $B$.

#### (d) Find the closure of the set.

$\overline{A} = A \cup \\{-1\\}$

$\overline{B} = [0, 1]$.


### 3.2.3 Decide whether the following sets are open, closed or neither.

#### (a) $\mathbb{Q}$

We have $\mathbb{Q}$ is dense in $\mathbb{R}$. It is not open because for any element in $\mathbb{Q}$, its neighborhood contains irrationals. It is not closed because its closure is $\mathbb{R}$.

#### (b) $\mathbb{N}$

It is closed. For any $n \in \mathbb{N}$, there is a neighborhood of $n$ e.g. $(n-1/2, n+1/2)$ that contains only $n$. The set has no limit points so it vacuously contains its limits.

#### (c) $\\{x \in \mathbb{R}: x \neq 0\\}$

The set is open because its complement (a single point 0) is closed. $\\{0\\}$ does not have any limit points so it vacuously contains its limit points.

#### (d) $\\{1 + 1/4 + 1/9 + ... + 1/n^2: n \in \mathbb{N} \\}$

The set is not closed because the series $\sum 1/n^2$ converges by 2.4.7. Suppose $\lim s_n = L$. Since the sequence of partial sums is strictly increasing, $s_n < L \forall n \in \mathbb{N}$. Thus the set does not contain its limit point $L$.

The set is not open because each $s_n$ has a neighborhood containing real numbers not in the set.

#### (e) $\\{1 + 1/4 + 1/9 + ... + 1/n: n \in \mathbb{N} \\}$

The set is closed. The series $\sum 1/n$ diverges so it does not have any limit points, so it vacuously contains its limits.




# 3.3 Compact Sets

## Exercises

### 3.3.3 Prove the converse of Theorem 3.3.4 by showing that if a set $K \subseteq \mathbb{R}$ is closed and bounded, then it is compact.

Let $(a_n)$ be a sequence in $K$. Since $K$ is bounded, the sequence $(a_n)$ is bounded.

By the Bolzano-Weierstrass theorem 2.5.5, $(a_n)$ contains a convergent subsequence, $(a_{n_k})$. Suppose $a_{n_k} \to a$. Since $K$ is closed, $a \in K$ by 3.2.7.

Thus the sequence $(a_n)$ in $K$ has a subsequence that converges to a limit that is also in $K$. Hence we conclude $K$ is compact by 3.3.1.



### 3.3.4 Assume $K$ is compact and $F$ is closed. Decide if the following sets are definitely compact, definitely closed, both, or neither.

#### (a) $K \cap F$

By theorem 3.3.4 $K$ is closed and bounded. By theorem 3.2.14 $K \cap F$ is closed.

Since $K \cap F \subset K$ and $K$ is bounded, $K \cap F$ is bounded. Thus by theorem 3.3.4 $K \cap F$ is compact.


#### (b) $\overline{F^c \cup K^c}$

By theorem 3.2.12 closure $\overline{F^c \cup K^c}$ is closed.

Note that $F^c \cup K^c = (F \cap K)^c$ by De Morgan's law.

Since $K \cap F$ is bounded in $\mathbb{R}$, $K \cap F \subseteq [-M, M]$ for some $M \in \mathbb{R}$. It follows that $(K \cap F)^c \supseteq (-\infty, -M) \cup (M, \infty)$, thus it is not bounded. $F^c \cup K^c \subseteq \overline{F^c \cup K^c}$. 

$\overline{F^c \cup K^c}$ is not bounded, thus it is not compact.


#### (c) $K \setminus F$

$K \setminus F \subset K$, so it is bounded.

It is neither definitely closed or definitely compact.

Consider $K = [0, 3]$ and $F = [2, 4]$. Then $K \setminus F = [0, 2)$ which is not closed.

Consider $K = [0, 1] \cup \\{2\\}$ and $F = \\{2\\}$. Then $K \setminus F = [0, 1]$ which is closed and compact.


#### (d) $\overline{K \cap F^c}$

By theorem 3.2.12 closure $\overline{K \cap F^c}$ is closed.

Since $\overline{K \cap F^c} \subseteq \overline{K}$, and $K = \overline{K}$, $\overline{K \cap F^c}$ is bounded.

Thus $\overline{K \cap F^c}$ is compact.



### 3.3.8 Let $K$ and $L$ be nonempty compact sets, and define $d = \inf \\{|x-y|: x \in K, y \in L\\}$. 

#### (a) If $K$ and $L$ are disjoint, show $d > 0$ and that $d = |x_0 - y_0|$ for some $x_0 \in K$ and $y_0 \in L$.

Since $d = \inf \\{|x-y|: x \in K, y \in L\\}$, $d + \frac{1}{n}$ is not a lower bound for all $n \in \mathbb{N}$. Thus we can find $x_n \in K$ and $y_n \in L$ such that $d \leq |x_n - y_n| < d + \frac{1}{n}$. We have constructed a sequence $|x_n - y_n|$ which converges to $d$.

Since $K$ is compact and $x_n \in K$, by definition, there exists a convergent subsequence $x_{nk} \to x_0$ where $x_0 \in K$. 

Since $L$ is compact and $y_{nk} \in L$, there exists a convergent sequence $y_{nkj} \to y_0$ where $y_0 \in L$.

By theorem 2.5.2, $x_{nkj} \to x_0$. Thus we have $x_{nkj} - y_{nkj}$ which is a subsequence of $|x_n - y_n|$. By theorem 2.3.3 and exercise 2.3.10, $|x_{nkj} - y_{nkj}| \to |x_0 - y_0|$.

Since $|x_n - y_n| \to d$, by theorem 2.5.2 $|x_{nkj} - y_{nkj}| \to d$. Thus $d = |x_0 - y_0|$ for some $x_0 \in K$ and $y_0 \in L$.

Since $K$ and $L$ are disjoint, $x_0 \neq y_0$. Thus $d > 0$.


#### (b) Show that it's possible to have $d = 0$ if we assume only that the disjoint sets $K$ and $L$ are closed.

Consider $K = \\{n: n \in \mathbb{N}\\}$ and $L = \\{n + \frac{1}{n}: n \in \mathbb{N}, n \geq 2\\}$. 

For $n \geq 2$, $n + \frac{1}{n}$ is not an integer. Thus the two sets are disjoint. 

$K$ consists of isolated points so it vacuously contains its limit points. Thus $K$ is closed.

The sequence $(n + \frac{1}{n}) \to n$ which is contained in $L$. Thus $L$ is closed.

We have $|n + \frac{1}{n} - n| = \frac{1}{n}$. Thus $d < \frac{1}{n}$ for all $n \geq 2$. Hence $d = 0$.



### 3.3.9 Follow these steps to prove the final implication in theorem 3.3.8. Assume $K$ satisfies (i) and (ii), and let $\\{O_\lambda: \lambda \in \Lambda \\}$ be an open cover for $K$. For contradiction, let's assume that no finite subcover exists. Let $I_0$ be a closed interval containing $K$.

#### (a) Show that there exists a nested sequence of closed intervals $I_0 \supseteq I_1 \supseteq I_2 \supseteq ...$ with the property that, for each $n$, $I_n \cap K$ cannot be finitely covereed and $\lim |I_n| = 0$.




### 3.3.10

