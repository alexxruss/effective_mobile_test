# Тестовое задание Effective Mobile

## Описание

Проект состоит из двух сервисов:

- backend-приложение на Python
- nginx reverse proxy

nginx принимает HTTP-запросы на порт 80 и проксирует запросы в backend-сервис, работающий внутри Docker-сети на порту 8080.


## Структура проекта

```text
effective_mobile_test/
├── backend/
│   ├── Dockerfile
│   └── app.py
├── nginx/
│   └── nginx.conf
├── docker-compose.yml
├── README.md
└── .gitignore
```

## Используемые технологии

- Python 3.12
- Docker
- Docker Compose
- Nginx


## Запуск проекта

```bash
docker compose up --build
```

## Проверка работы

После запуска выполнить: 

```bash
curl http://localhost
```

Ожидаемый результат:

```text
Hello from Effective Mobile!
```

## Остановка проекта

```bash
docker compose down
```

## Архитектура 

```text
Client -> Nginx:80 -> Backend:8080
```

## Особенности реализации

- Backend-сервис недоступен с хоста
- Взаимодействие сервисов происходит через внутренюю Docker-сеть
- Nginx использует reverse proxy через proxy_pass
- Backend запускается от пользователя без root-прав
