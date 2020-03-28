FROM registry.access.redhat.com/ubi8/nodejs-10

RUN npm install -g tileserver-gl-light

RUN curl -o /opt/app-root/src/map.mbtiles https://openmaptiles.os.zhdk.cloud.switch.ch/v3.6.1/extracts/europe/NFhO1bt4UOScDn1xf7TjEwEvvoOHGNQ5/2017-07-03_italy_centro.mbtiles

RUN chgrp 0 /opt/app-root/src/map.mbtiles && \
    chmod g+rwX /opt/app-root/src/map.mbtiles

EXPOSE 8080
USER 1001
ENTRYPOINT ["tileserver-gl-light", "/opt/app-root/src/map.mbtiles"]
