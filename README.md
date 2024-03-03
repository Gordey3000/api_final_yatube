## Проект API для социальной сети Yatube
### Описание:
Незарегистрированные пользователи могут просматривать посты, комментарии, группы проекта. Для зарегистрированных пользователей доступны подписка на понравившихся авторов, добавление постов, комментариев, а также удаление и редактирование собственных публикаций и комментариев.

### В API доступны следующие эндпоинты:
http://127.0.0.1:8000/api/v1/posts/ При GET-запросе на этот эндпоинт будет получен список публикаций (при указании параметров limit и offset выдача будет осуществляться с пагинацией). При POST-запросе буден создана новая публикация. Анонимные POST-запросы запрещены.

http://127.0.0.1:8000/api/v1/posts/{id}/ GET-запрос позволяет поучить публикацию по id. PUT- и PATCH-запросы позволяют редактировать публикацию. DELETE-запрос удаляет публикацию. Анонимные PUT-, PATCH- и DELETE-запросы запрещены. Обновить и удалить публикацию может только автор публикации.

http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/ При GET-запросе будут получены все комментарии к публикации. При POST-запросе будет создан новый комментарий.

http://127.0.0.1:8000/api/v1/posts/{post_id}/comments/{id}/ При GET-запросе будет получен комментарий по id. При PATCH- и PUT-запросах комментарий будет отредактирован. DELETE-запрос удалит комментарий. Анонимные PUT-, PATCH- и DELETE-запросы запрещены.

http://127.0.0.1:8000/api/v1/groups/ При GET-запросе будет получен список сообществ.

http://127.0.0.1:8000/api/v1/groups/{id}/ При GET-запросе будет получена информация о сообществе по id.

http://127.0.0.1:8000/api/v1/follow/ При GET-запросе будет получен список всех подписок пользователя, сделавшего запрос. При POST-запросе будет создана новая подписка пользователя, сделавшего запрос, на пользователя, переданного в теле запроса. Анонимные POST-запросы запрещены.

http://127.0.0.1:8000/api/v1/jwt/create/ Получение JWT-токена.

http://127.0.0.1:8000/api/v1/jwt/refresh/ Обновление JWT-токена.

http://127.0.0.1:8000/api/v1/jwt/verify/ Проверка JWT-токена.
### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Gordey3000/api_final_yatube
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python -m venv env
```

```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install -U pip
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
