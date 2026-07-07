Observability Demo Service

Run locally

pip install -r requirements.txt
uvicorn app:app --host 0.0.0.0 --port 8000

Run with Docker

docker build -t obs-service .
docker run -p 8000:8000 obs-service

Deploy (pick one, all support a Dockerfile / single-file FastAPI app)


Render.com: New Web Service -> connect repo (or "Public Git Repo") -> it will
detect the Dockerfile, or set Start Command to
uvicorn app:app --host 0.0.0.0 --port $PORT
Railway.app: New Project -> Deploy from repo -> same start command as above
Fly.io: fly launch in this folder (it will pick up the Dockerfile), then fly deploy


After deploy, your base URL will look like:
https://<your-app>.onrender.com
https://<your-app>.up.railway.app
https://<your-app>.fly.dev

Endpoints:
GET /work?n=K
GET /metrics
GET /healthz
GET /logs/tail?limit=N
