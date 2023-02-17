FROM python:3.11

# Create the user that will run the app
RUN adduser --disabled-password --gecos '' ml-api-user

WORKDIR /opt/ML_Deploy_MSCD/section-08-deploying-with-containers/house-prices-api

ARG PIP_EXTRA_INDEX_URL

# Install requirements, including from Gemfury
RUN apt-get update
RUN apt-get install -y git

#ADD ./house-prices-api /opt/house-prices-api/
RUN cd /opt
RUN git clone https://github.com/marcyhelen/ML_Deploy_MSCD.git
#RUN cd /opt/ML_Deploy_MSCD/section-08-deploying-with-containers

RUN pip install --upgrade pip
#RUN pip install -r /opt/house-prices-api/requirements.txt
RUN ls
RUN pip install -r /opt/ML_Deploy_MSCD/section-08-deploying-with-containers/house-prices-api/requirements.txt


RUN chmod +x /opt/ML_Deploy_MSCD/section-08-deploying-with-containers/house-prices-api/run.sh
RUN chown -R ml-api-user:ml-api-user ./

USER ml-api-user

EXPOSE 8001

CMD ["bash", "./run.sh"]
