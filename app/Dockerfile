#Stage-1
FROM golang:1.16.0-alpine3.13 as builder
COPY ./app/main.go ./
RUN go build -o /gitops-go-app ./main.go

#Stage-2
FROM alpine:3.13
EXPOSE 8080
COPY --from=builder /gitops-go-app /.
ENTRYPOINT ["./gitops-go-app"]
