FROM golang:1.10 as builder
COPY onyxium-market-feed/ /go/src/github.com/onyxium-strategies/onyxium-market-feed
WORKDIR /go/src/github.com/onyxium-strategies/onyxium-market-feed
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o market-feed .

FROM alpine:latest
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /go/src/github.com/onyxium-strategies/onyxium-market-feed/market-feed .
CMD ["./market-feed"]
