# Kim Dorim · 김도림

**Kotlin으로 사용자 화면과 데이터 흐름을 구현하는 개발자입니다.**

시니어 일자리 앱 **DodoJob**에서 구직·교육과 기업 채용 관리 기능을 구현했습니다. 강의 영상 재생·이어보기, 지원서 제출, 면접 제안 등 사용자 흐름을 데이터 저장과 화면 상태 갱신까지 연결했습니다.

현재는 **FEMS-MIDAS** 팀 프로젝트에서 에너지 데이터 처리 API와 MQTT 기반 장치 제어 기능을 개발하며 서비스 연동 경험을 넓히고 있습니다.

## Tech Stack

프로젝트에서 사용한 주요 기술입니다.

**Android**  
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white)
![Coroutines](https://img.shields.io/badge/Coroutines-7F52FF?style=flat-square)
![StateFlow](https://img.shields.io/badge/StateFlow-4285F4?style=flat-square)

**Data**  
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=black)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)

**Backend & IoT**  
Java · Spring Boot · Python · FastAPI · MQTT

## Selected Projects

아래는 팀 프로젝트에서 제가 구현하고 연동한 기능입니다. 프로젝트명은 개인 포크로, 각 PR은 팀 원본의 기여 내역으로 연결됩니다.

### [DodoJob](https://github.com/gjyfdsdjj/dodojob)

시니어를 위한 일자리·교육·복지 Android 앱  
<sub>Kotlin · Jetpack Compose · Coroutines · StateFlow · Media3/ExoPlayer · Supabase</sub>

- **교육·영상:** 강의 영상 재생·이어보기, 희망 직무 기반의 규칙형 강의 추천, 수강·찜 상태 연동을 구현했습니다. [PR #110](https://github.com/ehdrms3535/dodojob/pull/110) · [PR #96](https://github.com/ehdrms3535/dodojob/pull/96)
- **시니어 구직:** 공고 상세 조회와 지원서 제출을 연결하고, 경력·자격증을 조회·추가하는 이력서 관리 기능을 구현했습니다. [PR #121](https://github.com/ehdrms3535/dodojob/pull/121) · [PR #70](https://github.com/ehdrms3535/dodojob/pull/70)
- **기업 채용 관리:** 공고·지원자 목록, 상세 조회와 면접 제안을 연동하고, 열람 상태 변경에 따라 목록과 미열람 수를 갱신했습니다. [PR #79](https://github.com/ehdrms3535/dodojob/pull/79) · [PR #132](https://github.com/ehdrms3535/dodojob/pull/132)
- **프로필·복지:** 프로필 사진과 복지 목록·분류·검색, 사용자별 신청 내역을 DB 데이터에 연결했습니다. [PR #144](https://github.com/ehdrms3535/dodojob/pull/144) · [PR #62](https://github.com/ehdrms3535/dodojob/pull/62)

**구현 포인트 — 강의 영상 이어보기**  
사용자·강의별 재생 위치를 Supabase에 저장하고, 다시 열면 ExoPlayer에 복원했습니다. 재생 중 5초 간격과 플레이어 종료 시점에 위치를 전달하며, 저장 위치가 뒤늦게 로드되는 경우도 반영했습니다.

---

### [Real Estate Hub](https://github.com/gjyfdsdjj/real-estate-hub-project)

부동산 조회·비교·거래 협의 웹 서비스  
<sub>Java · Spring Boot · JPA · WebSocket/STOMP · PostgreSQL · Supabase Storage</sub>

- **채팅:** 채팅방·메시지 API를 구현하고 WebSocket/STOMP와 JWT 인증을 연동했습니다. [PR #17](https://github.com/pyodolski/real-estate-hub-project/pull/17)
- **매물 비교:** 비교 그룹 생성·조회·이름 변경·삭제, 매물 추가·제거, 그룹 소유자 검사와 가중치 기반 비교 로직을 구현했습니다. [PR #23](https://github.com/pyodolski/real-estate-hub-project/pull/23)
- **매물 조회:** 본인 매물·전체 매물·본인 제외 매물 목록과 상세 조회 API를 구현했습니다. [PR #27](https://github.com/pyodolski/real-estate-hub-project/pull/27)
- **실거래가 조회:** 실거래가 조회 API와 응답 데이터를 구성했습니다. [PR #67](https://github.com/pyodolski/real-estate-hub-project/pull/67)
- **매물 이미지:** 이미지 등록 API와 Supabase Storage 저장 기능을 연동했습니다. [PR #94](https://github.com/pyodolski/real-estate-hub-project/pull/94)

**구현 포인트 — 서로 다른 매물 조건 비교**  
가격·단위면적당 가격·준공연도를 min-max 방식으로 정규화하고, 항목별 가중치를 적용해 매물 순위를 계산했습니다. 가격은 낮을수록, 준공연도는 높을수록 높은 점수를 부여하며 차트용 원시값도 함께 반환했습니다. 이는 조건 기반 비교 기능으로, 가격 예측 모델과는 구분됩니다.


---

### [FEMS-MIDAS](https://github.com/gjyfdsdjj/FEMS-MIDAS) · 진행 중

공장 에너지 모니터링 및 제어 시스템  
<sub>Python · FastAPI · SQLAlchemy · MQTT · Supabase</sub>

- **에너지 분석 API:** 전력 소비·요금·절감액·탄소 배출량 추정과 피크 시간대 분석 기능을 구현했습니다. [PR #10](https://github.com/ehdrms3535/FEMS-MIDAS/pull/10)
- **장치 제어 연동:** 스케줄러와 MQTT 발행 기능을 연결해 펠티어 소자를 제어하는 흐름을 구현했습니다. [PR #13](https://github.com/ehdrms3535/FEMS-MIDAS/pull/13)
- **자연어 명령 처리:** 음성 전사와 자연어를 구조화된 장치 제어 명령으로 변환하는 기능을 추가했습니다. [PR #37](https://github.com/ehdrms3535/FEMS-MIDAS/pull/37)
- **DB·화면 통합:** Supabase 연동, 수동·음성 제어 개선, 대시보드의 실제 데이터 연결에 기여했습니다. [PR #42](https://github.com/ehdrms3535/FEMS-MIDAS/pull/42)
- **다중 공장 구성:** 공장 4개 구성과 node_B 분리, DB 기반 스케줄링을 반영했습니다. [PR #43](https://github.com/ehdrms3535/FEMS-MIDAS/pull/43)

**구현 포인트 — 추정값과 실측값 구분**  
에너지 API에서는 스케줄의 가동 시간과 정격 전력을 이용한 추정 경로, 센서 측정값을 이용한 계산 경로를 구분했습니다. 절감액은 항상 가동하는 기준선과 비교한 계산값으로, 실측 절감 성과와 구분해 해석하도록 했습니다.


---

### [Smart Grid Optimization Platform · SGOP](https://github.com/gjyfdsdjj/Smart-Grid-Optimization-Platform)

전력 수요 예측과 선로 위험도를 비교하는 스마트 그리드 시뮬레이션 플랫폼  
<sub>Python · Streamlit · Plotly · pandas · TensorFlow · pytest</sub>

- **시나리오 비교:** 현재 예측 결과를 시나리오 A로 저장하고, 설정 변경 후 결과 B와 총부하 그래프·위험 선로 이용률을 비교하는 화면을 구현했습니다. [PR #9](https://github.com/waterspouut/Smart-Grid-Optimization-Platform/pull/9)
- **위험 시간대 시각화:** 위험도가 높은 선로의 피크 시각을 그래프에 표시하고, 시간대·부하 배율·위험 등급에 따른 설명을 보강했습니다. [PR #9](https://github.com/waterspouut/Smart-Grid-Optimization-Platform/pull/9)
- **예측 시각 처리:** 예측 기준 시각이 데이터의 마지막 시각을 넘지 않도록 보정하고, 위험도 계산에서 날짜를 포함한 타임스탬프로 부하를 조회하도록 수정했습니다. [PR #9](https://github.com/waterspouut/Smart-Grid-Optimization-Platform/pull/9)
- **학습 재현성 설정:** LSTM 학습 시 Python·NumPy·TensorFlow의 난수 시드를 고정했습니다. [PR #16](https://github.com/waterspouut/Smart-Grid-Optimization-Platform/pull/16)
- **예측 결과 검증:** mock·baseline 예측의 결과 개수, 부하 값, 구간 상·하한 순서, 피크 시각 범위, 부하 배율 반영 등을 확인하는 테스트를 추가했습니다. [PR #17](https://github.com/waterspouut/Smart-Grid-Optimization-Platform/pull/17)

**구현 포인트 — 설정 변경 전후를 비교할 수 있는 예측 화면**  
Streamlit 세션에 기준 결과를 보관하고 새 예측 결과와 함께 표시해, 부하 배율 등을 바꿨을 때 총부하와 위험 선로 이용률이 어떻게 달라지는지 확인하도록 했습니다. 예측 결과의 구조와 값에 대한 검증은 mock·baseline을 대상으로 작성했으며, 학습된 모델의 정확도 평가는 별도로 구분했습니다.

---

<sub>각 프로젝트는 팀의 공동 결과물이며, 위 설명은 제 PR로 확인되는 기여 범위입니다.</sub>
