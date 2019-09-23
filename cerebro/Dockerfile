#1.	Deploy separate container for Cerebro and protect it with Nginx 
# I thought to protect it via ssl certificate but i was not sure.
# this section of protecting with ngnix was not set
FROM openjdk:11-jre-slim

MAINTAINER israel vinitzer <israel.vinitzer@gmail.com>
ENV CEREBRO_VERSION 0.8.4

RUN  apt-get update \
 && apt-get install -y wget \
 && rm -rf /var/lib/apt/lists/* \
 && mkdir -p /opt/cerebro/logs \
 && wget -qO- https://github.com/lmenezes/cerebro/releases/download/v${CEREBRO_VERSION}/cerebro-${CEREBRO_VERSION}.tgz \
  | tar xzv --strip-components 1 -C /opt/cerebro \
 && sed -i '/<appender-ref ref="FILE"\/>/d' /opt/cerebro/conf/logback.xml \
 && addgroup -gid 1000 cerebro \
 && adduser -gid 1000 -uid 1000 cerebro \
 && chown -R cerebro:cerebro /opt/cerebro

WORKDIR /opt/cerebro
EXPOSE 9000
USER cerebro
ENTRYPOINT [ "/opt/cerebro/bin/cerebro" ]