---
layout: post
title: Useful Maths for CS Engineers in Crypto
---

*Part 3: Euclidean Algorithm*

Working in Cryptography needs a good knowledge at Maths. However, for a Computer Science Engineer (such as me), Maths sometimes seems to be too complicated to absorb. So I realize that it is useful to summarize some typical theorems which usually appears whenever working in Cryptography. They includes

+ [Fermat's Little Theorem](https://nvietsang.github.io/Useful-Maths-for-CS-Engineers-in-Crypto)
+ [Fast Exponential](https://nvietsang.github.io/Fast-Exponential)
+ [The Chinese Reminder Theorem](https://nvietsang.github.io/Chinese-Reminder-Theorem)
+ [Euclidean Algorithm](https://nvietsang.github.io/Euclidean-Algorithm)
+ [Extended Euclidean Algorithm](https://nvietsang.github.io/Extended-Euclidean-Algorithm)
+ [Bézout’s theorem](https://nvietsang.github.io/Extended-Euclidean-Algorithm)

In this post, we quickly get the idea of Euclidean Algorithm through an example.

## Euclidean Algorithm
This algorithm determines the greatest common divisor of two integers very efficiently. It is based on the following theorem.

```
If b = 0, then gcd(a,b) = |a|
If b != 0, then gcd(a,b) = gcd(|b|, a mod |b|)

euclid(int a, int b, int gcd){
    int r
    a = |a|
    b = |b|
    while (b != 0){
        r = a % b
        a = b
        b = r
    }
    gcd = a
}
```

**Example:** We want to compute **gcd(100,35)**. 
We obtain gcd(100,35) = gcd(35, 100 mod 35) = gcd(35,30) = gcd(30,5) = gcd(5,0) = 5
