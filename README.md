# ⚽ DataKick (데이터킥)
**유럽 5대 리그 데이터 분석, 승패 예측, 그리고 실시간 트래픽 처리를 위한 백엔드 엔지니어링 프로젝트**

---

## 1. Project Overview (프로젝트 개요)
* **프로젝트명:** DataKick (데이터킥)
* **개발 기간:** 2026.02 ~ (진행 중)
* **개발 인원:** 1인 (Backend-Focused Full Stack)
* **기획 의도:**
    * 단순한 경기 결과 확인을 넘어, **데이터(Data)와 논리(Logic)** 에 기반한 승패 예측 시스템을 구축합니다.
    * **대용량 데이터 처리, 동시성 제어, 실시간 시스템 모니터링** 등 백엔드 개발의 핵심 역량을 실제 서비스 수준으로 구현하여 기술적 깊이를 증명하는 것을 목표로 합니다.

<br>

## 2. Tech Stack (기술 스택)

| Category | Technology | Usage |
| :--- | :--- | :--- |
| **Language** | Java 17 | 주요 비즈니스 로직 구현 |
| **Framework** | Spring Boot 3.x | REST API 서버 및 배치 처리 |
| **Database** | MySQL 8.0 | 관계형 데이터 저장 (팀, 선수, 경기, 베팅 기록) |
| **Cache / NoSQL** | **Redis** | 실시간 스코어 캐싱, 베팅 랭킹(Sorted Set) 구현 |
| **ORM** | Spring Data JPA / QueryDSL | 복잡한 통계 쿼리 및 동적 쿼리 처리 |
| **External API** | API-Football | 유럽 주요 리그 경기 데이터 및 선수 정보 수집 |
| **Monitoring** | Prometheus & Grafana | 서버 상태 및 비즈니스 메트릭 모니터링 |
| **DevOps** | Docker, AWS EC2 | 컨테이너 기반 배포 환경 구축 (예정) |

<br>

## 3. Key Features (핵심 기능)

### A. Data Analysis & Prediction (분석 및 예측)
* **자동화된 데이터 수집:** `Spring Scheduler`를 활용해 매일 새벽 유럽 주요 리그 경기 데이터 및 선수 부상 정보 수집.
* **승패 예측 알고리즘:** 홈/어웨이 승률, 최근 5경기 득실 흐름, 핵심 선수 결장 정보를 종합한 자체 알고리즘 구현.
* **xG(기대 득점) 분석:** 실제 득점과 기대 득점(xG)을 비교하여 팀의 '운(Luck)'과 '실력(Skill)'을 수치화하고 시각화.
* **Back-testing (검증):** 과거 시즌 데이터에 알고리즘을 대입해 예측 모델의 정확도를 시뮬레이션하고 검증.

### B. Real-time Service (실시간 서비스)
* **Live Score Tracking:** 경기 중 실시간 점수, 슈팅 수 변동을 추적하고 `Redis` 캐싱을 통해 조회 성능 최적화.
* **Mock Betting (모의 배팅):** 사용자 포인트로 경기 결과를 예측하는 시뮬레이션 게임.
* **Real-time Ranking:** `Redis Sorted Set (ZSET)`을 활용한 실시간 유저 랭킹 보드 제공.
* **Concurrency Control:** 다수의 유저가 동시에 배팅하거나 포인트를 정산할 때 발생하는 Race Condition을 방지하기 위해 `@Transactional` 및 낙관적 락(Optimistic Lock) 적용.

### C. System Monitoring (운영 및 유지보수)
* **Dashboard:** `Grafana`를 통해 API 호출량, 에러율, JVM 메모리 사용량, 배치 작업 성공 여부를 실시간 모니터링.

<br>

## 4. Database Schema (ERD)
*(프로젝트 진행에 따라 구체적인 ERD 다이어그램이 업데이트될 예정입니다.)*

* **`Teams` / `Players`:** 팀 및 선수 기초 정보
* **`Matches`:** 경기 일정, 결과, 상태 (Live/Finished)
* **`Match_Advanced_Stats`:** xG, 슈팅 수, 점유율 등 세부 분석 지표
* **`Team_Power_Stats`:** 분석용 2차 가공 데이터 (홈/어웨이 승률, 공격력/수비력 지수)
* **`Betting_History`:** 사용자 모의 배팅 기록 및 정산 내역
* **`Job_Execution_Logs`:** 배치 스케줄러 실행 이력 및 상태 로그

<br>

## 5. Troubleshooting (문제 해결 경험)
*(개발 과정에서 발생하는 기술적 문제와 해결 과정을 기록할 예정입니다.)*

* [작성 예정]
* [작성 예정]
* [작성 예정]

---
