# Api YAMDb в Docker

### С чего начать:
1. Склонировать репозиторий

2. Выполнить в консоли (из папки с проектом) команду:
```
docker-compose up
```
и дождаться запуска двух контейнеров ```db_1 и web_1```

3. Перейти по адресу: ```http://localhost:8000/admin/``` и убедиться, что открылась страница с приглашением ввести данные админитратора для авторизации.
4. Для заполнения базы тестовыми данными перейти в контейнер ```web_1``` командой: ```docker exec -it <id контейнера> bash```; далее выполнить миграции командой: ```python manage.py migrate```.

5. В контейнере будет присутсвовать файл с тестовыми данными ```fixtures.json```. Выполить команду: ```python manage.py loaddata fixtures.json```

6. Данные успешно загруженый в базу. Переходим по адресу ```http://0.0.0.0:8000/admin/```, в ```username``` вводим ```testadmin```, а в ```password``` вводим ```12345678```

7. Наслаждаемся
