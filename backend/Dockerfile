FROM python:3.9-alpine

WORKDIR /app

COPY . /app

COPY requirements.txt ./

RUN apk add -u zlib-dev jpeg-dev gcc musl-dev

RUN apk add libpq-dev python3-dev

RUN pip3 install gunicorn

RUN pip3 install --no-cache-dir -r requirements.txt

#RUN pip3 install --upgrade django-cors-headers

COPY wsgi-entrypoint.sh /

ENTRYPOINT ["sh", "/wsgi-entrypoint.sh"]

