# API для сервиса YaMDB
### Описание
Благодаря этому проекту можно оценивать фильмы, оставлять коментарии, отзывы.
### Технологии
Python 3.7
Django 2.2.16
Docker
GitHub Actions

### Запуск проекта в dev-режиме локально
- Установите и активируйте виртуальное окружение
- Запустите docker-compose командой
```
docker-compose up
``` 

- У вас развернётся проект, запущенный через Gunicorn с базой данных Postgres
- При развёртывании проекта, будут установлены зависимости а также запущен локальный сервер по адресу 127.0.0.1
- Далее в терминале, внутри установленного контейнера выполните миграции
``` 
docker-compose exec web python manage.py migrate
```
- Создайте супер-пользователя
``` 
docker-compose exec web python manage.py createsuperuser
```
- Соберите статику
```
docker-compose exec web python manage.py collectstatic
```
Если же после внесенных изменений нужно развернуть проект на боевом сервере,
выполните последовательно несколько команд из корневой папки проекта:
```
git add .
git commit -m <commit_name>
git push
```
Проект будет протестирован и запущен на боевом сервере по адресу 51.250.16.233

### Наслаждайтесь
### Авторы
Denis Razgonyaev

![WORKFLOW](https://github.com/lightning1701/yamdb_final/actions/workflows/yamdb_workflow.yaml/badge.svg)
