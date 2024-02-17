FROM python:3.10-alpine As builder


WORKDIR /app
COPY requirements.txt /app
RUN pip3 install -r requirements.txt

COPY . /app

CMD ["gunicorn","-k","geventwebsocket.gunicorn.workers.GeventWebSocketWorker","-w","4","--preload","-b","0.0.0.0","server:app"]

