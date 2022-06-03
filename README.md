# API Yatube
API для сайта yatube

Доступны для работы через API:
- посты
- группы
- комментарии
- подписки
- токены

## Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/enjoywg/api_final_yatube
```
```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:
```
python3 -m venv venv
```
```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```

Выполнить миграции:
```
python3 manage.py migrate
```

Запустить проект:
```
python3 manage.py runserver
```

## Примеры запросов к API
### Получение публикаций
```
GET /api/v1/posts/
```

### Создание публикации
```
POST /api/v1/posts/
```
Request Body schema
```
{
    text (required): string (текст публикации)
    image: string or null <binary>
    group: integer or null (id сообщества)
}
```

### Подписки
```
GET /api/v1/follow/
```

### Получение комментариев
```
GET /api/v1/posts/{post_id}/comments/
```
