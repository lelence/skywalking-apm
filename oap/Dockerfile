FROM apache/skywalking-base:6.0.0-GA

LABEL maintainer="toan@maogogo.com"

ENV SKYWALKING_HOME=/skywalking \
    JAVA_OPTS=" -Xms256M -Xmx512M"

WORKDIR $SKYWALKING_HOME

RUN set -eux; \
    apk add --no-cache --virtual \
    bash tzdata; \
    ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime; \
    echo "Asia/Shanghai" > /etc/timezone; \
    rm -rf "config/log4j2.xml"; \
    rm -rf "webapp"; rm -rf "agent";

# COPY log4j2.xml config/

COPY docker-entrypoint.sh .

EXPOSE 12800 11800

ENTRYPOINT ["sh", "docker-entrypoint.sh"]