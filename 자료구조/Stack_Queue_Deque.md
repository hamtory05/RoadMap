<h1 align = "center"> Stack  Queue  Deque</h1>

## STACK (스택)
* 데이터를 쌓아 올린 형태의 자료구조
* 후입 선출 구조 (LIFO : Last In First Out) : 마지막에 삽입된 자료가 먼저 삭제되는 구조
* append : 삽입 연산, pop : 삭제 연산

``` python
stack = []

# 삽입 연산
stack.append(1)
stack.append(2)

print(stack) # [1, 2]

# 삭제 연산
stack.pop()

print(stack) # [1]

```

<br>

## Queue (큐)
* 선입 선출 구조 (FIFO : First In First Out) : 먼저 들어온 것이 먼저 나가는 구조
* put : 삽입 연산, get : 삭제 연산
* 멀티스레드 큐에 사용

``` python
from queue import Queue

# 큐 생성
q = Queue()

# 삽입 (Enqueue)
q.put(10)
q.put(20)

print(list(q.queue)) # [10, 20]

# 삭제 (Dequeue)
q.get()

print(list(q.queue)) # [10]

```

<br>

## Deque (데큐)
* 양쪽에서 삽입과 삭제가 가능 (Double-Ended Queue)
* append, appendleft : 삽입 연산
* pop, popleft : 삭제 연산
* 단순한 큐 구현에 사용

``` python
from collections import deque

# 데큐 생성
d = deque()

# 삽입 
d.append(1)
d.append(2)
d.appendleft(3)
d.appendleft(4)

print(list(d)) # [4, 3, 1, 2]

# 삭제
d.pop()
d.popleft()

print(list(d)) # [3, 1]
```