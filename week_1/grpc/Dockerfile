FROM golang:1.21.6-alpine3.18 AS builder
COPY . /github.com/Sunshine31/microservices_course/week_1/grpc/source
WORKDIR /github.com/Sunshine31/microservices_course/week_1/grpc/source
RUN go mod download
RUN go build -o ./bin/crud_server cmd/grpc_server/main.go

FROM alpine:latest

WORKDIR /root/
COPY --from=builder /github.com/Sunshine31/microservices_course/week_1/grpc/source/bin/crud_server .
CMD ["./crud_server"]


