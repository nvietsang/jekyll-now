---
layout: post
title: Useful Maths for CS Engineers in Crypto
mathjax: true
---

*(Part 5: Chinese Reminder Theorem)*

Working in Cryptography needs a good knowledge at Maths. However, for a Computer Science Engineer (such as me), Maths sometimes seems to be too complicated to absorb. So I realize that it is useful to summarize some typical theorems which usually appears whenever working in Cryptography. They includes

+ [Fermat's Little Theorem](https://nvietsang.github.io/Useful-Maths-for-CS-Engineers-in-Crypto)
+ [Fast Exponential](https://nvietsang.github.io/Fast-Exponential)
+ [The Chinese Reminder Theorem](https://nvietsang.github.io/Chinese-Reminder-Theorem)
+ [Euclidean Algorithm](https://nvietsang.github.io/Euclidean-Algorithm)
+ [Extended Euclidean Algorithm](https://nvietsang.github.io/Extended-Euclidean-Algorithm)
+ [Bézout’s theorem](https://nvietsang.github.io/Extended-Euclidean-Algorithm)

## The Chinese Reminder Theorem
### Problem statement
Given $n_1, n_2, ..., n_k$ such that they are pairwise coprime and 

$$x \equiv a_1 \pmod{n_1}$$
$$x \equiv a_2 \pmod{n_2}$$
$$...$$
$$x \equiv a_k \pmod{n_k}$$

Find $x$?

### Solution
**Step 1:** Calculate $N = n_1n_2...n_k$ and $N_i = \frac{N}{n_i}$

**Step 2:** Calculate $y_i = N_i^{-1} \pmod{n_i}$

**Step 3:** Calculate $x = \sum_{i=1}^k a_iy_iN_i \pmod{N}$

### Example
Find $x$ such that

$$x \equiv 5 \pmod{7}$$
$$x \equiv 3 \pmod{11}$$
$$x \equiv 10 \pmod{13}$$

$N = 7\times 11 \times 13 = 1001$

$N_1 = \frac{1001}{7} = 143$, $N_1 = \frac{1001}{11} = 91$, $N_3 = \frac{1001}{13} = 77$

$y_1 = 143^{-1} \pmod{7} = 5$,
$y_2 = 91^{-1} \pmod{11} = 4$,
$y_1 = 77^{-1} \pmod{13} = 12$

$x = (5\times 5 \times 143 + 3\times 4 \times 91 + 10\times 12 \times 77) \pmod{1001} = 894$


