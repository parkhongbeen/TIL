## 이진 트리

어떤 트리든 이진 트리로 표현이 가능하며, 구현이 단순한 편이라 가장 많이 쓰이는 트리입니다. 이진 트리의 가장 큰 특징은 최대 차수가 2입니다. 이진 트리에서는 왼쪽 서브트리와 오른쪽 서브트리를 구분하며 0개의 노드를 가질 수 있습니다.

![image-20200701001758403](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200701001758403.png)

### 이진 트리 순회

- 전위 순회(preorder traverse): 뿌리(root)를 먼저 방문
- 중위 순회(inorder traverse): 왼쪽 하위 트리를 방문 후 뿌리(root)를 방문
- 후위 순회(postorder traverse): 하위 트리 모두 방문 후 뿌리(root)를 방문
- 층별 순회(level order traverse): 위 쪽 node들부터 아래 방향으로 차레로 방문

![image](https://user-images.githubusercontent.com/53684676/86145001-5e69b900-bb31-11ea-90f7-6b6d6819b820.png)

전위순회: `0 - 1 - 3 - 7 - 8 - 4 - 9 - 10 - 2 - 5 - 11 - 6` / 뿌리 -> 왼쪽자식 -> 오른쪽자식 순 

중위순회: `7 - 3 - 8 - 1 - 9 - 4 - 10 - 0 - 11 - 5 - 2 - 6` / 왼쪽자식 -> 뿌리 -> 오른쪽자식

후위순회: `7 - 8 - 3 - 9 - 10 - 4 - 1 - 11 - 5 - 6 - 2 - 0` / 왼쪽자식 -> 오른쪽자식 -> 뿌리

층별순회: `0 - 1 - 2 - 3 - 4 - 5 - 6 - 7 - 8 - 9 - 10 - 11` / 노드의 순서대로

### code

- 전위순회![image](https://user-images.githubusercontent.com/53684676/86145489-f23b8500-bb31-11ea-8564-e79cb8196042.png)

- 중위순회![image](https://user-images.githubusercontent.com/53684676/86145513-f8c9fc80-bb31-11ea-93c2-217d9f6f9ae8.png)

- 후위순회

  ![image](https://user-images.githubusercontent.com/53684676/86145543-ff587400-bb31-11ea-8da4-a3c02fcf3b6e.png)

- 층별순회![image](https://user-images.githubusercontent.com/53684676/86146310-0764e380-bb33-11ea-9229-d39499148fa2.png)

참조: [블로그](https://lee-seul.github.io/algorithm/python/2017/04/09/data-structure-04-tree.html), [블로그](https://m.blog.naver.com/rlakk11/60159303809)

