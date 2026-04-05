# Kittygram
Проект, который дает возможность пользователям публиковать фотографии своих котов, их достижения и другию краткую информацию о них. Доступ предоставляется зарегистрированным пользователям

# Стек технологий
- Python 3.12
- Django 5.1
- Gunicorn 23.0
- Django Rest Framework 3.15
- Pillow 11.0
- PostgreSQL
- Docker
- Nginx


# Как запустить проект:
## 1 вариант(из готовых образов)
1. скачать docker-compose.production.yml
2. создать файл с переменными окружениями .env в корне проекта(пример заполнения в .env.example)
3. выполнить команду docker compose -f docker-compose.production.yml up
4. выполнить миграции 
- sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
- sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
- sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
5. Проверить доступность проекта по localhost

## 2 вариант(сборка проекта из исходников)
1. Клонировать репозиторий и перейти в него:

```
git clone https://github.com/SerjB45/kittygram_final.git
```

```
cd kittygram_backend
```

2. Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

3. Установить зависимости из файла requirements.txt:

```
pip install -r backend/requirements.txt
```

4. создать файл с переменными окружениями .env в корне проекта(пример заполнения в .env.example)

5. Запустите проект 
```
sudo docker compose up
```

6. выполнить миграции 
- sudo docker compose exec backend python manage.py migrate
- sudo docker compose exec backend python manage.py collectstatic
- sudo docker compose exec backend cp -r /app/collected_static/. /backend_static/static/

7. Проверить доступность проекта по localhost