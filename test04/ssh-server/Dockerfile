FROM ubuntu:16.04
MAINTAINER Sven Dowideit <SvenDowideit@docker.com>
 
#RUN apt-get update && apt-get install -y openssh-server
RUN apt-get update && apt-get install -y openssh-server \
&& mkdir /var/run/sshd \
&& useradd -ms /bin/bash test \
&& sed -ie 's/test:!/test:\$6\$pIPlIFrg\$WZRTmOoouwD6L\/IDgz8fw97agQjdeXticOJyayjUYwmiuNKkJE92rBtr0XDXhVE4rSi9PkWv8rtnA0rCuR6ts\//g' /etc/shadow \
&& sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config \
&& sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd
 
#COPY data/* /.ROOT/
 
ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile
 
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
