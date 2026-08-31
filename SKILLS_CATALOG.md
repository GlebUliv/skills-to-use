# 📚 AI Agent Skills & Rulebook Catalog

Этот файл служит корневым индексом всех доступных директив и скиллов. Модель обращается к нему для маршрутизации и подключает полный текст конкретного скилла по требованию.

---

### 🛡️ 1. Архитектурная безопасность и предотвращение регрессий
* **`01-impact-pre-analysis.md`** — *Анализ рисков и радиуса поражения.* Запрещает менять файлы до формирования отчета о сайд-эффектах и одобрения плана.
* **`02-contract-api-protection.md`** — *Защита публичных контрактов.* Запрещает ломать публичные интерфейсы, сигнатуры API, DTO и схемы БД без миграции.
* **`05-surgical-edit-minimality.md`** — *Хирургическое редактирование.* Ограничивает объем изменений минимальным диффом, защищает краевые кейсы и существующую логику.
* **`09-security-injection-sanitization.md`** — *Защита от уязвимостей.* Запрещает неэкранированные SQL/NoSQL запросы, небезопасный HTML-рендер и утечки секретов.
* **`11-migration-zero-downtime-schema.md`** — *Безопасные миграции БД.* Паттерн Expand-and-Contract, неблокирующие индексы и предотвращение даунтайма.
* **`18-feature-flag-safe-rollout.md`** — *Поэтапный релиз.* Изоляция рискованной новой логики под тогглы фич-флагов с сохранением стабильного фоллбэка.

---

### 🧪 2. Тестирование, дебаг и наблюдаемость
* **`03-test-type-integrity.md`** — *Контроль тестов и типов.* Обязательная проверка тайпчекера/линтера и написание воспроизводящего теста перед фиксом.
* **`06-silent-regression-forensics.md`** — *Глубокий поиск скрытых регрессий.* Расследование багов, когда тесты зеленые, через вскрытие моков и слепых зон.
* **`07-silent-failure-logging-guard.md`** — *Защита от подавления ошибок.* Запрет пустых `catch`, сохранение stack trace и структурированные логи деградации.

---

### ⚡ 3. Качество кода, UX и производительность
* **`04-state-lifecycle-safety.md`** — *Безопасность состояния и хуков.* Изоляция сайд-эффектов, чистота стейта и обязательный teardown для подписок/таймеров.
* **`08-concurrency-race-condition-guard.md`** — *Защита от гонок и дублей.* Внедрение `AbortController`, дебаунс/троттлинг и идемпотентность действий.
* **`10-mobile-responsive-gesture-safety.md`** — *Мобильный и адаптивный UX.* Учет Safe Area, экранной клавиатуры и минимальных тач-зон (44x44+).
* **`12-no-hardcoded-strings-guard.md`** — *Запрет хардкода строк.* Вынос всех UI-текстов, сообщений и ошибок в централизованные словари/константы.
* **`17-performance-re-render-guard.md`** — *Оптимизация рендеров и CPU.* Мемоизация тяжелых расчетов, стабильные хэндлеры и индексация коллекций в `Map`/`Set`.
* **`19-type-soundness-no-any-guard.md`** — *Строгая типизация без `any`.* Запрет читерских кастов (`as any`), использование runtime narrowing и Zod-валидации.

---

### 🧠 4. Управление памятью, контекстом и процессами
* **`13-living-state-persistence.md`** — *Внешняя память проекта.* Фиксация ключевых инвариантов и прогресса в `.ai/CURRENT_STATE.md`.
* **`14-architecture-index-lookup.md`** — *Индекс структуры.* Навигация по слоям проекта через легковесный `.ai/ARCHITECTURE_INDEX.md`.
* **`15-architect-executor-decomposition.md`** — *Разделение ролей.* Планирование в markdown (Фаза 1) отдельно от пошагового написания кода (Фаза 2).
* **`16-session-compaction-handoff.md`** — *Передача контекста.* Генерация чекпоинта завершения и промпта для старта в новом чистом окне чата.
* **`20-pr-changelog-diff-summarizer.md`** — *Генератор PR.* Автоматическая сборка структурированного описания изменений по `git diff`.


- **Interactive UI / Forms / Telemetry:**
    * `.skills/21-analytics-telemetry-guard.md`
    * `.skills/23-a11y-accessibility-guard.md`
- **Network / Offline / Sync:**
    * `.skills/22-offline-network-resilience.md`
- **Environment / Infrastructure / CI:**
    * `.skills/24-env-bootstrap-dryrun.md`

- **Security / Auth / Data Access / Uploads:**
     * `.skills/09-security-injection-sanitization.md`
     * `.skills/25-auth-authorization-rbac-guard.md`
     * `.skills/26-secrets-anti-leak-entropy-guard.md`
     * `.skills/27-ssrf-path-traversal-defense.md`
     * `.skills/28-rate-limiting-dos-guard.md`