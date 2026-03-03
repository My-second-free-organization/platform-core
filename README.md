# FlowForge Platform Core

![CI](https://github.com/My-second-free-organization/platform-core/actions/workflows/ci.yml/badge.svg)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)

The core workflow engine powering FlowForge's business process automation platform. BPMN 2.0 compliant with complex event processing, rule evaluation, and distributed task orchestration.

## Tech Stack
- **Language:** Java 21 / Kotlin
- **Framework:** Spring Boot 3.2
- **Database:** PostgreSQL 16 + Redis 7
- **Messaging:** Apache Kafka
- **Build:** Gradle 8.x

## Quick Start
```bash
docker-compose up -d postgres redis kafka
./gradlew bootRun
./gradlew test
```

## Architecture
```
┌──────────────────────────────────────────┐
│            Platform Core                  │
├──────────┬─────────┬─────────┬──────────┤
│ Workflow │  Task   │  Rule   │  Event   │
│  Engine  │ Manager │ Engine  │ Processor│
├──────────┴─────────┴─────────┴──────────┤
│          Persistence (JPA/Redis)         │
├──────────────────────────────────────────┤
│       PostgreSQL / Redis / Kafka         │
└──────────────────────────────────────────┘
```
