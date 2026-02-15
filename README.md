# Spring Boot 3 Observability with Grafana Stack

A comprehensive microservices observability demo showcasing distributed tracing, metrics collection, and log aggregation using Spring Boot 3 and the Grafana observability stack.

## Architecture

This project demonstrates a microservices architecture with two services:
- **Loan Service** - Main service that processes loan applications
- **Fraud Detection Service** - Validates loan requests for fraud patterns

All services are instrumented with Spring Boot 3 Observability features and monitored through the Grafana stack.

![img.png](img.png)

## Tech Stack

- **Spring Boot 3** - Microservices framework with native observability support
- **Grafana** - Visualization and dashboarding
- **Prometheus** - Metrics collection and storage
- **Tempo** - Distributed tracing backend
- **Loki** - Log aggregation system
- **MySQL** - Database for both services
- **Micrometer** - Application metrics instrumentation

## Prerequisites

- Java 17 or higher
- Maven 3.6+
- Docker & Docker Compose

## Getting Started

### 1. Start Infrastructure Services

```bash
docker compose up -d
```

This will start MySQL, Grafana, Prometheus, Tempo, and Loki.

### 2. Run Loan Service

```bash
cd loan-service
mvn spring-boot:run
```

### 3. Run Fraud Detection Service

```bash
cd fraud-detection-service
mvn spring-boot:run
```

## Access Points

| Service | URL | Description |
|---------|-----|-------------|
| Grafana | http://localhost:3000 | Dashboards and visualization |
| Prometheus | http://localhost:9090 | Metrics browser |
| Tempo | http://localhost:3110 | Trace queries |
| Loki | http://localhost:3100 | Log queries |

## Features

- ✅ Distributed tracing across microservices
- ✅ Metrics collection and visualization
- ✅ Centralized log aggregation
- ✅ Pre-configured Grafana dashboards
- ✅ Correlation between traces, metrics, and logs
- ✅ Service dependency mapping

## Project Structure

```
.
├── loan-service/              # Main loan processing service
├── fraud-detection-service/   # Fraud validation service
├── docker/                    # Configuration files for observability stack
│   ├── grafana/              # Grafana datasources and dashboards
│   ├── prometheus/           # Prometheus configuration
│   ├── tempo/                # Tempo configuration
│   └── mysql/                # Database initialization scripts
└── docker-compose.yml        # Orchestration for all infrastructure
```

## License

MIT
