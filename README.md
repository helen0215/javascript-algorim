# javascript-algorim
니 약점 알고리즘 쯔ㅉ쯔ㅉ쯔ㅉ쯔

# Tip
> 알고리즘 풀때 도움 되는 팁 정리 

## 대소문자 범위
x.charCodeAt을 통해 아스키 코드로 바꾸어 검사하는 방법 <br/>
대문자 : 65 \~ 90 (A\~Z, 26개)<br/>
소문자 : 97 \~ 122 (a\~z)<br/>

## indexOf
문자열 중복을 순회하며 검사할때 문자열의 indexOf와 해당 순회값 i가 같다면 처음 나왔다는 의미이다<br/>
```javascript
if(s.indexOf(s[i]) === i) answer+=s[i];
```

## 격자판 최대합
이중 포문을 돌고 행고정, 열고정을 생각할것 [i][j], [j][i]<br/>
대각선은 [i][i], [i][length-i-1]<br/>

## 봉우리
네방향 탐색<br/>
격자의 가장자리는 항상 나보다 작다, 가장자리는 살펴보지 말것<br/>
행 i, 열 j (1, 2) 인경우 dx, dy 베열을 초기화 해서 사용)<br/>
dx = [-1(위), 0 (오른쪽), 1 (아래), 0 (왼쪽)]<br/>
dy = [0(위),  1 (오른쪽), 0 (아래), -1 (왼쪽)]<br/>
이 경오 (1, 2) 의 위를 보고 싶다면 i + dx[k], j + dy[k], k는 0~3까지 있음 네방향이니까<br/>

## 회문 문자열
회문 문자열은 주어진 문자열의 나누기 2만큼의 몫을 돌면면서 앞뒤를 검사하면된다.<br/>
reverse 사용도 고려해볼 수 있다<br/>

## 숫자만 추출
숫자인 문자열이 숫자인지 알려면 isNaN 로 판단해 볼 수 있다<br/>

## 문자거리
특정 문자간 거리를 구할때 (특정 문자가 해당 문자열에서 여러개 출연) 1차 배열인 경우<br/> 
→ 방향(특정 문자열의 왼쪽으로 부터의 거리) 으로 한번 ← 방향(특정 문자열의 오른쪽부터 떨어진 거리)으로<br/> 
한번 반복문을 돌아서 (시간 복잡도는 O(N)) 더 작은 값으로 하면 된다<br/>

## 완전탐색
for문으로 모두 돌면서 모든 경우의 수를 찾아야함 (대표적인 완전탐색 문제)<br/>
경우의 수는 4x4(학생수가 4명이니까)<br/>

## Tow Pointer Algorithm
sort는 nlogn<br/>
p1, p2는 반복문 **한번**으로 끝내는 알고리즘 n+m<br/>
p1=p2=0<br/>
배열은 주어진 조건으로 정렬해야하며 해당 포인터가 가리키는 값이 조건에 맞아 푸시되는 경우 해당 포인터를 증가시킴<br/>
연속 부분수열에서는 lt, rt 포인터를 두고 계속 특정 조건에 같이 증가 (5. > 3. 연속 부분수열 코드 참고)
