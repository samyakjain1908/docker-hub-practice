FROM golang:1.18-alpine AS build

RUN mkdir -p /go/src/github.com/samyakjain1908/docker-hub-practice ~/.ssh && \
    apk add --no-cache git openssh-client make gcc libc-dev
WORKDIR /go/src/github.com/samyakjain1908/docker-hub-practice
COPY . .
RUN make build

FROM alpine:3
COPY --from=build /go/src/github.com/samyakjain1908/docker-hub-practice/article-server /bin/article-server
CMD /bin/article-server
