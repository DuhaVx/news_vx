# News VX

Веб-приложение на Django для публикации новостей. Использует SQLite и менеджер пакетов uv.

## Стек
- Python 3.11+
- Django 5
- SQLite
- uv (управление зависимостями и виртуальным окружением)

## Быстрый старт
1) Установите [uv](https://github.com/astral-sh/uv#installation) при необходимости.
2) Создайте виртуальное окружение и установите зависимости:
```
cd C:\Users\kashk\OneDrive\Documents\repo\news_vx
uv venv
uv sync
```
3) Скопируйте файл `env.example` в `.env` и задайте значения:
```
SECRET_KEY=случайная_строка
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
```
4) Примените миграции и создайте суперпользователя:
```
uv run python manage.py migrate
uv run python manage.py createsuperuser
```
5) Запустите сервер разработки:
```
uv run python manage.py runserver
```
Приложение будет доступно на `http://127.0.0.1:8000/`. Админка — на `http://127.0.0.1:8000/admin/`.

## Основные возможности
- Админка Django для управления новостями.
- Публичный список новостей с фильтрацией по заголовку.
- Страница детального просмотра новости.
- Классовые представления, базовая стилизация в `templates/base.html`.

## Структура окружения
- Конфиденциальные значения хранятся в `.env` (не коммитится).
- Настройки загружаются через `django-environ` в `config/settings.py`.

## Полезные команды
- Формирование миграций: `uv run python manage.py makemigrations`
- Применение миграций: `uv run python manage.py migrate`
- Создание суперпользователя: `uv run python manage.py createsuperuser`
- Запуск дев-сервера: `uv run python manage.py runserver`