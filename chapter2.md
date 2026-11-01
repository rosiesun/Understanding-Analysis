Understanding Analysis - Chapter 2 <br>
Sequences and Series
================
Rosie Sun <br>
2026-10-31



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



