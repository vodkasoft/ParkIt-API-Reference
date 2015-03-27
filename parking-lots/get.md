# get

Gets one parking lot by ID.

## HTTP Request

GET /parking-lots/:id

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| id             | string    | The parking lot id.  |

## Authorization

This request requires admin user authorization. The user must be a member of the
organization that owns the parking lot.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns a
[Parking lot resource](README.md#resource-representation).

## Example

*Request*

```HTTP
GET /parking-lots/sampleParkingLotId HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleParkingLotId",
  "name": "Sample Parking Lot",
  "totalSpaces": 50,
  "availableSpaces": 15,
  "boundaries": [
    {
      "lat": 37.4217550,
      "lng": -122.0846330
    },
    {
      "lat": 37.2217550,
      "lng": -122.0846330
    },
    {
      "lat": 37.4217550,
      "lng": -122.1846330
    }
  ]
}
```
