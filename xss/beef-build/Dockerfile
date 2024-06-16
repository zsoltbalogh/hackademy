FROM ubuntu:24.04

ENV LANG=C.UTF-8
ENV LANGUAGE=en_US:en
ENV LC_ALL=C.UTF-8

RUN apt-get update && \
	apt-get install -y git nodejs ruby sudo

WORKDIR /root

RUN git clone https://github.com/beefproject/beef.git

WORKDIR /root/beef

RUN	yes | TERM=xterm /root/beef/install
RUN sed -ie s/\"beef\"/\"test\"/ config.yaml 

EXPOSE 3000

ENTRYPOINT /root/beef/beef