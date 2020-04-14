FROM golang:alpine as builder
RUN apk add git
RUN git clone https://github.com/PimmyTrousers/pastescraper.git /build
WORKDIR /build
RUN go build -o pastescrape .

FROM alpine
COPY --from=builder /build/pastescrape /app/

WORKDIR /app
ENTRYPOINT ["./pastescrape", "-config", "./config.yml"]