# AUTOGENERATED FILE
FROM resin/i386-alpine-buildpack-deps:latest

ENV NODE_VERSION 9.0.0

# Install dependencies
RUN apk add --no-cache libgcc libstdc++ libuv libcrypto1.0 libssl1.0

RUN curl -SLO "http://resin-packages.s3.amazonaws.com/node/v$NODE_VERSION/node-v$NODE_VERSION-linux-alpine-i386.tar.gz" \
	&& echo "92750ee83f51695af4d0efb80a96608ba75d970982e993c1258a830e6fa2ff74  node-v9.0.0-linux-alpine-i386.tar.gz" | sha256sum -c - \
	&& tar -xzf "node-v$NODE_VERSION-linux-alpine-i386.tar.gz" -C /usr/local --strip-components=1 \
	&& rm "node-v$NODE_VERSION-linux-alpine-i386.tar.gz" \
	&& npm config set unsafe-perm true -g --unsafe-perm \
	&& rm -rf /tmp/*

CMD ["echo","'No CMD command was set in Dockerfile! Details about CMD command could be found in Dockerfile Guide section in our Docs. Here's the link: http://docs.resin.io/deployment/dockerfile"]
