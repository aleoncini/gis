FROM registry.fedoraproject.org/fedora-minimal

RUN microdnf install nodejs && microdnf clean all

RUN groupadd jboss && useradd jboss -g jboss

USER jboss

RUN cd /home/jboss \
    && mkdir "${HOME}/.npm-packages" \
    && npm config set prefix "${HOME}/.npm-packages" \
    && echo 'NPM_PACKAGES="${HOME}/.npm-packages"' >> .bashrc \
    && echo 'export PATH="$PATH:$NPM_PACKAGES/bin"' >> .bashrc \
    && source ~/.bashrc

RUN npm install -g tileserver-gl-light

WORKDIR /home/jboss

COPY run.sh /home/jboss
COPY 2017-07-03_italy_rome.mbtiles /home/jboss/map.mbtiles
RUN  chmod +x /home/jboss/run.sh

EXPOSE 8080
ENTRYPOINT ["/bin/bash", "/home/jboss/run.sh"]
