# **API Yatube**
### **Описание**

Это REST API для Yatube, через эту программу смогут работать мобильное приложение, чат бот. Через эту программу можно будет передавать любые данный в любое приложение


### **Стек**
![python version](https://img.shields.io/badge/Python-3.8-green)
![django version](https://img.shields.io/badge/Django-2.0.2-green)
![drf version](https://img.shields.io/badge/django_rest_framework-3.13-green)
![djoser](https://img.shields.io/badge/Djoser--green)

### Ообенности
* Создание пользователя.
* Получение токена аутентификации пользователя.
* Просмотр списка публикаций и информации о конкретной публикации.
* Размещение и изменение публикаций с возможностью указания группы.
* Просмотр всех комментариев к конкретной публикации и отдельного комментария.
* Размещение и редактирование комментариев.
* Просмотр списка существующих групп и информации об конкретной группе.
* Возможность подписаться на конкретного автора и увидеть список подписок.

### **Запуск проекта в dev-режиме**

1. Клонируйте репозиторий.

```
git clone git@github.com:Alex-Develepor/api_final_yatube.git
```


2. Установите и активируйте виртуальное окружение
```
python -m venv venv
``` 
```
source venv/Scripts/activate
```

3. Установите зависимости из файла requirements.txt
```
pip install -r requirements.txt
```
4. Создайте миграции:
```
python3 manage.py migrate
```
5. Запустите проект
```
python manage.py runserver
```

### Возможности

- Для создания публикации используем:
```
POST /api/v1/posts/
```
- Обновление публикации:

```
PUT /api/v1/posts/{id}/
```
- Удаление публикации:

```
DEL /api/v1/posts/{id}/
```
- Частичное обновление публикации:

```
PATCH /api/v1/posts/{id}/
```

- Получение доступа к эндпоинту ```/api/v1/follow/``` (подписки) доступен только для авторизованных пользователей.

### Добавить группу в проект нужно через админ панель Django:

после авторизации, переходим в раздел Groups и создаем группы.

```r
admin/
```

- Доступ авторизованным пользователем доступен по JWT-токену (Joser), который можно получить выполнив POST запрос по адресу:

```
POST /api/v1/jwt/create/
```

- Передав в body данные пользователя (например в postman):

```
{
"username": "string",
"password": "string"
}
```

- Полученный токен добавляем в headers (postman), после чего буду доступны все функции проекта:

```
Authorization: Bearer {your_token}
```

- Обновить JWT-токен:

```
POST /api/v1/jwt/refresh/
```

- Проверить JWT-токен:

```
POST /api/v1/jwt/verify/
```


### Автор проекта 
* [Дворецкий Александр](https://github.com/Alex-Develepor)
