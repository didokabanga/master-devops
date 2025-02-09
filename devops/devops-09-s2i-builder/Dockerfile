FROM ubuntu:22.04
EXPOSE 8082

RUN apt-get update && apt-get install -y wget build-essential && apt-get clean

RUN wget https://nodejs.org/dist/v20.13.1/node-v20.13.1-linux-x64.tar.xz \
    && mkdir -p /node && tar -xf node-v20.13.1-linux-x64.tar.xz -C /node \
    && chmod +x -R /node/node-v20.13.1-linux-x64

COPY .s2i/bin /usr/local/s2i

LABEL io.openshift.s2i.scripts-url=image:///usr/local/s2i

RUN chown -R 1001:0 /opt/app-root
USER 1001

CMD ["echo","please refer usage"]