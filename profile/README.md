<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00E5FF,100:1E3A8A&height=250&section=header&text=Level%20Up%20Together&fontSize=60&fontColor=ffffff&fontAlign=50&animation=fadeIn" width="100%" alt="Level Up Together Header" />

<br/>

## 🎮 Welcome to Level Up Together

**Level Up Together**는 일상을 RPG 게임처럼 즐기는 라이프 RPG 플랫폼입니다.<br/>
일상의 활동을 **미션**으로 바꾸고, 목표 달성을 **경험치**로 보상하며, **길드**에서 함께 성장합니다.

<br/>

<a href="https://www.level-up-together.com">
  <img src="https://img.shields.io/badge/Service-level--up--together.com-1E3A8A?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Service"/>
</a>
<a href="mailto:contact@pink-spider.io">
  <img src="https://img.shields.io/badge/Email-contact@pink--spider.io-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
</a>

<br/><br/>

<img src="https://img.shields.io/badge/Status-Beta-yellow?style=flat-square" alt="Status"/>
<img src="https://komarev.com/ghpvc/?username=Level-Up-Together&label=Visitors&style=flat-square" alt="Visitors"/>

<br/><br/>

</div>

---

### 📂 Recent Repositories

<!-- REPOS_START -->
| Repository | Description | Updated |
|:-----------|:------------|:--------|
| [product-service](https://github.com/Level-Up-Together/product-service) | 미션·상품 관리 백엔드 마이크로서비스 (Java 21, Spring Boot 3.4, GraphQL DGS) | 오늘 |
| [e2e-test-bot](https://github.com/Level-Up-Together/e2e-test-bot) | 실제 사용자처럼 API를 호출해 시스템 전체를 검증하는 E2E 테스트 봇 (TypeScript, 시뮬레이션 모드 지원) | 2일 전 |
<!-- REPOS_END -->

<br/>

---

### ✨ Core Features

| Feature | Description |
|:--|:--|
| **Mission System** | 일상 목표를 미션으로 등록하고, 완료하면 경험치를 얻습니다 |
| **Level & EXP** | 경험치를 쌓아 레벨업하고, 성장 과정을 한눈에 봅니다 |
| **Guild** | 관심사가 비슷한 사람들과 길드를 만들어 함께 도전합니다 |
| **Achievement** | 특별한 도전 과제를 달성하면 업적 뱃지를 받습니다 |
| **Daily Check-in** | 매일 출석 체크로 보너스 보상을 받습니다 |
| **Feed & Social** | 피드로 활동을 공유하고 친구를 관리합니다 |

<br/>

---

### 🏗️ Architecture

마이크로서비스 아키텍처로 설계한 풀스택 플랫폼입니다.

```text
┌─────────────────────────────────────────────────────────┐
│                        Clients                          │
│   Web (Next.js)   │   Admin (Next.js)   │   App (RN)    │
└─────────┬───────────────────┬───────────────────┬───────┘
          │                   │                   │
          ▼                   ▼                   ▼
┌───────────────────┐ ┌───────────────────┐       │
│    API Gateway    │ │ Admin API Gateway │◀──────┘
└─────────┬─────────┘ └─────────┬─────────┘
          │                     │
    ┌─────▼─────┐         ┌─────▼─────┐
    │  Product  │         │   Admin   │
    │  Service  │         │  Service  │
    └─────┬─────┘         └─────┬─────┘
          │                     │
          ▼                     ▼
┌─────────────────────────────────────────────────────────┐
│   Config Server   │   Service Discovery   │   Kafka     │
└─────────────────────────────────────────────────────────┘
          │
          ▼
┌─────────────────────────────────────────────────────────┐
│   PostgreSQL   │   Redis   │   AWS (Terraform)          │
└─────────────────────────────────────────────────────────┘
```

<br/>

---

### 🚀 Repositories

링크가 있는 저장소는 공개 저장소입니다. `코드` 형태로만 적힌 저장소는 비공개입니다.

#### ☕ Backend Services

| Repository | Description | Stack |
|:--|:--|:--|
| [product-service](https://github.com/Level-Up-Together/product-service) | 미션·상품 관리 마이크로서비스 | Java 21, Spring Boot 3.4, GraphQL (DGS) |
| `level-up-together-platform` | 공유 플랫폼 라이브러리 (Kernel, Infra, Saga) | Java 21, Spring Boot 3.4, QueryDSL |
| `admin-service` | 어드민 백엔드 서비스 | Java 21, Spring Boot 3.4, GraphQL (DGS), Kafka |
| `api-gateway` | 사용자 API 게이트웨이 | Spring Cloud Gateway, Redis |
| `admin-api-gateway` | 어드민 API 게이트웨이 | Spring Cloud Gateway, Redis |
| `config-server` | Spring Cloud Config 서버 | Java 21, Spring Cloud Config |
| `config-repository` | 환경별 설정 파일 저장소 | YAML |
| `service-discovery` | Netflix Eureka 서비스 디스커버리 | Java 21, Eureka Server |

#### 🖥️ Frontend & Mobile

| Repository | Description | Stack |
|:--|:--|:--|
| `level-up-together-frontend` | 사용자 웹 애플리케이션 | Next.js 14, TypeScript, Tailwind CSS |
| `level-up-together-admin-frontend` | 어드민 웹 패널 | Next.js 14, TypeScript, Tailwind CSS |
| `level-up-together-react-native` | iOS / Android 모바일 앱 | React Native 0.83, TypeScript |

#### 🛠️ Infrastructure · Data · Testing

| Repository | Description | Stack |
|:--|:--|:--|
| `level-up-together-infra` | AWS 인프라 (IaC) | Terraform (EC2, RDS, ALB, CloudFront, Route53) |
| `datagrip-project` | DB 스키마 및 SQL 스크립트 | PostgreSQL |
| [e2e-test-bot](https://github.com/Level-Up-Together/e2e-test-bot) | E2E 테스트 자동화 봇 | TypeScript, Axios |

<br/>

---

### 🛠️ Tech Stack

<div align="center">
  <img src="https://img.shields.io/badge/Java_21-007396?style=flat-square&logo=openjdk&logoColor=white" alt="Java 21"/>
  <img src="https://img.shields.io/badge/Spring_Boot_3-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot 3"/>
  <img src="https://img.shields.io/badge/Spring_Cloud-6DB33F?style=flat-square&logo=spring&logoColor=white" alt="Spring Cloud"/>
  <img src="https://img.shields.io/badge/GraphQL_(DGS)-E10098?style=flat-square&logo=graphql&logoColor=white" alt="GraphQL DGS"/>
  <img src="https://img.shields.io/badge/Apache_Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white" alt="Apache Kafka"/>
  <br/>
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Next.js_14-000000?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js 14"/>
  <img src="https://img.shields.io/badge/React_Native-61DAFB?style=flat-square&logo=react&logoColor=black" alt="React Native"/>
  <img src="https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white" alt="Tailwind CSS"/>
  <br/>
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis"/>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white" alt="AWS"/>
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white" alt="Terraform"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=githubactions&logoColor=white" alt="GitHub Actions"/>
  <br/>
  <img src="https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white" alt="Playwright"/>
  <img src="https://img.shields.io/badge/JUnit_5-25A162?style=flat-square&logo=junit5&logoColor=white" alt="JUnit 5"/>
  <img src="https://img.shields.io/badge/Pact-Contract_Testing-E03C8A?style=flat-square" alt="Pact"/>
</div>

<br/>

---

### 📊 GitHub Metrics

<p align="center">
  <img src="https://raw.githubusercontent.com/Level-Up-Together/.github/main/github-metrics.svg" alt="Level Up Together GitHub Metrics" />
</p>

---

<div align="center">
  <p>👀 <b>Contact & Support</b></p>
  <p>현재 비공개 사이드 프로젝트로 운영 중입니다. 협업·제휴 문의는 이메일로, 공개 저장소의 코드 질문은 해당 저장소의 이슈(Issue)로 남겨주세요.</p>
  <a href="mailto:contact@pink-spider.io">
    <img src="https://img.shields.io/badge/Email-contact@pink--spider.io-1E3A8A?style=flat-square&logo=gmail&logoColor=white" alt="Email"/>
  </a>
</div>
