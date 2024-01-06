FROM python:3.8.12

WORKDIR /app

ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1


RUN apt-get clean && rm -rf /var/lib/apt/lists/*

COPY ./requirements /app/requirements
COPY ./requirements.txt /app/requirements.txt
COPY .env.dev /app/.env.dev

ADD . .

RUN pip install -U pip
RUN pip install -r requirements.txt
RUN python manage.py makemigrations
RUN python manage.py migrate
RUN python manage.py collectstatic --noinput -v3
