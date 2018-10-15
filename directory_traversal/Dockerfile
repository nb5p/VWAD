FROM alpine

RUN apk add --no-cache php && \
        rm -rf /var/cache/apk/*

WORKDIR /dt
RUN echo '<?php include($_GET["'"filename"'"]); ?>' > file.php
RUN echo '<?php echo phpinfo(); ?>' > phpinfo.php

EXPOSE 3000
CMD php -S 0.0.0.0:3000
