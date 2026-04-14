# Dockerized Flask App

A tiny Flask web application that returns a JSON response at the root endpoint.

## Run without Docker

1. Install Python 3.12+.
2. Install dependencies:
   - `pip install -r requirements.txt`
3. Start app:
   - `python app.py`
4. Open `http://localhost:5000`.

## Build Docker image

```bash
docker build -t YOUR_DOCKERHUB_USERNAME/dockerized-flask-app:latest .
```

## Run Docker container

```bash
docker run --rm -p 5000:5000 YOUR_DOCKERHUB_USERNAME/dockerized-flask-app:latest
```

Then open `http://localhost:5000`.

## Push to Docker Hub

```bash
docker login
docker push YOUR_DOCKERHUB_USERNAME/dockerized-flask-app:latest
```

Docker Hub repository format is `username/repository`.
