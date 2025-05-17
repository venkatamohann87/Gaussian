# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1:
Initialize a zero matrix a of size n×(n+1) for the augmented matrix and a zero vector x for the solutions.
### Step 2:
Input the augmented matrix elements from the user into a.
### Step 3:
Apply Gaussian Elimination to transform the matrix into an upper triangular form, checking for zero pivots.
### Step 4:
Perform Back Substitution to find the solution vector x and print the values of all unknowns.

## Program:
```

/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: VENKATA MOHAN N
RegisterNumber: 212224230298
*/


import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f '%(i,x[i]),end='')

```

## Output:







![Screenshot 2025-04-27 143806](https://github.com/user-attachments/assets/18486dfe-a1a1-4a1f-86dd-aa74b2ef7e66)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
