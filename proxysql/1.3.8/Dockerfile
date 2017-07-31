FROM debian:jessie

ENV PROXYSQL_VERSION=1.3.8

RUN apt-get update && \
	apt-get install -y wget mysql-client && \
	wget https://github.com/sysown/proxysql/releases/download/v$PROXYSQL_VERSION/proxysql_$PROXYSQL_VERSION-debian8_amd64.deb -O /opt/proxysql_debian8_amd64.deb && \
	dpkg -i /opt/proxysql_debian8_amd64.deb && \
	rm -f /opt/proxysql_debian8_amd64.deb && \
	rm -rf /var/lib/apt/lists/*

COPY proxysql.cnf /etc/proxysql.cnf

EXPOSE 6032 6033

VOLUME ["/var/lib/proxysql"]

ENTRYPOINT ["proxysql", "-f"]

# NOTES
# 
# Read more about configuration on: https://github.com/sysown/proxysql/wiki
# 
# - To override configuration mount your config to /etc/proxysql.cnf
# - Data volume is located at /var/lib/proxysql
