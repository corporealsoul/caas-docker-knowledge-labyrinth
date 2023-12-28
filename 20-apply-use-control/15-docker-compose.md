### Try Docker Compose ,

**Address ,** https://docs.docker.com/compose/gettingstarted/


### Step 1: Define the application dependencies

**Create a directory for the project:**

`anup@ubuntu-22042-08:~$ mkdir composetest`

`anup@ubuntu-22042-08:~$ cd composetest`

**Create a file called app.py in your project directory and paste the following code in:**

`anup@ubuntu-22042-08:~/composetest$ nano app.py `

    import time
    
    import redis
    from flask import Flask
    
    app = Flask(__name__)
    cache = redis.Redis(host='redis', port=6379)
    
    def get_hit_count():
        retries = 5
        while True:
            try:
                return cache.incr('hits')
            except redis.exceptions.ConnectionError as exc:
                if retries == 0:
                    raise exc
                retries -= 1
                time.sleep(0.5)
    
    @app.route('/')
    def hello():
        count = get_hit_count()
        return 'Hello World! I have been seen {} times.\n'.format(count)

**Create another file called requirements.txt in your project directory and paste the following code in:**

`anup@ubuntu-22042-08:~/composetest$ nano requirements.txt`

    flask
    redis


### Step 2: Create a Dockerfile

`anup@ubuntu-22042-08:~/composetest$ nano Dockerfile`

    # syntax=docker/dockerfile:1
    FROM python:3.7-alpine
    WORKDIR /code
    ENV FLASK_APP=app.py
    ENV FLASK_RUN_HOST=0.0.0.0
    RUN apk add --no-cache gcc musl-dev linux-headers
    COPY requirements.txt requirements.txt
    RUN pip install -r requirements.txt
    EXPOSE 5000
    COPY . .
    CMD ["flask", "run"]


### Step 3: Define services in a Compose file

`anup@ubuntu-22042-08:~/composetest$ nano docker-compose.yml`

    services:
      web:
        build: .
        ports:
          - "8000:5000"
      redis:
        image: "redis:alpine"


### Step 4: Build and run your app with Compose

`anup@ubuntu-22042-08:~/composetest$ docker compose up`

**Browser :** http://192.168.56.8:8000/


### Step 5: Edit the Compose file to add a bind mount

`anup@ubuntu-22042-08:~/composetest$ nano docker-compose.yml `

    services:
      web:
        build: .
        ports:
          - "8000:5000"
        volumes:
          - .:/code
        environment:
          FLASK_DEBUG: "true"
      redis:
        image: "redis:alpine"


### Step 6: Re-build and run the app with Compose

`anup@ubuntu-22042-08:~/composetest$ docker compose up`

**Browser :** http://192.168.56.8:8000/ 


### Step 8: Experiment with some other commands

`anup@ubuntu-22042-08:~/composetest$ docker compose up -d`

`anup@ubuntu-22042-08:~/composetest$ docker compose ps`

`anup@ubuntu-22042-08:~/composetest$ docker compose run web env`

anup@ubuntu-22042-08:~/composetest$ docker compose stop


<br>
