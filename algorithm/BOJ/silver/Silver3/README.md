- 1.백준(1003) 피보나치 함수
    #### 위 문제는 단순히 0과1이 나온 횟수를 구하는 문제가 아닌 메모제이션을 이용하여 반복적인 계산을 피해 시간초과가 나지않게 하는것이 주 목적이다.
    - 피보나치 함수를 재귀적으로 사용하지만 동일한 계산을 할 때 효율적인 메모제이션 방식을 이용하여 이미 계산된 피보나치 수열의 값을 저장하는 방식으로 시간초과 해결
    - 0이 나온횟수와 1이 나온횟수의 패턴을 분석한 결과 
        - 1이 나온횟수 = fib(n)의 값과 동일
        - 0이 나온횟수 = fib(n-1)의 값과 동일
        위와 같은 패턴이 나온다는걸 확인 

- 2.백준(1929) 소수 구하기
    #### 일반적인 소수를 구하는 방법이 아닌 에라토스테네스의 체를 이용하는 방법으로 푸는 문제이다
    - i = 2 ~ i*i<N 까지 반복문을 돌린다 그 이유는 어차피 배수이기때문에 원하는 의 루트값까지만 가도 이미 모든 소수는 구해진다
    - j = 2*i ~ j<=N 까지 j=j+i 즉 주어진값의 배수만큼 반복을 돌아준다
    - 미리 선언했던 배열의 모든 값을 0으로 바꾼 후 만약 현재 값이 제거 되지않았다면 그 배수부터 제거 하는 방식으로 처리한다
    - 에라토스테네스의 체는 소수를 한번에 찾거나 개수 등을 찾을 때 유용하다 

- 3.백준(1463) 1로 만들기
    #### 다이나믹 프로그래밍을 이용하여 푸는 문제이다. 한 번 계산된 값을 테이블에 저장하야 재연산하는 과정을 피하는 방법이다. 만약 배열의 값이 저장되어있지 않다면 새롭게 갱신한다.
    - 3으로 나뉘어지면서 2로 나뉘어지는경우 
        - 3으로 나뉘어진 값과 2로 나뉘어진 값 중 최소값을 찾는다
        - 그 최소값과 N-1을 한 값중 최솟값을 찾아 그 값을 배열의 갱신해준다. 이 과정이 필요한가 ?
    - 3으로만 나뉘어지는경우 
        - 3으로 나뉘어진 값과 N-1을 한 값중 최솟값을 찾아 그 값을 배열의 갱신해준다.
    - 2으로 나눠지는 경우 
        - 2로 나뉘어진 값과 N-1값 중 최솟값을 찾아 그 값을 배열의 갱신
    - 둘 다 아닌경우
        - N-1의 값을 배열의 갱신

- 4.백준(11399) ATM
    #### 단순하게 주어진 값을 정렬 한 뒤 필요한 시간을 더해주기만 하면 끝나는 문제로 난이도가 상당히 낮았다.
    - 단순하게 주어진 값을 정렬한 후 최소 대기줄부터 계산

- 5.백준(11047) 동전
    #### 그리디 알고리즘에 대표적인 문제로 최소동전으로 원하는 동전의 합을 만드는 방법이다.
    - 그리디 알고리즘 문제이므로 별다른 방법이 존재하지않고 현재 상황에 가장 최선의 해를 찾아주기만 하면 쉽게 풀린다.

- 6.백준(9095) 1,2,3 더하기
    #### 다이나믹 프로그래밍을 이용하여 해당 정수를 1,2,3의 합으로 나타내는 문제이다.
    - 처음 1,2,3 테이블을 기준으로 동적프로그래밍 기법을 사용하여 테이블을 갱신하는 방법으로 풀면 간단하게 풀 수 있다.
        - 4는 결국 3번 테이블의 경우의 수 + 2번 테이블의 경우의 수 + 1번 테이블의 경우의 수이다 
        - 일반화 N번은 결국  N-1테이블 + N-2테이블 + N-3테이블로 표현할 수 있다.

- 7.백준(1966) 프린터 큐
    #### 큐와 우선순위 큐 두가지를 이용하여 해결하면 쉽게 해결할 수 있는 문제였다 하지만 나에게는 생소한 접근방법이라 어려웠다....
    - 문서에 중요도와 인덱스를 저장하는 큐와 문서의 중요도를 우선순위로 저장하는 우선순위 큐 두 개를 생성
        - 주어진 조건에 맞게 큐 에다가{인덱스, 중요도}삽입 , 우선순위 큐에는 {중요도}만을 삽입
        - 큐의 원소가 하나라도 있다면 반복 실행
            - 현재 큐에 저장된 인덱스와 중요도를 가져온 뒤 제거
            - 가져온 중요도와 우선순위큐에 저장된 중요도(가장높은 순서)가 같다면 카운터를 1증가
                - 중요도와 인덱스 모두 같다면 그 문서가 찾는 문서이므로 카운터 출력 후 break
            - 중요도가 같지않다면 큐에서 빼온 원소를 다시 큐에 제일 마지막에 삽입

- 8.백준(2108) 통계학
    #### 최빈값을 제외하고는 단순하게 풀 수 있는 문제였다... 인덱스를 잘 설정해야한다...
    #### 배열의 인덱스는 양수만 접근이 가능하다 음수가 나왔을 경우 처리하는 방법에 대해 알 수 있었다.
    먼저 오름차순으로 배열 정렬
    - 산술평균
        - float 보다 double 자료형이 더 정확하다!
    - 중간값
        - 단순하게 정렬된 배열의 중간값 반환
    - 최빈값
        - 절대값이 4000은 넘지 않음
            - 빈도수와 인덱스를 저장이 필요하므로 구조체 벡터 생성
            - 반복을 돌면서 빈도수 계산
            - 만약 최빈값이 중복이라면 2번째로 작은 수를 출력해야므로 정렬기준을 새롭게 정의
    - 범위 
        - 배열의 처음과 끝의 차이를 반환

- 9.백준(2606) 바이러스
    #### 그래프 탐색 문제이다 DFS 또는 BFS를 이용하여 해결이 가능하다
    ##### <u>주의 : 함수를 쓸 때  call by reference를 사용해야 메모리 초과와 시간초과를 피할 수 있다.</u>
    DFS로 구현
    - 주어진 조건에 맞게 그래프 생성
    - 감염여부를 저장할 배열 생성
    - DFS 탐색 시작
        - 탐색을 하면서 갯수를 한개씩 증가
    - 최초 1번 컴퓨터는 횟수에 포함되지않으므로 1개를 빼준다


- 10.백준(11726) 2xn 타일링
    #### 다이나믹 프로그래밍 문제이며 메모제이션을 이용한다
    ##### <u>주의 : 큰 수를 계산할 때 오버플로우가 날 수 있으므로 최종 단계가 아닌 계산 도중 다이나믹 테이블에 값을 넣을 때 % 10007을 해줘야 한다. </u>
    DP로 구현
    - 0,1,2값 을 미리 배열에 삽입
    - 타일링 패턴을 보면 결국 DP[N] = DP[N-1] + DP[N-2]의 구조를 가지고 있으므로 해당 식에 맞게 계산

    

- 11.백준(2579) 계단오르기

#### 다이나믹 프로그래밍 문제이며 메모제이션을 이용한다
##### <u>주의 : 패턴을 파악하면 쉬운 문제인데 ... 파악하기까지 오래 걸렸음... </u>

DP로 구현
- 0,1,2,3의 경우 최대 값을 미리계산
N=5라고 가정한다면
- 최초 DP에 저장된 N-2의 값과 자기 자신을 더함 3칸이상 연속될 수 없다는 조건이 있으므로  DP[N-2]의 값은 연속되지 않은 2칸이전의 최대값임
- 반복문을 돌면서 DP[N-3] + N-2 + N .. 이런식으로 더해가며 최대값을 갱신한다
- 최대값 테이블을 갱신하고 리턴해주면 된다.


- 12.백준(9461) 파도반 수열

#### 다이나믹 프로그래밍 문제이며 메모제이션을 이용한다
##### <u>패턴만 파악하면 쉽게 해결가능 단 자료형을 주의하자! 항상 제일 마지막 케이스를 넣어봐서 오버플로우를 확인하는 습관 필요 </u>

DP로 구현
- 0,1,2,3,4,5의 경우 값을 미리 계산
N=5라고 가정한다면
- DP[N] = DP[N-4] + DP[N-5] 패턴으로 리턴해주면 간단하게 해결가능하다
