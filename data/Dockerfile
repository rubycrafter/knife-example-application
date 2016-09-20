FROM devopsftw/baseimage:dev

# YEKT locale
ENV TZ=Asia/Yekaterinburg
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

ADD config/data.json /etc/consul/conf.d/data.json

ENV CONSUL_HOST consul

RUN mkdir /data && echo "Hello world" > /data/index.html
CMD ["echo", "data volume"]
