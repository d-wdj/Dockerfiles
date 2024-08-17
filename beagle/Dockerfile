ARG builder=dwdj/builder-ubuntu:latest
FROM $builder AS builder
WORKDIR /tmp
RUN wget https://faculty.washington.edu/browning/beagle/beagle.06Aug24.a91.jar &&\
    wget https://faculty.washington.edu/browning/beagle/bref3.06Aug24.a91.jar &&\
    wget https://faculty.washington.edu/browning/beagle/unbref3.06Aug24.a91.jar

FROM adoptopenjdk/openjdk8:debianslim-jre
COPY --from=builder /tmp/beagle.06Aug24.a91.jar beagle.jar
COPY --from=builder /tmp/bref3.06Aug24.a91.jar bref3.jar
COPY --from=builder /tmp/unbref3.06Aug24.a91.jar unbref3.jar
