by lezo, xell

Python 소개

primary prompt: >>>


두번째 prompt 그리고 라인 추가 입력시: ...

-> 여러줄을 입력하고 마지막 ... prompt에서 키입력 없이 엔터를 입력해
   해당명령셋을 끝낸다.


주석(코맨트): #(hash character)로 시작한다.

-> 명령어 첫줄에 코맨트를 쓸수있고, 공백( whitespace ) 또는 코드 다음에도 쓸 수 있다.
   하지만 문자열 안에서는 단순한 '#'문자이므로 주석의 기능으로 쓸수없다.


#Numbers
```
10 ** 2 --> 10^2 의미
10 // 3 --> 정수부만 출력
10 % 3 --> 소수부 --> 나머지만 출력
-> 정수( 10, 2, 3 )는 int 타입


5/3 --> 나눗셈의 결과는 항상 float이다.
1.6666666666666667
round(_, 2)
1.67
```
-> 소수(1.67)는 float 타입.


>>> width = 20
>>> height = 5 * 9
>>> width * height
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


#Strings
```
인터렉트브 모드에서 밑줄(_) 의미
-> The last printed expression assigned.

raw string 사용 : 줄바꿈(\n) 되지 않는다.
-> print(r'abcd\nabcd')
'abcd\nabcd'

'aa' * 3 --> aa 3회 반복

ex)
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
len(word)
6
```