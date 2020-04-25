FROM golang:latest 
RUN mkdir /app 
RUN apt update && apt install git
RUN cd /tmp && git clone https://github.com/corylanou/tns-restful-json-api.git && cd tns-restful-json-api/v9 && ls  && mv * /app
ADD . /app/ 
WORKDIR /app 
RUN go get -u github.com/gorilla/mux
RUN go build -o main . 

CMD ["/app/main"]
