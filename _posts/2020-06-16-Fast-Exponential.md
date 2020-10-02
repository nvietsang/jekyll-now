---
layout: post
mathjax: true
title: Useful Maths for CS Engineers in Crypto
---

*(Part 2: Fast Exponential)*

Working in Cryptography needs a good knowledge at Maths. However, for a Computer Science Engineer (such as me), Maths sometimes seems to be too complicated to absorb. So I realize that it is useful to summarize some typical theorems which usually appears whenever working in Cryptography. They includes

+ [Fermat's Little Theorem](https://nvietsang.github.io/Useful-Maths-for-CS-Engineers-in-Crypto)
+ [Fast Exponential](https://nvietsang.github.io/Fast-Exponential)
+ [The Chinese Reminder Theorem](https://nvietsang.github.io/Chinese-Reminder-Theorem)
+ [Euclidean Algorithm](https://nvietsang.github.io/Euclidean-Algorithm)
+ [Extended Euclidean Algorithm](https://nvietsang.github.io/Extended-Euclidean-Algorithm)
+ [Bézout’s theorem](https://nvietsang.github.io/Extended-Euclidean-Algorithm)

## Fast Exponentiation
### Problem Statement
We want to compute $x^e \pmod{n}$ in a fast way.

### Solution
Apply the Square and Multiply Algorithm. The pseudocode is as follows.
```
write e in binary format. p is number of bits of e.
z <- 0
for i from p-1 to 0 do
    z <- z*z (mod n)
    if e[i] = 1:
        z <- z * x (mod n)
return z
```

### Example
Compute $688^79 \pmod{3337}$

$79 = (1001111)_2$

|i  |e[i]| z $\pmod{3337}$ |
|---|----|---|
| 6 |  1 | $1^2\times 688 = 688$  |
| 5 |  0 | $688^2 = 2827$  |
| 4 |  0 | $2827^2 = 3151$  |
| 3 |  1 | $3151^2\times 688 = 2564$  |
| 2 |  1 | $2564^2\times 688 = 1574$  |
| 1 |  1 | $1574^2\times 688 = 595$  |
| 0 |  1 | $595^2\times 688 = 1570$  |
{: .tablelines}

