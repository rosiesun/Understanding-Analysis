Understanding Analysis - Chapter 2 <br>
Sequences and Series
================
Rosie Sun <br>
2026-10-31


# 2.2 The Limit of a Sequence

### Definition 2.2.1.
A sequence is a function whose domain is $\mathbb{N}$.


### Definition 2.2.3 convergence of a sequence
A sequence $(a_n)$ converges to a real number $a$ if, for every positive number $\epsilon$, there exists an $N \in \mathbb{N}$ such that whenever $n \geq N$ it follows that $|a_n - a| < \epsilon$.


### Definition 2.2.4 
Given a real number $a \in \mathbb{R}$ and a positive number $\epsilon > 0$, the set 

$$V_\epsilon(a) = \\{x \in \mathbb{R}: |x - a| < \epislon\\}$$

is called the $\epsilon$-neighborhood of $a$.


### Definition 2.2.3B convergence of a sequence, topological version
A sequence $(a_n)$ converges to $a$ if, given any $\epsilon$-neighborhood $V_\epsilon(a)$ of $a$, there exists a point in the sequence after which all of the terms are in $V_\epsilon(a)$. In other words, every $\epsilon$-neighborhood contains all but a finite number of the terms of $(a_n)$.




# 2.3 The Algebraic and Order Limit Theorems

### Definition 2.3.1
A sequence $(x_n)$ is bounded if there exists a number $M > 0$ such that $|x_n| \leq M$ for all $n \in \mathbb{N}$.


### Theorem 2.3.2
Every convergent sequence is bounded.

Proof:

Assume $(x_n)$ converges to a limit $l$. This means that given a particular value of $\epsilon$, say $\epsilon = 1$, we know there must exist an $N \in \mathbb{N}$ such that if $n \geq N$, then $x_n$ is in the interval $(l - 1, l + 1)$. Not knowing whether $l$ is positive or negative, we can certainly conclude that 

$$|x_n| < |l| + 1$$

for all $n \geq N$.

We still need to worry slightly about the terms in the sequence that come before the Nth term. Because there are only a finite number of these, we let 

$$M = \max \\{|x_1|, |x_2|, ..., |x_{N-1}|, |l| + 1\\}$$

It follows that $|x_n| \leq M$ for all $n \in \mathbb{N}$.


### Theorem 2.3.3 algebraic limit theorem
Let $\lim a_n = a$ and $\lim b_n = b$. Then

(i) $\lim (c a_n) = ca$ for all $c \in \mathbb{R}$

(ii) $\lim (a_n + b_n) = a + b$

(iii) $\lim (a_n b_n) = ab$

(iv) $\lim (a_n / b_n) = a/b$ provided $b \neq 0$.

Proof:

(i)

Consider the case where $c \neq 0$. We want to show that the sequence $(c a_n)$ converges to $ca$. Let $\epsilon$ be some arbitrary positive number. 

We have 

$$|c a_n - ca| = |c| ||a_n - a|$$

We can choose an $N$ such that 

$$|a_n - a| < \frac{\epsilon}{|c|}$$

whenever $n \geq N$. Observe that for all $n \geq N$,

$$|c a_n - ca| = |c| |a_n - a| < |c| \frac{\epsilon}{|c|} = \epsilon$$

The case $c = 0$ reduces to showing that the constant sequence (0, 0, ...) converges to 0.





## Exercises

### 2.3.1 Let $x_n \geq 0$ for all $n \in \mathbb{N}$.

#### (a) If $(x_n) \to 0$, show that $(\sqrt{x_n}) \to 0$.

Let $\epsilon > 0$. 

Since $(x_n) \to 0$, there exists $N \in \mathbb{N}$ such that $|x_n - 0| < \epsilon^2$ for all $n \geq N$. 

Since $x_n \geq 0$, we can write $0 \leq x_n < \epsilon^2$ for all $n \geq N$. 

Since the square root function is monotonically increasing on $[0, \infty)$, we have $\sqrt{x_n} < \sqrt{\epsilon^2}$. Therefore we have $\sqrt{x_n} < \epsilon$. 

Thus we can write $|\sqrt{x_n} - 0| < \epsilon$ for all $n \geq N$. Hence we conclude $(\sqrt{x_n}) \to 0$.

#### (b) If $(x_n) \to x$, show that $(\sqrt{x_n}) \to \sqrt{x}$.

If $x = 0$, then $(\sqrt{x_n}) \to \sqrt{x} = 0$ from part (a). Therefore for the rest of the proof assume $x \neq 0$.

By the order limit theorem (2.3.4), if $x_n \geq 0$ for all $n \in \mathbb{N}$, then $x \geq 0$. Thus $x > 0$ in our case.

Let $\epsilon > 0$.

Since $(x_n) \to x$, there exists $N \in \mathbb{N}$ such that 

$$|x_n - x| < \sqrt{x} \epsilon$$

for all $n \geq N$. We have

$$
\begin{aligned}
|\sqrt{x_n} - \sqrt{x}| 
    &= \left| \frac{(\sqrt{x_n} - \sqrt{x}) (\sqrt{x_n} + \sqrt{x})}{\sqrt{x_n} + \sqrt{x}} \right| \\
    &= \frac{|x_n - x|}{\sqrt{x_n} + \sqrt{x}} \\
    &\leq \frac{|x_n - x|}{\sqrt{x}} \\
    &< \frac{\sqrt{x} \epsilon}{\sqrt{x}} \\
    &= \epsilon
\end{aligned}
$$

for all $n \geq N$.

Hence we conclude that $(\sqrt{x_n}) \to \sqrt{x}$.



### 2.3.2 Using only Definition 2.2.3, prove that if $(x_n) \to 2$, then 

#### (a) $\frac{2 x_n - 1}{3} \to 1$

Let $\epsilon > 0$.

Since $(x_n) \to 2$, there exists $N \in \mathbb{N}$ such that $|x_n - 2| < \frac{3}{2} \epsilon$ for all $n \geq N$.

We have

$$
\begin{aligned}
\left| \frac{2 x_n - 1}{3} - 1 \right| 
    &= \left| \frac{2x_n - 4}{3} \right| \\
    &= \frac{2}{3} |x_n - 2| \\
    &< \frac{2}{3} \frac{3}{2} \epsilon \\
    &= \epsilon
\end{aligned}
$$

for all $n \geq N$.

Hence we conclude that $\frac{2 x_n - 1}{3} \to 1$.


#### (b) $\frac{1}{x_n} \to 1/2$

Let $\epsilon > 0$. 

Since $(x_n) \to 2$, there exists $N_1 \in \mathbb{N}$ such that $|x_n - 2| < 2 \epsilon$ for all $n \geq N_1$, and there exists $N_2 \in \mathbb{N}$ such that $|x_n - 2| < 1$ for all $n \geq N_2$. Note that $|x_n - 2| < 1$ implies $ < x_n < 3$.

Let $N = \max \\{N_1, N_2\\}$.

Then for all $n \geq N$, we have $|x_n - 2| < 2 \epsilon$ and $1 < x_n < 3$.

We have

$$
\begin{aligned}
\left| \frac{1}{x_n} - \frac{1}{2} \right| 
    &= \left| \frac{2-x_n}{2x_n} \right| \\
    &= \frac{|2 - x_n|}{2 |x_n|} \\
    &< \frac{|2 - x_n|}{2} \\
    &< \frac{2 \epsilon}{2} \\
    &= \epsilon
\end{aligned}
$$

Hence we conclude that $\frac{1}{x_n} \to 1/2$.



### 2.3.10 Consider the following list of conjectures. Provide a short proof for those that are true and a counterexample for any that are false.

#### (a) If $\lim (a_n - b_n) = 0$, then $\lim a_n = \lim b_n$.

The statement is false. 

Consider the sequences $a_n = n$ and $b_n = n$ for $n \in \mathbb{N}$. Then $\lim (a_n - b_n) = \lim 0 = 0$, but $(a_n)$ and $(b_n)$ diverge.


#### (b) If $(b_n) \to b$, then $|b_n| \to |b|$.

By the reverse triangle inequality, we have

$$| |b_n| - |b| | \leq |b_n - b|$$

where $|b_n - b|$ can be made arbitrarily small in the tail. Thus the statement is true.


#### (c) If $(a_n) \to 0$ and $(b_n - a_n) \to 0$, then $(b_n) \to a$.

Presumability the conclusion is $(b_n) \to 0$. By the algebraic limit theorem, we have

$$\lim b_n = \lim (b_n - a_n) + (a_n) = \lim (b_n - a_n) + \lim a_n = 0$$

Thus the statement is true.


#### (d) If $(a_n) \to 0$ and $|b_n - b| \leq a_n$ for all $n \in \mathbb{N}$, then $(b_n) \to b$.

We have 

$$|b_n - b| \leq |a_n - 0|$$

where the tail of $|a_n - 0|$ can be made arbitrarily small. Thus the statement is true.



### 2.3.12 A typical task in analysis is to decipher whether a property possessed by every term in a convergent sequence is necessarily inherited by the limit. Assume $(a_n) \to a$, and determine the validity of each claim. Try to produce a counterexample for any that are false.

#### (a) If every $a_n$ is an upper bound for a set $B$, then $a$ is also an upper bound for $B$.

We want to show that the statement is true. Assume towards contradiction that $a$ is not an upper bound of $B$. Then there exists some $b \in B$ such that $b > a$.

Since $(a_n) \to a$, there exists $N \in \mathbb{N}$ such that $|a_n - a| < b-a$ for all $n \geq N$. 

Thus we have $a - (b-a) < a_N < a + (b-a)$, and $a_N < b$. So $a_N$ is not an upper bound of $B$. This contradicts the hypothesis that every $a_n$ is an upper bound of $B$.


#### (b) If every $a_n$ is in the complement of the interval (0, 1), then $a$ is also in the complement of (0, 1).

We want to show that the statement is true. Assume towards contradiction that $a \in (0, 1)$.

Let $\epsilon = \min \\{a, 1-a\\}$.

Since $(a_n) \to a$, there exists $N \in mathbb{N}$ such that $|a_n - a| < \epsilon$ for all $n \geq N$. Then we have $a - \epsilon < a_n < a + \epsilon$. It follows that

$$a - a \leq a - \epsilon < a_n < a + \epsilon \leq a + (1-a)$$

Thus $0 < a_n < 1$ for all $n \geq N$. This contradicts the hypothesis that every element is in the complement of (0, 1).


#### (c) If every $a_n$ is rational, then $a$ is rational.

The statement is false. 

By 1.4.3, for $n \in \mathbb{N}$, there exists a rational number $q_n$ between two real numbers $\sqrt{2} < q_n < \sqft{2} + \frac{1}{n}$. Thus $(q_n) \to \sqft{2}$, but $\sqrt{2}$ is not rational.




# 2.4 The Monotone Convergence Theorem and a First Look at Infinite Series

### 2.4.7 Let $(a_n)$ be a bounded sequence.

#### (a) Prove that the sequence defined by $y_n = \sup \\{a_k: k \geq n \\}$ converges.

Let $|a_n| \leq M$ for all $n \in \mathbb{N}$. Then 

$$-M \leq a_n \leq y_n \leq M$$ 

for all $n \in \mathbb{N}$. So $(y_n)$ is bounded.

Since $\\{a_k: k \geq 1\\} \supseteq \\{a_k: k \geq 2\\} \supseteq ...$, taking supremum over a smaller set is no larger. Thus $y_n$ is monotonically decreasing. 

By the monotone convergence theorem 2.4.2, $(y_n)$ converges.


#### (b) The limit superior of $(a_n)$, or $\limsup a_n$, is defined by $\limsup a_n = \lim y_n$. Provide a reasonable definition for $\liminf a_n$ and briefly expalin why it always exists for any bounded sequence.

Let $x_n = \inf \\{a_k: k \geq n \\}$.

Define $\liminf a_n = \lim x_n$.

Since $(a_n)$ is bounded, $(x_n)$ is bounded (same argument as part (a)).

Since $\\{a_k: k \geq 1\\} \supseteq \\{a_k: k \geq 2\\} \supseteq ...$, taking infimum over a smaller set is no smaller. Thus $x_n$ is monotonically increasing. 

By 2.4.2 $(x_n)$ converges.


#### (c) Prove that $\liminf a_n \leq \limsup a_n$ for every bounded sequence, and give an example of a sequence for which the inequality is strict.

We have $x_n = \inf \\{a_k: k \geq n\\}$ and $y_n = \sup \\{a_k: k \geq n\\}$. 

Then $x_n \leq a_n \leq y_n$ for all $n \in \mathbb{N}$. By the order limit theorem 2.3.4, $\lim x_n \leq \lim y_n$. Thus $\liminf a_n \leq \limsup a_n$.

The sequence $a_n = \sin (\frac{n}{2} \pi)$ for $n \in \mathbb{N}$ is bounded and $\limsup a_n = 1$ and $\liminf a_n = -1$.


#### (d) Show that $\liminf a_n = \limsup a_n$ if and only if $\lim a_n$ exists. In this case, all three share the same value.

$\Rightarrow$

Suppose $\liminf a_n = \limsup a_n= a$. We have $\lim x_n = \lim y_n$. 

Note that $x_n \leq a_n \leq y_n$ for all $n \in \mathbb{N}$. By the squeeze theorem, $\lim a_n = a$.

$\Leftarrow$

Suppose $\lim a_n = a$. Let $\epsilon > 0$. There exists $N \in \mathbb{N}$ such that $|a_n - a| < \epsilon$ for all $n \geq N$. 

We have $a - \epsilon < a_n < a + \epsilon$ for all $n > N$. Then 

$$a - \epsilon \leq x_n \leq y_n a + \epsilon$$

Taking the limit as $n \to \infty$, by the order limit theorem 2.3.4, 

$$a - \epsilon \leq \liminf a_n \leq \limsup a_n \leq a + \epsilon$$

Since $\epsilon$ is arbitrary, we conclude $\liminf a_n = \limsup a_n = a$.

