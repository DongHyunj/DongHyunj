![Header](https://capsule-render.vercel.app/api?type=waving&color=0:141E30,100:2472fc&height=230&section=header&text=정동현&fontSize=52&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=병목을%20측정으로%20찾고,%20수치로%20증명하는%20백엔드%20엔지니어&descAlignY=56&descAlign=50&descSize=17)

<div align="center">

# 안녕하세요, 백엔드 엔지니어 정동현입니다 <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">

**Java · Spring** | **Kafka · Redis 이벤트 기반 아키텍처** | **Kubernetes 무중단 운영**

</div>

---

## <img src="https://media.giphy.com/media/QssGEmpkyEOhBCb7e1/giphy.gif" width="25"> About Me

막연한 **느리다 · 깨진다 · 멈춘다**를 측정 가능한 수치로 바꾸는 것에서 시작합니다.

k6 · nGrinder로 병목을 재현하고, 구조를 바꿔 해결한 뒤, **같은 조건에서 다시 측정해 증명합니다.**
모든 개선은 before / after 수치와 실측 스크린샷으로 남기고, 장애는 직접 재현해서 복구까지 검증합니다.

두 프로젝트의 결과물은 **자체 서버에 배포해 지금도 운영 중이며**, 모든 수치의 측정 과정과 스크린샷은 [포트폴리오](https://donghyunj.github.io)에 기록되어 있습니다.

---

## <img src="https://media.giphy.com/media/3oriNZoNvn73MZaFYk/giphy.gif" width="25"> Key Results - 모두 직접 측정한 수치입니다

<div align="center">

| 지표 | Before | After | 검증 방법 |
|:---|:---:|:---:|:---|
| **결제 응답 p95** | 3.5초 | **193ms** | k6 동일 조건 부하 (결제 100VU + 통계 5VU · 5분) |
| **동일 부하 처리량** | 6,529건 | **18,587건 (약 2.8배)** | k6 최종 런 (성공률 99.97%) |
| **메시지 정합성** | 유령 4건 · 누락 600여 건 | **0건** | 결제 성공 ↔ Kafka 발행 ↔ 통계 DB 적재 3자 건수 대조 |
| **장애 후 정합성 회복** | 약 40분 | **약 2분** | Consumer 처리량 21 → 150건/s 개선 후 Lag 소진 실측 |
| **무중단 배포** | - | **전환 중 실패 응답 0건** | Blue/Green 전환 순간 0.1초 폴링 관측 |
| **목록 조회 TPS** | 2.3 | **8.7 (약 3.8배)** | nGrinder 52VU |

</div>

---

## 🏆 Awards & Teamwork

- 🥇 **BEYOND SW 캠프 24기 우수수료생** - 수료생 20명 중 3명 선정 (한화시스템)
- 🎖️ **고용노동부 기관 평가 대표 수강생** - 기관 대표 기수에서 2인 선정

**Nexus 5인 팀 팀장 - 기여와 협업 방식**

<div align="center">

| 기여 | PR | 협업 방식 |
|:---:|:---:|:---:|
| **1,066 커밋** (팀 전체의 49%) | **247개 머지** | `[Feat] #이슈번호` 컨벤션 · 이슈 연동 feature 브랜치 전략 |

</div>

---

## 🚀 Projects

### 🏢 Nexus - 프랜차이즈 공급망 주문관리(SCM) SaaS

> 팀 Fiveguys **5인** · 2026.04 - 2026.06 | 담당 : **팀장 · 발주/통계/실시간 알림 백엔드 · 인프라 전반**

[![Live](https://img.shields.io/badge/Live_Demo-nexus.deatytim.com-2ea44f?style=flat-square&logo=googlechrome&logoColor=white)](https://nexus.deatytim.com)
[![Repo](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/beyond-sw-camp/be24-fin-Fiveguys-Nexus)
[![Detail](https://img.shields.io/badge/포트폴리오-트러블슈팅_상세-3b82f6?style=flat-square&logo=githubpages&logoColor=white)](https://donghyunj.github.io/projects/nexus/)

프랜차이즈 본사-가맹점의 매출·재고·발주를 통합 관리하는 B2B SCM. 통계 집계를 **모놀리식 동기 쿼리 → Kafka 이벤트 기반 MSA + Redis Cluster 사전 집계**로 단계적으로 고도화했습니다.

`Spring Boot` `Kafka` `Redis Cluster` `Kubernetes` `Jenkins` `MariaDB` `SSE` `Prometheus/Grafana` `k6`

- **결제·통계 자원 경합 제거** - 커넥션 풀 경합을 k6로 재현, MSA 분리·조회 라우팅 분리(피크 14.9초 → 2.74초) 후 Redis 사전 집계까지 적용해 결제 p95 최종 **3.5초 → 193ms**
- **메시지 정합성** - `AFTER_COMMIT` 발행으로 유령 메시지 **4건 → 0건**, 멱등 Consumer + DLQ로 누락 **600여 건 → 0건** (발행 = INSERT 건수 전수 일치 검증)
- **Redis Cluster(Master 3 · Replica 3) 직접 구축** - 목적별 자료구조 사전 집계 + Pipeline 왕복 15회 → 2회, Consumer 처리량 **21건/s → 150건/s**
- **K8s 5노드 Blue/Green 무중단 배포** - Jenkins+Kaniko 인클러스터 빌드, 전환 순간 0.1초 폴링으로 **실패 응답 0건 확인**

<details>
<summary><b>📖 아키텍처 진화 4단계 요약 펼쳐보기</b></summary>

<br>

1. **모놀리식 병목** - 결제·통계가 커넥션 풀 공유, 피크 시 결제 p95 14.9초까지 악화 → MSA 분리 + 라우팅 분리로 2.74초 회복
2. **Kafka 정합성** - 커밋 전 발행로 생긴 유령 메시지를 건수 대조로 검출, Outbox vs XA vs `AFTER_COMMIT` 비교 후 채택
3. **Redis 사전 집계** - 통계 6개 API p95 126~401ms → 94~133ms, 7일 TTL + ShedLock 새벽 배치로 실시간/장기 저장 이원화
4. **장애 복구 실험** - Kafka offset earliest 재생으로 통계 저장소 18,376건 재구축(18분, 중복·DLT 0건), Redis Cluster failover 재현

</details>

<br>

### 🚕 TalleMalle - 위치 기반 택시 동승 매칭 플랫폼

> 팀 saraITne **5인** · 2026.01 (4주) | 담당 : **모집(Recruit) 도메인 백엔드 전체**

[![Live](https://img.shields.io/badge/Live_Demo-tallemalle.deatytim.com-2ea44f?style=flat-square&logo=googlechrome&logoColor=white)](https://tallemalle.deatytim.com)
[![Repo](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square&logo=github)](https://github.com/beyond-sw-camp/be24-3rd-saraITne-TalleMalle)
[![Wiki](https://img.shields.io/badge/Wiki-성능_개선_문서-blue?style=flat-square&logo=github)](https://github.com/beyond-sw-camp/be24-3rd-saraITne-TalleMalle/wiki/5.-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-%28Performance-Improvement%29-%F0%9F%9A%80)

지도에서 같은 방향 사용자끼리 택시 동승을 매칭하는 서비스. 모집글 조회 → 동시 참여 → 상태 관리 → 실시간 브로드캐스트까지의 흐름을 설계·구현했습니다.

`Spring Boot 3` `JPA/Hibernate` `WebSocket/STOMP` `MariaDB` `AWS EC2·S3` `nGrinder`

- **N+1 · 카테시안 곱 하이브리드 해결** - owner는 `JOIN FETCH`, 컬렉션은 `@BatchSize(100)` IN절 + Slice 페이징 → TPS **2.3 → 8.7 (3.8배)**
- **동시 참여 오버부킹 차단** - read-modify-write 경쟁 상태를 비관적 쓰기 락으로 직렬화, 오버부킹·갱신 손실 **0건** (낙관적 락 배제 근거 포함)
- **정합성 있는 실시간 알림** - `AFTER_COMMIT` 이후에만 STOMP 브로드캐스트, 롤백된 상태가 전파되지 않도록 설계
- **지도 경계(Bounds) 조회 + 300ms 디바운싱** - 전국 전체 조회를 화면 영역 조회로 축소

---

## 🛠️ Tech Stack

**주력 - 문제를 해결할 때 쓰는 것들**

![Java](https://img.shields.io/badge/Java_17-007396?style=for-the-badge&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)
![JPA](https://img.shields.io/badge/Spring_Data_JPA-59666C?style=for-the-badge&logo=hibernate&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=for-the-badge&logo=mariadb&logoColor=white)
![Apache Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)

**직접 구축·운영해 본 것들**

![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white)
![AWS](https://img.shields.io/badge/AWS_EC2·S3-FF9900?style=for-the-badge&logo=amazonwebservices&logoColor=white)

**측정·검증 도구**

![k6](https://img.shields.io/badge/k6-7D64FF?style=for-the-badge&logo=k6&logoColor=white)
![nGrinder](https://img.shields.io/badge/nGrinder-00B4AB?style=for-the-badge&logo=naver&logoColor=white)
![Git](https://img.shields.io/badge/Git·GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

---

## <img src="https://media.giphy.com/media/VgCDAzcKvsR6OM0uWg/giphy.gif" width="30"> Current Focus

| 영역 | 내용 | 상태 |
|:---|:---|:---:|
| **라이브 데모 상시 운영** | Nexus · TalleMalle을 자체 서버에 배포, 도메인·TLS·모니터링 포함 운영 | ![Live](https://img.shields.io/badge/운영중-2ea44f?style=flat-square) |
| **포트폴리오 사이트** | [donghyunj.github.io](https://donghyunj.github.io) - 트러블슈팅 전 과정 상세 문서화 | ![Live](https://img.shields.io/badge/운영중-2ea44f?style=flat-square) |
| **기술 블로그** | 학습·트러블슈팅 기록 | ![Progress](https://img.shields.io/badge/진행중-3498db?style=flat-square) |

---

## 📜 Certifications

<div align="center">

![정보처리산업기사](https://img.shields.io/badge/정보처리산업기사-2024-1B6CA8?style=for-the-badge)
![SQLD](https://img.shields.io/badge/SQLD-2023-1B6CA8?style=for-the-badge)
![PCCE](https://img.shields.io/badge/프로그래머스_PCCE-Lv4-1B6CA8?style=for-the-badge)

</div>

---

## 📫 Contact

<div align="center">

[![Portfolio](https://img.shields.io/badge/Portfolio-donghyunj.github.io-3b82f6?style=for-the-badge&logo=githubpages&logoColor=white)](https://donghyunj.github.io/)
[![Blog](https://img.shields.io/badge/Blog-donghyun0826.tistory.com-000000?style=for-the-badge&logo=tistory&logoColor=white)](https://donghyun0826.tistory.com/)
[![Email](https://img.shields.io/badge/Email-deatytim@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:deatytim@gmail.com)

</div>

---

<div align="center">

### "측정하지 않으면 개선할 수 없고, 증명하지 못하면 개선한 것이 아닙니다"

<br>

![Profile Views](https://komarev.com/ghpvc/?username=DongHyunj&color=141E30&style=flat-square&label=Profile+Views)

</div>

![Footer](https://capsule-render.vercel.app/api?type=waving&color=0:2472fc,100:141E30&height=120&section=footer)
