# nim-webrtc-voice: NIM-backed WebRTC voice app (Flask + Socket.IO).
# Build from the REPO ROOT (shared/ imports):
#   docker build -f nim-webrtc-voice/Dockerfile -t nim-webrtc-voice .
FROM python:3.11-slim

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

WORKDIR /app

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt

COPY . /app

WORKDIR /app/nim-webrtc-voice

EXPOSE 5000

CMD ["python", "server.py"]
