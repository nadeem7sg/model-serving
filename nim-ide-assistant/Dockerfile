# nim-ide-assistant: OpenAI-compatible API for IDE coding assistants (Cline/Cursor)
# backed by NIM. Build from the REPO ROOT (shared/ imports):
#   docker build -f nim-ide-assistant/Dockerfile -t nim-ide-assistant .
FROM python:3.11-slim

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

WORKDIR /app

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY . /app

WORKDIR /app/nim-ide-assistant

EXPOSE 8080

CMD ["python", "server.py"]
