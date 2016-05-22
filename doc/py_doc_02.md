by lezo, xell



#if
```
>>> x = int(input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
...     x = 0
...     print('Negative changed to zero')
... elif x == 0:
...     print('Zero')
... elif x == 1:
...     print('Single')
... else:
...     print('More')
...
More
```
Why Doesn't Python Hav Switch/Case? 
[(readme)](http://www.pydanny.com/why-doesnt-python-have-switch-case.html)
```
파이썬에는 switch ~ case 없다! 안만들었다.
if ... elif ... elif ... 로 대체한다.

그래서! -> switch ~ case를 대체할 다양한 방법들이 생겨나고 이를 수긍/찬양한다. -> 한쪽에선 스톡홀름 신드룸으로 비꼰다.

판단은 스스로... 
일단 if ... elif ... 수준으로 짜자.
참고로 switch ~ case 는 코드 정적 분석에서 복잡도를 높게 평가한다. (c++ 경우)
```


#for
words 리스트에 들어 있는 내용 출력
```
>>> # Measure some strings:
... words = ['cat', 'window', 'defenestrate']
>>> for w in words:
...     print(w, len(w))
...
cat 3
window 6
defenestrate 12
```

words 리스트를 순회하며 추가하되 추가된 내용은 반영되지 않으려면?

리스트를 복제해서 순회하고 수정/추가는 원본에 insert 한다.
```
>>> for w in words[:]:  # Loop over a slice copy of the entire list.
...     if len(w) > 6:
...         words.insert(0, w)
...
>>> words
['defenestrate', 'cat', 'window', 'defenestrate']
```


#range()

수를 순서대로 순회하고 싶을 때.
```
>>> for i in range(5):
...     print(i)
...
0
1
2
3
4

range(5) --> range(0, 5) : 0 ~ 4
range(0, 10, 3) --> [0,10) step 3
range(-10, -100, -30) --> [-10, -100) step -30
```

리스트를 인덱스로 접근하여 출력하고 싶을 때.
```
>>> a = ['Mary', 'had', 'a', 'little', 'lamb']
>>> for i in range(len(a)):
...     print(i, a[i])
...
0 Mary
1 had
2 a
3 little
4 lamb
```

인자를 출력하고 싶을 때. 
```
 >>> list(range(5))
[0, 1, 2, 3, 4] 
```


#break
```
for 순회가 끝나면 else로 출력하는 부분이 인상적이다.

>>> for n in range(2, 10):
...     for x in range(2, n):
...         if n % x == 0:
...             print(n, 'equals', x, '*', n//x)
...             break
...     else:
...         # loop fell through without finding a factor
...         print(n, 'is a prime number')
...
2 is a prime number
3 is a prime number
4 equals 2 * 2
5 is a prime number
6 equals 2 * 3
7 is a prime number
8 equals 2 * 4
9 equals 3 * 3
```


#continue
```
>>> for num in range(2, 10):
...     if num % 2 == 0:
...         print("Found an even number", num)
...         continue
...     print("Found a number", num)
Found an even number 2
Found a number 3
Found an even number 4
Found a number 5
Found an even number 6
Found a number 7
Found an even number 8
Found a number 9
```


#pass
```
The pass statement does nothing. 
It can be used when a statement is required syntactically but the program requires no action.
```

```
>>> while True:
...     pass  # Busy-wait for keyboard interrupt (Ctrl+C)
...
```

```
This is commonly used for creating minimal classes

>>> class MyEmptyClass:
...     pass
...
```

```
Another place pass can be used is as a place-holder for a function or conditional body when you are working on new code, 
allowing you to keep thinking at a more abstract level.

>>> def initlog(*args):
...     pass   # Remember to implement this!
...
```


#Defining Functions
```
함수 만들기

>>> def fib(n):    # write Fibonacci series up to n
...     """Print a Fibonacci series up to n."""
...     a, b = 0, 1
...     while a < n:
...         print(a, end=' ')
...         a, b = b, a+b
...     print()
...
>>> # Now call the function we just defined:
... fib(2000)
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597

cf.) global variables cannot be directly assigned a value within a function (unless named in a global statement)
```
```
even functions without a return statement do return a value, 
albeit a rather boring one. This value is called None (it’s a built-in name).

>>> fib(0)
>>> print(fib(0))
None
```
```
함수 리턴

>>> def fib2(n):  # return Fibonacci series up to n
...     """Return a list containing the Fibonacci series up to n."""
...     result = []
...     a, b = 0, 1
...     while a < n:
...         result.append(a)    # see below
...         a, b = b, a+b
...     return result
...
>>> f100 = fib2(100)    # call it
>>> f100                # write the result
[0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
```
