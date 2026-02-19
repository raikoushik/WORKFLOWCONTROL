# Workflow Controller

Single-page Workflow Controller dashboard (HTML/CSS/JS) ready for static hosting.

## Run locally

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Deploy with Docker

Build image:

```bash
docker build -t workflow-controller .
```

Run container:

```bash
docker run --rm -p 8080:80 workflow-controller
```

Then open `http://localhost:8080`.

## Project files

- `index.html`: app source.
- `Dockerfile`: production-ready static deployment via NGINX.
- `.dockerignore`: reduces image build context.
