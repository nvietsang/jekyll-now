---
layout: post
title: Useful Maths for CS Engineers in Crypto
---

*(Part 4: Extended Euclidean Algorithm)*

Working in Cryptography needs a good knowledge at Maths. However, for a Computer Science Engineer (such as me), Maths sometimes seems to be too complicated to absorb. So I realize that it is useful to summarize some typical theorems which usually appears whenever working in Cryptography. They includes

+ [Fermat's Little Theorem](https://nvietsang.github.io/Useful-Maths-for-CS-Engineers-in-Crypto)
+ [Fast Exponential](https://nvietsang.github.io/Fast-Exponential)
+ [The Chinese Reminder Theorem](https://nvietsang.github.io/Chinese-Reminder-Theorem)
+ [Euclidean Algorithm](https://nvietsang.github.io/Euclidean-Algorithm)
+ [Extended Euclidean Algorithm](https://nvietsang.github.io/Extended-Euclidean-Algorithm)
+ [Bézout’s theorem](https://nvietsang.github.io/Extended-Euclidean-Algorithm)

## Extended Euclidean Algorithm
In the previous part, the Euclidean Algorithm determines the greatest common divisor **gcd(a,b)** of the two integers **a** and **b**.
In this post, the Extended Euclidean Algorithm determines **u** and **v** such that **gcd(a,b) = au + bv**. This is known as Bézout's theorem.

In cryptography, we usually meet a case in which **gcd(a,b) = 1**. It also means **a** and **b** are co-prime numbers. This algorithm is applied to find the inverse of a number. We consider an example of calculating the inverse of **b (mod a)**

<p align="center"><img src="https://latex.codecogs.com/gif.latex?b^{-1}&space;\pmod&space;a&space;=&space;?"/></p>

Since Bézout's theorem, we have

<p align="center"><img src="https://latex.codecogs.com/gif.latex?au&space;&plus;&space;bv&space;=&space;1"/></p>

Hence,
<p align="center"><img src="https://latex.codecogs.com/gif.latex?bv&space;=&space;1&space;-&space;au"/></p>

<p align="center"><img src="https://latex.codecogs.com/gif.latex?bv&space;\equiv&space;1&space;\pmod&space;a"/></p>

Therefore, **v** is the inverse of **b (mod a)**
<p align="center"><img src="https://latex.codecogs.com/gif.latex?v&space;=&space;b^{-1}&space;\pmod&space;a"/></p>

We don't dive deeper into the pseudo code of the algorithm. Instead, we take a hand-calculating example to find the inverse of **28 (mod 75)**.

Note: we use the notation **u[0]** to point the value of **u** at line **0**.

First of all, we initialize the table as follows. Notice that **u[0] = 0, u[1] = 1, v[0] = 1, v[1] = 0**. Notation **q** stands for quotient.

|No.|    | u | v |q|
|---|----|---|---|-|
| 0 | 75 | 0 | 1 | |
| 1 | 28 | 1 | 0 | |

Secondly, **q[1] = 75/28 = 2** and the reminder is **19**
**u[2] = u[0] - u[1].q[1] = 1 - 0.2 = 1**
**v[2] = v[0] - v[1].q[1] = 0 - 1.2 = -2**
|No.|    | u | v |q|
|---|----|---|---|-|
| 0 | 75 | 1 | 0 | |
| 1 | 28 | 0 | 1 | 2|
| 2 | 19 | 1 | -2 | |

Thirdly, **q[2] = 28/19 = 1** and the reminder is **9**
**u[3] = u[1] - u[2].q[2] = 0 - 1.1 = -1**
**v[3] = v[1] - v[2].q[2] = 1 - (-2).1 = 3**
|No.|    | u | v |q|
|---|----|---|---|-|
| 0 | 75 | 1 | 0 | |
| 1 | 28 | 0 | 1 | 2|
| 2 | 19 | 1 | -2 | 1|
| 3 | 9 | -1 | 3 | |

Then, **q[3] = 19/9 = 2** and the reminder is **1**
**u[4] = u[2] - u[3].q[3] = 1 - (-1).2 = 3**
**v[4] = v[2] - v[3].q[3] = -2 - 3.2 = -8**
|No.|    | u | v |q|
|---|----|---|---|-|
| 0 | 75 | 1 | 0 | |
| 1 | 28 | 0 | 1 | 2|
| 2 | 19 | 1 | -2 | 1|
| 3 | 9 | -1 | 3 | 2|
| 4 | 1 | 3 | -8 | |

Then, **q[4] = 9/1 = 9** and the reminder is **0**. Whenever the reminder is **0**, we stop the algorithm. Since **a** and **b** are co-prime numbers, the inverse of **b (mod a)** always exists.
|No.|    | u | v |q|
|---|----|---|---|-|
| 0 | 75 | 1 | 0 | |
| 1 | 28 | 0 | 1 | 2|
| 2 | 19 | 1 | -2 | 1|
| 3 | 9 | -1 | 3 | 2|
| 4 | 1 | 3 | -8 | 9|
| 5 | 0 |  |  | |

We have the result
<p align="center"><img src="https://latex.codecogs.com/gif.latex?28^{-1}&space;\pmod{75}&space;=&space;-8&space;\pmod{75}&space;=&space;67"/></p>

It is easy to verify that 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?75\times&space;3&space;&plus;&space;28&space;\times&space;(-8)&space;=&space;1"/></p>
