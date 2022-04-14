# team-assignment-list
원티드 프리온보딩 FE 코스 8개 기업 팀 과제에서 달성한 역할과 성과

## 코스 소개
### 일정
- 2022.2.21 ~ 3.25(5주)
### 내용
- 웹 프론트엔드 심화(React, CSS), 서버 통신 심화(네트워크) 학습
- 팀 과제(8개 기업), 개인 과제(1개 기업)
### 안내
- [https://www.wanted.co.kr/events/pre_onboarding_course_8](https://www.wanted.co.kr/events/pre_onboarding_course_8)

## 과제 소개
## 1. 카트라이더 랭킹 페이지 클론
### 역할과 성과
- Progress circle chart (파일위치: /src/components/atoms/ProgressCircle.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2/blob/dev/src/components/atoms/ProgressCircle.js))
    - 컴포넌트 재사용성 고려하여 기능 구현<br>
    
      ```jsx
       ProgressCircle 컴포넌트는 부모 컴포넌트로 부터 2개의 파라미터를 인자로 받는다. 
       인자 1 color: 도너 차트 외곽선 색깔
       인자 2 percent: 도너 차트 
      ```
      ```jsx
       <ProgressCircle color="#07f" percent={RankingData[1].win} />
      ```
      <br>
      <img src="https://user-images.githubusercontent.com/87353284/158306214-c1dca079-44da-405b-bb0c-f11fe8c11876.gif" width=90%">
 <br>

- Top Ranker 영역 마크업과 스타일링 (파일위치: src/components/molecules/TopRank.js)
    - DB에서 수신한 Ranker 정보와 연동하여 Top Ranker 데이터 랜더링<br>
      ```jsx
          topRank.map((obj) => {
            RankingData = [
              ...RankingData,
              {
                nickName: obj.nickName,
                character: `{API생략}/${obj.character}.png`,
                point: obj.points
                  .toString()
                  .replace(/\B(?<!\.\d*)(?=(\d{3})+(?!\d))/g, ','),
                win: obj.win,
                retire: obj.Retired,
              },
            ];
          });
      ```
      <img src="https://user-images.githubusercontent.com/87353284/158315125-db4cf4bb-7de1-48fe-ab7d-26d680d2be09.png" width="80%">

### 개선 필요사항
- topRank에 map함수로 적용하면 배열 전체를 순회하는 부분하기 때문에 1 ~ 3위까지만 배열을 자르고 그 데이터 map으로 순회하게 하여 리소스 효율화

### 배포 링크
[https://wanted-pre-onboarding-09.github.io/wanted-codestates-project-9-2](https://wanted-pre-onboarding-09.github.io/wanted-codestates-project-9-2)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2)
