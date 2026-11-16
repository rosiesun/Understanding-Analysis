Understanding Analysis - Chapter 4 <br>
Functional Limits and Continuity
================
Rosie Sun <br>
2026-11-02


# 4.2 Functional Limits


# 4.3 Continuous Functions


# 4.4 Continuous Functions on Compact Sets

## Exercises

### 4.4.1 

#### (a) Show that $f(x) = x^3$ is continuous on all of $\mathbb{R}$.

Let $\epsilon > 0$. Let $c \in \mathbb{R}$. We want to show that $f(x) = x^3$ is continuous at $c$.

Let $\delta = \min \\{1, \frac{\epsilon}{3c^2 + 3|c| + 1}\\}$. Suppose $|x - c| < \delta$.

We have 

$$x^3 - c^3 = (x - c) (x^2 + xc + c^2)$$

so we can focus on the term $x^2 + sc + c^2$.

Note that by reverse triangle inequality, $|x| - |c| \leq |x - c| < 1$. So $|x| < |c| + 1$.

$$
\begin{aligned}
|(x^2 + xc + c^2)|
    &= |x (x + c) + c^2| \\
    &\leq |x (x + c)| + |c^2| \\
    &= |x| |x + c| + c^2 \\
    &\leq (|c| + 1) (|x| + |c|) + c^2 \\
    &\leq (|c| + 1) (2 |c| + 1) + c^2 \\
    &= 3c^2 + 3|c| + 1
\end{aligned}
$$

Then

$$
\begin{aligned}
|f(x) - f(c)| &= |x^3 - c^3| \\
    &= |x - c| |x^2 + xc + c^2| \\
    &\leq \frac{\epsilon}{3c^2 + 3|c| + 1} (3c^2 + 3|c| + 1) \\
    &= \epsilon
\end{aligned}
$$

Hence we conclude $f(x)$ is continuous at $c$. Since $c \in \mathbb{R}$ is arbitrary, $f(x) = x^3$ is continuous on all of $\mathbb{R}$.


#### (b) Argue using Theorem 4.4.5 that $f$ is not uniformly continuous on $\mathbb{R}$.

We want to show that there exists a $\epsilon > 0$ and two sequences in $\mathbb{R}$ satisfying $|x_n - y_n| \to 0$ but $|f(x_n) - f(y_n)| \geq \epsilon$.

Consider $\epsilon = 3$, $y_n = n$ and $x_n = n + \frac{1}{n}$.

We have 

$$|x_n - y_n| = |n + \frac{1}{n} - n| = \frac{1}{n} \to 0$$

but

$$
\begin{aligned}
|f(x_n) - f(y_n)| &= |(n + \frac{1}{n})^3 - n^3| \\
    &= |(n + \frac{1}{n} - n) ((n + \frac{1}{n})^2 + n (n + \frac{1}{n}) + n^2)| \\
    &= |\frac{1}{n} (3n^2 + \frac{1}{n^2} + 3)| \\
    &= |3n + \frac{1}{n^3} + \frac{3}{n}| \\
    &\geq 3n
\end{aligned}
$$

Thus $|f(x_n) - f(y_n)| \geq 3n \geq 3$ for all $n \in \mathbb{N}$.

Hence we conclude $f(x) = x^3$ is not uniformly continuous on $\mathbb{R}$.


#### (c) Show that $f$ is uniformly continuous on any bounded subset of $\mathbb{R}$.

Suppose $A \subseteq \mathbb{R}$ is a bounded subset. Then $A \subseteq [-M, M]$ for some $M > 0$.

Let $\epsilon > 0$, $x, y \in A$. Then $|x| \leq M$ and $|y| \leq M$.

Let $\delta = \frac{\epsilon}{3M^2}$. Suppose $|x - y| < \delta$.

We have

$$
\begin{aligned}
|f(x) - f(y)| &= |x^3 - y^3| \\
    &= |x - y| |x^2 + xy + y^2| \\
    &\leq |x - y| (|x^2| + |xy| + |y^2|) \\
    &\leq |x - y| (M^2 + M^2 + M^2) \\
    &< \frac{\epsilon}{3M^2} (3M^2) \\
    &= \epsilon
\end{aligned}
$$

Hence we conclude that $f(x) = x^3$ is uniformly continuous on $A$.



### 4.4.2

#### (a) Is $f(x) = 1/x$ uniformly continuous on (0, 1)?

The function is not uniformly continuous on (0, 1). Consider $\epsilon = 1$. 

Let $x_n = \frac{1}{n + 2}$ and $y_n = \frac{1}{n + 1}$ be two sequences in (0, 1). Then

$$|x_n - y_n| = |\frac{1}{n + 2} - \frac{1}{n + 1}| \to 0$$

but

$$|f(\frac{1}{n + 2}) - f(\frac{1}{n + 1})| = |(n + 2) - (n + 1)| = 1$$

Thus $|f(x_n) - f(y_n)| \geq 1$ for all $n \in \mathbb{N}$. 

Hence $f(x) = 1/x$ is not uniformly continuous on (0, 1).


#### (b) Is $g(x) = \sqrt{x^2 + 1}$ uniformly continuous on (0, 1)?

The function is uniformly continuous on (0, 1). Let $\epsilon > 0$.

Let $\delta = \epsilon$. Suppose $x, y \in (0, 1)$ and $|x - y| < \delta$.

Since $x, y \in (0, 1)$, we have $|x + y| < 2$ and $\sqrt{x^2 + 1} > 1$, $\sqrt{y^2 + 1} > 1$. Thus $\sqrt{x^2 + 1} + \sqrt{y^2 + 1} > 2$.

Then we have

$$
\begin{aligned}
|g(x) - g(y)| &= |\sqrt{x^2 + 1} - \sqrt{y^2 + 1}| \\
    &= |\frac{(\sqrt{x^2 + 1} - \sqrt{y^2 + 1}) (\sqrt{x^2 + 1} + \sqrt{y^2 + 1}) }{\sqrt{x^2 + 1} + \sqrt{y^2 + 1}} | \\
    &= \frac{|(x^2 + 1) - (y^2 + 1)|}{\sqrt{x^2 + 1} + \sqrt{y^2 + 1}} \\
    &\leq \frac{|(x^2 + 1) - (y^2 + 1)|}{2} \\ 
    &= \frac{|x^2 - y^2|}{2} \\
    &= |x - y| \frac{|x + y|}{2} \\
    &< \epsilon \frac{2}{2} \\
    &= \epsilon
\end{aligned}
$$

Hence $g(x) = \sqrt{x^2 + 1}$ uniformly continuous on (0, 1).


#### (c) Is $h(x) = x \sin (1/x)$ uniformly continuous on (0, 1)?




### 4.4.6 Give an example of each of the following, or state that such a request is impossible. For any that are impossible, supply a short explanation for why this is the case.

#### (a) A continuous function $f: (0, 1) \to \mathbb{R}$ and a Cauchy sequence $(x_n)$ such that $f(x_n)$ is not a Cauchy sequence.



#### (b) A uniformly continuous function $f: (0, 1) \to \mathbb{R}$ and a Cauchy sequence $(x_n)$ such that $f(x_n)$ is not a Cauchy sequence.



#### (c) A continuous function $f: [0, \infty) \to \mathbb{R}$ and a Cauchy sequence $(x_n)$ such that $f(x_n)$ is not a Cauchy sequence.



### 4.4.8 Give an example of each of the following, or provide a short argument for why the request is impossible.

#### (a) A continuous function defined on [0, 1] with range (0, 1).

Not possible.

By theorem 4.4.1, a continuous function maps a compact set to a compact set.


#### (b) A continuous function defined on (0, 1) with range [0, 1].



#### (c) A continuous function defined on (0, 1] with range (0, 1).



### 4.4.9 A function $f: A \to \mathbb{R}$ is called Lipschitz if there exists a bound $M > 0$ such that $|\frac{f(x) - f(y)}{x - y}| \leq M$ for all $x \neq y \in A$. Geometrically speaking, a function $f$ is Lipschitz if there is a uniform bound on the magnitude of the slpes of lines drawn through any two points on the graph of $f$.

#### (a) Show that if $f: A \to \mathbb{R}$ is Lipschitz, then it is uniformly continuous on $A$.

Suppose $f: A \to \mathbb{R}$ is Lipschitz. 

Let $\epsilon > 0$. 

Let $\delta = \frac{\epsilon}{M}$. Suppose $x, y \in A$ and $|x - y| < \delta$.

We have

$$|f(x) - f(y)| \leq |x - y| M < \frac{\epsilon}{M} M = \epsilon$$

Hence $f$ is uniformly continuous on $A$.


#### (b) Is the converse statement true? Are all uniformly continuous functions necessarily Lipschitz?

The converse is not true.

Consider $f(x) = \sqrt{x}$ on $A = [0, 1]$. Since $\sqrt{x}$ is continuous, it is uniformly continuous on [0, 1] by theorem 4.4.7.

Take $y = 0$, we have

$$|\frac{f(x) - f(0)}{x - 0}| = \frac{\sqrt{x}}{x} = \frac{1}{\sqrt{x}}$$

Then

$$\lim_{x \to 0^+} \frac{1}{\sqrt{x}} \to \infty$$

So the slope is unbounded.



### 4.4.11 Let $f$ be defined on all of $\mathbb{R}$. If $B$ is a subset of $\mathbb{R}$, define the set $g^{-1}(B)$ by $g^{-1}(B) = \\{x \in \mathbb{R}: f(x) \in B\\}$. Show that $f$ is continuous if and only if $f^{-1}(G)$ is open whenever $G \subseteq \mathbb{R}$ is an open set.

$\Rightarrow$

Suppose $f$ is continuous on $\mathbb{R}$.

Let $G \subseteq \mathbb{R}$ be an open set. We want to show that $f^{-1}(G)$ is open.

Let $c \in f^{-1}(G)$ and take $f(c) = y$. 

Since $G$ is open, there exists $\epsilon > 0$ such that $V_\epsilon(y) \subseteq G$.

By theorem 4.3.2, there exists $V_\delta(c)$ with the property that $x \in V_\delta(c)$ implies $f(x) \in V_\epsilon(f(c))$.

Let $x \in V_\delta(c)$. Since $f(x) \in V_\epsilon(y) \subseteq G$, $x \in f^{-1}(G)$. 

Thus $V_\delta(c) \subseteq f^{-1}(G)$.

We conclude that $f^{-1}(G)$ is open.

$\Leftarrow$

Suppose $f^{-1}(G)$ is open whenever $G \subseteq \mathbb{R}$ is an open set. 

Let $c \in \mathbb{R}$. We want to show that $f$ is continuous at $c$.

Let $\epsilon > 0$.

Consider $G = V_\epsilon(f(c))$. Then $f(c) \in G$, and $c \in f^{-1}(G)$.

By hypothesis $f^{-1}(G)$ is open. There exists $\delta > 0$ such that $V_\delta(c) \subseteq f^{-1}(G)$.

Suppose $x \in V_\delta(c)$. Then $x \in f^{-1}(G)$ and $f(x) \in G = V_\epsilon(f(c))$. 

Hence $f$ is continuous at $c$.



### 4.4.12 Review Exercise 4.4.11 and then determine which of the following statements is true about a continuous function defined on $\mathbb{R}$:

#### (a) $f^{-1}(B)$ is finite whenever $B$ is finite.


#### (b) $f^{-1}(K)$ is compact whenever $K$ is compact.


#### (c) $f^{-1}(A)$ is bounded whenever $A$ is bounded.


#### (d) $f^{-1}(F)$ is closed whenever $F$ is closed.



### 4.4.13 

#### (a) Show that a uniformly continuous function preserves Cauchy sequences; that is, if $f: A \to \mathbb{R}$ is uniformly continuous and $(x_n) \subseteq A$ is a Cauchy sequence, then show $f(x_n)$ is a Cauchy sequence.


#### (b) Let $g$ be a continuous function on the open interval $(a, b)$. Prove that $g$ is uniformly continuous on $(a, b)$ if and only if it is possible to define values $g(a)$ and $g(b)$ at the endpoints so that the extended function $g$ is continuous on $[a, b]$. (In the forward direction, first produce candidates for $g(a)$ and $g(b)$, and then show the extended $g$ is continuous.)



### 4.4.14 Construct an alternate proof of Theorem 4.4.7 using the open cover characterization of compactness from the Heine-Borel Theorem (Theorem 3.3.8)

Theorem 4.4.7 states that a function that is continuous on a compact set $K$ is uniformly continuous on $K$. 

Let $\epsilon > 0$.

Since $f$ is continuous on $K$, for each $x \in K$, there exists $\delta_x > 0$ such that $|f(x) - f(y)| < \epsilon/2$ whenever $y \in K$ and $|x - y| < \delta_x$.

Consider the open cover of $K$

$$\bigcup_{x \in K} V_{\delta_x / 2}(x)$$

Since $K$ is compact, by Heine-Borel theorem (3.3.8), there is a finite subcover $V_{\delta_1 /2}(x_1), ..., V_{\delta_n/2}(x_n)$.

Let $\delta = \min \\{\delta_1 /2, ..., \delta_n /2 \\}$.

Suppose $x, y \in K$ and $|x - y| < \delta$.

Since $x \in K$, $x \in V_{\delta_k /2}(x_k)$ for some $k \in \\{1, ..., n\\}$.

We have

$$
\begin{aligned}
|y - x_k| &= |y - x_k + x - x| \\
    &\leq |y - x| + |x - x_k| \\
    &< \delta + \delta_k /2 \\
    &\leq \delta_k /2 + \delta_k /2 \\
    &= \delta_k
\end{aligned}
$$

Then $|y - x_k| < \delta_k$ and $|x - x_k| < \delta_k$. Thus 

$$
\begin{aligned}
|f(x) - f(y)| &= |f(x) - f(y) + f(x_k) - f(x_k)| \\
    &\leq |f(x) - f(x_k)| + |f(x_k) - f(y)| \\
    &< \epsilon/2 + \epsilon/2 \\
    &= \epsilon
\end{aligned}
$$

Hence $f$ is uniformly continuous on $K$.