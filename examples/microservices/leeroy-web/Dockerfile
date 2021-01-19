ARG BASE registry.cn-hangzhou.aliyuncs.com/zjltest/base:v15
FROM golang:1.12.9-alpine3.10 as builder
COPY web.go .
# `skaffold debug` sets SKAFFOLD_GO_GCFLAGS to disable compiler optimizations
RUN go build -o /app .

FROM $BASE
COPY --from=builder /app .
