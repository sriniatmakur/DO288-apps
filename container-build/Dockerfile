# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent
EXPOSE 8080
RUN sed -i 's/Listen 80/Listen 8080/' /etc/httpd/conf/httpd.conf
RUN chown 1001:0 /var/log/httpd && \
    chown 1001:0 /var/run/httpd && \
    chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd
USER 1001
ENTRYPOINT ["httpd"]
CMD ["-D", "FOREGROUND"]
