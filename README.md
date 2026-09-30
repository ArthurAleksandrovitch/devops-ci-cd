# 🚀 DevOps CI/CD — Учебные проекты

Коллекция учебных проектов по **DevOps, CI/CD, Docker, GitHub Actions и автоматизации сборки приложений**.

В каждом проекте настроены собственные процессы сборки, проверки и автоматизации доставки приложений.

---

# 📚 Проекты

|  № | Проект                                                        | Технологии            | Docker | CI/CD |
| -: | ------------------------------------------------------------- | --------------------- | :----: | :---: |
| 01 | 🧪 [my-first-cicd](https://github.com/ArthurAleksandrovitch/my-first-cicd) | CI/CD, GitHub Actions |    —   |   ✅   |
| 02 | 🐍 [my-python-app](https://github.com/ArthurAleksandrovitch/my-python-app) | Python                |    ✅   |   ✅   |
| 03 | 🟢 [my-node-app](https://github.com/ArthurAleksandrovitch/my-node-app)     | Node.js               |    ✅   |   ✅   |
| 04 | 🐹 [my-go-app](https://github.com/ArthurAleksandrovitch/my-go-app)         | Go                    |    ✅   |   ✅   |
| 05 | 🐘 [my-php-app](https://github.com/ArthurAleksandrovitch/my-php-app)       | PHP                   |    ✅   |   ✅   |
| 06 | ⚙️ [my-cpp-app](https://github.com/ArthurAleksandrovitch/my-cpp-app)       | C++                   |    ✅   |   ✅   |
| 07 | ☕ [hello-java](https://github.com/ArthurAleksandrovitch/hello-java)        | Java, Maven, JUnit    |    ✅   |   ✅   |
| 08 | 🦀 [my-rust-app](https://github.com/ArthurAleksandrovitch/my-rust-app)     | Rust, Cargo, Clippy   |    ✅   |   ✅   |

# 🚀 CD — Continuous Delivery / Deployment

Проекты, в которых автоматизирована доставка готового приложения или артефактов после успешной сборки и проверки.

|  № | Проект                                                                             | Технологии         |  Способ публикации |
| -: | ---------------------------------------------------------------------------------- | ------------------ | :----------------: |
| 01 | 🦀 [hello-rust](https://github.com/ArthurAleksandrovitch/hello-rust)               | Rust, Docker, GHCR |       📦 GHCR      |
| 02 | 🐹 [hello-go-releases](https://github.com/ArthurAleksandrovitch/hello-go-releases) | Go, GitHub Actions | 📦 GitHub Releases |
| 03 | 🐍 [hello-python](https://github.com/ArthurAleksandrovitch/hello-python) | Python, PyInstaller, GitHub Actions | 📦 GitHub Releases |
| 04 | 🟣 [hello-dotnet](https://github.com/ArthurAleksandrovitch/hello-dotnet) | C#, .NET 8, GitHub Actions | 📦 GitHub Releases |
---

# 🦀 CD 01 — hello-rust

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/hello-rust)**

Rust-приложение с автоматической сборкой Docker-образа и публикацией контейнера в **GitHub Container Registry (GHCR)**.

### Основные технологии

* Rust
* Cargo
* Rustfmt
* Clippy
* Docker
* Docker Buildx
* GitHub Actions
* GitHub Container Registry (GHCR)

### CI

Pipeline выполняет:

* проверку форматирования через Rustfmt;
* статический анализ через Clippy;
* запуск unit- и integration-тестов;
* release-сборку Rust-приложения.

### CD

После успешного выполнения CI на ветке `main`:

```text
GitHub
   ↓
GitHub Actions
   ↓
Rust Build & Test
   ↓
Docker Build
   ↓
GHCR
   ↓
📦 ghcr.io/arthuraleksandrovitch/hello-rust
```

Docker-образ автоматически публикуется в **GitHub Container Registry** и может быть получен командой:

```bash
docker pull ghcr.io/arthuraleksandrovitch/hello-rust:latest
```

---

# 🐹 CD 02 — hello-go-releases

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/hello-go-releases)**

Go-приложение с автоматической сборкой бинарников для нескольких платформ и публикацией готовых файлов в **GitHub Releases**.

### Основные технологии

* Go
* Go Modules
* GitHub Actions
* GitHub Releases
* Cross-platform builds

### CI

Pipeline выполняет:

* проверку форматирования;
* статический анализ;
* запуск тестов;
* сборку приложения.

### CD

После создания Git-тега версии:

```text
Git Tag
   ↓
GitHub Actions
   ↓
Go Build
   ↓
Cross-platform binaries
   ↓
GitHub Releases
   ↓
📦 Готовые бинарники
```

В релизах проекта публикуются готовые бинарники для нескольких платформ.

# 🐍 CD 03 — hello-python

🔗 [**Открыть репозиторий**](https://github.com/ArthurAleksandrovitch/hello-python)

Python-приложение с автоматической сборкой standalone-бинарников с помощью **PyInstaller** и публикацией готовых файлов в **GitHub Releases**.

### Основные технологии

* Python 3.12
* PyInstaller
* pytest
* Ruff
* GitHub Actions
* GitHub Releases

### CI

Pipeline выполняет:

* проверку качества кода через Ruff;
* проверку форматирования;
* запуск unit-тестов;
* сборку приложения через PyInstaller.

### CD

После создания Git-тега версии:

```text
Git Tag
   ↓
GitHub Actions
   ↓
Lint / Format
   ↓
Tests
   ↓
PyInstaller Build
   ↓
Platform Binaries
   ↓
GitHub Releases
   ↓
📦 Готовые исполняемые файлы
```

Для релиза `v0.2.0` публикуются готовые бинарники для:

* Linux x64
* macOS ARM64
* Windows x64

# 🟣 CD 04 — hello-dotnet

🔗 [**Открыть репозиторий**](https://github.com/ArthurAleksandrovitch/hello-dotnet)

C#/.NET-приложение с автоматической сборкой self-contained single-file бинарников для нескольких платформ и публикацией готовых файлов в **GitHub Releases**.

### Основные технологии

- C#
- .NET 8
- xUnit
- GitHub Actions
- GitHub Releases
- Cross-platform builds
- Self-contained deployment
- PublishSingleFile

### CI

Pipeline выполняет:

- восстановление NuGet-зависимостей;
- проверку форматирования через `dotnet format`;
- сборку проекта;
- запуск unit-тестов.

### CD

После создания Git-тега версии:

```text
Git Tag
   ↓
GitHub Actions
   ↓
.NET Build & Test
   ↓
dotnet publish
   ↓
Self-contained Single-file
   ↓
5 Platform Binaries
   ↓
GitHub Releases
   ↓
📦 Готовые исполняемые файлы
```

# 🧪 01 — my-first-cicd

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/my-first-cicd)**

Один из первых учебных проектов для знакомства с принципами **CI/CD и GitHub Actions**.

### Основные технологии

* Git
* GitHub
* GitHub Actions
* CI/CD

---

# 🐍 02 — my-python-app

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/my-python-app)**

Учебное Python-приложение с автоматизированной сборкой и проверками.

### Основные технологии

* Python
* Docker
* GitHub Actions

### CI

Pipeline автоматизирует проверку и сборку проекта.

---

# 🟢 03 — my-node-app

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/my-node-app)**

Node.js-приложение, контейнеризированное с помощью Docker.

### Основные технологии

* Node.js
* npm
* Docker
* GitHub Actions

### CI

Автоматическая установка зависимостей, проверка проекта и сборка Docker-образа.

---

# 🐹 04 — my-go-app

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/my-go-app)**

Учебное приложение на языке Go с автоматизированной сборкой.

### Основные технологии

* Go
* Go modules
* Docker
* GitHub Actions

### CI

Pipeline выполняет автоматическую сборку и проверку приложения.

---

# 🐘 05 — my-php-app

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/my-php-app)**

PHP-приложение, запускаемое внутри Docker-контейнера.

### Основные технологии

* PHP
* Docker
* GitHub Actions

### CI

Автоматическая проверка проекта и сборка Docker-образа.

---

# ⚙️ 06 — my-cpp-app

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/my-cpp-app)**

C++ приложение с автоматическим форматированием, сборкой и контейнеризацией.

### Основные технологии

* C++
* Clang
* Clang-Format
* Docker
* GitHub Actions

### CI

Pipeline включает:

* проверку форматирования;
* сборку проекта;
* тестирование;
* сборку Docker-образа.

---

# ☕ 07 — hello-java

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/hello-java)**

Java-приложение с Maven, JUnit 5 и multi-stage Docker-сборкой.

### Основные технологии

* Java 17
* Maven
* JUnit 5
* Maven Shade Plugin
* Docker
* GitHub Actions

### CI

Pipeline выполняет:

* настройку JDK 17;
* кэширование Maven-зависимостей;
* сборку проекта;
* запуск тестов;
* проверку Maven lifecycle;
* сборку Docker-образа.

---

# 🦀 08 — my-rust-app

🔗 **[Открыть репозиторий](https://github.com/ArthurAleksandrovitch/my-rust-app)**

Rust-приложение с проверкой форматирования, статическим анализом, тестированием и Docker-сборкой.

### Основные технологии

* Rust
* Cargo
* Rustfmt
* Clippy
* Docker
* GitHub Actions

### CI

Pipeline состоит из следующих этапов:

```text
┌─────────────────────┐
│   Lint & Format     │
│ Rustfmt + Clippy    │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│    Build & Test     │
│ Cargo Check         │
│ Debug Build         │
│ Release Build       │
│ Cargo Test          │
└──────────┬──────────┘
           ↓
┌─────────────────────┐
│    Docker Build     │
│ Build Image         │
│ Test Container      │
│ Upload Artifact     │
└─────────────────────┘
```

---

# 🛠️ Используемые технологии

### Languages

```text
Python
JavaScript / Node.js
Go
PHP
C++
Java
Rust
C#
```

### DevOps

```text
Git
GitHub
GitHub Actions
Docker
Docker BuildKit
CI/CD
```

### Build & Test

```text
npm
Go Modules
Maven
JUnit
Cargo
Clippy
Rustfmt
Clang
Clang-Format
.NET CLI
dotnet format
xUnit
```

---

# 🔄 Общая схема CI/CD

Большинство проектов используют следующий подход:

```text
          👨‍💻 Разработка
                 │
                 ▼
              Git
                 │
                 ▼
             GitHub
                 │
                 ▼
        ┌─────────────────┐
        │ GitHub Actions  │
        └────────┬────────┘
                 │
        ┌────────┴────────┐
        ▼                 ▼
     🔍 Check           🔨 Build
        │                 │
        └────────┬────────┘
                 ▼
              🧪 Test
                 │
                 ▼
          ┌───────────────┐
          │   Delivery    │
          └───────┬───────┘
                  │
          ┌───────┴────────┐
          ▼                ▼
     🐳 Docker         📦 Releases
          │                │
          ▼                ▼
        GHCR          GitHub Releases
```

---

# 📦 Контейнеризация

В Docker-проектах используются Dockerfile для создания воспроизводимого окружения.

В зависимости от проекта применяются:

* обычная Docker-сборка;
* multi-stage builds;
* минимальные runtime-образы;
* `.dockerignore`;
* запуск приложений от непривилегированного пользователя в проектах, где это настроено;
* автоматическая проверка Docker-образов в CI.

---

# ⚙️ GitHub Actions

GitHub Actions используется для автоматизации процессов разработки.

Типичные этапы pipeline:

```text
Checkout
   ↓
Setup Environment
   ↓
Lint / Format
   ↓
Build
   ↓
Test
   ↓
Delivery
   ↓
Artifact / Docker Image / Release
```

---

# 🎯 Цели обучения

В рамках этих проектов изучаются:

* основы DevOps;
* принцип CI/CD;
* работа с Git и GitHub;
* создание GitHub Actions workflows;
* автоматизация сборки;
* автоматическое тестирование;
* статический анализ кода;
* форматирование исходного кода;
* создание Docker-образов;
* multi-stage Docker builds;
* работа с Docker BuildKit;
* сохранение артефактов GitHub Actions;
* публикация Docker-образов в GHCR;
* публикация бинарных файлов в GitHub Releases.

---

# 📊 CI-проекты и технологии

| Проект        | Язык    | Docker | GitHub Actions | Тестирование |
| ------------- | ------- | :----: | :------------: | :----------: |
| my-first-cicd | —       |    —   |        ✅       |       —      |
| my-python-app | Python  |    ✅   |        ✅       |       ✅      |
| my-node-app   | Node.js |    ✅   |        ✅       |       ✅      |
| my-go-app     | Go      |    ✅   |        ✅       |       ✅      |
| my-php-app    | PHP     |    ✅   |        ✅       |       —      |
| my-cpp-app    | C++     |    ✅   |        ✅       |       ✅      |
| hello-java    | Java    |    ✅   |        ✅       |       ✅      |
| my-rust-app   | Rust    |    ✅   |        ✅       |       ✅      |

---

# 👨‍💻 Автор

**Артур Любин Александрович (ArthurAleksandrovitch)**

🔗 [GitHub](https://github.com/ArthurAleksandrovitch)

---

> 📌 Все проекты являются учебными работами и предназначены для изучения практик CI/CD, контейнеризации и автоматизации разработки.
