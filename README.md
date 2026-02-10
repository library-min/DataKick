⚽ DataKick (데이터킥)
European Football Data Analysis & Prediction Platform

유럽 5대 리그 데이터 분석, 승패 예측, 그리고 실시간 트래픽 처리를 위한 백엔드 엔지니어링 프로젝트

1. Project Overview (프로젝트 개요)
프로젝트명: DataKick

개발 기간: 2026.02 ~ 진행 중

개발 인원: 1인 (Backend-Focused Full Stack)

기획 의도:

단순한 경기 결과 확인을 넘어, **데이터(Data)와 논리(Logic)**에 기반한 승패 예측 시스템을 구축합니다.

대용량 데이터 처리, 동시성 제어, 실시간 시스템 모니터링 등 백엔드 개발의 핵심 역량을 실제 서비스 수준으로 구현하는 것을 목표로 합니다.

2. Tech Stack (기술 스택)
Backend: Java 17, Spring Boot 3.x, Spring Data JPA

Database: MySQL 8.0 (Main DB), Redis (Cache & Ranking)

API: API-Football (External Data Source)

DevOps: Docker, AWS EC2 (배포 예정), Prometheus & Grafana (모니터링)

Tools: IntelliJ, GitHub, Postman

3. Key Features (핵심 기능)
A. Data Analysis & Prediction (분석 및 예측)
자동화된 데이터 수집: Spring Scheduler를 활용해 매일 유럽 주요 리그 경기 데이터 및 선수 정보 수집.

승패 예측 알고리즘: 홈/어웨이 승률, 최근 득점 흐름, 선수 결장 정보를 종합한 자체 알고리즘 구현.

xG(기대 득점) 분석: 실제 득점과 기대 득점(xG)을 비교하여 팀의 '운(Luck)'과 '실력(Skill)'을 수치화.

Back-testing (검증): 과거 시즌 데이터에 알고리즘을 대입해 예측 모델의 정확도를 시뮬레이션.

B. Real-time Service (실시간 서비스)
Live Score Tracking: 경기 중 실시간 점수 변동을 추적하고 Redis 캐싱을 통해 조회 성능 최적화.

Mock Betting (모의 배팅): 사용자 포인트로 경기 결과를 예측하는 시뮬레이션 게임.

Real-time Ranking: Redis Sorted Set을 활용한 실시간 유저 랭킹 보드 제공.

Concurrency Control: 배팅 및 포인트 정산 시 발생하는 동시성 이슈 제어 (@Transactional, Optimistic Lock).

4. Database Schema (ERD)
(프로젝트 진행에 따라 구체적인 ERD 다이어그램이 업데이트될 예정입니다.)

Teams / Players: 팀 및 선수 기초 정보

Matches: 경기 일정 및 결과

Match_Advanced_Stats: xG, 슈팅 수 등 세부 분석 지표

Team_Power_Stats: 분석용 2차 가공 데이터 (홈/어웨이 승률 등)

Betting_History: 사용자 모의 배팅 기록

5. Troubleshooting (문제 해결)
(개발 과정에서 발생하는 기술적 문제와 해결 과정을 기록합니다.)

[작성 예정] 외부 API 호출 제한(Rate Limit) 해결 과정

[작성 예정] 대량의 경기 데이터 배치 처리 성능 개선

[작성 예정] 실시간 배팅 동시성 문제 해결
