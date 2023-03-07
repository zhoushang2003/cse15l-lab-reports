## Sigma sigma [Hard]

### Constrain

```1s, 256M```

### Description

The pronunciations of $\sigma$ and $\Sigma$ are exactly the same, but it would be a challenge when we combine them together.

Denote that $\sigma_{k}(n) = \sum_{d | n} d^{k}$, i.e. the summation $k$-th power of all the divisors of $n$.

Find
$$
S_{k}^{m}(n) =
\left \{
\begin{aligned}
    &\sigma_{k}(n) &, m = 0 \\
    &\sum_{i = 1}^{n} S_{k}^{m - 1}(i) &, m \geq 1 \\
\end{aligned}
\right .
$$

### Input

One line contains three space separated integers $m$, $k$ and $n$.

$1 \leq m \leq 4, 1 \leq k \leq 4, 1 \leq n \leq 10^{11}$.

### Output

Print the corresponding value of $S_{k}^{m}(n) \mod{1 \ 000 \ 000 \ 007}$.

### Sample input 1

```
2 2 2
```

### Sample output 1

```
7
```

### Sample input 2

```
3 3 3
```

### Sample output 2

```
61
```

### Hint

$$
S_{2}^{2}(2) = \sum_{i = 1}^{2} \sum_{j = 1}^{i} \sigma_{2}(j) = \sigma_{2}(1) + \sigma_{2}(1) + \sigma_{2}(2) = 1 + 1 + 5 = 7
$$

$$
\begin{aligned}
&S_{3}^{3}(3) = \sum_{i = 1}^{3} \sum_{j = 1}^{i} \sum_{l = 1}^{j} \sigma_{3}(l) \\
= &\sigma_{3}(1) + \sigma_{3}(1) + \sigma_{3}(1) + \sigma_{3}(2) + \sigma_{3}(1) \\
+ &\sigma_{3}(1) + \sigma_{3}(2) + \sigma_{3}(1) + \sigma_{3}(2) + \sigma_{3}(3) \\
= &1 + 1 + 1 + 9 + 1 + 1 + 9 + 1 + 9 + 28 = 61
\end{aligned}
$$

<div STYLE="page-break-after: always;"></div>
