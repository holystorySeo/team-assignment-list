# team-assignment-list
원티드 프리온보딩 FE 코스 8개 기업 팀 과제 개인 작업 성과

## 코스 소개
### 일정
- 2022.2.21 ~ 3.25(5주)
### 내용
- 웹 프론트엔드 심화(React, CSS), 서버 통신 심화(네트워크) 학습
- 팀 과제(8개 기업), 개인 과제(1개 기업)
### 안내
- [https://www.wanted.co.kr/events/pre_onboarding_course_8](https://www.wanted.co.kr/events/pre_onboarding_course_8)

## 과제 소개
## 1. 카트 라이더 랭킹 페이지
### 작업 성과
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

- Top Ranker 영역 마크업과 스타일링 (파일위치: src/components/molecules/TopRank.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-2/blob/dev/src/components/molecules/TopRank.js))
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
    <br><br>
## 2. 쇼핑몰 리뷰 등록과 확인 페이지
### 작업 성과
- 상세 페이지 마크업과 스타일링 작업 (폴더위치: src/components/organisms/detail [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/tree/dev/src/components/organisms/detail))
  
  <img src="https://user-images.githubusercontent.com/87353284/157573743-18202d52-a16e-4dd1-a7b7-246f422454d8.png" width="20%"/>

- 상세 페이지 마우스 드래그에 따른 이미지 슬라이드 기능(feat. 슬라이딩 dot 연동) 
  - 이미지 슬라이드 기능 (파일위치: src/components/organisms/detail/DetailImg.js [코드보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/organisms/detail/DetailImg.js))
  - 슬라이딩 닷 기능 (파일위치: src/components/atmoms/SlideDots.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/atmoms/SlideDots.js))

  <img src="https://user-images.githubusercontent.com/87353284/157575419-ae705da4-8c79-48fc-8aaa-81f7b20da634.gif" width="20%"/>

- 좋아요 버튼 구현(feat. Redux 전역저장소와 연동, click에 따른 좋아요 count Number 갱신) (파일위치: src/components/atmoms/Likes.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/atmoms/Likes.js))

  <img src="https://user-images.githubusercontent.com/87353284/157575735-c6ba4893-edaa-4b38-baa4-0c9a3e41f1df.gif" width="20%"/>

- 공유링크 모달 구현 (파일위치: src/components/atmoms/ShareItems.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9/blob/dev/src/components/atmoms/ShareItems.js))

  <img src="https://user-images.githubusercontent.com/87353284/157576370-3819910b-46c3-41dd-b87e-ad6311eb1376.gif" width="20%"/>

### 개선 필요사항
- 상세 페이지 이미지 슬라이드 기능 고도화(마우스 드래그에 따른 이미지 이동)
### 배포 링크
[https://balaan9.netlify.app](https://balaan9.netlify.app)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-9)
     <br><br>
## 3. 해시업 폼 구현하기
### 작업 성과
- (폴더위치: src/components/atoms/ [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-7-1/tree/dev/src/components/atoms))
- 폼 생성하기 페이지 마크업과 스타일링
  - 필수 옵션이 모두 채워지면 우측 하단 '폼 저장' 버튼이 활성화
    
  <img src="https://user-images.githubusercontent.com/87353284/158739152-0f2e500a-4a24-40e5-9821-8624185059ec.png" width="30%" />

- 필드 추가와 삭제
   - 리덕스 툴킷을 활용하여 전체 필드 리스트를 갱신
   - 개별 컴포넌트별로 옵션 관련 상태 전역에서 별도 관리
    
    <img src="https://user-images.githubusercontent.com/87353284/158739879-e9f2fe91-ec10-4803-ad78-bbbe139eb4c9.gif" width="30%" />

- Drag & Drop
   - Drag&Drop API를 이용
    
    <img src="https://user-images.githubusercontent.com/87353284/158740442-dd388761-eec2-46ed-9ff8-5f11579feec5.gif" width="30%" />

- 폼 저장
   - 저장 후 전체 정보 초기화
    
    <img src="https://user-images.githubusercontent.com/87353284/158740545-53d43689-814f-491a-a7f0-d08e73850d2c.gif" width="30%" />

### 개선 필요사항
- 해시업 폼 UX 제고 위한 CSS 스타일링
- Drag & Drop에서 Drop 전 Drag만 해도 각 필드의 위치가 바뀌게 하는 기능 고도화
### 배포 링크
[https://datable-9.netlify.app](https://datable-9.netlify.app)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-7-1](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-7-1)
 <br><br>
## 4. 기업 & 개인 fit 진달 결과 페이지
### 작업 성과
- 모두/본인/회사 Tab 컴포넌트 구현 (파일 위치: src/components/TabSection.vue [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-11/blob/dev/src/components/TabSection.vue))
   - `v-for` 로 `button` 태그 3개 생성
   - `v-on:click`으로 클릭된 탭의 `active CSS` 적용
   - `$emit` 메소드로 Tab index를 ‘자식 컴포넌트(`TabSection.vue`)’에서 ‘부모 컴포넌트(`App.vue`)’로 전달

     <img src="https://user-images.githubusercontent.com/87353284/163503122-bc1ed745-6bf8-4525-bbbd-b4fd2427ff82.gif" width="30%" />
### 배포 링크
[https://gravylab.netlify.app](https://gravylab.netlify.app)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-11](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-11)
 <br><br>
## 5. 모바일 앱 내 한 섹션 웹 페이지 화
### 작업 성과
- 원자 단위 컴포넌트 keyframes 애니메이션 작업
  - 좋아요 버튼 (파일 위치: src/components/atoms/Likes.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-4/blob/dev/src/components/atoms/Likes.js))
    
    <img src="https://user-images.githubusercontent.com/87353284/163504670-45e0fee1-1441-4054-88f5-11b4f191bbb7.gif" width="20%" />
    
  - 공유하기 버튼 (파일 위치: src/components/atoms/Share.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-4/blob/dev/src/components/atoms/Share.js))
    
    <img src="https://user-images.githubusercontent.com/87353284/163505563-375a533e-b549-4cb6-aabd-2e9925999665.gif" width="20%" />
### 배포 링크
[https://wanted-pre-onboarding-09.github.io/wanted-codestates-project-9-4](https://wanted-pre-onboarding-09.github.io/wanted-codestates-project-9-4)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-4](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-4)
<br><br>
## 6. 휴양림 메모 저장 서비스
### 작업 성과
- Skeleton UI Loading Component ver.1(파일 위치: src/components/common/Loading.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-8/blob/dev/src/components/common/Loading.js))
- Skeleton UI Loading Component ver.2(파일 위치: src/components/common/Loading2.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-8/blob/dev/src/components/common/Loading2.js))
   - linear-gradient와 keyframes로 version 1 은 background-position, version 2는 background-image를 변화시켜 로딩 효과 구현
    
      |version 1|version 2|
      |:-:|:-:|
      |<img src="https://user-images.githubusercontent.com/87353284/158618174-61afc828-fd8e-4cf9-941c-f3f2678f23a2.gif" width="30%">|<img src="https://user-images.githubusercontent.com/87353284/158629672-358ac06d-385d-40f1-8beb-58aa299c462e.gif" width="30%">|
### 배포 링크
[https://doublenc-9.netlify.app](https://doublenc-9.netlify.app/)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-8](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-8)
<br><br>
## 7. 간병인 신청하기
### 작업 성과
- 돌봄 스케줄 예약 캘린더 기능 구현 (파일 위치: 기업 요청으로 비공개 처리)
    <details>
    <summary>캘린더 기능 코드 보기</summary>

    ```jsx
        import React, { useState } from 'react';
        import { useDispatch } from 'react-redux';
        import styles from '../css/Schedule.module.css';
        import { changeStartDate, changeEndDate } from '../store/scheduleSlice';
        import CareSelect from './CareSelect';

        const Schedule = () => {
          const [startDateValue, setStartDateValue] = useState('');
          const [endDateValue, setEndDateValue] = useState('');
          const dispatch = useDispatch();

          const StartDateValueHandler = (e) => {
            const variable = String(e.target.value);
            setStartDateValue(variable);
            dispatch(changeStartDate(variable));
          };

          const EndDateValueHandler = (e) => {
            const variable = String(e.target.value);
            setEndDateValue(variable);
            dispatch(changeEndDate(variable));
          };

          return (
            <>
              <section className={styles.schedule_container}>
                <div className={styles.schedule_main}>
                  <div className={styles.date_container}>
                    <div className={styles.day_container}>
                      <div className={styles.dayTitle}>시작일</div>
                      <div className={styles.day}>
                        <input
                          type="date"
                          data-placeholder="날짜 선택"
                          required
                          aria-required="true"
                          value={startDateValue}
                          className={styles.selectDay}
                          onChange={StartDateValueHandler}
                        ></input>
                      </div>
                    </div>
                    <div className={styles.day_container}>
                      <div className={styles.dayTitle}>종료일</div>
                      <div className={styles.day}>
                        <input
                          type="date"
                          data-placeholder="날짜 선택"
                          required
                          aria-required="true"
                          value={endDateValue}
                          className={styles.selectDay}
                          onChange={EndDateValueHandler}
                        ></input>
                      </div>
                    </div>
                  </div>
                </div>
                <CareSelect />
              </section>
            </>
          );
        };

        export default Schedule;
    ```

    </details>
- 시작일과 종료일 리덕스 전역 저장소 관리
    <details>
    <summary>리덕스 코드 보기</summary>

    ```jsx
        import { createSlice } from '@reduxjs/toolkit';

        const initialState = {
          startDate: '', // yyyy-MM-dd
          endDate: '', // yyyy-MM-dd
          visitTime: '', // hh:mm:ss
          hour: 0,
          startCare: '선택',
          dayCare: '선택',
        };

        const scheduleSlice = createSlice({
          name: 'scheduleSlice',
          initialState,
          reducers: {
            changeStartDate: (state, action) => {
              state.startDate = action.payload;
            },
            changeEndDate: (state, action) => {
              state.endDate = action.payload;
            },
            changeVisitTime: (state, action) => {
              state.visitTime = action.payload;
            },
            changeHour: (state, action) => {
              state.hour = action.payload;
            },
            changeStartCare: (state, action) => {
              state.startCare = action.payload;
            },
            changeDayCare: (state, action) => {
              state.dayCare = action.payload;
            },
            clearDate: () => initialState,
          },
        });

        export const {
          changeStartDate,
          changeEndDate,
          changeVisitTime,
          changeHour,
          clearDate,
          changeStartCare,
          changeDayCare,
        } = scheduleSlice.actions;
        export default scheduleSlice.reducer;
    ```

    </details>
    
  <img src="https://user-images.githubusercontent.com/87353284/163510399-7150fa67-047d-45ac-882c-340adda4242a.gif" width="30%" />
### 배포 링크
[https://caredoc.netlify.app](https://caredoc.netlify.app)
### 개선 필요사항
- 캘린더 라이브러리 적용한 UX 고도화(예, date picker 등)
- 캘린더 시작일과 종료일 설정 기능 (종료일이 시작일 보다 앞일 수 없음)
    <br><br>
## 8. 듀얼 셀렉터 
### 작업 성과
- 검색 컴포넌트 구현 (파일 위치: src/components/SearchBar.js [코드 보기](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-3/blob/dev/src/components/SearchBar.js))
  - 듀얼 셀렉터 왼쪽/오른쪽 검색 기능에 모두 동일 컴포넌트 재사용
  - section props로 구분

    ```jsx
       <SearchBar section="left" />
       <SearchBar section="right" />
    ```

    <img src="https://user-images.githubusercontent.com/87353284/158937078-899f6a8b-bbb8-43d8-952e-0b195b5c551b.gif" width="40%">

- 왼쪽 셀렉터 검색 기능 알고리즘 구현(feat. 리덕스 리듀서 함수, 파일명: optionSlice.js, 리듀서: updateLeftSearch)

  - 오른쪽 셀렉터에 아무것도 없는 경우: 초기 옵션중을 filter함수로 순회하여 검색어 포함 여부 indexOf로 판별
  - 오른쪽 셀렉터에 요소가 있는 경우: 1)초기 옵션에서 오른쪽 셀렉터 요소 필터 2)필터 후 남은 요소 중에서 검색어 포함 여부 indexOf로 판별
  - 함수 체이닝으로 변수 선언 줄이고 코드 간결화
    <details>
    <summary>왼쪽 셀렉터 검색 기능 리듀서 코드 자세히 보기</summary>

    ```jsx
      availableOptions: emojiMenus, /* 왼쪽 셀럭터 옵션 */
      selectedOptions: [], /* 오른쪽 셀럭터 옵션 */

      updateLeftSearch(state, action) {
        // 오른쪽 옵션에 아무것도 없는 경우
        if (state.selectedOptions.length === 0) {
          state.availableOptions = [
    	  ...emojiMenus.filter((option) => {
    	    return option.name.indexOf(action.payload) !== -1;
    	  }),
    	];
        } else {
          /* 오른쪽 옵션에 요소가 있는 경우 */
    	const newArr = emojiMenus
    	  .filter((option) => {
    	    return (
    	      state.selectedOptions
    		.map((el) => {
    		  return el.name;
    		})
    		.indexOf(option.name) === -1
    	    );
    	  })
    	  .filter((option) => {
    	    return option.name.indexOf(action.payload) !== -1;
    	  });

    	state.availableOptions = [...newArr];
          }
        },
    ```

    </details>

- 오른쪽 셀렉터 검색 기능 알고리즘 구현(feat. 리덕스 리듀서 함수, 파일명: optionSlice.js, 리듀서: updateRightSearch)

  - 왼쪽 셀렉터에 아무것도 없는 경우: 오른쪽 셀렉터를 filter함수로 순회하여 검색어 포함 여부 indexOf로 판별
  - 왼쪽 셀렉터에 요소가 있는 경우: 1)초기 옵션에서 왼쪽 셀렉터 요소 필터 2)필터 후 남은 요소 중에서 검색어 포함 여부 indexOf로 판별
  - 함수 체이닝으로 변수 선언 줄이고 코드 간결화
    <details>
    <summary>오른쪽 셀렉터 검색 기능 리듀서 코드 자세히 보기</summary>

    ```jsx
      availableOptions: emojiMenus, /* 왼쪽 셀럭터 옵션 */
      selectedOptions: [], /* 오른쪽 셀럭터 옵션 */

       updateRightSearch(state, action) {
          // 왼쪽 옵션에 아무것도 없는 경우
          if (state.availableOptions.length === 0) {
    	state.selectedOptions = [
    	  ...emojiMenus.filter((option) => {
    	    return option.name.indexOf(action.payload) !== -1;
    	  }),
    	];
          } else {
    	const newArr = emojiMenus
    	  .filter((option) => {
    	    return (
    	      state.availableOptions
    		.map((el) => {
    		  return el.name;
    		})
    		.indexOf(option.name) === -1
    	    );
    	  })
    	  .filter((option) => {
    	    return option.name.indexOf(action.payload) !== -1;
    	  });

    	state.selectedOptions = [...newArr];
          }
        },
    ```

    </details>
### 배포 링크
[https://logpreesso-9.netlify.app](https://logpreesso-9.netlify.app)
### 저장소 링크
[https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-3](https://github.com/wanted-pre-onboarding-09/wanted-codestates-project-9-3)
<br><br>
## 생산 콘텐츠
### [(CSS) Skeleton UI 제작](https://jobcoding.tistory.com/214?category=1011893)
### (CSS) Progress Bar Chart 제작(예정)
### (CSS) 슬라이딩(feat. 슬라이딩 닷 연동) 제작(예정)
### (React) 초기 컴포넌트 설계 구조 설정의 중요성(예정)  
