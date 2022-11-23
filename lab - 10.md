```python
(200).__sub__(100) #오브젝트에 메소드 호출
```




    100




```python
(200).__mul__(100)
```




    20000




```python
(200).__truediv__(100)
```




    2.0




```python
[10,20,30,40].pop()
```




    40




```python
dir(int)
```




    ['__abs__',
     '__add__',
     '__and__',
     '__bool__',
     '__ceil__',
     '__class__',
     '__delattr__',
     '__dir__',
     '__divmod__',
     '__doc__',
     '__eq__',
     '__float__',
     '__floor__',
     '__floordiv__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getnewargs__',
     '__gt__',
     '__hash__',
     '__index__',
     '__init__',
     '__init_subclass__',
     '__int__',
     '__invert__',
     '__le__',
     '__lshift__',
     '__lt__',
     '__mod__',
     '__mul__',
     '__ne__',
     '__neg__',
     '__new__',
     '__or__',
     '__pos__',
     '__pow__',
     '__radd__',
     '__rand__',
     '__rdivmod__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__rfloordiv__',
     '__rlshift__',
     '__rmod__',
     '__rmul__',
     '__ror__',
     '__round__',
     '__rpow__',
     '__rrshift__',
     '__rshift__',
     '__rsub__',
     '__rtruediv__',
     '__rxor__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__sub__',
     '__subclasshook__',
     '__truediv__',
     '__trunc__',
     '__xor__',
     'as_integer_ratio',
     'bit_length',
     'conjugate',
     'denominator',
     'from_bytes',
     'imag',
     'numerator',
     'real',
     'to_bytes']




```python
dir(list)
```




    ['__add__',
     '__class__',
     '__class_getitem__',
     '__contains__',
     '__delattr__',
     '__delitem__',
     '__dir__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__getitem__',
     '__gt__',
     '__hash__',
     '__iadd__',
     '__imul__',
     '__init__',
     '__init_subclass__',
     '__iter__',
     '__le__',
     '__len__',
     '__lt__',
     '__mul__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__reversed__',
     '__rmul__',
     '__setattr__',
     '__setitem__',
     '__sizeof__',
     '__str__',
     '__subclasshook__',
     'append',
     'clear',
     'copy',
     'count',
     'extend',
     'index',
     'insert',
     'pop',
     'remove',
     'reverse',
     'sort']




```python
class dog:
    def bark(self):
        print('멍멍~~')
        
my_dog = dog()
my_dog.bark()
```

    멍멍~~
    


```python
class dog:
    def __init__(self,name):
        self.name = name
    def bark(self):
        print('멍멍~~')
    
my_dog = dog('jindo')
my_dog.bark()
```

    멍멍~~
    


```python
class dog:
    def __init__(self,name):
        self.name = name
        
    def __str__(self):
        return'my_dog의 정보 : dog(name = '+self.name+')'
    
my_dog = dog('jindo')
print(my_dog)
```

    my_dog의 정보 : dog(name = jindo)
    


```python
n = 100
m = 100
if n is m:
    print('n is m')
else:
    print('n is not m')
```

    n is m
    


```python
id(n),id(m)
```




    (2104210445776, 2104210445776)




```python
class vector2d:
    def __init__(self,x,y):
        self.x = x
        self.y = y
    def __str__(self):
        return "({},{})".format(self.x,self.y)
    def mul(self,other):
        return vector2d(self.x * other.x, self.y * other.y)
    def truediv(self,other):
        return vector2d(self.x / other.x, self.y / other.y)
    def neg(self):
        return vector2d(- self.x, -self.y)
        
v1 = vector2d(30,40)
v2 = vector2d(10,20)
v3 = v1.mul(v2)
print('v1 * v2 = ',v3 )
v4 = v1.truediv(v2)
print('v1 / v2 = ',v4 )

v5 = v1.neg()
print('\n-v1 = ',v5 )
```

    v1 * v2 =  (300,800)
    v1 / v2 =  (3.0,2.0)
    
    -v1 =  (-30,-40)
    


```python
import math as m

class vector2d:
    def __init__(self,x,y):
        self.x = x
        self.y = y
    def __str__(self):
        return "{}".format(self.x)
    def __lt__(self,other):
         return vector2d(m.sqrt(self.x**2 + self.y**2) > m.sqrt(other.x**2 + other.y **2), self.y / other.y)
    def __ge__(self,other):
         return vector2d(m.sqrt(self.x**2 + self.y**2) <= m.sqrt(other.x**2 + other.y **2), self.y / other.y)
v1 = vector2d(30,40)
v2 = vector2d(10,20)
v3 = v1 < v2
print('v1 > v2 = ',v3 )
v5 = v1 <= v2
print('v1 <= v2 = ',v5 )
v4 = v1 > v2
print('v1 < v2 = ',v4 )
v6 = v1 >= v2
print('v1 >= v2 = ',v6 )
```

    v1 > v2 =  True
    v1 <= v2 =  True
    v1 < v2 =  False
    v1 >= v2 =  False
    


```python
class rect:
    def __init__(self,width,height):
        self.width = width
        self.height = height
r1 = rect(100,200)
print(r1.__dict__)
print(r1.__dict__['width'])
```

    {'width': 100, 'height': 200}
    100
    


```python
class rect:
    def __init__(self,width,height):
        self.__width = width
        self.__height = height
r1 = rect(100,200)
print(r1.__dict__)
print(r1.__dict__['_rect__width'])
```

    {'_rect__width': 100, '_rect__height': 200}
    100
    


```python

```
