# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:

### STEP 1:  Start the Program

### STEP 2: Import the NumPy library for matrix operations.

### STEP 3: Input a matrix A as a 2D NumPy array.

### STEP 4: Let n, m be the dimensions of matrix A.

### STEP 5: Create matrices Q and u of size n × n to store orthonormal and intermediate vectors respectively.

### STEP 6: Initialize the first vector:

Set u[:, 0] = A[:, 0]

Normalize u[:, 0] to get the first column of Q.

### STEP 7: For remaining vectors (i = 1 to n-1):

Set u[:, i] = A[:, i]

Subtract projections of A[:, i] onto each of the previous Q[:, j] vectors.

Normalize the result to obtain Q[:, i].

### STEP 8: Compute elements of matrix R using the formula:
for i ≤ j.

### STEP 9: Print the orthonormal matrix Q and the upper triangular matrix R.

### STEP 10: End the program.

## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by:  RAGA SUSANTH
RegisterNumber: 212224230217
'''

import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q Matrix is\n",Q)
    print("The R Matrix is\n",R)
a = np.array(eval(input()))
QR_Decomposition(a)

```

## Output

![image](https://github.com/user-attachments/assets/91b9e521-e016-4e4b-81d4-a315a6bf7e1a)


![image](https://github.com/user-attachments/assets/181777ad-5fea-40b3-8a02-0407d0a3a3b1)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
