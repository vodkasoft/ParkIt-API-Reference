# get

Gets one parking space by ID.

## HTTP Request

GET /spaces/:id

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| id             | string    | The parking lot id.  |

## Authorization

This request requires admin user authorization. The user must be a member of the
organization that owns the parking space.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns a
[Parking space resource](README.md#resource-representation).

## Example

*Request*

```HTTP
GET /spaces/sampleParkingSpaceId HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleParkingSpaceId",
  "number": "12",
  "state": "vacant",
  "reserved": false,
  "sensor": {
    "id": "sampleSensorId",
    "serialNumber": "sampleSensorSerialNumber",
  },
  "location": {
    "lat": 37.2217550,
    "lng": -122.0846330
  }
}
```
