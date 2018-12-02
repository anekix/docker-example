
FROM ubuntu:18.04
RUN apt-get update && apt-get install -y python python-dev python3.6 python3.6-dev python-pip
RUN pip install setuptools pip --upgrade --force-reinstall
RUN apt-get update && apt-get install -y gcc
COPY . /usr/src/app

RUN apt-get install -y uwsgi
WORKDIR /usr/src/app

COPY ./app_uwsgi.ini /etc/uwsgi/apps-enabled/app_uwsgi.ini

RUN pip install -r requirements.txt
#CMD ["python", "app.py"]
CMD ["uwsgi" , "--ini", "/usr/src/app/app_uwsgi.ini"]
