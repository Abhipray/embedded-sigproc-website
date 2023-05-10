+++ 
date = "2019-05-13"
title = "Tactile Vision & Gray code"
markup = "mmark"
+++

# Tactile Vision & Gray code

I took a break from my series on speech enhancement to work on a project for an Information Theory class. The project involved designing algorithms to translate images to vibration patterns felt on the chest. The work is summarized on the blog for the class here: https://theinformaticists.com/2019/03/22/tactile-vision1-0-seeing-the-world-through-vibrations/. There are lots of other really cool projects out there so do check it out! 

As part of the project, I implemented some algorithms to generate [Gray codes](https://en.wikipedia.org/wiki/Gray_code). Gray codes are an ordering a binary code that enforces a hamming distance(number of positions where two strings are different) of one for consecutive bitstrings. 

The algorithm described on [Wikipedia](https://en.wikipedia.org/wiki/Gray_code#n-ary_Gray_code) results in the following codes. The left column is the gray code bitstring and the right number is the decimal representation.

![img](gray_wiki.png)

As you can see if you pay attention to the rightmost character of the Gray code, the numbers wrap around ([0,1,2,2,0,1,2..]. Our requirement was to generate a ternary Gray code that did not wrap around for consecutive bitstrings (i.e we wanted the count to alternate). This was satisfied by an algorithm described in a paper titled "Generalized Gray Codes with Applications", by Guan (1998).

Here's Python code for it:

```

def gray_code_guan(N, K):
    n = [0] * (K+1)
    g = [0] * (K+1)
    u = [0] * (K+1)
    
    for i in range(K+1):
        g[i] = 0
        u[i] = 1
        n[i] = N
    out = []
    while g[K] == 0:
        digits = []
        for j in range(K-1, -1, -1):
            digits.append(g[j])
        out.append(digits)
        i = 0
        k = g[0] + u[0]
        while ((k>=n[i]) or (k < 0)):
            u[i] = -u[i]
            i += 1
            k = g[i] + u[i]
        g[i] = k
    return out
 ```

 Generated ternary Gray code:

 ![img](gray_guan.png)
