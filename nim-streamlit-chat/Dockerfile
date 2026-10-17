# nim-streamlit-chat: Streamlit chat UI backed by a NIM OpenAI-compatible endpoint.
# Build from the REPO ROOT (shared/ is imported at runtime):
#   docker build -f nim-streamlit-chat/Dockerfile -t nim-streamlit-chat .
FROM python:3.11-slim

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

WORKDIR /app

# Repo-wide deps first (shared/ imports resolve from the repo root).
COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt streamlit

# The whole tree: shared/ + every app dir (single-context monorepo build).
COPY . /app

WORKDIR /app/nim-streamlit-chat

EXPOSE 8501

CMD ["streamlit", "run", "app.py", "--server.address=0.0.0.0", "--server.port=8501"]
