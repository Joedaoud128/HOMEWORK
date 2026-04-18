# Dockerized Flask App

A tiny Flask web application that returns a JSON response at the root endpoint.

## Deployed Application

https://homework-mvd4.onrender.com

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

## CI/CD Deployment Pipeline

Every push to the `main` branch triggers a GitHub Actions workflow that:

1. Builds a Docker image.
2. Pushes the image to Docker Hub.
3. Triggers a new deployment in Render.

Workflow file:

- `.github/workflows/deploy.yml`

### GitHub Secrets Required

Add the following repository secrets in GitHub (`Settings` -> `Secrets and variables` -> `Actions`):

- `DOCKERHUB_USERNAME`: your Docker Hub username
- `DOCKERHUB_TOKEN`: Docker Hub access token
- `RENDER_DEPLOY_HOOK_URL`: Render deploy hook URL for your service

### Notes

- Update the deployed app link above to your real Render URL.
- Keep Render configured to deploy from the Docker image pushed by this workflow.
