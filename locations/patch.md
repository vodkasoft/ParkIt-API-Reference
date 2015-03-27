# patch

Updates an existing location. Can use partial data.

## HTTP Request

PATCH /locations/:id

## Parameters

| Parameter name | Data Type | Description      |
|:---------------|:----------|:-----------------|
| id             | string    | The location id. |

## Authorization

This request requires super user authorization.

## Request Body

This request must contain the relevant portions of an
[Locations resource](README.md#resource-representation).

## Response

If successful, this method returns an
[Locations resource](README.md#resource-representation).

## Example

*Request*

```HTTP
PATCH /locations/sampleLocationId HTTP/1.1
Host: example.com

{
  "name": "Sample Location Modified"
}
```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleLocationId",
  "name": "Sample Location Modified",
  "location": {
    "lat": 37.4217550,
    "lng": -122.0846330
  }
}
```
