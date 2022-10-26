FROM python:3.7-slim
WORKDIR /app
COPY . .
RUN pip3 install --upgrade pip
RUN apt-get update \
    && apt-get -y install libpq-dev gcc \
    && pip3 install psycopg2
RUN pip3 install -r requirements.txt --no-cache-dir
CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000"]
