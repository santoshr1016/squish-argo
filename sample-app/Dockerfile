# Build image
FROM golang:alpine as builder

WORKDIR /

COPY . ./

RUN go build


FROM alpine:3.9
COPY --from=builder /sample-app /sample-app
COPY --from=builder /index.html /index.html

EXPOSE 3100
ENTRYPOINT "/sample-app"