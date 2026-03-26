# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
import numpy as np
def QR_decomposition (A):
    n,m = A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]= A[:,i]
        for j in range(i):
            u[:,i] = (A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R = np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
    print(Q)
    print(R)
a= np.array(eval(input()))
QR_decomposition(a)
```


## Output:

<img width="808" height="746" alt="Screenshot 2026-03-26 113149" src="https://github.com/user-attachments/assets/71e78d4d-7e76-45c4-9091-df0fd8058cfe" />



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
