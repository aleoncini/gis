FROM registry.access.redhat.com/ubi8/nodejs-10

RUN npm install -g tileserver-gl-light

COPY 2017-07-03_italy_rome.mbtiles /opt/app-root/src

RUN chgrp 0 /opt/app-root/src/2017-07-03_italy_rome.mbtiles && \
    chmod g+rwX /opt/app-root/src/2017-07-03_italy_rome.mbtiles

EXPOSE 8080
USER 1001
ENTRYPOINT ["tileserver-gl-light", "/opt/app-root/src/2017-07-03_italy_rome.mbtiles"]
