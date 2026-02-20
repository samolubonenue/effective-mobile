# Todo API

REST API для управления задачами на Laravel.

## Требования

- PHP 8.1+
- Composer

## Установка

```bash
git clone <repository-url>
cd todo-api
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
```

## Запуск

```bash
php artisan serve
```

Сервер будет доступен по адресу: http://127.0.0.1:8000

## API Endpoints

### Получить все задачи

```
GET /api/tasks
```

### Получить задачу по ID

```
GET /api/tasks/{id}
```

### Создать задачу

```
POST /api/tasks
Content-Type: application/json

{
    "title": "Название задачи",
    "description": "Описание задачи",
    "status": "pending"
}
```

Поля:
- `title` (обязательное) - название задачи
- `description` (опциональное) - описание
- `status` (опциональное) - статус: pending, in_progress, completed

### Обновить задачу

```
PUT /api/tasks/{id}
Content-Type: application/json

{
    "title": "Новое название",
    "status": "completed"
}
```

### Удалить задачу

```
DELETE /api/tasks/{id}
```

## База данных

По умолчанию используется SQLite. Файл базы данных: `database/database.sqlite`
