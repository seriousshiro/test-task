# 🚀 Go + Nginx + Docker Compose

Минималистичный проект, состоящий из:

- **Golang backend API**
- **Nginx reverse proxy**
- **Docker + Docker Compose**
  
---

  
## 📦 Архитектура

```text
Client(Host)
   |
   v
+----------+       +--------------------+
|  Nginx   | ----> |  Golang Backend    |
|  80:80   |       |  :8080             |
+----------+       +--------------------+
       Docker Compose Network
```
---

## 🌳 Структура проекта
```text
.
├── backend
│   ├── Dockerfile
│   └── main.go
├── nginx
│   └── nginx.conf
├── docker-compose.yml
├── .env
└── README.md
```
---

## 🚨 Требования

Для запуска проекта необходимо иметь установленный Docker и Docker Compose.

## Запуск проекта
1. Клонируйте этот репозиторий:
   ```bash
   git init
   git clone https://github.com/seriousshiro/test-task.git
   cd repo_folder
   ```
2. Соберите и запустите контейнеры
   ```bash
   docker compose up -d
   ```
3. Проверка контейнеров
   ```bash
   docker compose ps
   ```
---
   
## 💻⚙️ Проверка выполнения основной функции приложения
1. Сетевой запрос
  ```bash
  curl localhost:80
  ```
  **Ожидаемый ответ:**
  ```text
  Hello from Effective Mobile!
  ```
2. Проверка Health check'a
  ```bash
  curl localhost:80/health
  ```
  **Ожидаемый ответ:**
  ```text
  OK
  ```
---

## 🛠 Используемые технологии
* Golang backend - HTTP сервер
* Nginx - web reverse proxy
* Docker - контейнеризация
* Docker compose - оркестрация 
* Multistage build - оптимизация объема образа
* Healthcheck - оценка состояния контейнера 