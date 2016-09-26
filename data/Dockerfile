FROM busybox

# YEKT locale
ENV TZ=Asia/Yekaterinburg
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN mkdir /data && echo "Hello world" > /data/index.html
CMD ["echo", "data volume"]
