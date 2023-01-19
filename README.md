# api_final

## Автор:
Svyatoslav [Svyat94] (https://github.com/Svyat94) Vinogradov


## Описание:
api final - это REST API для блог-платформы Yatube. Позволяет просматривать и отправлять посты, просматривать группы, подписываться на авторов.

## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Svyat94/api_final_yatube
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/Scripts/activate 
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```
## Примеры:
### Запрос JWT токена с использованием логина и пароля пользователя New_user:
```
  [POST].../api/v1/jwt/create/
  {
    "username": "New_user",
    "password": "qwerty1"
}
```
### Ответ:
```
{ 
    token ...
}
```
### Запрос с использованием токена пользователя New_user для публикации поста:
```
    [POST].../api/v1/posts/
    {
    "text": "Какой-то текст",
    "group": 1   
    }
```

### Ответ:
```
{
    "id": 2,
    "text": "Какой-то текст",
    "author": "New_user",
    "image": null,
    "group": 1,
    "pub_date": "2023-01-18T23:06:55.7894563Z"
}
```
### Запрос для просмотра групп анонимным пользователем:
```
    [GET].../api/v1/groups/
```
### Пример ответа:
```
    [
    {
        "id": 1,
        "title": "что-то важное1",
        "slug": "something",
        "description": "..."
    },
    {
        "id": 1,
        "title": "что-то важное2",
        "slug": "something2",
        "description": "...2"
    }
]
```

### Подробная документация в формате ReDoc доступна по адресу .../redoc/