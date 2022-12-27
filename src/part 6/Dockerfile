FROM nginx

WORKDIR /home/

COPY nginx.conf /etc/nginx/nginx.conf
COPY part_6.sh /home/

RUN apt-get update && apt-get install -y gcc spawn-fcgi libfcgi-dev; \
apt-get clean && rm -rf /var/lib/apt/lists/*; \
chown -R nginx:nginx /etc/nginx/nginx.conf; \
chown -R nginx:nginx /var/cache/nginx; \
chown -R nginx:nginx /home; \
touch /var/run/nginx.pid; \
chown -R nginx:nginx /var/run/nginx.pid;

USER nginx
HEALTHCHECK --interval=5m --timeout=3s CMD curl -f http://localhost/ || exit 1

ENTRYPOINT ["bash", "./part_6.sh"]
