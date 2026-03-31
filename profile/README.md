<h1 align="center">Level Up Together</h1>

<p align="center">
  <strong>일상을 게임처럼, 함께 성장하는 라이프 RPG 플랫폼</strong>
</p>

<p align="center">
  <a href="https://dev.level-up-together.com:3000"><img src="https://img.shields.io/badge/Beta-Live_Demo-brightgreen?style=flat-square" alt="Beta"/></a>
  <img src="https://img.shields.io/badge/Status-In_Development-yellow?style=flat-square" alt="Status"/>
  <img src="https://img.shields.io/badge/Version-0.1.0-blue?style=flat-square" alt="Version"/>
  <img src="https://komarev.com/ghpvc/?username=Level-Up-Together&label=Visitors&style=flat-square" alt="Visitors"/>
</p>

---

## Demo

**Beta Version**: [https://dev.level-up-together.com:3000](https://dev.level-up-together.com:3000)

---

## About

**Level Up Together**는 일상생활을 RPG 게임처럼 즐길 수 있는 웹/앱 플랫폼입니다.

매일 반복되는 일상이 지루하게 느껴지시나요? 우리는 일상의 모든 활동을 **미션**으로 바꾸고, 목표 달성을 **경험치**로 보상하며, 함께 성장하는 **길드 시스템**을 통해 동기부여를 제공합니다.

---

## Core Features

| Feature | Description |
|---------|-------------|
| **Mission System** | 일상 목표를 미션으로 등록하고 완료 시 경험치 획득 |
| **Level & EXP** | 경험치를 쌓아 레벨업, 성장 과정을 시각화 |
| **Guild** | 관심사가 비슷한 사람들과 길드를 만들어 함께 도전 |
| **Achievement** | 특별한 도전 과제 달성 시 업적 뱃지 획득 |
| **Daily Check-in** | 매일 출석 체크로 보너스 보상 |
| **Feed & Social** | 피드를 통한 활동 공유, 친구 관리 |
| **Gamification** | 게임화 요소를 통한 지속적 동기부여 |

---

## Architecture

마이크로서비스 아키텍처 기반으로 설계된 풀스택 플랫폼입니다.

```
┌─────────────────────────────────────────────────────┐
│                     Clients                         │
│  Web (Next.js)  │  Admin (Next.js)  │  App (RN)    │
└────────┬────────────────┬───────────────┬───────────┘
         │                │               │
         ▼                ▼               ▼
┌─────────────────────────────────────────────────────┐
│                   API Gateway                       │
└────────┬────────────────┬───────────────┬───────────┘
         │                │               │
    ┌────▼────┐    ┌──────▼──────┐  ┌─────▼─────┐
    │ Product │    │   Admin     │  │  Other    │
    │ Service │    │   Service   │  │  Services │
    └────┬────┘    └──────┬──────┘  └─────┬─────┘
         │                │               │
         ▼                ▼               ▼
┌─────────────────────────────────────────────────────┐
│  Config Server  │  Service Discovery  │  Kafka      │
└─────────────────────────────────────────────────────┘
         │
         ▼
┌─────────────────────────────────────────────────────┐
│  PostgreSQL  │  Redis  │  AWS (Terraform)            │
└─────────────────────────────────────────────────────┘
```

---

## Tech Stack

**Backend**
![Java](https://img.shields.io/badge/Java_21-%23ED8B00.svg?style=flat&logo=openjdk&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot_3-%236DB33F.svg?style=flat&logo=spring-boot&logoColor=white)
![Spring Cloud](https://img.shields.io/badge/Spring_Cloud-%236DB33F.svg?style=flat&logo=spring&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL_(DGS)-%23E10098.svg?style=flat&logo=graphql&logoColor=white)
![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=flat&logo=apache-kafka&logoColor=white)

**Frontend**
![TypeScript](https://img.shields.io/badge/TypeScript-%23007ACC.svg?style=flat&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js_14-%23000000.svg?style=flat&logo=next.js&logoColor=white)
![React Native](https://img.shields.io/badge/React_Native-%2361DAFB.svg?style=flat&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-%2306B6D4.svg?style=flat&logo=tailwindcss&logoColor=white)

**Database & Cache**
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-%23316192.svg?style=flat&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-%23DC382D.svg?style=flat&logo=redis&logoColor=white)

**Infrastructure**
![AWS](https://img.shields.io/badge/AWS-%23232F3E.svg?style=flat&logo=amazonwebservices&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-%237B42BC.svg?style=flat&logo=terraform&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-%230db7ed.svg?style=flat&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-%232671E5.svg?style=flat&logo=githubactions&logoColor=white)

**Testing**
![Playwright](https://img.shields.io/badge/Playwright-%232EAD33.svg?style=flat&logo=playwright&logoColor=white)
![JUnit](https://img.shields.io/badge/JUnit_5-%2325A162.svg?style=flat&logo=junit5&logoColor=white)
![Pact](https://img.shields.io/badge/Pact-Contract_Testing-%23E03C8A.svg?style=flat)

---

## Repositories

### Backend Services

| Repository | Description | Stack |
|------------|-------------|-------|
| `level-up-together-platform` | 공유 플랫폼 라이브러리 (Kernel, Infra, Saga) | Java 21, Spring Boot 3, QueryDSL |
| `product-service` | 미션/상품 관리 마이크로서비스 | Java 21, Spring Boot 3, GraphQL (DGS) |
| `admin-service` | 어드민 백엔드 서비스 | Java 21, Spring Boot 3, GraphQL (DGS), Kafka |
| `config-server` | Spring Cloud Config 서버 | Java 21, Spring Cloud Config |
| `config-repository` | 환경별 설정 파일 저장소 | YAML |
| `service-discovery` | Netflix Eureka 서비스 디스커버리 | Java 21, Eureka Server |

### Frontend & Mobile

| Repository | Description | Stack |
|------------|-------------|-------|
| `level-up-together-frontend` | 사용자 웹 애플리케이션 | Next.js 14, TypeScript, Tailwind CSS |
| `level-up-together-admin-frontend` | 어드민 웹 패널 | Next.js 14, TypeScript, Tailwind CSS |
| `LevelUpTogetherReactNative` | iOS/Android 모바일 앱 | React Native 0.83, TypeScript |

### Infrastructure & Testing

| Repository | Description | Stack |
|------------|-------------|-------|
| `level-up-together-infra` | AWS 인프라 (IaC) | Terraform (EC2, RDS, ALB, CloudFront, Route53) |
| `level-up-together-sql` | DB 스키마 및 마이그레이션 | PostgreSQL |
| `e2e-test-bot` | E2E 테스트 자동화 봇 | TypeScript, Axios |

---

## Contributors

<a href="https://github.com/dev-minimalism">
  <img src="https://ghchart.rshah.org/dev-minimalism" alt="dev-minimalism's GitHub Contribution Graph"/>
</a>

---

## Contributing

현재 Private Side Project로 운영 중입니다. 기여에 관심이 있으시다면 Issue를 통해 문의해 주세요.

---

## Contact

<p>
  <a href="mailto:ceo@pink-spider.io"><img src="https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white"/></a>
</p>
