# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Import numpy and sys modules for array manipulation and system exit.

2.Initialize the augmented matrix and solution vector using np.zeros().

3.Read user input into the matrix using nested loops.

4.Apply forward elimination to convert it into upper triangular form.

5.Check for division by zero errors at each diagonal pivot.

6.Use back substitution to solve for the unknown variables.

7.Print the formatted solutions and end the program.
## Program:
```
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
       sys.exit('Divide by zero is detected!')
       

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
   print('X%d = %0.2f' % (i,x[i]),end=' ')

```

## Output:
<img width="1353" height="817" alt="image" src="https://github.com/user-attachments/assets/d2d765a3-22c8-4cf9-ba25-e58bdceaa16d" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

