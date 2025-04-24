---
title: AWS API Gateway
layout: default
---
# AWS API Gateway 🚪

> *for entire guide refer* : [What is restful api](https://aws.amazon.com/what-is/restful-api/)

## What is an API
An application programming interface (API) defines the rules that you must follow to communicate with other software systems. Developers expose or create APIs so that other applications can communicate with their applications programmatically.

It is a gateway between ```Client``` and ```Resources```

- **Clients** : They are the users who want to access information from the web. Can be a person or a software system that uses the API.

- **Resources** : Resources are the information that different applications provide to their clients. Resources can be images, videos, text, numbers, or any type of data.
The machine that gives the information is called ```Server``` .

## What is REST ?
**RE**presentational **S**tate **T**ransfer is a software architecture that imposes conditions on how an API should work.
Principles of REST architecture style:
1. Uniform Interface 
2. Client-Server
3. Stateless
4. Cacheable
5. Layered System
6. Code on demand

## Working of RESTful API
1. The client sends a request to the server. The client follows the API documentation to format the request in a way that the server understands.
2. The server authenticates the client and confirms that the client has the right to make that request.
The server receives the request and processes it internally.
3. The server returns a response to the client. 
4. The response contains information that tells the client whether the request was successful. The response also includes any information that the client requested.
 
## Contents of Restful API client request
- Universal resource identifier
- Method [ get ,post,put delete]
- Header [ Data and parameter ]
	- Parameter can be path parameter, query parameter, cookier parameter

## Contents of Server response
- Status line : Contains status code 
- Message body
- Headers

## API Gateway vs Load Balancer
API gateway : Middleware component b/w client and backend services providing a centralized entry point for accessing various endpoint and functionalities.

Load balancer : acts as  a traffic distributor evenly ditributing incoming requests across multiple backend services or instances to optimize resource utilization, improve availability, and enhance performance. 

## Amazon API Gateway
Amazon API Gateway is an AWS service for creating, publishing, maintaining, monitoring, and securing REST, HTTP, and WebSocket APIs at any scale.

## API endpoint
- Edge Optimised : routes requests to nearest Cloudfront Point of present
> Edge-optimized APIs capitalize the names of HTTP headers
- Regional : Clients in the same region
- Private :  only be accessed from your Amazon Virtual Private Cloud (VPC) using an interface VPC endpoint, which is an endpoint network interface (ENI) that you create in your VPC.

##
Use HTTP Headers for sending,
	- Directives ( read the input in JSON format )
	- Metadata ( who is making the request )
	- Common data to be sent on every request ( like Authentication, session )

Use Path Parameters to make,
	- Specific requests on a resource ( /country/state/city )
	- They must form a logical hiera	- rchy

Use Query Parameters for sending,
	- Action requests on a resource ( like pagination, filters )
## Proxy Resource
## Cross-Origin Resource Sharing CORS

## USEcases:
- custom header, parameter string, query string
- hit the api endpoint using REACT frontend
- connect api gateway to load balancer to connect to the EC2 instances inside a private subnet which are running express apps
- use authorizer role 
