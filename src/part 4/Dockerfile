FROM nginx

WORKDIR /home/

COPY hello.c /home/
COPY nginx.conf /etc/nginx/nginx.conf
COPY part_4.sh /home/

RUN apt-get update && apt-get install -y gcc spawn-fcgi libfcgi-dev;

ENTRYPOINT ["bash", "./part_4.sh"]

