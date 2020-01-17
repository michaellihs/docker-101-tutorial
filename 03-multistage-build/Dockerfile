FROM golang:1.13.5-alpine3.10 AS gobuild

ADD . /src
RUN cd /src && go build -o goapp

FROM alpine
RUN mkdir app
WORKDIR app
COPY --from=gobuild /src/goapp /app/
ENTRYPOINT ./goapp
