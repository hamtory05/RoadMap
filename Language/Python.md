<h1 align = "center"> Python </h1>

### Python 특징
1. 파이썬은 스크립트 언어이다. (소스코드를 한 줄씩 읽는다는 뜻)
2. 동적 타입 언어이다. (변수의 자료형을 정해주지 않아도 알아서 정해줌)

## 

### Print 함수
``` python
print("Hello World")
print("파이썬 시작!")

# print() 함수의 두번째 인자에 아무 값도 넣지 않으면 '\n'가 자동으로 입력됨.
# 만약 한 줄로 출력하고 싶다면
print("Hello World", end = " ")
print("파이썬 시작!")

# 출력 값
>> Hello World
>> 파이썬 시작!
>> Hello World 파이썬 시작!
```

##

### 변수 선언
``` python
# 변수 시작할 때 언더바(_), 영어, 한글로 변수 선언 가능 (한글로 변수 선언은 추천하지 않음)
_tmp = 0 # 사용 가능

# 대소문자 구분됨
tmp = 1  # 사용 가능
Tmp = 2  # 사용 가능

# 쓸 수는 있지만 안 쓰는게 가장 좋음
변수 = 3  # 사용 가능

# 변수 시작할 때 닷(.), 숫자로 변수 선언하면 오류
.tmp = 1  # 사용 불가
1tmp = 2  # 사용 불가

```

##

### 연산자
``` python
tmp_1 = 2 + 3   # 덧셈 연산자
tmp_2 = 2 * 3   # 뺄셈 연산자
tmp_3 = 2 / 3   # 나누기 연산자
tmp_4 = 2 // 3  # 몫 연산자
tmp_5 = 2 % 3   # 나머지 연산자
tmp_6 = 2 ** 3  # 제곱 연산자

# 2와 3을 변수 처리해서 계산도 가능
n1, n2 = 2, 3
tmp_7 = n1 + n2

# 출력 값
>> 5
>> 6
>> 0.6666666666666666
>> 0
>> 2
>> 8
>> 5
```

##

### 중첩 연산자
``` python

```
