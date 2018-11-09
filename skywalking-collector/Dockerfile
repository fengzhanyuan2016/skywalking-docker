FROM java:openjdk-8u111-jre
ENV SKYWALKING_VERSION=5.0.0-GA
ADD http://mirrors.tuna.tsinghua.edu.cn/apache/incubator/skywalking/${SKYWALKING_VERSION}/apache-skywalking-apm-incubating-${SKYWALKING_VERSION}.tar.gz  /
RUN tar -zxvf /apache-skywalking-apm-incubating-${SKYWALKING_VERSION}.tar.gz

LABEL maintainer="iven.feng@outlook.com"

ENV ES_CLUSTER_NAME=skywalking \
    ES_CLUSTER_SNIFFER=true \
    ES_ADDRESSES=localhost:9300 \
    BIND_HOST=0.0.0.0  \
    NAMING_BIND_HOST=0.0.0.0 \
    NAMING_BIND_PORT=10800 \
    REMOTE_BIND_PORT=11800 \
    AGENT_GRPC_BIND_PORT=11800 \
    AGENT_JETTY_BIND_HOST=0.0.0.0 \
    AGENT_JETTY_BIND_PORT=12800 \
    UI_JETTY_BIND_PORT=12800 \
    UI_JETTY_BIND_HOST=0.0.0.0 \
    UI_SERVER_PORT=8080 \
    UI_ADMIN_PASSWORD=admin \
    UI_RIBBON_LIST_SERVERS=127.0.0.1:10800

COPY  /apache-skywalking-apm-incubating /apache-skywalking-apm-incubating

EXPOSE 8080 10800 11800 12800

CMD ["/apache-skywalking-apm-incubating/bin/startup.sh"]
