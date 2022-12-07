```python
import numpy as np
array = np.array([0,1,2,3,4,5,6,7,8,9])
array
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
array = np.array(range(0,10))
array
```




    array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
array = np.array(range(0,10,2))
array
```




    array([0, 2, 4, 6, 8])




```python
c = array
print("c.shape = {}\nc.ndim = {}\nc.dtype = {}\nc.size = {}\nc.itemsize = {}\n".format(c.shape,c.ndim,c.dtype,c.size,c.itemsize))
```

    c.shape = (5,)
    c.ndim = 1
    c.dtype = int32
    c.size = 5
    c.itemsize = 4
    
    


```python
import random as rd
a = np.array([23,45,67,7,2,30,34,82])
print('a = array{}\n'.format(a))

print('최대값 :',a.max())
print('최대값 :',a.min())
print('최대값 :',a.mean(),'\n')

b = np.random.randint(0,99,size = 10)
print('b = {}\n'.format(b))

print('최대값 :',b.max())
print('최대값 :',b.min())
print('최대값 :',b.mean(),'\n')

c = np.append(a,b)
print('c = {}'.format(c))




a = np.array([[1,2,3],[4,5,6],[7,8,9]])
print("a =",a)
b = np.array([[2,2,2], [2,2,2], [2,2,2]])
print("b =",b,'\n')

print("a + b =",a+b)
print("a - b =",a - b)
print("a * b =",a*b)
print("a / b =",a/b)
print("a @ b =",a @ b)
print("a ** 2 =",a**2)
```

    a = array[23 45 67  7  2 30 34 82]
    
    최대값 : 82
    최대값 : 2
    최대값 : 36.25 
    
    b = [80 30 87  4 57 88 42 85 37 56]
    
    최대값 : 88
    최대값 : 4
    최대값 : 56.6 
    
    c = [23 45 67  7  2 30 34 82 80 30 87  4 57 88 42 85 37 56]
    a = [[1 2 3]
     [4 5 6]
     [7 8 9]]
    b = [[2 2 2]
     [2 2 2]
     [2 2 2]] 
    
    a + b = [[ 3  4  5]
     [ 6  7  8]
     [ 9 10 11]]
    a - b = [[-1  0  1]
     [ 2  3  4]
     [ 5  6  7]]
    a * b = [[ 2  4  6]
     [ 8 10 12]
     [14 16 18]]
    a / b = [[0.5 1.  1.5]
     [2.  2.5 3. ]
     [3.5 4.  4.5]]
    a @ b = [[12 12 12]
     [30 30 30]
     [48 48 48]]
    a ** 2 = [[ 1  4  9]
     [16 25 36]
     [49 64 81]]
    


```python
a1 = np.full((3,3),2)
print("a1 =",a1,'\n')

a2 = np.arange(1,13)
print("a2 =",a2,'\n')

a3 = np.arange(3, 51,3)
print("a3 =",a3,'\n')

a4 = np.linspace(0,20,5)
print("a4 =",a4,'\n')
```

    a1 = [[2 2 2]
     [2 2 2]
     [2 2 2]] 
    
    a2 = [ 1  2  3  4  5  6  7  8  9 10 11 12] 
    
    a3 = [ 3  6  9 12 15 18 21 24 27 30 33 36 39 42 45 48] 
    
    a4 = [ 0.  5. 10. 15. 20.] 
    
    


```python
a1 = np.arange(1,13).reshape(2,6)
print("a1 =",a1,'\n')

a2 = np.arange(1,31).reshape(3,10)

print("a2 =",a2,'\n')

a3 = np.arange(1,31).reshape(6,5)
print("a3 =",a3,'\n')

a4 = np.transpose(a3)
print("a4 =",a4,'\n')
```

    a1 = [[ 1  2  3  4  5  6]
     [ 7  8  9 10 11 12]] 
    
    a2 = [[ 1  2  3  4  5  6  7  8  9 10]
     [11 12 13 14 15 16 17 18 19 20]
     [21 22 23 24 25 26 27 28 29 30]] 
    
    a3 = [[ 1  2  3  4  5]
     [ 6  7  8  9 10]
     [11 12 13 14 15]
     [16 17 18 19 20]
     [21 22 23 24 25]
     [26 27 28 29 30]] 
    
    a4 = [[ 1  6 11 16 21 26]
     [ 2  7 12 17 22 27]
     [ 3  8 13 18 23 28]
     [ 4  9 14 19 24 29]
     [ 5 10 15 20 25 30]] 
    
    


```python
a = np.random.randint(0,101,size = 15).reshape(3,5)
print("a =",a,'\n')

print("a의 열방향 최댓값 :",a.max(axis = 1))
print("a의 열방향 최솟값 :",a.min(axis = 1))
print("a의 열방향 평균 :",a.mean(axis = 1),'\n')

print("a의 행방향 최댓값 :",a.max(axis = 0))
print("a의 행방향 최솟값 :",a.min(axis = 0))
print("a의 행방향 평균 :",a.mean(axis = 0),'\n')
```

    a = [[78 10 15 41 59]
     [61  5 66 90  1]
     [46 95  7 32 95]] 
    
    a의 열방향 최댓값 : [78 90 95]
    a의 열방향 최솟값 : [10  1  7]
    a의 열방향 평균 : [40.6 44.6 55. ] 
    
    a의 행방향 최댓값 : [78 95 66 90 95]
    a의 행방향 최솟값 : [46  5  7 32  1]
    a의 행방향 평균 : [61.66666667 36.66666667 29.33333333 54.33333333 51.66666667] 
    
    


```python
a = np.array(range(1,11))
print('a =',a)
b = a[1:9:2]
print('b=',b)
```

    a = [ 1  2  3  4  5  6  7  8  9 10]
    b= [2 4 6 8]
    


```python
a = np.array(range(1,11))
b = a[-5:]
print("b =",b)
c = a[-4:]
print("c =",c)
d = a[:-7]
print("d =",d)
e = a[0:10:2]
print("e =",e)
f = a[10:0:-2]
print("f =",f)
```

    b = [ 6  7  8  9 10]
    c = [ 7  8  9 10]
    d = [1 2 3]
    e = [1 3 5 7 9]
    f = [10  8  6  4  2]
    


```python
a = np.arange(0,24).reshape(4,3,2)
np.concatenate((a[0,0],a[2,1]),axis = 0)
```




    array([ 0,  1, 14, 15])




```python
np.concatenate((a[0,0],a[1,0]),axis = 0)
```




    array([0, 1, 6, 7])




```python
a[0],a[1],a[2]
```




    (array([[0, 1],
            [2, 3],
            [4, 5]]),
     array([[ 6,  7],
            [ 8,  9],
            [10, 11]]),
     array([[12, 13],
            [14, 15],
            [16, 17]]))




```python
a = np.arange(0,16).reshape(4,4)
print("b =",a[:4,1:2])
print("c =",a[2,1:4])
print("d =",a[:2,:2])
print("e =",a[1:3,1:3])
```

    b = [[ 1]
     [ 5]
     [ 9]
     [13]]
    c = [ 9 10 11]
    d = [[0 1]
     [4 5]]
    e = [[ 5  6]
     [ 9 10]]
    


```python
np.concatenate((a[0:2,:]),axis = 0)
```




    array([0, 1, 2, 3, 4, 5, 6, 7])




```python
print("g =",np.concatenate((a[2:,:]),axis = 0))
```

    g = [ 8  9 10 11 12 13 14 15]
    


```python
print("h =",np.concatenate((a[1:2,1:]),axis = 0),np.concatenate((a[3:,1:]),axis = 0))

```

    h = [5 6 7] [13 14 15]
    


```python
a = np.array([[1,1,-1],[2,-1,3],[1,2,1]])
b = np.array([[0],[9],[8]])
x = np.linalg.solve(a,b)
print(x)
```

    [[1.]
     [2.]
     [3.]]
    


```python
A = np.array([[1,1,-1],[2,-1,3],[1,2,1]],dtype = 'int32')
print("{:10f}".format(np.linalg.det(A)))
```

    -11.000000
    
