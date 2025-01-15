<h1 align = "center"> Graph </h1>

## Graph
* 정점(Vertex)과 간선(Edge)로 구성된 자료구조
* 비선형 구조
* 여러개의 노드와 그 노드를 연결하는 관계를 표현

<br>

## 그래프 구성 요소 및 구조적 특성
### 정점 (Vertex)
* 데이터를 저장하는 그래프의 기본 단위
* 노드(Node)라고도 함
* Node 표현 : A - B - C

<br>

### 간선 (Edge)
* 정점과 정점을 연결하는 선
* 간선에 방향성이 있는 경우 >> 방향 그래프 (Directed Graph)
* 간선에 방향성이 없는 경우 >> 무방향 그래프 (Undirected Graph)
* Edge 표현 : (A, B), (B, C)

<br>

### 경로
* 경로 : 정점과 간선으로 이어지는 연결
* 단순 경로 : Node를 최대 한 번만 지나는 경로
* Cycle : 시작과 끝의 Node가 같은 경로
* DAG(Directed Acycle Graph) : 방향성이 있고 사이클이 없는 그래프

<br>

### 무방향 그래프 (Undirected Graph)
* 간선(Edge)에 방향이 없는 그래프
* 두 정점(Vertex)이 서로 연결되어 있다면, 어느 방향으로든 이동 가능
* 간선은 (A, B) 또는 {A, B}로 표현됨
* In-degree와 Out-degree 개념이 따로 필요하지 않음(간선 수로 차수 계산)

``` 
    A
   / \
  B - C

* 정점 A에 연결된 간선 (A, B), (A, C) : 2개 >> 차수 2 
* 정점 B에 연결된 간선 (A, B), (B, C) : 2개 >> 차수 2
* 정점 C에 연결된 간선 (A, C), (B, C) : 2개 >> 차수 2
* 무방향 그래프에서 모든 정점의 차수 합은 전체 간선 수의 2배
* 차수의 합 = 간선 수 * 2
```

```
n개의 정점이 있고, 모든 정점 쌍 사이에 간선이 존재한다고 가정
간선 수를 구하는 공식 : n(n-1) / 2
```

<br>

### 방향 그래프 (Directed Graph)
* 간선에 방향이 있는 그래프
* A에서 B로 갈 수 있어도, B에서 A를 갈 수 없음
* (A -> B) 형태로 방향성을 나타냄

```
n개의 정점이 있고, 모든 정점 쌍 사이에 방향이 있는 간선이 존재한다고 가정
간선 수를 구하는 공식 = n(n-1)

* 방향 그래프에서 A -> B 와 B -> A는 서로 다른 간선으로 취급됨
```

#### In-degree (진입차수) : 해당 정점으로 돌아오는 간선의 수
* 간선이 다른 정점 -> 해당 정점으로 향하는 경우, 진입차수가 증가됨

``` python 
A → B  # 정점 A의 진입차수 = 1 (C -> A)
B → C  # 정점 B의 진입차수 = 1 (A -> B)
C → A  # 정점 C의 진입차수 = 1 (B -> C)

```

#### Out-degree (진출차수) : 해당 정점에서 나가는 간선의 수
* 간선이 해당 정점 -> 다른 정점으로 향하는 경우,  진출차수가 증가됨

``` python
A → B  # 정점 A의 진출차수 = 1 (A → B)
B → C  # 정점 B의 진출차수 = 1 (B → C)
C → A  # 정점 C의 진출차수 = 1 (C → A)
```

<br>

### 가중치 그래프 (Weighted Graph)
* 간선에 가중치(Weight) 가 부여된 그래프
* 가중치는 간선의 비용, 거리, 시간 등을 나타낼 수 있음
* 가중치는 숫자로 표현되며, 각 간선에 연결됨
* 방향이 있을 수도 있고, 없을 수도 있음
* 응용 분야 : 최단 경로 찾기, 네트워크 흐름 분석

```python
A --(5)-- B  # A -> B 간선의 가중치 = 5
B --(3)-- C  # B -> C 간선의 가중치 = 3
A --(2)-- C  # A -> C 간선의 가중치 = 2

# A -> B -> C 경로의 가중치는 ?
# (A -> B) + (B -> C) = 5 + 3 = 8

```

<br>

## 인접 (Adjacency)
* 두 개의 정점(Node)이 간선(Edge)로 연결되어 있는 상태를 의미
* 정점 A와 정점 B 사이에 간선이 존재하면, A와 B는 인접

<br>

### 무방향 그래프에서의 인접

```
간선에 방향이 없으므로, 간선이 A - B로 연결되어있다면
A는 B와 인접, B는 A와 인접
```

<br>

### 방향 그래프에서의 인접

```
방향 그래프는 방향이 중요
간선이 A -> B라면, B는 A와 인접, A는 B와 인접하지 않음
간선이 B -> A라면, A와 B는 인접, B는 A와 인접하지 않음
```

<br>

### 완전 그래프 (Complete Graph)
* 완전 그래프는 그래프의 모든 정점이 서로 인접한 상태인 그래프
* n개의 정점이 있는 완전 그래프에서 모든 정점 쌍 사이에 간선이 존재

```
정점: A, B, C, D  
간선: (A-B), (A-C), (A-D), (B-C), (B-D), (C-D)

간선 수 = n(n-1) / 2
```

<br>

### 부분 그래프 (Subgraph)
* 원래의 그래프에서 일부 정점과 간선을 선택하여 만든 그래프
* 선택된 정점과 간선이 원래 그래프에 존재해야 함이 조건

``` python
# 원래 그래프
정점: A, B, C, D  
간선: (A-B), (A-C), (B-C), (C-D)


# 부분 그래프
정점: A, B, C  
간선: (A-B), (A-C)
<<<<<<< HEAD
```

<br>

## 그래프 구조 구현

### 인접 행렬 (Adjacency Matrix)
* 그래프의 정점 간 연결 상태를 2차원 배열(행렬)로 나타낸 자료구조
* 정점 i와 j가 인접하면 1, 그렇지 않으면 0 or 무한대(inf)로 표시

<br>

#### 무방향 그래프의 인접 행렬
``` python
정점: A, B, C, D

    A  B  C  D
A [ 0, 1, 1, 0 ]
B [ 1, 0, 1, 1 ]
C [ 1, 1, 0, 0 ]
D [ 0, 1, 0, 0 ]

* 무방향 그래프의 인접 행렬은 대칭 행렬
```

<br>

#### 방향 그래프의 인접 행렬
```python
정점: A, B, C

    A  B  C
A [ 0, 1, 0 ]
B [ 0, 0, 1 ]
C [ 1, 0, 0 ]

* 간선의 방향에 따라 행렬에 값이 다르게 표시되므로 대칭 행렬이 아닐 수 있음

```

<br>

### 가중치 그래프의 인접 행렬
```
정점: A, B, C

    A  B  C
A [ 0, 4, ∞ ]
B [ ∞, 0, 3 ]
C [ 2, ∞, 0 ]

* 간선의 존재 여부를 가중치 값으로 나타냄
* 연결되지 않은 정점은 무한대로 표시
```

<br>

### 인접 행렬의 장단점

#### 장점
* 직관적이고 간단하다
* O(1) 시간 복잡도, 두 정점 간의 연결 여부를 빠르게 확인 가능함

#### 단점
* 공간 복잡도가 높다
* n개의 정점이 있는 그래프에서 인접 행렬의 크기는 n x n 이므로, 메모리를 많이 사용함
* 간선이 적은 희소 그래프에서는 공간 낭비가 심함
* 모든 간선을 탐색해야함으로 O(n**2)의 시간 복잡도를 가짐

<br>

### 인접 리스트 (Vertex and Edge List)
* 그래프의 정점들과 그에 연결된 간선들을 효율적으로 저장하는 자료구조
* 메모리 사용량 낮음, 희소 그래프에 적합
* 정점이 연결되지 않으면 빈 리스트
* 시간 복잡도는 O(k) (K = 정점에 연결된 간선의 수)

``` python
# 정점 그래프 정의
vertex_list = ['0', '1', '2', '3', '4', '5']

# 간선 그래프 정의
edge_list = [(0, 1), (1, 0), (1, 4), (4, 1), (3, 4), (4, 3), (2, 5), (5, 2)]

# 인접 리스트 생성
adjacency_list = [[] for vertex in vertex_list]

# print(adjacency_list) : [[], [], [], [], [], [], []] -> 초기 상태

# 간선을 기반으로 인접 리스트 채우기
for edge in edge_list:
    # 간선 리스트를 순회하며, 각 정점에 연결된 정점을 인접 리스트에 추가
    adjacency_list[edge[0]].append(edge[1])

print(adjacency_list)  # [[1], [0, 4], [5], [4], [1, 3], [2]]
```

``` python
# DFS를 사용하여 연결된 노드 찾기
def dfs(start_node, adjac_lst):
    visited = [] # 방문한 노드를 저장할 리스트, 중복 방지
    stack = [start_node] # 탐색할 노드를 저장하는 스택, 초기값은 시작 노드
    while stack: # 스택이 비어있지 않은 동안 반복
        current = stack.pop() # 스택의 맨 위에서 노드를 꺼냄
        if current not in visited: # 현재 노드가 아직 방문되지 않았다면
            visited.append(current) # visited에 추가
            for neighbor in adjac_lst[current]: # 현재 노드의 모든 이웃 노드를 순회
                if neighbor not in visited: # 이웃 노드 중 방문하지 않은 노드가 있다면
                    stack.append(neighbor) # 스택에 추가
    return visited # 노드들의 순서를 리스트로 반환

### [ DFS 실행 과정 설명 ] ###
# stack_node가 0일 때 current = 0
# visited에 0이 없으므로, visited에 0이 추가
# adjacency_list의 0번째 인덱스의 값은 1
# 즉 0번째 인덱스와 1번째 인덱스가 연결되어있다는 뜻
# for문을 통해 1번째 인덱스의 노드를 순회
# 1번째 인덱스의 노드는 (0, 1), 0은 visited 되었으므로 패스
# 4 노드를 visited 되지 않았으므로 stack에 추가 후 다시 이 작업을 반복
# 연결되어있지 않은 노드를 발견하면 stack이 빈 리스트가 되어 작업이 종료됨

# 그래프 탐색 및 출력
def explore_all_nodes(adjac_lst):
    for node in range(len(adjac_lst)):
        # 각 정점에서 DFS를 실행
        connected_nodes = sorted(dfs(node, adjac_lst))
        print(f"Node {node} is connected to: {connected_nodes}")


# 정점 리스트 및 간선 리스트
vertex_list = ['0', '1', '2', '3', '4', '5']
edge_list = [(0, 1), (1, 0), (1, 4), (4, 1), (3, 4), (4, 3), (2, 5), (5, 2)]

# 인접 리스트 생성
adjacency_list = [[] for _ in vertex_list]
for edge in edge_list:
    adjacency_list[edge[0]].append(edge[1])

# print(adjacency_list)  # [[1], [0, 4], [5], [4], [1, 3], [2]]

# 각 노드에서 연결된 노드를 확인하고 출력
explore_all_nodes(adjacency_list)


# [ 결과 값 ]
# Node 0 is connected to: [0, 1, 3, 4]
# Node 1 is connected to: [0, 1, 3, 4]
# Node 2 is connected to: [2, 5]
# Node 3 is connected to: [0, 1, 3, 4]
# Node 4 is connected to: [0, 1, 3, 4]
# Node 5 is connected to: [2, 5]

```
