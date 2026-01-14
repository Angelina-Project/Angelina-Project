<img src="./docs/logo-readme.png" style="max-width:256px;">

---
## `ANGELINA TRADING PLATFORM`

### `powered by SCORPION Engine`

---
**Автоматизированная B2C платформа для торговли и анализа на фондовом рынке**

---
## Общая концепция

Angelina Project — это **пользовательская оболочка** (UI, управление, уведомления, админка) над отдельным высокопроизводительным движком — **Scorpion Engine**, который отвечает за торговые стратегии, анализ и риск-менеджмент.

Таким образом, проект состоит из **двух связанных частей**:

1. **Angelina Project** — пользовательский сервис (B2C):
    - UI (веб-интерфейс + Telegram)
    - работа с пользователями, счетами и подписками
    - администрирование и управление стратегиями
    - уведомления и отчётность

2. **Scorpion Engine** — торговый движок (B2B/B2C):
    - технический и фундаментальный анализ
    - автоматизация стратегий
    - исполнение сделок
    - управление подписками на автоматическую торговлю
    - риск-менеджмент

---

## Основной функционал

### Пользовательские возможности (Core):
- Регистрация и вход через Keycloak
- Подключение брокерского счёта через API-ключ
- Подписка на торговые стратегии
- Автоматизация сделок по выбранной стратегии
- Получение сигналов и уведомлений (Telegram, Email)
- Просмотр котировок и торговой статистики
- Асинхронная генерация отчётов (XLSX)

### Административные возможности (Backoffice):
- Управление ролями пользователей
- Модерация стратегий и аналитиков
- Управление сущностями (счета, подписки, сделки)
- Аудит действий

---

## Архитектура

### Angelina Project (оболочка)
- **UI-MVC** — временный UI на Thymeleaf
- **Telegram-bot** — уведомления и базовые действия
- **API Gateway** — единая точка входа для backend (Spring Cloud Gateway)
- **Core-service** — работа с пользователями, счетами, подписками
- **Backoffice-service** — управление платформой и стратегиями
- **Notification-service** — отправка уведомлений (RabbitMQ → Telegram/Email)
- **Report-service** — асинхронная генерация торговых отчётов

**Инфраструктура:**
- Keycloak — аутентификация и авторизация (OAuth2, JWT)
- PostgreSQL — основная база данных
- Redis — кэш (котировки)
- RabbitMQ — брокер событий (уведомления, отчёты)

---

---

<img src="./docs/scorpion-logo.png" style="max-width:192px; width:192px;">

### Scorpion Engine (движок)
- **Scorpion API** — фасад и API движка
- **Dronehive-service** — исполнение стратегий, управление потоками-дронами
- **Smart-service** — технический анализ и генерация сигналов
- **Analytical-service** — фундаментальный анализ (Spring AI, Ollama) *(будущий сервис)*
- **Risk-management-service** — управление рисками *(будущий сервис)*

**Интеграции:**
- Stock Exchange APIs — рыночные данные (REST/WebSocket/gRPC)
- Broker APIs — совершение сделок (REST/WebSocket/gRPC)
- PostgreSQL — основная база данных
- Redis — кэш (критерии, анализ, подписки)

---

## Коммуникации

| Откуда             | Куда                | Протокол    |
|--------------------|---------------------|-------------|
| UI / Telegram      | API Gateway         | REST        |
| API Gateway        | Keycloak            | OAuth2      |
| API Gateway        | Core / Backoffice   | REST        |
| Core-service       | Scorpion API        | REST        |
| Backoffice-service | Scorpion API        | REST        |
| Scorpion API       | Dronehive / Smart   | gRPC        |
| Dronehive          | Brokers / Exchanges | REST / gRPC |
| Smart-service      | Exchanges           | REST / gRPC |
| Notification       | Telegram / Email    | RabbitMQ    |
| Report-service     | Core-service        | RabbitMQ    |

---

## Технологии

- **Java 21, Spring Boot, Spring WebFlux, Spring Cloud**
- **PostgreSQL, TimescaleDB, Redis** - хранение данных
- **Apache Kafka** - event-driving
- **gRPC, REST API, WebSockets**
- **Keycloak (OAuth2, JWT)**
- **Micrometer, Prometheus, Loki, Grafana** — мониторинг
- **DL4J, Spring AI, Ollama** — анализ и ML
- **Thymeleaf** — временный UI
- **Telegram API** — Телеграм-бот

---

## Запуск

### Минимальные требования
- JDK 21
- Gradle
- Docker Compose (Postgres, TimescaleDB, Redis, Keycloak, RabbitMQ, Ollama, Loki, Grafana, Prometheus)

### Сборка
```bash
./mvnw clean package
//TODO
```

### Запуск через Docker Compose (dev)

```bash
docker-compose up -d
//TODO
```

---


Документация и схемы находятся здесь:

- [Архитектура (PDF + диаграммы)](./docs/architecture.md)
- [Structurizr DSL](./docs/dsl/workspace.dsl)
- [Диаграммы (PNG)](./docs/png/)
- [Презентация (PDF)](./docs/pdf/architecture.pdf)


---
## Будущие планы

* Маркетплейс стратегий с рейтингами
* Расширенный фундаментальный анализ (Analytical-service)
* Риск-менеджмент (Risk-service)
* Push-уведомления и моб. клиент
* Переписывание UI на React/Vue
* B2B интеграция: использование Scorpion Engine как отдельного продукта

---
**Разработка и архитектура:** ***Stanislav Kuprienko*** ©
---

### ® Angelina ###

<img src="./docs/character.png" style="max-width: 256px; width=256px;">

