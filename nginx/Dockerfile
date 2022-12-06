FROM nginx:stable-alpine

RUN wget -O /usr/bin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.2.5/dumb-init_1.2.5_x86_64
RUN chmod +x /usr/bin/dumb-init
# This translates signal SIGTERM to SIGQUIT so that nginx gracefully shuts down
ENTRYPOINT ["/usr/bin/dumb-init", "-c", "-r", "15:3", "--", "/docker-entrypoint.sh"]
ADD nginx.conf /
CMD ["nginx", "-c", "/nginx.conf"]
