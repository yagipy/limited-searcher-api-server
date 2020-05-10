FROM golang:1.12.9-alpine3.10 as builder
COPY main.go .
RUN go build -o /url .

FROM alpine:3.10
# Define GOTRACEBACK to mark this container as using the Go language runtime
# for `skaffold debug` (https://skaffold.dev/docs/workflows/debug/).
ENV GOTRACEBACK=single
CMD ["./url"]
COPY --from=builder /url .
