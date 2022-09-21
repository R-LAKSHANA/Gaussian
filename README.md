# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Get the order of the matrix from the user.
2. Get the value for the augumented matrix from the user.
3. Apply guassian elimination using for() loop.
4. Apply back substitution to find the solution of the matrix.

## Program:
```python
#Program to find the solution of a matrix using Gaussian Elimination.
#Developed by: R LAKSHANA
#RegisterNumber: 22004909

import numpy as np
import sys
#get the input
n=int(input())   #matrix order
#augumented matrix
a=np.zeros((n,n+1))
#store solution
x=np.zeros(n)

#to get A matrix
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

#to apply guassian elimination
for i in range(n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero found')
        
    for j in range(i+1,n):
        scalar_value=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-scalar_value*a[i][k]

#back substitution
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]

    x[i]=x[i]/a[i][i]

#to display the solution
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end = ' ')
```

## Output:
![gaussian elimination](/Output.png)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

