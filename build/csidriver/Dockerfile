FROM golang:1.12-alpine3.10 AS builder

COPY . /go/src/github.com/kubeedge/kubeedge

RUN CGO_ENABLED=0 go build -v -o /usr/local/bin/csidriver -ldflags="-w -s" \
github.com/kubeedge/kubeedge/cloud/cmd/csidriver

FROM alpine:3.9

COPY --from=builder /usr/local/bin/csidriver /usr/local/bin/csidriver

ENTRYPOINT ["csidriver"]
