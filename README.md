# Ex: 02 - Huffman - Shannon_fano
## AIM:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average codeword length, Entropy, Variance, Redundancy, Efficiency.

## TOOLS REQUIRED:
Python IDE with Numpy and Scipy.

## PROGRAM:
```
import numpy as np
import math

p = []
lengths = [] # Changed from 1k
L = 0        # Initialize Average Length
hs = 0       # Initialize Entropy

n = int(input("Enter the number of Samples: "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample value {i + 1}: "))
    p.append(pr)

for j in range(n):
    ln = float(input(f"Enter the length of the sample value {j + 1}: "))
    lengths.append(ln)

# Avg length of the code word
for k in range(n):
    Avg1 = p[k] * lengths[k]
    L = L + Avg1

# Entropy
for k in range(n):
    # Log base 2 of (1/p) is the same as -log2(p)
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e

hs = round(hs, 3)

# Efficiency
eff = round(hs / L, 3)

# Redundancy
red = round(1 - eff, 3)

# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lengths[k] - L) ** 2
    var = var + var1

var = round(var, 3)

print(f"\nAverage Codeword Length is: {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redundancy is: {red}")
print(f"Variance is: {var}")
```

## CALCULATION:
<img width="1080" height="1349" alt="199839cc-db9a-42e2-b7c5-b178ab31ae60" src="https://github.com/user-attachments/assets/d73c0b44-35ee-4d03-8450-48e5ac2003ff" />
<img width="1080" height="1368" alt="30866049-cb9a-4f83-85db-ae45600f8da3" src="https://github.com/user-attachments/assets/045d7c79-f43a-45cd-8d58-384ff5be6622" />
<img width="1080" height="1379" alt="973ff2a4-3221-4ac6-a225-8bb73686d565" src="https://github.com/user-attachments/assets/848f0869-769c-4d3b-8b62-9ad753e0b605" />


## OUTPUT:
<img width="802" height="362" alt="2a126a4c-466b-4a03-b44d-55ca3b48a1ef" src="https://github.com/user-attachments/assets/94958db0-a6cb-498e-a632-427ac851d6a5" />


## RESULT:
The Huffman and Shannon-Fano of the given statistics {} using python are verified.
