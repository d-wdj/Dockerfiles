ARG builder=dwdj/builder-ubuntu:latest
FROM $builder AS builder
WORKDIR /tmp
RUN wget -O beagle.jar https://faculty.washington.edu/browning/beagle/beagle.06Aug24.a91.jar &&\
    wget -O bref3.jar https://faculty.washington.edu/browning/beagle/bref3.06Aug24.a91.jar &&\
    wget -O unbref3.jar https://faculty.washington.edu/browning/beagle/unbref3.06Aug24.a91.jar

FROM adoptopenjdk/openjdk8:debianslim-jre
COPY --from=builder /tmp/beagle.jar beagle.jar
COPY --from=builder /tmp/bref3.jar bref3.jar
COPY --from=builder /tmp/unbref3.jar unbref3.jar
RUN apt-get update &&\
    apt-get install -y --no-install-recommends procps &&\
    apt-get clean &&\
    rm -rf /var/lib/apt/lists/*
