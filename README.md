# Pi-With-Python
#### Calculating Pi with Python. 
#### I guess you could call it "Pithon" :laughing:.

# What does it do?
#### Well it calculates Pi with Python :trollface:.

# How does it do it?
#### This program utilizes 3 algorithms for calculating pi in order to demostrate the strengths and weaknesses of all 3.
Bailey–Borwein–Plouffe formula | Bellard’s formula | Chudnovsky algorithm
------------------------------ | ----------------- | ---------------------
[Link](http://en.wikipedia.org/wiki/Bailey%E2%80%93Borwein%E2%80%93Plouffe_formula) | [Link](http://en.wikipedia.org/wiki/Bellard%27s_formula) | [Link](http://en.wikipedia.org/wiki/Chudnovsky_algorithm)
## Bailey–Borwein–Plouffe formula:
```python 
def plouffBig(n):
    pi = Decimal(0)
    k = 0
    while k < n:
        pi += (Decimal(1)/(16**k))*((Decimal(4)/(8*k+1))-(Decimal(2)/(8*k+4))-(Decimal(1)/(8*k+5))-(Decimal(1)/(8*k+6)))
        k += 1
```
## Bellard’s formula
```python 
def bellardBig(n):
    pi = Decimal(0)
    k = 0
    while k < n:
        pi += (Decimal(-1)**k/(1024**k))*( Decimal(256)/(10*k+1) + Decimal(1)/(10*k+9) - Decimal(64)/(10*k+3) - Decimal(32)/(4*k+1) - Decimal(4)/(10*k+5) - Decimal(4)/(10*k+7) -Decimal(1)/(4*k+3))
        k += 1
    pi = pi * 1/(2**6)
```
## Chudnovsky algorithm
```python
def chudnovskyBig(n):
    pi = Decimal(0)
    k = 0
    while k < n:
        pi += (Decimal(-1)**k)*(Decimal(factorial(6*k))/((factorial(k)**3)*(factorial(3*k)))* (13591409+545140134*k)/(640320**(3*k)))
        k += 1
    pi = pi * Decimal(10005).sqrt()/4270934400
    pi = pi**(-1)
```
