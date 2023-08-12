# Container stage para compilar o programa hello.go
# Gera o binário hello

FROM golang:1.20.5 AS builder

WORKDIR /go/src

COPY src/ .

RUN go build

# Imagem mínima para rodar o programa compilado hello

FROM scratch

COPY --from=builder /go/src/hello /

CMD [ "/hello" ]