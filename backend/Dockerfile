FROM golang:1.22-alpine AS build

WORKDIR /app
COPY main.go .
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o backend_req main.go


FROM gcr.io/distroless/base-debian12
WORKDIR /app
COPY --from=build /app/backend_req .
USER 65532:65532
HEALTHCHECK --interval=10s --timeout=3s --start-period=5s --retries=3 \
 CMD ["/app/backend_req", "-healthcheck"]
ENTRYPOINT [ "./backend_req" ] 