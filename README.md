[![example workflow](https://github.com/Port-tf/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)](https://github.com/Port-tf/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg?event=push)
[![Redoc](https://img.shields.io/website?down_color=red&down_message=offline&label=Redoc&style=plastic&up_color=green&up_message=online&url=http%3A%2F%2F51.250.111.14%2Fredoc%2F)](http://51.250.111.14/redoc/)

# Проект YaMDb 
Cобирает отызвы пользьвателей на фильмы, музыку, книги (произведения)\
Пользователя могут публиковать отзывы на произведения, оценивать их (по шкале от 1 до 10), и обсуждать отзывы в комментариях.\
Средний рейтинг каждого произведения рассчитывается автоматически.\
Список категорий и жанров определен администратором, но может быть расширен в будущем.


### .env-файл
SECRET_KEY='' - укажите секретный ключ\
DB_ENGINE=django.db.backends.postgresql - укажите какая БД используться\
DB_NAME=postgres - название БД\
POSTGRES_USER=admin - Логин для подключения к БД\
POSTGRES_PASSWORD=123123 - Пароль для подключения к БД\
DB_HOST=db - Название контейнера\
DB_PORT=5432 - Порт для подключени к БД\
ALLOWED_HOSTS=* - Хосты
DEBUG=False - Режим дегаб


### Команды для запуска проекта
Запустите docker-compose командой
```
docker-compose up -d
```
Выполните миграции
```
docker-compose exec web python manage.py migrate
```
Создайте суперпользователя
```
docker-compose exec web python manage.py createsuperuser
```
Соберите статику
```
docker-compose exec web python manage.py collectstatic --no-input
```
Если у Вас уже есть наполненная база для этого проекта, можете ее скопировать
```
docker-compose exec web cp fixtures.json app/
docker-compose exec web python manage.py loaddata fixtures.json
```

##### Ссылка на документацию:
http://51.250.111.14//redoc/

##### Автор проекта: Игорь Шкода
