FROM influxdb:latest

LABEL author="Q"
LABEL version="1.0.0"
LABEL description="InfluxDB docker image"

USER root

ADD influxdb.template.conf /influxdb.template.conf

ADD run.sh /run.sh
RUN chmod +x /run.sh

CMD ["/run.sh"]

