```python
class dog:
    def __init__(self,name,age):
        self.name = name
        self.age = age
        
    def __str__(self):
        return'이름은 '+self.name+'이고, 나이는 {}살 입니다.'.format(self.age)
my_dog = dog('Mango',3)
print(my_dog)
```

    이름은 Mango이고, 나이는 3살 입니다.
    


```python
class Counter:
    def __init__(self,number = 0):
        self.number = number
        if (self.number >= 100 or self.number <= -1):
             self.number = 0
    def reset(self):
        self.number = 0
    def inc(self):
        if(self.number < 100):
            self.number += 1
        else:
            self.numebr = 0
    def dec(self):
        if(self.number > -1):
            self.number -= 1
        else:
            self.numebr = 0
    def __str__(self):
        return 'C({})'.format(self.number)
    def __add__(self,other):
        a = self.number + other.number
        if (a < 100):
            return 'C({})'.format(a)
        else:
            return 'C({})'.format(0)
    def __sub__(self,other):
        b = self.number - other.number
        if (b > -1):
            return' C({})'.format(b)
        else:
            return 'C({})'.format(0)
    
c1 = Counter(10)
c1.inc()
print('c1 =',c1)
print()

c2 = Counter()
c2.inc()
c2.inc()
c2.dec()
print('c2 =',c2)
c2.reset()
print('c2 =',c2)
print()

c3 = Counter(10)
c4 = Counter(20)
c5 = c3 + c4
c6 = c3 - c4
print('c5 =',c5)
print('c6 =',c6)
```

    c1 = C(11)
    
    c2 = C(1)
    c2 = C(0)
    
    c5 = C(30)
    c6 = C(0)
    


```python
class BankAccount:
    def __init__(self,name,num,bal = 0):
        self.name = name
        self.num = num
        self.bal = bal
    def __str__(self):
        return ''+self.name+'님의 계좌 '+self.num+'의 잔고는 {}원입니다'.format(self.bal)
    def get_name(self):
        return self.name
    def get_account_num(self):
        return self.num
    def get_balance(self):
        return self.bal
    def deposit(self,money):
        self.bal += money
    def withdraw(self,money):
        if (self.bal >= money):
            self.bal -= money
        else:
            print('계좌 잔고는 {}원으로 인출 요구 금액{}원보다 작습니다.'.format(self.bal,money))
    
        
account1 = BankAccount('홍길동','1234-0001')
print(account1)
account1.deposit(2000)
print(account1)
account1.withdraw(500)
print(account1)
account1.withdraw(5000)
```

    홍길동님의 계좌 1234-0001의 잔고는 0원입니다
    홍길동님의 계좌 1234-0001의 잔고는 2000원입니다
    홍길동님의 계좌 1234-0001의 잔고는 1500원입니다
    계좌 잔고는 1500원으로 인출 요구 금액5000원보다 작습니다.
    


```python
class Student:
    def __init__(self,name,student_id,korean_quiz = 0,math_quiz = 0,science_quiz= 0,total_score = 0,avg_score = 0):
        self.name = name
        self.student_id = student_id
        self.korean_quiz = korean_quiz
        self.math_quiz = math_quiz
        self.science_quiz = science_quiz
        self.total_score = total_score
        self.avg_score = avg_score
    def __str__(self):
        return '''이름 : {},학번 : {}
        국어성적 : {},수학성적 : {},과학성적 : {}
        합계 : {},평균 : {}'''.format(self.name,self.student_id,self.korean_quiz,self.math_quiz,self.science_quiz,self.total_score,self.avg_score)
    def get_name(self):
        return self.name
    def get_student_id(self):
        return self.student_id
    def get_korean_quiz(self):
        return self.korean_quiz
    def get_math_quiz(self):
        return self.math_quiz
    def get_science_quiz(self):
        return self.science_quiz
    def set_korean_quiz(self,a):
        self.korean_quiz = a
    def set_math_quiz(self,b):
        self.math_quiz = b
    def set_science_quiz(self,c):
        self.science_quiz = c
    def get_total_score(self):
        self.total_score = self.korean_quiz + self.math_quiz + self.science_quiz
    def get_avg_score(self):
        self.avg_score = (self.korean_quiz + self.math_quiz + self.science_quiz) / 3
name = input('학생의 이름을 입력하세요 : ')
student_id = input('학생의 학번을 입력하세요 : ')

student = Student(name,student_id)
korean_quiz = int(input('학생의 국어 성적을 입력하세요 : '))
math_quiz = int(input('학생의 수학 성적을 입력하세요 : '))
science_quiz = int(input('학생의 과학 성적을 입력하세요 : '))
student.set_korean_quiz(korean_quiz)
student.set_math_quiz(math_quiz)
student.set_science_quiz(science_quiz)
student.get_total_score()
student.get_avg_score()
print(student)

    
    
    
        
```

    학생의 이름을 입력하세요 : 홍길동
    학생의 학번을 입력하세요 : 20200012
    학생의 국어 성적을 입력하세요 : 85
    학생의 수학 성적을 입력하세요 : 90
    학생의 과학 성적을 입력하세요 : 95
    이름 : 홍길동,학번 : 20200012
            국어성적 : 85,수학성적 : 90,과학성적 : 95
            합계 : 270,평균 : 90.0
    


```python
MIN_VOLUME = 0
MAX_VOLUME = 20
MIN_CHANNEL = 0
MAX_CHANNEL = 200
class TV:
    

    def __init__(self,volume = 5,channel = 0,is_on = 0):
        self.volume = volume
        self.channel = channel
        self.is_on = is_on
    def __str__(self):
        if self.is_on == 1:
            return '볼륨 = {}, 채널 = {}'.format(self.volume,self.channel)
        else:
            return 'TV가 꺼진 상태입니다'
    def toggle_power(self):
        if self.is_on == 0:
            self.is_on = 1
        else:
            self.is_on = 0
    def get_channel(self):
        return self.channel
    def set_channel(self,choice):
        self.channel = choice
        if choice < 0 or choice > 201:
            return '채널오류'
        
    def get_volume(self):
        return self.volume
    
    def set_volume(self,choice):
        self.volume = choice
        if choice < 0 or choice > 20:
            return '볼륨오류'
        
    def volume_up(self):
        if self.volume <  MAX_VOLUME: 
            self.volume += 1
    def volume_down(self):
        if self.volume >  MIN_VOLUME:
            self.volume -= 1
    def channel_up(self):
        self.channel += 1
        if self.channel >= 201:
            self.channel = 0
    def channel_down(self):
        self.channel -= 1
        if self.channel < 0:
            self.channel = 200
    
        
my_tv = TV()
print(my_tv)
my_tv.toggle_power()
print(my_tv)
my_tv.set_channel(200)
print(my_tv)
my_tv.volume_up()
my_tv.channel_up()
print(my_tv)
```

    TV가 꺼진 상태입니다
    볼륨 = 5, 채널 = 0
    볼륨 = 5, 채널 = 200
    볼륨 = 6, 채널 = 0
    


