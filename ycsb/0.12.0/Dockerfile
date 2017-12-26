FROM alpine:latest

ENV YCSB_VERSION=0.12.0

RUN apk --no-cache add curl python openjdk7-jre && \
  curl -O --location  https://github.com/brianfrankcooper/YCSB/releases/download/${YCSB_VERSION}/ycsb-${YCSB_VERSION}.tar.gz && \
  apk del curl && \
  tar xfz ycsb-${YCSB_VERSION}.tar.gz && \
  rm -rf ycsb-${YCSB_VERSION}.tar.gz && \
  mkdir /opt && \
  mv ycsb-${YCSB_VERSION} /opt/ycsb

ENTRYPOINT ["/opt/ycsb/bin/ycsb"]

CMD ["--help"]
