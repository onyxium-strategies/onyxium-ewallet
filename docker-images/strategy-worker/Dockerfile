FROM golang:1.10 as builder
COPY onyxium-strategy-worker/ /go/src/github.com/onyxium-strategies/onyxium-strategy-worker
WORKDIR /go/src/github.com/onyxium-strategies/onyxium-strategy-worker
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o strategy-worker .

FROM alpine:latest
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /go/src/github.com/onyxium-strategies/onyxium-strategy-worker/.env .
COPY --from=builder /go/src/github.com/onyxium-strategies/onyxium-strategy-worker/strategy-worker .
CMD ["./strategy-worker"]
