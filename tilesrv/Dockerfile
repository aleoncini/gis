FROM registry.access.redhat.com/ubi8/nodejs-10

npm install tileserver-gl-light

WORKDIR /opt/app-root/src/

RUN wget -c https://openmaptiles.com/download/WyI4NWE5ZjM3Yi1lODcwLTRlYTAtOGNkYy03MWE3YWI3ZjI2NGQiLCItMSIsODQxOV0.Xn4Hbw.FcGY8z-Lvv26QqY8LyW_nwof1dM/osm-2017-07-03-v3.6.1-italy_rome.mbtiles

WORKDIR /opt/app-root/src/
EXPOSE 8080
CMD tileserver-gl-light --verbose 2017-07-03_italy_rome.mbtiles

