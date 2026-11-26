# РОЗДІЛ 2. ПРОЄКТУВАННЯ АРХІТЕКТУРИ СИСТЕМИ

## 2.1. Контекстне та контейнерне моделювання системи (C4 Model: Levels 1–2)

### C4 Level 1: System Context Diagram

```mermaid
C4Context
    title System Context Diagram — Fishing Analytics Platform

    Person(angler, "Рибалка", "Користувач, що фіксує сесії риболовлі та отримує ML-прогнози клювання")
    System(platform, "Fishing Analytics Platform", "Інтелектуальна аналітична платформа для збору телеметрії та прогнозування ефективності риболовлі")
    System_Ext(weather_api, "OpenWeatherMap API", "Зовнішній сервіс гідрометеорологічних даних")

    Rel(angler, platform, "Фіксує сесії, переглядає прогнози та аналітику", "HTTPS / REST")
    Rel(platform, weather_api, "Отримує актуальні погодні метрики", "HTTPS / REST (JSON)")