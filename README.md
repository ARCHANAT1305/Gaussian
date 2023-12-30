# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Prompt the user to enter the size (n) of the square matrix representing the system of linear equations.
2. Create matrices 'a' to store the augmented matrix and 'x' to store the solution vector.
3. Iterate through each row of the augmented matrix to perform forward elimination, creating zeros below the main diagonal by subtracting multiples of the current row.
4. Starting from the last row, use backward substitution to solve for the variables by substituting known values back into previous equations.
5. Ensure that division by zero is not encountered during the elimination process; exit the program with an error message if detected.
6. Display the solution vector, representing the values of the variables that satisfy the system of linear equations.
## Program:
```

Program to find the solution of a matrix using Gaussian Elimination.
Developed by:ARCHANA.T 
RegisterNumber:212223240013
import numpy as np
import sys
n= int(input())
a = np.zeros((n,n+1))
x= np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    
    for j in range (i+1,n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range (n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
        
    x[i] = x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')
     
```

## Output:

![Gaussian ](https://github.com/ARCHANAT1305/Gaussian/assets/145975189/6f15cf4c-6a0d-427d-9ae3-bce5a4dd29fa)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

