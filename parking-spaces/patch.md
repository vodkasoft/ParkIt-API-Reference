# patch

Updates an existing parking space. Can use partial data.

## HTTP Request

PATCH /spaces/:id

## Parameters

| Parameter name | Data Type | Description            |
|:---------------|:----------|:-----------------------|
| id             | string    | The parking space id.  |

## Authorization

This request requires admin user authorization. The user must be a member of the
organization that owns the parking space.

## Request Body

This request must contain the relevant portions of a
[Parking Space resource](README.md#resource-representation).

## Response

If successful, this method returns a
[Parking Space resource](README.md#resource-representation).

## Example

*Request*

```HTTP
PATCH /spaces/sampleParkingSpaceId HTTP/1.1
Host: example.com

{
  "state": "occupied"
}
```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleParkingSpaceId",
  "number": "12",
  "state": "occupied",
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
