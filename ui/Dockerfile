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
    rm -rf "config"; rm -rf "oap-libs"; \
    rm -rf "agent";

COPY docker-entrypoint.sh .
COPY logback.xml webapp/

EXPOSE 8080

ENTRYPOINT ["sh", "docker-entrypoint.sh"]