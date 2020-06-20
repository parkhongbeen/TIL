## 카운팅 정렬

**Counting Sort**는 non-comparision sort 기법으로 정렬 알고리즘이며 **O(N)의 시간복잡도**를 갖습니다.

먼저 예시전에 이해를 돋기 위해 누군가 만들어놓은 애니메이션을 참고해주세요.

https://www.cs.miami.edu/home/burt/learning/Csc517.091/workbook/countingsort.html

예를 들어, 다음과 같은 input에 대해 counting sort를 수행한다면,

```python
input = [2, 0, 1, 4, 5, 4, 3, 2, 0, 1, 1, 0, 5, 4, 3]
```

**첫째로,** input의 원소들의 빈도 값을 세어서 counting에 저장해줍니다.

```python
counting = [3, 3, 2, 2, 3, 2]
```

counting의 각 원소 값은 인덱스에 해당하는 원소가 inpur에 얼마나 존재하는지 나타내줍니다. 예를 들어 `counting[0] = 3` 인데, 인덱스 값인 0이 원소로서 input에 3개 들어있다는 것을 나타냅니다. `counting[1] = 3`인데 인덱스 값인 1이 원소로서 input에 3개가 들어있다는 것을 나타냅니다. **두번째**로 counting의 각 요솟값에 직전 요솟값을 더해서 업데이트해줍니다.

```python
counting = [3, 6, 8, 10, 13, 15]
```

input을 정렬해서 담을 output을 만듭니다. 처음엔 비어있다는 뜻에서 모든 원소를 -1로 설정합니다. input을 정렬해서 담을 것이므로 input과 같은 길이로 만들어 줍니다.

```python
output = [-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1]
```

couting의 의미는 다음과 같습니다.

`counting[0] = 3`: 0은 output[0]에서 output[2]까지 세자리 차지한다.

`counting[1] = 6`: 1은 output[3]에서 output[5]까지 세자리 차지한다.

....

**세번째로,** 역순으로 input의 요솟값을 output에 채워 넣습니다.

input의 마지막 원소는 3입니다. `couting[3] = 10`을 참조하면 3은 output[9]의 자리를 차지한다는 것을 알 수 있습니다. (끝부터 채워나갑니다.)

```python
output = [-1, -1, -1, -1, -1, -1, -1, -1, -1, 3, -1, -1, -1, -1, -1]
```

한자리 채워 넣었으므로 couting[3]의 값을 -1합니다. `couting[3] = 9`

그다음 input의 원소는 4입니다. `couting[4] = 13`을 참조하면 4는 ouput[12]의 자리를 차지한다는 것을 알 수 있습니다.

```python
output array = [-1, -1, -1, -1, -1, -1, -1, -1, -1, 3, -1, -1, 4, -1, -1]
```

한자리 채워 넣었으므로 couting[4]의 값을 -1 합니다.

`counting[4] = 12`

이렇게 채워나가는 작업을 반복하다 보면

```python
output = [0, 0, 0, 1, 1, 1, 2, 2, 3, 3, 4, 4, 4, 5, 5]
```

처럼 정렬된 array를 얻을 수 있습니다.

데이터 개수가 n일 때 input의 빈도를 세는 계산 복잡성은 O(n)입니다. 데이터 전체를 한 번씩 훑어야 하기 때문입니다.

out을 만들 때도 역순으로 모두 훑어야 하기 때문에 O(n)입니다. counting을 업데이트할 때 max(요솟값 중 최댓값)만큼 반복문을 돌리기 때문에 복잡성 또한 O(max)가 됩니다.

결론적으로 전체적인 계산 복잡성은 O(n+max)가 됩니다. max가 충분히 작을 경우 O(n)이 되겠지만, max가 커질 경우 max가 counting sort의 계산 복잡성을 지배하게 됩니다.

코드는 아래와 같습니다.

![image](https://user-images.githubusercontent.com/53684676/84779025-c6db7500-b01e-11ea-8686-4c5e3bd4eb63.png)

