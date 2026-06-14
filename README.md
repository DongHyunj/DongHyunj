## 👨‍💻 About Me
<div align="center">
  <br>
  <i>"항상 <b>'이 코드가 최선인가?'</b>를 스스로에게 묻습니다."</i>
  <br><br>
</div>

**🎯 아키텍처와 성능에 진심인 백엔드 엔지니어**
> 단순히 돌아가는 코드를 넘어, 사용자에게 실질적인 가치를 제공하는 **서비스**를 만드는 것에 큰 매력을 느낍니다.
> 막연한 "느리다 · 깨진다 · 멈춘다"를 측정 가능한 수치로 바꾸고, 병목을 찾아 구조로 해결한 뒤 다시 질문합니다.
> 무중단 배포 · 성능 개선 · 시스템 아키텍처를 끊임없이 고민합니다.

**🎓 Education & Certifications**
- 🏫 **한화시스템 BEYOND SW 캠프 24기** (2025.12 ~ 2026.06 · 수료)
- 🏫 **KH 정보교육원 Java/Spring 백엔드 양성 과정 수료** (2023)
- 🏅 **정보처리산업기사** | **SQLD**
- 🧩 **프로그래머스 PCCE Lv4**

**🔥 Currently Focusing On**
- 대용량 트래픽에서의 **성능·데이터 정합성** — MSA 분리, Kafka 이벤트 기반 비동기 처리, Redis Cluster 집계를 직접 설계·검증합니다.
- **무중단 배포와 운영 안정성** — Kubernetes Blue/Green 배포, Prometheus·Grafana 모니터링으로 장애를 지표로 먼저 감지합니다.

---

<div align="center">
  <img src="./profile-3d-contrib/profile-night-view.svg" alt="3D Contributions" />
</div>

---

## 🛠️ Tech Stack

**Backend**

![Java](https://img.shields.io/badge/Java-007396?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![Spring Security](https://img.shields.io/badge/Spring_Security-6DB33F?style=for-the-badge&logo=springsecurity&logoColor=white)
![JPA](https://img.shields.io/badge/JPA-59666C?style=for-the-badge&logo=hibernate&logoColor=white)

**Messaging & Cache**

![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)

**Frontend**

![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=vuedotjs&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**Database**

![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

**Infra & DevOps**

![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![AWS EC2](https://img.shields.io/badge/AWS_EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white)
![AWS S3](https://img.shields.io/badge/AWS_S3-FF9900?style=for-the-badge&logo=amazons3&logoColor=white)

**Observability & Test**

![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![k6](https://img.shields.io/badge/k6-7D64FF?style=for-the-badge&logo=k6&logoColor=white)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)
![IntelliJ IDEA](https://img.shields.io/badge/IntelliJ_IDEA-000000?style=for-the-badge&logo=intellijidea&logoColor=white)

---

## 🚀 Projects

### 🏢 Nexus (SCM) — 프랜차이즈 공급망 주문관리 SaaS

> **한화시스템 BEYOND SW 캠프 최종(파이널) 프로젝트** | 팀 Fiveguys (5인) | 담당: **팀장 · 발주/통계/실시간 알림 백엔드 + 인프라**

[![Repo](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/beyond-sw-camp/be24-fin-Fiveguys-Nexus)
[![Service](https://img.shields.io/badge/Live-nexusscm.kro.kr-brightgreen?style=flat-square)](https://www.nexusscm.kro.kr)

**서비스 개요**

프랜차이즈 본사가 가맹점의 매출·재고·발주를 통합 관리하는 B2B 공급망 주문관리(SCM) 시스템.
실시간 알림(SSE)·통계 대시보드로 운영 가시성을 높이고, 통계 집계를 **모놀리식 동기 쿼리 → Kafka 이벤트 기반 MSA + Redis 집계**로 단계적으로 고도화.

`Spring Boot` `Kafka` `Redis Cluster` `Kubernetes` `SSE` `MariaDB` `Vue 3` `Nginx` `Prometheus/Grafana` `k6`

<br>

#### ⚡ 통계 집계 시스템 — 8단계 점진 고도화 (k6 동일 조건 측정)

| 지표 | 개선 전(모놀리식) | 개선 후(Redis Cluster) | 개선율 |
|:---:|:---:|:---:|:---:|
| **결제 응답 p95** | 4.0초 | **193 ms** | 🚀 약 **95% ↓** |
| **통계 응답 p95** | 1.97초 | **154 ms** | ⚡ 약 **92% ↓** |
| **처리량(동일 부하)** | 6,529건 | **18,587건** | 📈 약 **2.8배 ↑** |
| **정합성 회복 시간** | 약 40분 | **약 2분** | ⏱️ 약 **95% ↓** |

- **결제와 통계의 자원 경합 제거** — 통계를 MSA로 분리하고 결제 이벤트를 Kafka로 비동기 전달, 통계 조회 경로를 독립 서비스로 라우팅해 결제 p95를 14.9초 → 2.74초까지 회복
- **메시지 정합성** — `@TransactionalEventListener(AFTER_COMMIT)`로 커밋 후 발행 → 유령 메시지 4건 → 0건 / 멱등 Consumer(`ON DUPLICATE KEY UPDATE`)·DLQ로 누락 약 500건 → 0건
- **Redis Cluster(Master 3 + Replica 3) 직접 구축** — 자료구조(INCRBY·ZINCRBY·HSET) 사전 집계 + Pipeline으로 메시지당 왕복 15→2회, SPOF 해소
- **Kubernetes Blue/Green 무중단 배포** — 0.1초 간격 헬스 체크로 전환 검증(502·503 0건), Prometheus·Grafana로 가용성·Consumer Lag 모니터링

> 📖 트러블슈팅·아키텍처 진화 전 과정 → **[포트폴리오 상세 페이지](https://donghyunj.github.io/projects/nexus/)**

<br>

### 🚕 TalleMalle — 카풀 동승 모집 플랫폼

> **한화시스템 BEYOND SW 캠프 3차 프로젝트** | 팀 saraITne (5인) | 담당: **Recruit(모집) 도메인 백엔드 개발 & 성능 개선**

[![Repo](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/beyond-sw-camp/be24-3rd-saraITne-TalleMalle)
[![Wiki](https://img.shields.io/badge/Wiki-성능개선_문서-blue?style=flat-square&logo=github)](https://github.com/beyond-sw-camp/be24-3rd-saraITne-TalleMalle/wiki/5.-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-(Performance-Improvement)-%F0%9F%9A%80)
[![Service](https://img.shields.io/badge/Live-tallemalle.deatytim.com-brightgreen?style=flat-square)](https://tallemalle.deatytim.com)

**서비스 개요**

출발지·목적지가 유사한 승객들이 모집글을 통해 카풀을 구성하고 기사와 실시간 매칭되는 택시 동승 플랫폼.
WebSocket(STOMP) 기반 실시간 알림, JWT + OAuth2 인증, 토스 결제, AWS 인프라까지 구축.

`Spring Boot 3` `JPA/Hibernate` `Spring Security` `JWT` `OAuth2` `WebSocket/STOMP` `MariaDB` `AWS EC2·S3` `Docker` `nGrinder`

<br>

#### ⚡ 담당 기능 — Recruit(모집) 도메인 성능 개선

**🔥 Case 1. 메인 화면 모집글 조회 최적화 (N+1 & 카테시안 곱 해결)**

| 지표 | 개선 전 | 개선 후 | 개선율 |
|:---:|:---:|:---:|:---:|
| **평균 TPS** | 2.3 | **8.7** | 🚀 **+278% (3.8배 향상)** |
| **평균 응답시간** | 21,304 ms | **5,889 ms** | ⚡ **72% 단축** |

- **문제**: 1:N 관계에 다중 `JOIN FETCH` 적용 → 카테시안 곱 + Hibernate In-memory DISTINCT → 서버 메모리 과부하 & 약 29초 응답 지연
- **해결**:
  - 1:1 관계(`owner`) → `JOIN FETCH`로 단일 쿼리 처리
  - 1:N 관계(`participations`) → `@BatchSize(size=100)`로 N번 쿼리를 IN 1회로 묶어 카테시안 곱 제거
  - `Page` → `Slice` 변경으로 불필요한 `COUNT` 쿼리 제거
  - 지도 바운더리 좌표 기반 공간 필터링으로 DB 레벨 데이터 조기 차단

**🔒 Case 2. 동시성 제어 — 오버부킹 & 데드락 해결**

- **문제**: 6명 동시 참여 요청 시 Race Condition → 갱신 손실(Lost Update) → 오버부킹 & 데드락 → 500 에러
- **해결**: 비관적 락(`@Lock(PESSIMISTIC_WRITE)`, `SELECT FOR UPDATE`)으로 트랜잭션 직렬화
  - 데드락 & 갱신 손실 동시 해결, **데이터 정합성 100% 보장**
  - 정원 초과 스레드는 락 대기 후 최신 인원 데이터를 읽어 `RECRUIT_FULL` 예외 정상 반환

> 📖 쿼리 비교 · nGrinder 부하 테스트 전체 결과 → **[Wiki 성능 개선 문서](https://github.com/beyond-sw-camp/be24-3rd-saraITne-TalleMalle/wiki/5.-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-(Performance-Improvement)-%F0%9F%9A%80)**

---

## 📝 Blog

기술 학습 내용과 개발 트러블슈팅을 블로그에 꾸준히 기록하고 있습니다.

[![Tistory Blog](https://img.shields.io/badge/Tistory-donghyun0826-000000?style=for-the-badge&logo=tistory&logoColor=white)](https://donghyun0826.tistory.com/)

---

## 📫 Contact

<div align="center">
  <a href="https://donghyunj.github.io/">
    <img src="https://img.shields.io/badge/Portfolio-donghyunj.github.io-3b82f6?style=for-the-badge&logo=githubpages&logoColor=white"/>
  </a>
  &nbsp;
  <a href="https://donghyun0826.tistory.com/">
    <img src="https://img.shields.io/badge/Blog-donghyun0826.tistory.com-000000?style=for-the-badge&logo=tistory&logoColor=white"/>
  </a>
  &nbsp;
  <a href="https://github.com/DongHyunj">
    <img src="https://img.shields.io/badge/GitHub-DongHyunj-181717?style=for-the-badge&logo=github&logoColor=white"/>
  </a>
</div>

<br>

<div align="center">
  <i>⭐ 방문해 주셔서 감사합니다!</i>
</div>
