FROM resin/qemux86-64-debian:jessie

ENV GO_VERSION 1.9.1

RUN buildDeps='curl gcc g++ git' \
	&& set -x \
	&& apt-get update && apt-get install -y $buildDeps \
	&& rm -rf /var/lib/apt/lists/* \
	&& mkdir -p /usr/local/go \
	&& curl -SLO "https://storage.googleapis.com/golang/go$GO_VERSION.linux-amd64.tar.gz" \
	&& echo "07d81c6b6b4c2dcf1b5ef7c27aaebd3691cdb40548500941f92b221147c5d9c7  go1.9.1.linux-amd64.tar.gz" | sha256sum -c - \
	&& tar -xzf "go$GO_VERSION.linux-amd64.tar.gz" -C /usr/local/go --strip-components=1 \
	&& rm -f go$GO_VERSION.linux-amd64.tar.gz

ENV GOROOT /usr/local/go
ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
WORKDIR $GOPATH

COPY go-wrapper /usr/local/bin/

CMD ["echo","'No CMD command was set in Dockerfile! Details about CMD command could be found in Dockerfile Guide section in our Docs. Here's the link: http://docs.resin.io/deployment/dockerfile"]
