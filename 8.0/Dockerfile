FROM ubi8/ubi:latest
LABEL maintainer="webPDF Docker Maintainers <asptest>"

# installing packages...
RUN sudo yum install wget gpg

RUN echo -e "[webpdfrepo] \nname=webPDF Repository \nbaseurl=http://packages.softvision.de/centos/7/x86_64/webpdf/8/ \nenabled=1 \ngpgcheck=1" >/etc/yum.repos.d/webpdf.repo
RUN sudo wget https://packages.softvision.de/keys/public.gpg -P /tmp/
RUN sudo gpg --with-fingerprint /tmp/public.gpg
RUN sudo rpm --import /tmp/public.gpg
RUN yum update
RUN yum install webpdf -y

# clean ?

EXPOSE 8080

CMD service webpdf start && bash
