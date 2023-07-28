#stage 0

FROM golang:1.20 AS build 

WORKDIR /app

COPY ["go.mod", "go.sum", "/app/"]

RUN go mod download 

COPY . . 

RUN go build -o geek-life ./app


#stage 1

FROM ubuntu:23.10

COPY --from=build ./app/geek-life ./geek-life

ENTRYPOINT [ "./geek-life" ]

#docker build -t geek-life . 
#docker run -p 4000:4000 geek-life serve -t all