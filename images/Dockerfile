FROM alpine:latest

RUN apk --no-cache add openssh-server
#RUN apk --no-cache add python-minimal
RUN apk add --update python


RUN sed -i s/#PermitRootLogin.*/PermitRootLogin\ yes/ /etc/ssh/sshd_config

RUN echo "root:root" | chpasswd

COPY authorized_keys /root/.ssh/authorized_keys

RUN ssh-keygen -A

CMD ["/usr/sbin/sshd", "-D"]
