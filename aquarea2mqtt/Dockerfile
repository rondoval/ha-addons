ARG BUILD_FROM
ARG BUILD_ARCH

FROM golang as builder
RUN go get github.com/rondoval/aquarea2mqtt \
    && GOOS=linux GOARCH=$BUILD_ARCH CGO_ENABLED=0 go build -a -tags netgo -ldflags '-w -extldflags "-static"' -o /go/bin/aquarea2mqtt /go/src/github.com/rondoval/aquarea2mqtt/

FROM $BUILD_FROM
RUN adduser -S -D -H -h /aquarea appuser
USER appuser
COPY --from=builder /go/bin/aquarea2mqtt /aquarea/aquarea2mqtt
COPY --from=builder /go/src/github.com/rondoval//aquarea2mqtt/translation.json /aquarea/translation.json
WORKDIR /aquarea
ENTRYPOINT ./aquarea2mqtt
