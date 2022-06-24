# javascript-algorithm
네 약점 알고리듬

> 알고리 풀때 도움 되는 팁 정리 

# 대소문자 범위
x.charCodeAt을 통해 아스키 코드로 바꾸어 검사하는 방법 <br/>
대문자 : 65 \~ 90 (A\~Z, 26개)<br/>
소문자 : 97 \~ 122 (a\~z)<br/>

# indexOf
문자열 중복을 순회하며 검사할때 문자열의 indexOf와 해당 순회값 i가 같다면 처음 나왔다는 의미이다<br/>
```javascript
if(s.indexOf(s[i]) === i) answer+=s[i];
```

# 격자판 최대합
이중 포문을 돌고 행고정, 열고정을 생각할것 [i][j], [j][i]<br/>
대각선은 [i][i], [i][length-i-1]<br/>

# 봉우리
네방향 탐색<br/>
격자의 가장자리는 항상 나보다 작다, 가장자리는 살펴보지 말것<br/>
행 i, 열 j (1, 2) 인경우 dx, dy 베열을 초기화 해서 사용)<br/>
dx = [-1(위), 0 (오른쪽), 1 (아래), 0 (왼쪽)]<br/>
dy = [0(위),  1 (오른쪽), 0 (아래), -1 (왼쪽)]<br/>
이 경오 (1, 2) 의 위를 보고 싶다면 i + dx[k], j + dy[k], k는 0~3까지 있음 네방향이니까<br/>

# 회문 문자열
회문 문자열은 주어진 문자열의 나누기 2만큼의 몫을 돌면면서 앞뒤를 검사하면된다.<br/>
reverse 사용도 고려해볼 수 있다<br/>

# 숫자만 추출
숫자인 문자열이 숫자인지 알려면 isNaN 로 판단해 볼 수 있다<br/>

# 문자거리
특정 문자간 거리를 구할때 (특정 문자가 해당 문자열에서 여러개 출연) 1차 배열인 경우<br/> 
→ 방향(특정 문자열의 왼쪽으로 부터의 거리) 으로 한번 ← 방향(특정 문자열의 오른쪽부터 떨어진 거리)으로<br/> 
한번 반복문을 돌아서 (시간 복잡도는 O(N)) 더 작은 값으로 하면 된다<br/>

# 완전탐색
for문으로 모두 돌면서 모든 경우의 수를 찾아야함 (대표적인 완전탐색 문제)<br/>
경우의 수는 4x4(학생수가 4명이니까)<br/>

# Tow Pointer Algorithm
sort는 nlogn<br/>
p1, p2는 반복문 **한번**으로 끝내는 알고리즘 n+m<br/>
p1=p2=0<br/>
배열은 주어진 조건으로 정렬해야하며 해당 포인터가 가리키는 값이 조건에 맞아 푸시되는 경우 해당 포인터를 증가시킴<br/>
연속 부분수열에서는 lt, rt 포인터를 두고 계속 특정 조건에 같이 증가 (5. > 3. 연속 부분수열 코드 참고)<br/>
**연속** 된 부분수열이나 합을 찾을 때 위치를 사용할 수 있는지 가능한지 살펴볼것<br/>
```
예)
부분 수열인 경우 lt - rt + 1
```

# 슬라이딩 윈도우
for 문 한방에 끝낼 수 있음<br/>
k일간 최대매출 구하기 라면 보통 for문 두번으로 O(N^2) 로 끝나는데<br/>
O(N)으로 끝내는 기법, 창문영역을 두고 이동시키는 기법 (?)<br/>
12, 15, 11, 20, 25, 10 이라면<br/>
[12, 15, 11], 20, 25, 10, => 12, [15, 11, 20], 25, 10, => 12, 15, [11, 20, 25], 10, ...<br/>
```
예)
sum+=(arr[i]-arr[i-k]);
...
```

# 정렬

## 선택 정렬
선택 정렬은 첫 번째 자료를 두 번째 자료부터 마지막 자료까지 차례대로 비교하여 가장 작은 값을 찾아 첫 번째에 놓고, 두 번째 자료를 세 번째 자료부터 마지막 자료까지와 차례대로 비교하여 그 중 가장 작은 값을 찾아 두 번째 위치에 놓는 과정을 반복하며 정렬을 수행한다.

## 버블 정렬
서로 인접한 두 원소를 검사하여 정렬하는 알고리즘으로 선택 정렬과 기본 개념이 유사하다.<br/>
버블 정렬은 첫 번째 자료와 두 번째 자료를, 두 번째 자료와 세 번째 자료를, 세 번째와 네 번째를, … 이런 식으로 (마지막-1)번째 자료와 마지막 자료를 비교하여 교환하면서 자료를 정렬한다.<br/>
1회전을 수행하고 나면 가장 큰 자료가 맨 뒤로 이동하므로 2회전에서는 맨 끝에 있는 자료는 정렬에서 제외되고, 2회전을 수행하고 나면 끝에서 두 번째 자료까지는 정렬에서 제외된다.<br/> 
이렇게 정렬을 1회전 수행할 때마다 정렬에서 제외되는 데이터가 하나씩 늘어난다.

## 삽입 정렬
삽입 정렬은 두 번째 자료부터 시작하여 그 앞(왼쪽)의 자료들과 비교하여 삽입할 위치를 지정한 후 자료를 뒤로 옮기고 지정한 자리에 자료를 삽입하여 정렬하는 알고리즘이다.<br/>
즉, 두 번째 자료는 첫 번째 자료, 세 번째 자료는 두 번째와 첫 번째 자료, 네 번째 자료는 세 번째, 두 번째, 첫 번째 자료와 비교한 후 자료가 삽입될 위치를 찾는다.<br/> 
자료가 삽입될 위치를 찾았다면 그 위치에 자료를 삽입하기 위해 자료를 한 칸씩 뒤로 이동시킨다.<br/>
처음 Key 값은 두 번째 자료부터 시작한다.<br/>
자료 비교 시 key값이 더 작다면 앞의 값들은 정렬된 것이기에 순회를 멈추고 멈춘 위치에 해당 자료를 삽입한다.

# 그리디, 결정 알고리즘

## 한 회의실에서 가장 많이 회의할 수 있는 횟수 찾기 (greedy)
그리디는 정렬해야함, 회의실을 찾을때는 회의가 일찍 끝나는 시간으로 정렬 (끝나는 시간이 같으면 시작 시간으로 오름차순 정렬) <br />
다음 배열의 시작 시간이 끝난 시간보다 크거나 같다면 횟수를 증가시킴

## 이분 검색
시간복잡도는 O(logN)<br />
정렬된 배열에서 lt, rt과 mid = (lt + rt) / 2 의 몫으로 두고<br /> 
mid가 target 인지 보고 아니면 mid가 target 보다 크면 rt를 mid-1로 바꾼다<br />
아니면 lt를 mid+1 로 바꾼다. 이 과정을 반복한다. 

## 결정 알고리즘
이분 검색으로 lt = 배열에서 최대값 rt = 배열의 합 또는 아주 큰값) 사이에서 최적의 답을 찾는다.<br />
lt와 rt를 더하고 2로 나누어 mid 값을 구한다.<br />
mid 값으로 주어진 크기만큼 주어진 조건을 만족하는지 비교한다.<br />
만족한다면 rt 값을 mid - 1 로 바꾸고 mid를 다시구하여 반복한다.<br />
만족하지 않으면 lt를 mid + 1로 바꾸고 mid를 다시 구한다. lt가 rt보다 커질때까지 반복한다.<br />
(최대값을 찾느냐 최소값을 찾느냐 등 조건에 따라 lt, rt를 변경해야 하는게 반대가 될 수 있다)<br />
거리 등 정렬이 필요할 수도 있다. 문제를 잘 읽자

# 재귀, DFS

## DFS
왼쪽 자식 : 부모 * 2, 오른쪽 자식 : 부모 * 2 + 1<br />
전위순회 : 부모, 왼쪽 자식, 오른쪽 자식 순으로 출력<br />
중위순회 : 왼쪽 자식, 부모, 오른쪽 자식 순으로 출력<br />
후위순회 : 왼쪽 자식, 오른쪽 자식, 부모 순으로 출력

## 집합
부분집합은 공집합을 포함해서 2^n개가 존재

## Combination
<img width="141" alt="image" src="https://user-images.githubusercontent.com/60346043/174464910-34966345-124f-4bf1-a277-22610e552e6b.png"><br />
또는<br />
<img width="337" alt="image" src="https://user-images.githubusercontent.com/60346043/174464921-20fb212c-eefd-4a1c-b94a-169a074abfb7.png"><br />
5C3의 경우 5개중 3개를 뽑는 조합은 4C2(5를 포함한 경우) + 4C3(5를 포함하지 않는 경우)

조합은 수열과 다름 순열은 (1, 2) !== (2, 1) 이지만 조합에서 같다.
N개중 M개를 뽑는다 => 조합을 구하면 되는 문제이다<br />
1부터 4까지의 수 중 두개를 뽑는다고 했을때<br />
1은 2, 3, 4 를 뽑을수 있고 2는 (1, 2) !== (2, 1)는 같기 때문에 빼고 3, 4를 뽑을 수 있다.

# 그래프와 탐색

## 그래프와 인접 행렬
그래프의 각 노드(node, vertex, 정점, 꼭지점)과 엣지(edge, 간선)은 아래와 같이 표기한다.<br />
```graph(V, E)```

### 인접 행렬 (노드 개수가 적을때)
1. 무방향 그래프
<img width="329" alt="image" src="https://user-images.githubusercontent.com/60346043/175026627-5896b0a0-9be8-48aa-99fc-b019d68c6840.png">

<img width="587" alt="image" src="https://user-images.githubusercontent.com/60346043/175178992-a95f9392-7f58-4def-994b-af81f775b110.png">

    a. 노드 1과 연결된 노드는 1행에서 1로 체크된 열, 예) 2, 3

    b. 노드 2와 연결된 노드는 2행에서 1로 체크된 열, 예) 1, 4, 5


2. 방향 그래프
<img width="331" alt="image" src="https://user-images.githubusercontent.com/60346043/175026736-5c0eace5-459a-45f8-896c-41e7472f09f2.png">

<img width="586" alt="image" src="https://user-images.githubusercontent.com/60346043/175530862-b7389f87-0d5f-4b50-bf46-066e91d841dc.png">
    
    a. 노드 3에서 갈 수 있는 노드는 1행에서 1로 체크된 열, 예) 4


3. 가중치 방향 그래프
<img width="342" alt="image" src="https://user-images.githubusercontent.com/60346043/175026777-1a27ba97-7ec0-4049-b3ac-69bdddbe662f.png">

<img width="490" alt="image" src="https://user-images.githubusercontent.com/60346043/175179904-bb1465ba-c521-405f-a12b-f6103cf2fc37.png">

    a. 노드 1에서 갈 수 있는 노드와 가중치는 1행에서 0이 아닌 열, 예) 2, 가중치는 2

### 인접 리스트 (노드 개수가 많을때)
<img width="585" alt="image" src="https://user-images.githubusercontent.com/60346043/175531328-8b62e99e-8d82-4762-88fe-ef0b7df4b17b.png">

    a. 인접 행렬과 다르게 graph[v]에 해당 노드가 갈 수 있는 노드를 넣는 형태다. 예) 1행에 기록된 열들은 노드 1이 갈수 있는 다른 노드들.
    
    b. graph[v].length 만큼 돌면서 탐색한다.
    
    c. graph[v][i] = 갈 수 있는 노드

