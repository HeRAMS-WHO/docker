FROM nginx:stable-alpine
LABEL org.opencontainers.image.source = "https://github.com/HeRAMS-WHO/docker"
RUN wget -O /usr/bin/dumb-init https://github.com/Yelp/dumb-init/releases/download/v1.2.5/dumb-init_1.2.5_x86_64
RUN chmod +x /usr/bin/dumb-init
# This translates signal SIGTERM to SIGQUIT so that nginx gracefully shuts down
ENTRYPOINT ["/usr/bin/dumb-init", "-c", "-r", "15:3", "--", "/docker-entrypoint.sh"]
ADD nginx.conf /
RUN ["nginx", "-t", "-c", "/nginx.conf"]
CMD ["nginx", "-c", "/nginx.conf"]
