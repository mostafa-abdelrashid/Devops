FROM alpine:latest
LABEL maintainer="Mostafa"
LABEL description="this docker file installs Apache & PHP"

ENV PHPVERSION=82

RUN apk add --no-cache apache2 php${PHPVERSION}-apache2 php${PHPVERSION} && \
    mkdir -p /run/apache2 && \
    rm -rf /var/www/localhost/htdocs/index.html && \
    echo "<?php phpinfo(); ?>" > /var/www/localhost/htdocs/index.php && \
    chmod 755 /var/www/localhost/htdocs/index.php

EXPOSE 80
ENTRYPOINT ["httpd"]
CMD ["-D", "FOREGROUND"]

