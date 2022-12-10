# Slackbot을 이용한 근처 따릉이 대여소 조회 알리미
## 🚲 1. 소개
* slack에 주소를 입력하면 그 근처 최단거리(직선거리)의 따릉이 대여소 3곳의 거리와 그 위치가 표시된 지도가 나온다.
### 1-1. 팀원
|이름|역할|github|
|:---:|:-------:|:---:|
|이주환|주소 입력 -> 위도,경도 좌표 변환, 해당 위치 사진|https://github.com/LeeJuHwan|
|고건영|대여소 크롤링, 좌표에 따른 대여소 계산, slackbot 연결|https://github.com/goodyoung|

### 1-2. 실행 화면
![bikeSeoul](https://user-images.githubusercontent.com/10703294/206843948-bc91f91e-2a74-4254-ba6a-49b33905f4cd.gif)

## ⚙︎ 2. 기능 설명
- [따릉이 최종](https://github.com/goodyoung/bikeSeoul_slackbot/tree/main/%EB%94%B0%EB%A6%89%EC%9D%B4%20%EC%B5%9C%EC%A2%85)
### 2-1. [따릉이_total 기능]
- main file이다.
- slack bot을 구동하는 file.
- 사용자 text를 받아서 2-2,2-3 module을 이용해 대여소 3곳 조회
- 대여소 지도 사진 파일 slack에 upload.
### 2-2. [bikeSeoul]
*
*
*
### 2-3. [distance_kakaoapi]

## 🙋 3. KPT 회고  
### KPT
  + Keep(계속 해야할 것)
    + api token의 암호화

    + 경로 지정 (어느 컴퓨터에서도 할 수 있게)

    + module의 class화 

    + main 파일인 '따릉이_total'의 코드 정리가 필요하다.
  + Problem(문제점)
    + 지도 사진이 잘 나오긴 하지만 시간이 오래 걸린다.

    + '@~' bot mention을 사용 할 때만 가능하다.(slack api에 mention이 아닌 방법이 있을 것 같다.)
 
    + 거리 계산이 직선거리, 건물들이 많은 곳이라면 최적의 경로가 아닐 수 있다.

  + Try(앞으로 시도할 것)
    + python flask를 활용해 soket mode가 아닌 서버로 이용하는 방법.
 
    + 이 방법을 활용 한 Web도 같이 구현하면 좋을 것 같다.
 
    + 직선거리의 단점을 보완하기 위해 
      + Dijkstra(다익스트라) 등 최단경로 알고리즘을 구현하여 거리를 계산하는 방법.
      + kakao등 지도 api를 이용하여 최단경로를 찾는 방법.
    + 오류 처리 ex) 다른 지역이어도 제일 가까운 곳이 나오기 때문에 입력받는 지역을 서울로 한정지어야 한다.


