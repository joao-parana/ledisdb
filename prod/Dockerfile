FROM alpine:3.2

# Install cURL, tar e bash
RUN apk upgrade --update && \
    apk add curl ca-certificates tar bash && \
    curl -Ls https://circle-artifacts.com/gh/andyshinn/alpine-pkg-glibc/6/artifacts/0/home/ubuntu/alpine-pkg-glibc/packages/x86_64/glibc-2.21-r2.apk > /tmp/glibc-2.21-r2.apk && \
    apk add --allow-untrusted /tmp/glibc-2.21-r2.apk
    
COPY ledis-server /ledis-server

RUN chmod a+rx /ledis-server

CMD /ledis-server -config=/ledisdb.conf
