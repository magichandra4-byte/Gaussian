# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start and read the coefficient matrix and constant vector of the system of linear equations.
2. Form the augmented matrix by combining the coefficient matrix with the constant vector.
3. Select the pivot element and use elementary row operations to make all elements below the pivot zero.
4. Repeat the elimination process for each column until the matrix is in upper triangular form.
5. Use back substitution starting from the last equation to find the values of the unknown variables.
6. Display the solution of the system of linear equations and stop. 

## Program:

Program to find the solution of a matrix using Gaussian Elimination.
Developed by: VEDHA M
RegisterNumber: 212225230292

```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j] ==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j] [i]/a[i] [i]
        for k in range(n+1):
             a[j] [k]=a[j] [k] -ratio*a[i] [k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=a[i][n]
        for j in range(i+1,n):
            x[i]=x[i]-a[i][j]*x[j]
        x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=" ")
```


## Output:
![alt text](<Screenshot (76).png>)
![alt text](<Screenshot (77).png>)
![alt text](<Screenshot (78).png>)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

