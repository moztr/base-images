FROM resin/rpi-raspbian:jessie

ENV GO_VERSION 1.9.1

RUN buildDeps='curl gcc g++ git' \
	&& set -x \
	&& apt-get update && apt-get install -y $buildDeps \
	&& rm -rf /var/lib/apt/lists/* \
	&& mkdir -p /usr/local/go \
	&& curl -SLO "http://resin-packages.s3.amazonaws.com/golang/v$GO_VERSION/go$GO_VERSION.linux-armv6hf.tar.gz" \
	&& echo "77e2c134fac90bc291dd8afa9d58a939185cc1294e47eb6349fcbba1754320bd  go1.9.1.linux-armv6hf.tar.gz" | sha256sum -c - \
	&& tar -xzf "go$GO_VERSION.linux-armv6hf.tar.gz" -C /usr/local/go --strip-components=1 \
	&& rm -f go$GO_VERSION.linux-armv6hf.tar.gz

ENV GOROOT /usr/local/go
ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH

COPY go-wrapper /usr/local/bin/

CMD ["echo","'No CMD command was set in Dockerfile! Details about CMD command could be found in Dockerfile Guide section in our Docs. Here's the link: http://docs.resin.io/deployment/dockerfile"]
