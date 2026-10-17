# hf-webrtc-voice: WebRTC voice UI over vLLM (Flask + Socket.IO).
# Build from the REPO ROOT (shared/ imports):
#   docker build -f hf-webrtc-voice/Dockerfile -t hf-webrtc-voice .
FROM python:3.11-slim

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

WORKDIR /app

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY . /app

WORKDIR /app/hf-webrtc-voice

EXPOSE 5000

CMD ["python", "server.py"]
