FROM devopsftw/baseimage:dev

# YEKT locale
ENV TZ=Asia/Yekaterinburg
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN \
  add-apt-repository -y ppa:nginx/stable && \
  apt-get update && \
  apt-get install -y nginx && \
  rm -rf /var/lib/apt/lists/* && \
  echo "\ndaemon off;" >> /etc/nginx/nginx.conf && \
  chown -R www-data:www-data /var/lib/nginx

# Define mountable directories
VOLUME ["/etc/nginx/sites-enabled", "/etc/nginx/certs", "/etc/nginx/conf.d", "/var/log/nginx", "/var/www/html"]

ADD config/nginx.json /etc/consul/conf.d/nginx.json
ENV CONSUL_HOST consul

# Define working directory
WORKDIR /etc/nginx

# Define default command
CMD ["nginx"]

# Expose ports
EXPOSE 80
EXPOSE 443
