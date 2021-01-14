---
layout: post
title: Square Attack on 5-round AES with CUDA
mathjax: true
---
*(Part 1: Sequential computation)*

This post explain the sequential algorimtm of the square attack on a 5-round AES. Then, in the [second part](https://nvietsang.github.io/Attack-5-round-AES-with-CUDA-p2), I will show how to apply CUDA in order to save time of computation.

In order to deeply understand the principle of the attack, I recommend you to read the wonderful explaination of [David Wong](https://www.davidwong.fr/blockbreakers/square_4_attack5rounds.html). In this post, I just show a way of implementation.

The pseudo code below is a function used to attack a quadruplet of key. At first, the arguments include:
- **qid**: quadruplet ID, it specifies the quadruplet we want to attack. it can be 0, 1, 2, or 3. Four quadruplets are shown in the following figure.

<img src="{{ site.baseurl }}/figures/2021-01-13-quadruplets.png" style="width: 400px;"/>

- **idx1, idx2, idx3, idx4:** Four indexes of a quadruplet. For example, qid = 0, we can assign idx1 = 7, idx2 = 10, idx3 = 13, idx4 = 0.

- **ciphertexts:** contains the ciphertexts of 6 lambda-sets.
```
Input: qid, idx1, idx2, idx3, idx4, ciphertexts
Output: 4 bytes of key for a quadruplet
---
qid = qid * 4
key5[16] = [0, 0, ..., 0]
a[16]    = [0, 0, ..., 0]
for b1 from 0 to 255 do
    for b2 from 0 to 255 do
        for b3 from 0 to 255 do
            for b4 from 0 to 255 do
                key5[idx1] = b1
                key5[idx2] = b2
                key5[idx3] = b3
                key5[idx4] = b4

                for b_k4 from 0 to 255 do
                    is_key = true
                    for each lambda-set in 6 lambda-sets do
                        r = 0
                        for each ciphertext cpt in lambda-set do
                            a[idx1] = key5[idx1] xor cpt[idx1]  
                            a[idx2] = key5[idx2] xor cpt[idx2]  
                            a[idx3] = key5[idx3] xor cpt[idx3]  
                            a[idx4] = key5[idx4] xor cpt[idx4]

                            invert_shift_row(a)
                            invert_sub_bytes(a)
                            invert_mix_columns(a)

                            a[qid] =  b_k4 xor a[qid]

                            invert_shift_row(a)
                            invert_sub_bytes(a)
                            r = r xor a[qid]

                        if r != 0 then
                            is_key = false
                            break
                    
                    if is_key = true then
                        return (b1, b2, b3, b4)                            
```

In this attack, we apply the balanced property at the input of round 4. For a ciphertext and guessed bytes of keys, we follow the inverse direction to calculate the state at the input of round 4.

Notice that using ciphertexts of at most 6 lambda-sets, we can obtain a unique key at round 5. And only this unique key satifies the balanced property at the input of round 4.

We denote that a tuple (b1, b2, b3, b4, b_k4) is a candidate. In the algorithm, we sequentially check that whether each candidate satisfies the balanced property with all 6 sets of ciphertexts corresponding to 6 lambda-sets. If yes, that candidate is indeed the correct key at round 5. Otherwise, just 1 set of ciphertexts breaks the balanced property, the candidate can be concluded immediately that it's not the desired key.
