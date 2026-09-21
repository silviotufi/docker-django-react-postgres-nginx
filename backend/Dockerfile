
FROM python:3.9-slim-bookworm

WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

RUN apt-get update \
    && apt-get install -y \
        python3-dev \
        gcc \
        libffi-dev \
        libpq-dev \
        netcat-openbsd \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip

COPY ./requirements ./requirements

RUN pip install -r requirements/local.txt

COPY . .

ENTRYPOINT ["/usr/src/app/entrypoint.sh"]