# api_yamdb final

![workflow](https://github.com/maksim5652/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

Расширяемая база рецензий и отзывов. Предоставляет доступ через web-интерфейс и c использованием REST API

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

git clone https://github.com/maksim5652/api_yamdb.git

cd api_yamdb

Cоздать и активировать виртуальное окружение:

python3 -m venv venv
source venv/bin/activate
python3 -m pip install --upgrade pip setuptools pillow

Установить зависимости из файла requirements.txt:

pip install -r requirements.txt

Подготовить и выполнить миграции:

python3 manage.py makemigrations
python3 manage.py migrate

Запустить проект:

python3 manage.py runserver

### Шаблон наполенение env-файла:

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=maksim5652
DB_HOST=db
DB_PORT=5432
SECRET_KEY=p&l%385148kslhtyn^##a1)ilz@4zqj=rq&agdol^##zgl9(vs
ALLOWED_HOSTS=84.201.139.141,127.0.0.1,localhost
```
### Описание команд для запуска приложения в контейнерах
```
Выполняем миграции, создаем суперпользователя, подключаем статику:
```
```
docker-compose up -d --build
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```
### Требования:

1. Python 3.7 или выше
2. Django framework 2.2.16
3. Django Rest framework 3.12.4
4. requests 2.26.0
5. PyJWT 2.1.0
6. Django Rest framework simplejwt
7. django_filter

### Ссылка на проект:
http://84.201.139.141/admin/
http://84.201.139.141/redoc/