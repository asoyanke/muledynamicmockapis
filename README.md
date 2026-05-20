# Mulesoft Dynamic Mock APIs

Dynamic Mock APIs project enables flexible mocking of APIs using runtime-generated keys and payloads. It allows storing and retrieving mock responses dynamically using an Object Store.


# Overview
This service provides the capability to:

Dynamically create mock responses for APIs
Retrieve mock payloads using request metadata
Store and manage mock data using Object Store

# Key Concept

A unique key is generated using:
```
<HTTP_METHOD> + <ENDPOINT>
```
Example:
- GET/customer
- POST/order

# Supported Operations

## Mock GET API

Retrieve mock payload based on key.
- Input:
  - HTTP Method: GET
  - Endpoint: /resource

- Behaviour:
  - Combine method + endpoint → key
  - Fetch payload from Object Store
  - Return stored response


## Mock POST API
Retrieve mock payload for POST requests.
- Input:
  - HTTP Method: POST
  - Endpoint: /resource
- Behaviour:
  - Combine method + endpoint → key
  - Fetch payload from Object Store
  - Return stored response

# Object Store (OS) Operations

- Stores a payload against a generated key.
  - POST /api/os
  - Body 

```
{
  "method": "POST",
  "statuscode": "200",
  "path": "/resource",
  "payload": {
    "message": "TEST"
  }
}
```

- Retrieve Payload by Key
- Retrieve All Entries

# Benefits
- No need to hardcode mocks
- Dynamic and reusable mocking framework

# Useful for:

- Integration testing
- API simulation
- Backend unavailability scenarios
