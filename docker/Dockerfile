FROM python:3.9.1-slim
RUN apt-get update
# docker build нужно запускать из папки export-auditlogs-to-Splunk чтобы был правильный контекст при подборе include файлов
# пример docker build команды: 
# docker build -t s3-splunk-importer:latest -f ./docker/Dockerfile .
COPY /functions /app/functions
WORKDIR /app
RUN pip install --upgrade pip
RUN pip install -r functions/requirements.txt
CMD ["python3", "functions/main.py"]