---
mathjax: true
---

# Bernoulli number and zeta function

## Bernoulli number

We can define the following function $f(z)$.
$$
f(z) \equiv \frac{z}{e^z - 1}, \; \lim_{z \to 0}f(z) = \lim_{z \to 0}\frac{1}{e^z} = 1 \tag{1}
$$
The Bernoulli number, $B_n$, is defined as follows:
$$
f(z) = \sum_{n = 0}^{\infty}\frac{B_n}{n!}z^n \tag{2}
$$
### Theorem
$$
B_0 = 1, B_n = -\frac{1}{n+1}\sum_{k=0}^{n-1} \begin{pmatrix} n+1 \\ k \end{pmatrix}B_n \; (n \ge 1) \tag{3}
$$
, where
$$
\begin{pmatrix} n+1 \\ k \end{pmatrix} = \frac{(n+1)!}{k!(n+1-k)!}
$$

### Proof
By using $e^z = \sum_{n=0}^{\infty}z^n/n!$, we see that
$$
\frac{1}{f(z)}=\frac{e^z -1 }{z} = \sum_{n=0}^{\infty}\frac{z^n}{(n+1)!} \tag{4}
$$
By multiplying (1) and (4), we obtain
$$
f(z) \times \frac{1}{f(z)} = \left( \sum_{n=0}^{\infty} \frac{B_n}{n!}z^n \right) \left( \sum_{m=0}^{\infty} \frac{z^m}{(m+1)!}\right) = \sum_{n=0}^{\infty} \sum_{m=0}^{\infty} \frac{B_n z^{n+m}}{n! (m+1)!} \tag{5}
$$
With tranforming indecies, $l \equiv n+m, k = n = l - m$, we can rewrite (5) as
$$
\sum_{l=0}^{\infty} \left( \sum_{k=0}^{l}\frac{B_k}{k!}\frac{1}{(l-k+1)!}z^l \right) = 1 \tag{6}
$$
And (6) is further rewritten as
$$
\sum_{k=0}^{0}\frac{B_k}{k!}\frac{1}{(0-0+1)!}+\sum_{l=1}^{\infty}\sum_{k=0}^{l}\frac{B_k}{k!}\frac{1}{(l-k+1)!}z^l = 1 \tag{7}
$$
Since $B_0$ = 1, the first term of the L.H.S. of (7) equals 1. Therefore, we see that 
$$
\sum_{k=0}^{l}\frac{B_k}{k!}\frac{1}{(l-k+1)!}z^l = 0 \; (l \ge 1) \tag{8}
$$
By multiplying $(l+1)!$ on the both sides of (8), we obtain
$$
\sum_{k=0}^{l}B_k \begin{pmatrix} l+1 \\ k\end{pmatrix} = 0 \tag{9}
$$
Accordingly, 
$$
\sum_{k=0}^{l-1}B_k \begin{pmatrix} l+1 \\ k\end{pmatrix} + B_l (l+1)= 0 \tag{10}
$$
, because
$$
\begin{pmatrix} l+1 \\ l\end{pmatrix} = l+1 \tag{11}
$$
For several $k = 0, 1, 2, \cdots$, we see that $B_0 = 1, B_1 = -\frac{1}{2}, B_2 = \frac{1}{6}, \cdots$.

Next, we define $g(z)$ as
$$
g(z) \equiv f(z) + \frac{z}{2} \tag{12}
$$
Then, we can show that
$$
g(z) = \frac{2z + z(e^z - 1)}{2(e^z - 1)} = \frac{ze^z + z}{2(e^z - 1)} = \frac{z}{2}\frac{e^z + 1}{e^z - 1} \tag{13}
$$
It can be readily shown that $g(-z) = g(z)$, i.e., $g(z)$ is an even function. Also, 
$$
\begin{aligned}
g(z) &= f(z) + \frac{z}{2} = \left(1 + \frac{B_1}{1!}z^1 + \frac{B_2}{2!}z^2 + \frac{B_3}{3!}z^3 + \cdots\right) + \frac{z}{2} \\
&= \left( 1 + \frac{B_2}{2!}z^2 + \cdots \right) \\
&= \sum_{n=0}^{\infty} \frac{B_{2n}}{(2n)!}z^{2n}
\end{aligned} \tag{14}
$$

## zeta function
Before we move on to the zeta function section, we think about the expansion of $\cot(z)$ with Bernoulli numbers. 
$$
\begin{aligned}
\coth z &= \frac{\cosh z}{\sinh z} = \frac{e^z + e^{-z}}{e^z - e^{-z}} = \frac{e^{2z}+ 1}{e^{2z} - 1} \\
z \cosh z &= z \frac{e^{2z}+ 1}{e^{2z} - 1} = \frac{2z}{z}\frac{e^{2z}+ 1}{e^{2z} - 1} \\
&= g(2z) \\
&= \sum_{n=0}^{\infty} \frac{B_{2n}}{(2n)!}(2z)^{2n} \\
z \cot z &= 1 + \sum_{n=1}^{\infty} \frac{B_{2n}}{(2n)!}(2zi)^{2n}
\end{aligned} \tag{15}
$$
Next, we think about the partial fraction decomposition of $\cot(z)$. Before we consider $\cot z$, let's think about $\sin z$ whose roots are $0, k \pi \; (k = \plusmn 1, \plusmn 2, \cdots )$. Therefore, $\sin z $ can be factrize as 
$$
\begin{aligned}
\sin z &= (z - 0) \prod_{k=1}^{\infty} \left( 1 - \frac{z}{k \pi} \right) \left( 1 + \frac{z}{k \pi} \right) \\
&= z\prod_{k=1}^{\infty} \left( 1 - \frac{z^2}{k^2 \pi^2}\right) \\
\frac{\sin z}{z} &= \prod_{k=1}^{\infty} \left( 1 - \frac{z^2}{k^2 \pi^2}\right)
\end{aligned} \tag{16}
$$

By taking the logarithm of $\sin z / z$, we obtain
$$
\log (\sin z) - \log z = \sum_{k=1}^{\infty} \log \left(1 - \frac{z^2}{k^2 \pi^2} \right) \tag{17}
$$
Then, by taking the derivative of (17) with respect to $z$, we obtain
$$
\frac{\cos z}{\sin z} - \frac{1}{z} = \sum_{k=1}^{\infty} \frac{1}{1 - \frac{z^2}{k^2 \pi^2}} \cdot \left(- \frac{2z}{k^2\pi^2} \right)
$$
Consequently,
$$
\begin{aligned}
\cot z &= \frac{1}{z} + \sum_{k=1}^{\infty} \frac{2z}{z^2 - k^2 \pi^2} \\
z \cot z &= 1 + \sum_{k=1}^{\infty} \frac{2z^2}{z^2 - k^2 \pi^2} \\
&= 1 - 2 \sum_{k=1}^{\infty} \left( \frac{z^2/(k^2 \pi^2)}{1 - z^2/(k^2 \pi^2)} \right)
\end{aligned}　\tag{18}
$$
Note that the second term of the last equation of (18) represents the infinite geometric series with common ratio of $\frac{z^2}{k^2 \pi^2}$. Therefore,
$$
\begin{aligned}
z \cot z &= 1 - 2 \sum_{k=1}^{\infty} \sum_{m=1}^{\infty} \frac{(z^2)^m}{(k^2 \pi^2)^m} = 1 - 2 \sum_{k=1}^{\infty} \sum_{m=1}^{\infty} \frac{1}{k^{2m}}\left( \frac{z}{\pi} \right)^{2m} \\
&= 1 - 2 \sum_{k=1}^{\infty} \zeta(2m) \left( \frac{z}{\pi} \right)^{2m}
\end{aligned} \tag{19}
$$
, where zeta function is defined as
$$
\zeta (s) = \sum_{k=0}^{\infty} \frac{1}{k^s} = \frac{1}{\Gamma(s)} \int_0^{\infty} \frac{u^{s-1}}{e^u - 1}du \tag{20}
$$

By comparing (15) and (19), we obtain
$$
(-1)^m \frac{2^{2m}}{(2m)!}B_{2m} = (-2)\zeta(2m) \left( \frac{1}{\pi}\right)^{2m} \; (m=1, 2, 3, \cdots) \tag{21}
$$
The Euler's formula for the zeta function is:
$$
\zeta(2m) = \frac{(-1)^{m-1}(2\pi)^{2m}}{2 \cdot (2m)!} B_{2m} \; (m=1, 2, 3, \cdots) \tag{22}
$$ 

## Generalized Zeta Function
Let's think about the following integral
$$
\begin{aligned}
\int_0^\infty \frac{x^{n-1}}{z^{-1}e^x - 1}dx &= \int_0^\infty x^{n-1}ze^{-x} \sum_{k=0}^{\infty}(ze^{-x})^k dx \\
&= \sum_{0}^{\infty} \int_0^\infty t^{n-1}e^{-t} dt \frac{z^{k+1}}{(k+1)^n} \\
&= \Gamma(n) \sum_{k=1}^{\infty} \frac{z^k}{k^n}, \; (t \equiv (k+1)x)
\end{aligned} \tag{23}
$$
If we defined $g_n(z)$ as
$$
g_n(z) \equiv \sum_{k=1}^{\infty} \frac{z^k}{k^n}
$$
, then 
$$
g_n(z) = \frac{1}{\Gamma(n)} \int_0^\infty \frac{x^{n-1}}{z^{-1}e^x - 1}dx \tag{24}
$$
and $g_n(1) = \zeta(n)$.
