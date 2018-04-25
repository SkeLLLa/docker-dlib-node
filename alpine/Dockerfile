ARG VERSION
FROM mhart/alpine-node:${VERSION} as nodebase

FROM m03geek/dlib:alpine

COPY --from=nodebase /usr/bin/node /usr/bin/
COPY --from=nodebase /usr/lib/node_modules /usr/lib/node_modules
COPY --from=nodebase /usr/include/* /usr/include/
