# Практическая работа № 2 — Знакомство с Docker

## Описание проекта

Практическая работа посвящена изучению экосистемы Docker: созданию образов, запуску контейнеров, оптимизации сборки, настройке проверки здоровья и управлению версиями образов.

В качестве приложения используется Python-сервис на FastAPI, запускаемый с помощью Uvicorn.

## Персональные параметры

| Параметр | Значение |
|---|---|
| Номер ИСУ| 466519 |
| Персональный порт | 5449 |
| Персональный префикс | lishchuk |
| Секретный ключ | secret19lishchuk |


## Структура проекта

```text
assist-py/
├── app/
│   └── main.py
├── requirements.txt
├── Dockerfile
├── Dockerfile.optimized
├── .dockerignore
└── README.md
```
## Запуск приложения

### 1. Сборка Docker-образа

```bash
docker build -t lishchuk-assistant:final -f Dockerfile.optimized .
```

### 2. Запуск контейнера
```bash
docker run -d \
  --name lishchuk-assistant-final \
  -p 5449:5449 \
  -e APP_OWNER=lishchuk \
  -e APP_SECRET=secret19lishchuk \
  lishchuk-assistant:final
