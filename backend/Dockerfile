FROM python:3.12-slim

WORKDIR /app

RUN useradd -m appuser

COPY --chown=appuser:appuser app.py .

USER appuser

EXPOSE 8080

CMD ["python3", "app.py"]
