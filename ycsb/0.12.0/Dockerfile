FROM debian:jessie

ENV YCSB_VERSION=0.12.0

RUN apt-get update
RUN apt-get install -y wget default-jdk python2.7
RUN wget https://github.com/brianfrankcooper/YCSB/releases/download/$YCSB_VERSION/ycsb-$YCSB_VERSION.tar.gz -O /opt/ycsb.tar.gz
RUN tar xfvz /opt/ycsb.tar.gz -C /opt/
RUN mv /opt/ycsb-0.12.0/ /opt/ycsb/
RUN rm -f /opt/ycsb.tar.gz
RUN rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["python2.7", "/opt/ycsb/bin/ycsb"]
