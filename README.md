# Kim Dorim · 김도림

**화면에서 데이터, 장치 제어까지 이어지는 기능을 만듭니다.**  
Android 앱의 채용 관리와 Spring Boot 기반 채팅·매물 비교를 구현했습니다. 현재는 **FEMS-MIDAS**에서 에너지 데이터 처리와 MQTT 기반 제어 기능을 개발하고 있습니다.

### Tech Stack

프로젝트에서 사용한 주요 기술입니다.

![Java](https://img.shields.io/badge/Java-E76F00?style=flat-square)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white)
![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-4285F4?style=flat-square&logo=jetpackcompose&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MQTT](https://img.shields.io/badge/MQTT-660066?style=flat-square&logo=mqtt&logoColor=white)

## Selected Projects

아래는 팀 프로젝트에서 제가 구현하고 연동한 기능입니다. 프로젝트명은 개인 포크로, 각 PR은 팀 원본의 기여 내역으로 연결됩니다.

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

### [DodoJob](https://github.com/gjyfdsdjj/dodojob)

시니어를 위한 일자리·교육·복지 Android 앱  
<sub>Kotlin · Jetpack Compose · Coroutines · StateFlow · Supabase</sub>

- **지원자 관리 화면:** 기업이 지원자 목록을 확인하고 관련 화면으로 이동하는 UI와 내비게이션을 구현했습니다. [PR #41](https://github.com/ehdrms3535/dodojob/pull/41)
- **지원자 상세 조회:** 지원자 정보 화면과 DB 조회를 연결했습니다. [PR #131](https://github.com/ehdrms3535/dodojob/pull/131)
- **면접 제안:** 면접 제안 화면과 데이터 저장을 연결해 기업의 채용 업무 흐름을 구현했습니다. [PR #126](https://github.com/ehdrms3535/dodojob/pull/126)
- **열람 상태 갱신:** 지원자 상세 조회·면접 제안 시 미열람 상태를 열람 상태로 변경하도록 연결했습니다. [PR #132](https://github.com/ehdrms3535/dodojob/pull/132)
- **프로필 데이터 연동:** 시니어 프로필 사진을 DB 데이터와 연결했습니다. [PR #144](https://github.com/ehdrms3535/dodojob/pull/144)

**구현 포인트 — 사용자 행동과 상태 갱신 연결**  
공고 ID와 시니어 식별자로 갱신 대상을 지정하고, 기존 상태가 미열람인 경우에만 열람 상태로 바꾸도록 조건을 추가했습니다. 지원자 관리 화면에서는 갱신 결과를 목록 상태와 미열람 수에 반영했습니다.

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

<sub>각 서비스는 팀의 공동 결과물이며, 위 설명은 제 PR로 확인되는 기여 범위입니다.</sub>
