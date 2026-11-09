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

### 3.3.2 Decide which of the following sets are compact. For those that are not compact, show how Definition 3.3.1 breaks down. In other words, give an example of a sequence contained in the given set that does not possess a subsequence converging to a limit in the set.

#### (a) $\mathbb{N}$

Not compact. 

The sequence $(a_n)$ where $a_n = n, n \in \mathbb{N}$ does not have a convergent subsequence.


#### (b) $\mathbb{Q} \cap [0, 1]$

Not compact.

Since $\mathbb{Q}$ is dense in $\mathbb{R}$, consider a sequence in $\mathbb{Q} \cap [0, 1]$ that converges to $\sqrt{2}/2$. The limit is not contained in the set.


#### (c) The Cantor set

The Cantor set is bounded above by 1 and bounded below by 0. The Cantor set is an arbitrary intersection of closed sets, thus it is closed. 

Hence it is compact.


#### (d) $\\{1 + 1/2^2 + 1/3^2 + ... + 1/n^2: n \in \mathbb{N}\\}$

Not compact.

The partial sum converges to $\pi^2/6$ which is not in the set, because the partial sum is strictly increasing. Take any subsequence of $s_n$, it converges to $\pi^2/6$ which is not in the set.


#### (e) $\\{1, 1/2, 2/3, 3/4, ...\\}$

The set is bounded below by 0 and bounded above by 1.

The set has one limit point which is 1, and it is contained in the set. Thus it is closed.

Hence it is compact.



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



### 3.3.5 Decide whether the following propositions are true or false. If the claim is valid, supply a short proof, and if the claim is false, provide a counterexample.

#### (a) The arbitrary intersection of compact sets is compact.

We want to show the statement is true.

By theorem 3.3.4 compact sets are closed and bounded. 

By theorem 3.2.14 the intersection of an arbitrary collection of closed sets is closed. The intersection of compacts sets are also bounded. 

Thus the arbitrary intersection of compact sets is compact.


#### (b) The arbitrary union of compact sets is compact.

We want to show the statement is false.

Consider $\cup_{n \in \mathbb{N}} [0, n]$. Each closed interval is closed and bounded. However the arbitrary union is unbounded. Thus is it not compact.


#### (c) Let $A$ be arbitrary, and let $K$ be compact. Then, the intersection $A \cap K$ is compact.

We want to show the statement is false.

Consider $A = (0, 2)$ and $K = [1, 3]$. Then $A \cap K = [1, 2)$ which is not closed, thus not compact.


#### (d) If $F_1 \supseteq F_2 \supseteq ...$ is a nested sequence of nonempty closed sets, then the intersection $\cap_{n=1}^\infty F_n \neq \emptyset$.

We want to show that the statement is false.

Consider $\cap_{n \in \mathbb{N}} [n, \infty)$. Each interval $[n, \infty)$ is closed because its complement $(\infty, n)$ is open.

$F_1 \supset F_2 \supseteq ...$ since each interval removes one number at a time.

By the archimedian property, for any $x \in \mathbb{R}$, there exists $n \in \mathbb{N}$ such that $n > x$. Thus $x \notin \cap_{n \in \mathbb{N}} [n, \infty)$. Hence $\cap_{n \in \mathbb{N}} [n, \infty) = \emptyset$.



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

Bisect $I_0$ into two closed intervals $I_L$ and $I_R$. Consider $I_L \cap K$ and $I_R \cap K$. If both sets have a finite subcover, then $K$ has a finite subcover which contradicts the hypothesis. Thus at least one of $I_L \cap K$ and $I_R \cap K$ do not have a finite subcover. Pick that half and call it $I_1$. By construction $I_1 \subset I_0$.

Bisect $I_1$ into two closed intervals $I_{1L}$ and $I_{1R}$. Consider $I_{1L} \cap K$ and $I_{1R} \cap K$. If both sets have a finite subcover, then $I_1 \cap K$ has a finite subcover, which contradicts the previous step. Thus at least one of $I_{1L} \cap K$ and $I_{1R}$ do not have a finite subcover. Pick that half and call it $I_2$. By construction $I_2 \subset I_1 \subset I_0$.

Continuing in this fashion, we constructed $I_0 \supseteq I_1 \supseteq I_2 \supseteq ...$ with the property that, for each $n$, $I_n \cap K$ cannot be finitely covered.

Since in each step we bisect the interval, $|I_n| = \frac{1}{2^n} |I_0|$. Thus $\lim |I_n| = 0$.


#### (b) Argue that there exists an $x \in K$ such that $x \in I_n$ for all $n$.

Since $K$ is compact and $I_n$ is closed, by exercise 3.3.4, $I_n \cap K$ is compact. 

By the nested compact set property 3.3.5, $\cap_{n \in \mathbb{N}} (I_n \cap K) \noteq \emptyset$. Thus there exists some $x \in K$ such that $x \in I_n$ for all $n$.


#### (c) Because $x \in K$, there must exist an open set $O_{\lambda_0}$ from the original collection that contains $x$ as an element. Explain how this leads to the desired contradiction.

Since $x \in \O_{\lambda_0}$ and $O_{\lambda_0}$ is open, there exists a neighborhood $V_\epsilon(x) \subseteq O_{\lambda_0}$.

Since $|I_n| \to 0$, there exists some $m \in \mathbb{N}$ such that for all $n \geq m$, $|I_n| < \epsilon$. 

Suppose $y \in I_n$, $n \geq m$. Since $x \in I_n$ for all $n$, we have $|y - x| < \epsilon$. Thus $y \in V_\epsilon(x)$. Hence we have have $I_n \subseteq V_\epsilon(x)$ for all $n \geq m$.

Then we have for all $n \geq m$,

$$I_n \cap K \subseteq I_n \subseteq V_\epsilon(x) \subseteq O_{\lambda_0}$$

So $I_n \cap K$ has a finite subcover (a single subcover $O_{\lambda_0}$), which contradicts the assumption that $I_n \cap K$ cannot be finitely covered for all $n$.



### 3.3.10 Here is an alternate proof to the one given in Exercise 3.3.9 for the final implication in the Heine-Borel Theorem. Consider the special case where $K$ is a closed interval. Let $\\{O_\lambda: \lambda \in \Lambda \\}$ be an open cover for $[a, b]$ and define $S$ to be the set of all $x \in [a, b]$ such that $[a, x]$ has a finite subcover from $\\{O_\lambda: \lambda \in \Lambda\\}$. 

#### (a) Argue that $S$ is nonempty and bounded, and thus $s = \sup S$ exists.

Consider $[a, a] = \\{a\\}$. Since $a \in [a, b]$, $a$ is covered by some open set $O_{\lambda_0}$ in the collection. Thus $a \in S$ and $S$ is not empty.

Since $S \subseteq [a, b]$, $S$ has an upper bound $b$. Thus $s = \sup S$ exists.


#### (b) Now show $s = b$, which implies $[a, b]$ has a finite subcover.

Assume towards contradiction that $s < b$. 

Since $s \in [a, b]$ which is covered $\cup_{\lambda \in \Lambda} O_\lambda$, $s$ is covered by some open set in this collection $O_{\lambda_0}$.

Since $O_{\lambda_0}$ is open, and $s \in O_{\lambda_0}$, there exists an open neighborhood $V_\delta(s) \subseteq O_{\lambda_0}$ for some $\delta > 0$. Let $\epsilon = \min \\{\delta, b-s\\}$.

Since $s = \sup S$, there exists some $x \in S$ such that $s - \epsilon < x \leq s$. Since $x \in S$, $[a, x]$ has a finite subcover $O_{\lambda_1}, ..., O_{\lambda_n}$. 

Note that $|x - s| < \epsilon$. Thus $x \in V_\epsilon(s)$.

Note that $s + \frac{\epsilon}{2} \in V_\epsilon(s)$. By construction, we have $s + \frac{\epsilon}{2} \leq s + \frac{b-s}{2} < b$.

Since both $x$ and $s + \frac{\epsilon}{2}$ are in $V_\epsilon(s)$, it follows that the interval 

$$[x, s + \frac{\epsilon}{2}] \subseteq V_\epsilon(s) \subseteq O_{\lambda_0}$$

Since $O_{\lambda_1}, ..., O_{\lambda_n}$ covers $[a, x]$ and $O_{\lambda_0}$ covers $[x, s + \frac{\epsilon}{2}]$ and $[a, s + \frac{\epsilon}{2}] = [a, x] \cup [x, s + \frac{\epsilon}{2}]$, it follows that $O_{\lambda_0}, O_{\lambda_1}, ..., O_{\lambda_n}$ covers $[a, s + \frac{\epsilon}{2}]$.

Then $s + \frac{\epsilon}{2} \in S$. This contradicts the fact that $s = \sup S$.

Hence we conclude that $s = b$.

Now we want to show that $b \in S$, i.e. $[a, b]$ has a finite subcover.

Since $b \in [a, b]$, $b$ is covered an open set $O_{\lambda'}$ from the open cover $\cup_{\lambda \in \Lambda} O_\lambda$. Since $O_{\lambda'}$ is open, there exists $V_\epsilon(b) \subseteq O_{\lambda'}$.

Consider $x \in S$ such that $b - \frac{\epsilon}{2} < x \leq b$. We know such an $x$ exists because $b - \frac{\epsilon}{2}$ is not an upper bound.

Then $[a, x]$ has a finite subcover and $[x, b] \subseteq V_\epsilon(b) \subseteq O_{\lambda'}$. So $[a, b]$ has a finite subcover.


#### (c) Finally, prove the theorem for an arbitrary closed and bounded set $K$.

Suppose $\cup_{\lambda \in \Lambda} O_\lambda$ is an open cover of $K$.

Since $K$ is bounded, $K \subseteq [-M, M]$ for some $M \in \mathbb{R}$.

Since $K$ is closed, $K^c$ is open.

Then $[-M, M] \subseteq (\cup_{\lambda \in \Lambda} O_\lambda) \cup K^c$.

Then from part (b), $[-M, M]$ has a finite subcover $O_{\lambda_1}, ..., O_{\lambda_n}, K^c$.

Then $K$ has a finite subcover $O_{\lambda_1}, ..., O_{\lambda_n}$.



### 3.3.11 Consider each of the sets listed in Exercise 3.3.2. For each one that is not compact, find an open cover for which there is no finite subcover.

### (a) $\mathbb{N}$

Consider the open cover $\cup_{n \in \mathbb{N}} V_{1/2}(n)$. It is an open cover of $\mathbb{N}$ but there is no finite subcover that covers $\mathbb{N}$.


#### (b) $\mathbb{Q} \cap [0, 1]$

Let $a = \frac{\sqrt{2}}{2}$. Consider the open cover $\cup_{n \in \mathbb{N} (-1, a - \frac{1}{n}) \cup (a + \frac{1}{n}, 2)$. 

For any $x \in \mathbb{Q} \cap [0, 1]$, $x < a$ or $x > a$. There exists $n \in \mathbb{N}$ such that $x < a - \frac{1}{n}$ or $x > a + \frac{1}{n}$. Thus it is an open cover of $\mathbb{Q} \cap [0, 1]$.

Note that this open has no finite subcover. Given a finite subcover, let $N$ be the largest index. The union is $(-1, a - \frac{1}{N}) \cup (a + \frac{1}{N}, 2)$. Since $\mathbb{Q}$ is dense, there exists a rational number in $(a - \frac{1}{N}, a + \frac{1}{N})$, which is not in the subcover.


#### (c) $\\{1 + 1/2^2 + 1/3^2 + ... + 1/n^2: n \in \mathbb{N} \\}$

Consider the partial sum $s_n = 1 + 1/2^2 + ... + 1/n^2$ and the open cover $\cup_{n \in \mathbb{N}} (0, s_n)$.

The partial sum is strictly increasing. For any $s_n$ in the set, we have $s_n \in (0, s_{n+1})$. Then $\cup_{n \in \mathbb{N}} (0, s_n)$ is an open cover of the set.

Note that this open cover has no finite subcover. Consider $(0, s_{\lambda_1}), ..., (0, s_{\lambda_n})$. Take $M = \max \\{s_{\lambda_1}, ..., s_{\lambda_n}\\}$. There exists $s_k$ such that $s_k > M$ which is outside the subcover.

