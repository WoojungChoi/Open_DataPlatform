FROM python:3.6
WORKDIR /app
ADD . /app

RUN apt-get update
RUN pip install -r requirements.txt
RUN apt-get install -y net-tools 
RUN apt-get install -y vim 
RUN apt-get install -y openssh-server
RUN echo "PermitRootLogin yes" >> /etc/ssh/sshd_config
RUN echo 'root:root' |chpasswd
#RUN service ssh start

WORKDIR /app/CSV2MARIA
RUN chmod 755 /app/CSV2MARIA/start.sh
RUN chmod 755 /app/CSV2MARIA/this_run.sh
CMD ["bash","/app/CSV2MARIA/start.sh"]
