import numpy as np
import matplotlib.pyplot as plt

n = 10
l = 0.03
k = 0.5
t_int = 25
t_end = 200
dx = l/n

D = np.zeros(n)
b = np.zeros(n)
a = np.zeros(n)
c = np.zeros(n)
A = np.zeros(n)
C = np.zeros(n)
T = np.zeros(n)

D[0] = (3*k)/dx
D[1] = (2*k)/dx
D[n-1] = (3*k)/dx

a[1] = k/dx
b[1] = k/dx
c[0] = (2*k*t_int)/dx
c[n-1] = (2*k*t_end)/dx

a[0] = a[1]
a[n-1] = 0
b[0] = 0
b[n-1] = b[1]

for i in range(2, n-1):
  D[i] = D[1]
  a[i] = a[1]
  b[i] = b[1]

for i in range(0, n):
  A[i] = a[i]/(D[i] - b[i]*A[i-1])
  C[i] = (b[i]*C[i-1] + c[i])/(D[i] - b[i]*A[i-1])

T[n-1] = C[n-1]

j = n-2
while j >= 0:
    T[j] = A[j] * T[j+1] + C[j]
    j = j-1

solved = np.linspace(0.0, l, n)

fig, ax = plt.subplots()
ax.plot(solved,T);
ax.set_xlim(0,l);
ax.set_ylim(0,t_end);
plt.show()
