FROM m03geek/dlib:stretch

ARG BUILD_DEPS='wget xz-utils'
ARG LIB_PREFIX='/usr/local'
ARG VERSION

ENV NODE_VERSION=${VERSION}

RUN echo "Node.js: ${NODE_VERSION}" \
    && apt-get update && apt-get install -y ${BUILD_DEPS} --no-install-recommends \
    && wget https://nodejs.org/dist/v${NODE_VERSION}/node-v${NODE_VERSION}-linux-x64.tar.xz -O node.tar.xz \
    && tar -xJf node.tar.xz -C ${LIB_PREFIX} --strip-components=1 --no-same-owner \
    && ln -s ${LIB_PREFIX}/bin/node ${LIB_PREFIX}/bin/nodejs \
    && cd / \
    && rm node.tar.xz \
    && apt-get purge -y --auto-remove $BUILD_DEPS \
    && apt-get autoremove -y --purge \
    && rm -rf /var/lib/apt/lists/* /usr/share/man /usr/local/share/man /tmp/*
