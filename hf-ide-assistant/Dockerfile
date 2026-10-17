# hf-ide-assistant: OpenAI-compatible IDE assistant over vLLM (+ Switchyard
# multi-vLLM routing). Build from the REPO ROOT (shared/ imports):
#   docker build -f hf-ide-assistant/Dockerfile -t hf-ide-assistant .
FROM python:3.11-slim

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

WORKDIR /app

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY . /app

WORKDIR /app/hf-ide-assistant

EXPOSE 8080

CMD ["python", "server.py"]
