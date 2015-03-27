# get

Gets one location by ID.

## HTTP Request

GET /locations/:id

## Parameters

| Parameter name | Data Type | Description      |
|:---------------|:----------|:-----------------|
| id             | string    | The location id. |

## Authorization

This request requires admin user authorization.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns an
[Locations resource](README.md#resource-representation).

## Example

*Request*

```HTTP
GET /locations/sampleLocationId HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleLocationId",
  "name": "Sample Location",
  "location": {
    "lat": 37.4217550,
    "lng": -122.0846330
  }
}
```
