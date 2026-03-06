# Project Configuration

## Before running the containers, make the following changes.

### 1. Update database host

## Open the file:

```
todolist/settings.py
```

## Find the `HOST` parameter in the database configuration and change:

```
"{ip}"
```

to:

```
"mysql"
```

## This allows the application container to connect to the MySQL container using Docker's internal network.


---


### 2. Update Dockerfile

## Remove the following line because the database is not available during the build stage:

```
RUN python manage.py migrate
```

## Update the `ENTRYPOINT` instruction to run database migrations and start the application:

```
ENTRYPOINT ["sh", "-c", "python manage.py migrate && python manage.py runserver 0.0.0.0:8080"]
```


---


# Running the Application

## Build and start the containers:

```bash
docker compose up -d
```

## This command will:

* Build the application image
* Start the MySQL database container
* Run database migrations
* Start the Django application


---


# Access the Application

## Open your browser and go to:

```
http://localhost:8080
```





# Stopping the Application

## To stop and remove the running containers:

```bash
docker compose down
```