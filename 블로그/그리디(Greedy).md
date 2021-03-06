## 그리디(Greedy) 알고리즘

그리디 알고리즘은 탐욕알고리즘이라고도 불립니다. 이 알고리즘은 **그때그때 상황에 맞게 최선을 선택하며 문제를 해결해나가는 알고리즘**입니다. 그렇기에 최종적으로는 그 선택이 최적이라고 확신할 수는 없습니다.

예를 들어, "지금 당장 라면을 먹을 수 있지만, 한시간을 참은 후엔 랍스타를 먹을 수 있다."라고 가정한다면 그리드알고리즘의 경우 라면을 먹어버린다고 생각하시면 됩니다.

<!-- more -->

그렇다면 왜 사용하는가라는 의문이 들 수 있습니다. 그리드 알고리즘을 통해서도 최적을 구할 수 있다면 훨씬 효율적으로 사용할 수 있는 알고리즘입니다. 왜냐하면 그때그때 최선을 선택하기 때문에 성능이 빠릅니다. 또한 최적을 구하지 못하더라도 근사 알고리즘으로 사용할 수도 있습니다.

대표적으로 백준알고리즘의 [거스름돈](https://www.acmicpc.net/problem/5585)의 풀이를 보겠습니다.

![image](https://user-images.githubusercontent.com/53684676/86770786-38da3380-c08c-11ea-9d79-f00228d47f3d.png)