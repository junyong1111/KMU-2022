- 1.백준(1260) DFS와 BFS
  #### 깊이우선탐색(DFS) 와 너비우선탐색(BFS)를 구현하는 문제이며 Graph에서 가장 기본적인 탐색 방법이다.
  ##### <u>주의 : STL함수를 사용함에 있어서 call by reference를 사용해야 메모리 초과를 피할 수 있다.</u>
  1. 문제에서 주어진 조건으로 그래프의 간선들을 서로 연결해준다
     - 이어진 간선들의 정점은 오름차순으로 정렬해야 함
  2. 이미 방문이 끝난 노드들은 재방문을 방지하기 위하여 방문여부를 확인할 수 있는 배열 생성
  3. 최초 시작 정점을 기준으로 탐색시작
- DFS는 스택을 이용하여 구현
  1. 최초 출발정점을 스택에 넣은 후 DFS 출발
  2. 스택의 원소가 하나라도 있다면 다음 반복문 실행
     - 스택의 최상단의 원소를 출력 후 pop()하고 해당노드 방문 체크
     - 출발 노드의 간선을 모두 탐색하면서 만약 방문이 안된 노드라면 재귀적으로 DFS 호출
- 방문여부 배열 초기화
- BFS는 큐를 이용하여 구현
  1. 최초 출발정점을 큐에 넣은 후 BFS출발
  2. 큐의 원소가 하나라도 있다면 다음 반복문 실행
     - 현재 노드가 방문기록이 없다면 출력 후 해당 노드 방문체크, pop()
     - 출발 노드의 간선을 모두 탐색하면서 방문기록이 없는 노드를 push()
       - DFS와는 다르게 모든 간선을 탐색 이후 재귀적으로 BFS를 호출해야한다
     - 재귀적으로 BFS호출



- 2.백준(2805) 나무 자르기

  #### 이분탐색을 이용하여 간단하게 해결할 수 있는 문제
  ##### <u>주의 : int 정수형으로는 표현할 수 없는 수의 범위이다.</u>


  1. 주어진 나무의 길이 중 가장 긴 나무의 길이를 저장
  2. 이분탐색 시작
    - 가장 긴 나무의 길이의 반을 기준으로 잘라서 확인
      - 만약 총합이 더 짧다면 더 길게 잘라야함 오른쪽으로 탐색
      - 만약 총합이 더 길다면 더 짧게 잘라야함 왼쪽으로 탐색
      - 만약 값이라면 값 리턴

- 3.백준(1654) 랜선 자르기

  #### 이분탐색을 이용하여 간단하게 해결할 수 있는 문제
  #### 위 문제와 비슷한 형태이다.
  ##### <u>주의 : int 정수형으로는 표현할 수 없는 수의 범위이다.</u>

  1. 주어진 랜선의 길이 중 가장 긴 랜선의 길이를 저장
  2. 이분탐색 시작
    - 가장 긴 랜선의 절반부터 지정
    - 그 길이로 모든 랜선을 잘라서 
    - 만약 총합이 더 짧다면 더 길게 오른쪽
    - 만약 총합이 더 길다면 더 짧게 왼쪽
    
  
- 4.백준(1874) 스택 수열

#### 스택을 이용하여 간단하게 해결 가능

  1. 주어진 데이터를 받는 배열 선언
  2. 스택은 오름차순으로 입력되므로 최초 1을 푸쉬
  3. 스택의 원소가 하나라도 존재한다면 반복
    - 만약 스택의 최상단 값과 배열의 값이 같다면 pop()
    - 만약 배열의 값이 더 크다면 push()
    - 만약 배열의 값이 더 작다면 답이 없음
      - return 0;
  4. 위 정보를 저장한 배열을 출력해주면 끝!

- 5.백준(18111) 마인크래프트

#### 브르투포스 방법이다... 하지만 생각하기 어려웠다

  1. 주어진 정보의 MAP을만들고 max값과 min값을 저장
  2. 최소 시간을 구하는 함수 생성
    - 현재 맵을 전부 돌면서
    - 현재 땅의 위치보다 레벨이 높다면 (블록을 빼야함)
      - 빼고 인벤토리에 저장
    - 현재 땅의 위치보다 레벨이 낮다면 (블록을 더해야 함)
      - 필요한 블록의 개수를 1개 저장
  3. 블록값 계산
    - 변화가 없다면 0 리턴
    - 블록이 부족한경우 무한대값을 리턴
    - 그게 아니라면 걸리는 시간을 리턴
  4. MAX~MIN까지 반복을 돌면서 최소 시간이 걸리는 레벨과 시간을 찾아준다!

- 6.백준(1012) 유기농배추

#### 그래프 탐색 BFS 혹은 DFS를 사용하여 해결하는 문제이다 S1 단지번호붙이기랑 같은 문제이다.

  1. 주어진 정보에 맞게 배열 생성
  2. 2중 반복문 순회
    - 현재 맵을 전부 돌면서
    - 현재 위치에 배추가 있다면
      - BFS/DFS 순회 시작
        - 스택 또는 큐에 원소가 하나라도 있다면
        - 원소를 pop()
        - 4방향 탐색
        - 배추가 있다면 배추를 제거하고 다시 큐에 삽입 후 탐색
      - 연결된 모든 배추를 0으로만들고 카운터 1증가
  3. 위 결과에서 나온 카운터를 정답 벡터에 푸쉬
  4. 정답 벡터에 시작부터 끝까지 출력

- 7.백준(1927) 최소힙

#### 우선순위 큐를 이용하여문제이며 우선순위 큐를 사용할 수 있다면 쉽게 해결이 가능하다.

1. 오름차순으로 우선순위 큐 생성
2. 주어진 조건에 맞게 연산
- 만약 pop()을 하기전 원소가 없다면 0을 리턴

- 8.백준(11279) 최대힙

#### 우선순위 큐를 이용하여문제이며 위 문제와 같이 우선순위 큐를 사용할 수 있다면 쉽게 해결이 가능하다.

1. 내림차순으로 우선순위 큐 생성
2. 주어진 조건에 맞게 연산
- 만약 pop()을 하기전 원소가 없다면 0을 리턴
- 자연수가 아니라면 제외