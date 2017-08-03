#comment 
#Start from a base image
FROM Ubuntu 15.10
#install python
RUN apt-get update && apt-get upgrade && \ 
    apt-get install -y install python && \ 
    apt-get install -y python-pip
#working directory
RUN mkdir ussd/
WORKDIR ussd/
#install framework
COPY . ussd/
RUN cd ussd/ && pip install -y requirements.txt
CMD ["python","sms.py"]