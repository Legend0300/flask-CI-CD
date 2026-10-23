# flask-CI-CD

A small Flask app with a CI/CD pipeline on GitHub Actions.

## What the pipeline does

On every push to `main`, `.github/workflows/ci-cd.yml`:

1. Checks out the code and sets up Python 3.11.
2. Installs the dependencies from `requirements.txt`.
3. Runs the test suite with `pytest`.
4. Builds the Docker image `flask-lab-app`.

## The app

| Route | Returns |
|---|---|
| `/` | Home page |
| `/health` | `{"status": "ok"}` for health checks |
| `/data` | Sample data rendered as a page |

## Run it locally

```bash
docker compose up --build      # http://localhost:5000
```

or without Docker:

```bash
pip install -r requirements.txt
pytest -v
python app.py
```
