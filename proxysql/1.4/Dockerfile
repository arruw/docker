FROM debian:jessie

ENV PROXYSQL_VERSION=1.4.1

RUN apt-get update && \
	apt-get install -y wget mysql-client && \
	wget https://github.com/sysown/proxysql/releases/download/v$PROXYSQL_VERSION/proxysql_$PROXYSQL_VERSION-debian8_amd64.deb -O /opt/proxysql_debian8_amd64.deb && \
	dpkg -i /opt/proxysql_debian8_amd64.deb && \
	rm -f /opt/proxysql_debian8_amd64.deb && \
	rm -rf /var/lib/apt/lists/*

EXPOSE 6032 6033

VOLUME ["/var/lib/proxysql"]

ENTRYPOINT ["proxysql", "-f"]
