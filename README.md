# API Gateway POC using Zuul and a simple REST service

## apigatewaypoc-service - simple REST service running on port 9000

### Build & Run

mvn install

run MovieApplication.java

access http://localhost:9000/ghostbusters

## apigatewaypoc-zuul - a Zuul service running on port 8080

### What's going on?

Checkout apigatewaypoc-zuul/src/main/resources/application.properties

server.port=8080 - runs zuul on port 8080

zuul.routes.book.url=http://localhost:9000 - route to our rest service at port 9000

zuul.routes.book.path=/movies/** - tells that every call over /movies will be redirected to our rest service api on port

### Build & Run

mvn install

run ApiGatewayApplication.java

access http://localhost:8080/movies/ghostbusters 

	* under the hood it is mapped to http://localhost:9000/ghostbusters


