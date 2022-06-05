# api_yamdb final

https://github.com/maksim5652/yamdb_final/workflows/Django-app%20workflow/badge.svg

Расширяемая база рецензий и отзывов. Предоставляет доступ через web-интерфейс и c использованием REST API

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/maksim5652/api_yamdb.git
```

```
cd api_yamdb
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv venv
```

```
source venv/bin/activate
```

```
python3 -m pip install --upgrade pip setuptools pillow
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Подготовить и выполнить миграции:

```
python3 manage.py makemigrations
```

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Шаблон наполенение env-файла:

```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД 
```
### Описание команд для запуска приложения в контейнерах
```
docker-compose up -d --build
```
```
Выполняем миграции, создаем суперпользователя, подключаем статику:
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```
### Требования:

Python 3.7 или выше

Django framework 2.2.16

Django Rest framework 3.12.4

requests 2.26.0

PyJWT 2.1.0

Django Rest framework simplejwt

django_filter
