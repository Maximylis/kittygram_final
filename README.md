# Kittygram

[![Production CI/CD](https://img.shields.io/github/actions/workflow/status/Maximylis/kittygram/main.yml?branch=main&style=flat-square)](https://github.com/Maximylis/kittygram/actions/workflows/main.yml)

Проект Kittygram - платформа для публикации фотографий котов с возможностью ставить лайки.

## О проекте

**Kittygram** — это веб-приложение для публикации фотографий котов с возможностью ставить лайки. Пользователи могут загружать изображения своих питомцев, просматривать ленту других пользователей и отмечать понравившиеся фото.

### Функциональность

- Регистрация и аутентификация пользователей
- Загрузка фотографий котов
- Просмотр ленты с фотографиями
- Постановка и отмена лайков
- Адаптивный интерфейс

## Технологический стек

### Backend
- **Django** (5.1.1) — основной фреймворк
- **Django REST Framework** (3.15.2) — API
- **Djoser** (2.3.1) — аутентификация
- **PostgreSQL** (13.10) — база данных
- **Psycopg2-binary** (2.9.11) — драйвер PostgreSQL
- **Pillow** (11.0.0) — работа с изображениями
- **Gunicorn** — WSGI сервер

### Тестирование и качество кода
- **Pytest** (8.3.3) — тестирование
- **Pytest-django** (4.9.0) — интеграция Django с pytest
- **Pytest-pythonpath** (0.7.3) — управление путями в тестах
- **Flake8** (7.3.0) — линтинг
- **Flake8-isort** (7.0.0) — проверка сортировки импортов
- **PyYAML** (6.0.1) — работа с YAML

### Frontend
- **React** (18) — библиотека для UI
- **JavaScript/JSX**

### Инфраструктура
- **Docker** & **Docker Compose** — контейнеризация
- **Nginx** — веб-сервер и reverse-proxy
- **GitHub Actions** — CI/CD

## Как заполнить .env

Создайте файл `.env` в корне проекта:
```
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=name_db
DB_USER=name_user
DB_PASSWORD=db_password
DB_HOST=db
DB_PORT=5432
SECRET_KEY=your-secret-key
DEBUG=True
```

## Быстрое развертывание Kittygram

### Требования на сервере
```
Установите Docker на сервере (одна команда)
curl -fsSL https://get.docker.com -o get-docker.sh && sudo sh get-docker.sh
```

### Настройка секретов в GitHub
Добавьте эти секреты:
```
DOCKERHUB_USERNAME: логин от Docker Hub
DOCKERHUB_PASSWORD: пароль от Docker Hub
HOST: IP или домен сервера
USER: имя пользователя
SSH_KEY: приватный SSH ключ
TELEGRAM_ID: ваш Telegram ID
TELEGRAM_TOKEN: токен бота
POSTGRES_PASSWORD: пароль для БД
```

### Настройка сервера
Подключитесь к серверу один раз через SSH и создайте папку:
```
ssh root@ваш-сервер
mkdir -p ~/kittygram
exit
```

### Создайте файл .env на сервере

### Всё! Деплой автоматический
При каждом пуше в ветку main workflow самостоятельно:

Запускает тесты
Собирает Docker образы
Пушит их на Docker Hub
Подключается к серверу по SSH
Обновляет и запускает контейнеры
Применяет миграции
Собирает статику
Присылает уведомление в Telegram

# Автор 

## Maximylis
    GitHub: @Maximylis