## BFS(Breadth First Search, 너비 우선 탐색)

- `queue`를 이용하여 지금 위치에서 갈 수 있는 것들을 모두 큐에 넣는 방식입니다. 이 때, queue에 넣을 시점에 해당 노드를 방문했다고 체크해야합니다.

![image](https://upload.wikimedia.org/wikipedia/commons/5/5d/Breadth-First-Search-Algorithm.gif)

### 코드

```python
def bfs(graph, start_node):
    visit = list()
    queue = list()
    
    queue.append(start_node) # 시작노드를 큐에 넣어줌
    
    while queue: # 큐의 목록이 바닥날때까지 loop를 돌림
        node = queue.pop(0) # 큐의 맨 앞 노드를 꺼내옴
        if node not in visit: # 해당 노드가 아직 방문 리스트에 없다면
            visit.append(node) # 방문 리스트에 추가
            queue.extexd(graph[node]) #해당 노드의 자식노드들을 큐에 추가
            
    return visit
```



## DFS(Depth First Search, 깊이 우선 탐색)

- `stack`을 이용해서 갈 수 있는 만큼 최대한 깊이 가서 탐색 한 후, 더 이상 갈 곳이 없다면 이전 정점으로 돌아감

![](https://upload.wikimedia.org/wikipedia/commons/7/7f/Depth-First-Search.gif)

### 코드

```python
def dfs(graph, start_node):
    visit = list()
    stack = list()
    
    stack.append(start_node)
    
    while stack:
        node = stack.pop() # 큐의 맨 마지막 노드를 꺼내옴
        if node not in visit:
            visit.append(node)
            stack.extend(graph[node])
    return visit
```

참고자료: Wikimedia

