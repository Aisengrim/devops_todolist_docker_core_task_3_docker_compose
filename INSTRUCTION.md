### Create docker-compose.yml

### Change line 69 "HOST" value in todolist/settings.py: "{ip}" >> "mysql"

### Delete "RUN python manage.py migrate" in Dockerfile;

### Change on "ENTRYPOINT ["sh", "-c", "python manage.py migrate && python manage.py runserver 0.0.0.0:8080"]" in Dockerfile;Expand commentComment on lines R1 to R4Resolved

### Run command docker-compose up -d

### Go to localhost:8080 in your browser

### Run command docker-compose down