FROM java:8-jre-alpine

ADD /build/skywalking-agent.tar.gz .

LABEL maintainer="Toan <tli@jihuiduo.cn>"

# ARG SERVICE_NAME=${SERVICE_NAME:-JHD_EUREKA}
# ARG COLLECTOR_SERVICES=${COLLECTOR_SERVICES}

# ENV TZ="Asia/Shanghai"
# ENV LOG_LEVEL=DEBUG \
# 	SERVICE_NAME=JHD_APP \
# 	COLLECTOR_SERVICES=oap:11800

# ENV SW_AGENT_NAME=Test1234
# ENV SW_AGENT_COLLECTOR_BACKEND_SERVICES=oap:11800
# ENV SW_LOGGING_LEVEL=INFO 


COPY /build/scripts/docker-entrypoint.sh /

# for timezone
# RUN apk add -U --no-cache tzdata \
# 	&& cp /usr/share/zoneinfo/$TZ /etc/localtime \
# 	&& echo $TZ >  /etc/timezone \
# 	&& chmod u+x /usr/local/bin/configure-agent.sh

# ENTRYPOINT ["sh", "docker-entrypoint.sh"]
CMD ["tail", "-f", "/dev/null"]