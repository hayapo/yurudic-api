FROM golang:1.19-alpine as dev

ENV ROOT=/go/src/app

WORKDIR ${ROOT}

ENV CGO_ENABLED 0
ENV ELASTICSEARCH_URL=http://localhost:9200

RUN apk update && apk add git
RUN go install -v github.com/cosmtrek/air@latest
RUN go install -v golang.org/x/tools/gopls@latest
RUN go install -v github.com/cweill/gotests/gotests@latest
RUN go install -v github.com/josharian/impl@latest
RUN go install -v github.com/haya14busa/goplay/cmd/goplay@latest
RUN go install -v github.com/go-delve/delve/cmd/dlv@latest
RUN go install -v honnef.co/go/tools/cmd/staticcheck@latest

EXPOSE 8080

CMD ["air", "-c", ".air.toml"]