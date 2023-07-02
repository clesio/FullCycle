# Container stage para compilar o programa go

FROM golang:1.20.5 AS builder

WORKDIR /go/src

COPY src/ .

RUN go build

# Imagem mínima para rodar o programa compilado acima

FROM scratch

COPY --from=builder /go/src/hello /

CMD [ "/hello" ]