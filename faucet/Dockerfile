FROM python:3.6
ENV PYTHONUNBUFFERED 1
RUN mkdir /config
RUN mkdir /src
RUN git clone -b dev https://github.com/u-transnet/utschool-faucet /src
ADD /config/project/faucet/* /src/faucet/configs/
ADD /config/project/settings.py /src/settings/local.py
RUN pip install gunicorn
RUN pip install psycopg2
WORKDIR /src
RUN python3 create_pip_requirements.py
RUN pip install -r requirements.txt