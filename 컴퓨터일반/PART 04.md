## PART 04. 자료구조론

### 32. 스택을 사용하는 예
- 함수의 재귀호출
- 부프로그램의 호출
- 후위표기(postfix)식의 계산


### 40. 후위표기법(postfix) → 전위표기법(prefix)
ABC+D/-AE+BF*/+ → +-A/+BCD/+AE*BF


### 60. 데크
- Scroll: 입력 제한 데크
- Shelf: 출력 제한 데크


### 67. 이진트리의 성질
- 이진트리의 레벨 i에서의 최대 노드 수는 2^(i-1)이다.
- 깊이가 k인 이진트리의 경우 최소 k개의 노드를 가지며 최대 2^k - 1개의 노드를 갖는다.
- k개의 노드를 가지는 이진트리의 깊이는 최대 k이거나 최소 ⌈log(k+1)이다.
- 공백이 아닌 모든 이진트리 T에 대하여, n0는 리프 노드 수, n2는 차수가 2인 노드 수라고 하면 n0 = n2 + 1이다.


### 80. 이진트리의 내부경로, 외부경로
외부경로길이 = 내부경로길이 + 2*노드수


### 108. Prim 알고리즘, Kruskal 알고리즘
- Prim은 O(N^2)의 시간복잡도를 갖는다. (노드의 개수 N)
- Kruskal은 O(ElogE)의 시간복잡도를 갖는다 (간선의 개수 E)
- 밀집그래프(간선 수가 많은 그래프)에서는 Prim알고리즘이 더 효율적


### 110. 알고리즘
- 0/1 배낭 (0/1 Knapsack) 문제에 대하여 다항시간(Polynomial time) 내에 해결 가능한 알고리즘은 없다.


### 112. 버블정렬
정렬 전: 5 2 3 1 4  
1회전: 2 3 1 4 **5**  
2회전: 2 1 3 **4 5**  
3회전: 1 2 **3 4 5**  
4회전: 1 **2 3 4 5**  


### 116. 선택정렬
- 작은 값을 골라 맨 앞의 데이터와 교환 / 큰 값을 골라 맨 뒤의 데이터와 교환
정렬 전: 5 2 3 1 4  
1회전: **1** 2 3 5 4  
2회전: **1 2** 3 5 4  
3회전: **1 2 3** 5 4  
4회전: **1 2 3 4** 5  


### 118. 119. 삽입정렬
- 정렬된 리스트 & 정렬되지 않은 리스트
- 선택정렬에 비해 비교연산 횟수가 같거나 적다.
정렬 전: 5 2 3 1 4  
1회전: **2 5** 3 1 4  
2회전: **2 3 5** 1 4  
3회전: **1 2 3 5** 4  
4회전: **1 2 3 4 5**  


### 133. 136. 정렬
- 힙 정렬은 불안정 정렬이다.
- 삽입 정렬, 버블 정렬은 안정 정렬이다.
- 병합정렬은 항상 시간복잡도 O(nlogn)을 갖는다.


### 134. 다단계 합병 정렬
- 외부 정렬: 정렬한 데이터의 양이 많아서 테이프나 디스크를 이용하는 경우
- 다단계 합병 정렬: 테이프 장치에 저장된 대량의 데이터를 대상으로 하는 정렬


### 145. 146. 해싱
- 재해싱: 해시테이블의 크기를 다시 크게 조절하여 다시 저장하고 탐색
- 폴딩함수(Folding Function): 탐색키를 여러 부분으로 나누어 이들을 더하거나 배타적 논리합을 하여 해시 주소를 얻음

