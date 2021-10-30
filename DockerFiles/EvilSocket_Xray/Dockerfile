FROM docker.io/golang:alpine

#Add git and make to alpine
RUN apk add --no-cache git make

#Download and install xray as per instructions
RUN export GO111MODULE=off && \
    go get -v github.com/evilsocket/xray && \
    cd $GOPATH/src/github.com/evilsocket/xray && \
    make

#Default port for xray
EXPOSE 8080

#Settings for run
ENV PATH $GOPATH/src/github.com/evilsocket/xray:$PATH

#Build directory
WORKDIR $GOPATH/src/github.com/evilsocket/xray

CMD ["xray"]