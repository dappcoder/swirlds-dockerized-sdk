FROM anapsix/alpine-java

COPY sdk /usr/local/swirlds/sdk
COPY config.txt /usr/local/swirlds/sdk/config.txt
WORKDIR /usr/local/swirlds/sdk

ENTRYPOINT java -jar swirlds.jar
