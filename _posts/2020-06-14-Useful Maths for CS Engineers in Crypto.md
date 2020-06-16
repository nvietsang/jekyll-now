---
layout: post
title: Useful Maths for CS Engineers in Crypto
---

*(Part 1: Fermat's Little Theorem)*

Working in Cryptography needs a good knowledge at Maths. However, for a Computer Science Engineer (such as me), Maths sometimes seems to be too complicated to absorb. So I realize that it is useful to summarize some typical theorems which usually appears whenever working in Cryptography. They includes

+ [Fermat's Little Theorem](https://nvietsang.github.io/2020-06-14-Useful-Maths-for-CS-Engineers-in-Crypto)
+ [Fast Exponential](https://nvietsang.github.io/2020-06-16-Fast-Exponential)
+ [The Chinese Reminder Theorem](https://nvietsang.github.io/2020-06-16-Chinese-Reminder-Theorem)
+ [Euclidean Algorithm](https://nvietsang.github.io/2020-06-16-Euclidean-Algorithm)
+ [Extended Euclidean Algorithm](https://nvietsang.github.io/2020-06-16-Extended-Euclidean-Algorithm)
+ [Bézout’s theorem](https://nvietsang.github.io/2020-06-16-Extended-Euclidean-Algorithm)

## Fermat's Little Theorem
Given a prime number **p** and an integer number **a** satified that **gcd(a,p)=1**, we have 

<p align="center"><img src="https://latex.codecogs.com/gif.latex?a^{p-1}&space;\equiv&space;1&space;\pmod&space;p"/></p>

This theorem is used to prove the fomula of RSA. If we follow the popular notations of RSA where **m** is message, **c** is ciphertext, **(e, n)** is the public key (**n=pq**) and **d** is private key.

+ Encryption: ![equation](https://latex.codecogs.com/gif.latex?c&space;=&space;m^e&space;\mod&space;n)
+ Decryption: ![equation](https://latex.codecogs.com/gif.latex?c^d&space;\mod&space;n&space;=&space;m^{ed}&space;\mod&space;n&space;=&space;m)

**Proof**: 
Since we have
<p align="center"><img src="https://latex.codecogs.com/gif.latex?ed&space;\equiv&space;1&space;\mod&space;(p-1)(q-1)"/></p>

there exists an integer **k** satisfied that
<p align="center"><img src="https://latex.codecogs.com/gif.latex?ed&space;=&space;1&space;&plus;&space;k(p-1)(q-1)"/></p>
Therefore,
<p align="center"><img src="https://latex.codecogs.com/gif.latex?m^{ed}&space;=&space;m^{1&space;&plus;&space;k(p-1)(q-1)}&space;=&space;m.(m^{(p-1)})^{k(q-1)}"/></p>
We also have that 
<p align="center"><img src="https://latex.codecogs.com/gif.latex?m^{p-1}&space;\equiv&space;m&space;\pmod&space;p"/></p>

Hence,
<p align="center"><img src="https://latex.codecogs.com/gif.latex?m^{ed}&space;\equiv&space;m&space;\pmod&space;p"/></p>

Analogously, we see that
<p align="center"><img src="https://latex.codecogs.com/gif.latex?m^{ed}&space;\equiv&space;m&space;\pmod&space;q"/></p>

Because **p** and **q** are distinct prime numbers and **n=pq**, we obtain
<p align="center"><img src="https://latex.codecogs.com/gif.latex?m^{ed}&space;\equiv&space;m&space;\pmod&space;n"/></p>

