# hf-streamlit-chat: Streamlit chat UI over vLLM-served HF weights.
# Build from the REPO ROOT (shared/ is imported at runtime):
#   docker build -f hf-streamlit-chat/Dockerfile -t hf-streamlit-chat .
FROM python:3.11-slim

ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1

WORKDIR /app

COPY requirements.txt /tmp/requirements.txt
RUN pip install --no-cache-dir -r /tmp/requirements.txt streamlit

COPY . /app

WORKDIR /app/hf-streamlit-chat

EXPOSE 8501

CMD ["streamlit", "run", "app.py", "--server.address=0.0.0.0", "--server.port=8501"]
