by lezo, xell

#Python 소개
```
primary prompt: >>>


두번째 prompt 그리고 라인 추가 입력시: ...

-> 여러줄을 입력하고 마지막 ... prompt에서 키입력 없이 엔터를 입력해
   해당명령셋을 끝낸다.


주석(코맨트): #(hash character)로 시작한다.

-> 명령어 첫줄에 코맨트를 쓸수있고, 공백( whitespace ) 또는 코드 다음에도 쓸 수 있다.
   하지만 문자열 안에서는 단순한 '#'문자이므로 주석의 기능으로 쓸수없다.
```

#Numbers
```
10 ** 2 --> 10^2 의미
10 // 3 --> 정수부만 출력
10 % 3 --> 나머지만 출력
-> 정수( 10, 2, 3 )는 int 타입

5/3 --> 나눗셈의 결과는 항상 float이다.
1.6666666666666667
round(_, 2)
1.67
-> 소수(1.67)는 float 타입.

인터렉트브 모드에서 밑줄(_) 의미
-> The last printed expression assigned.

width = 20
height = 5 * 9
width * height
900
-> = 은 어떤 값을 변수에 대입한다.
   변수에 값을 대입하지 않으면 오류가 난다.

※ 참고
Fraction: 분수
Decimal: 소수
Imaginary number: 허수
floating point: 부동소수점

complex numbers: 복소수
-> 실수와 허수의 합으로 이루어지는 수
```


#Strings
```
문자열은 작은 따옴표( '...' )또는 큰 따옴표로( "..." ) 감쌀 수 있다.

>>> print('People's honor.')
SyntaxError: invalid syntax
>>>
>>> print('People\'s honor.')
People's honor.
>>>
작은 따옴표안에 작은 따옴표를 표시하려면 \' 를 써야한다.
큰 따옴표도 같은 방식으로 써야한다.

문자열은 여러줄에 걸쳐 쓸 수 있다.
여러줄을 쓰기위해 """.....""" 또는 '''.....'''를 사용 할 수 있다.

>>> '''Constantly look at yourself and learn
...    the rights and wrongs you have done.'''
'Constantly look at yourself and learn\n   the rights and wrongs you have done.'
 -> 개행 문자(end of line)는 항상 그 문자열에 포함된다.
 
>>> print("""\
... Usage: thingy [OPTIONS]
...      -h                     Display this usage message
...      -H  hostname           Hostname to connect to
... """)
Usage: thingy [OPTIONS]
         -h                     Display this usage message
         -H  hostname           Hostname to connect to

>>>
 -> 개행 문자 기능을 사용 하려면 문장 첫 줄 마지막에 \ 를 붙인다.
```

```
strings are immutable.
name = 'Python'
name[0] = 'p' --> error

raw string 사용 : 줄바꿈(\n) 되지 않는다.
-> print(r'abcd\nabcd')
'abcd\nabcd'

'aa' * 3 --> aa 3회 반복
```

```
 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1

word = 'Python'
word[-1] --> 마지막 문자
word[:2] --> character from the beginning to position 2 (excluded)
'Py'
word[4:] --> characters from position 4 (included) to the end
'on'
word[-2] --> characters from the second-last (included) to the end
'on'
word[:2] + word[2:]
'Python'
word[:]
'Python'
len(word)
6
```

#List
```
lists are a mutable.

cubes = [1, 8, 27, 65, 125]
cubes[3] = 64
cubes
[1, 8, 27, 64, 125]

cubes + [999]
[1, 8, 27, 64, 125, 999]

cubes.append(256)
cubes
[1, 8, 27, 64, 125, 256]

len(cubes)
6
```

```
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
letters
['a', 'b', 'c', 'd', 'e', 'f', 'g']

# replace some values
letters[2:5] = ['C', 'D', 'E']
letters
['a', 'b', 'C', 'D', 'E', 'f', 'g']

# now remove them
letters[2:5] = []
letters
['a', 'b', 'f', 'g']

# clear the list by replacing all the elements with an empty list
letters[:] = []
letters
[]
```

```
피보나치 수열
01 >>> a, b = 0, 1
02 >>> while b < 1000:
03 ...     print(b, end=',')
04 ...     a, b = b, a+b
05 ...
06 1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987,

설명
01 : a, b 동시 할당
02 : 콜론(:) 으로 멀티라인 시작
03 : print는 항상 마지막에 줄바꿈이 되는데, end 키워드를 적으면 줄바꿈이 일어나지 않는다.
     여기서는 end에 ',' 할당하여 줄바꿈 대신 ',' 출력 
03 ~ 04 : 공백, 탭 등으로 멀티라인 지속
05 : 멀티라인 종료
06 : 결과
```

#Footnotes
```
[1]	Since ** has higher precedence than -, -3**2 will be interpreted as -(3**2) and thus result in -9. To avoid this and get 9, you can use (-3)**2.
[2]	Unlike other languages, special characters such as \n have the same meaning with both single ('...') and double ("...") quotes. The only difference between the two is that within single quotes you don’t need to escape " (but you have to escape \') and vice versa.
```