# patch

Updates an existing parking lot. Can use partial data.

## HTTP Request

PATCH /parking-lots/:id

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| id             | string    | The parking lot id.  |

## Authorization

This request requires admin user authorization. The user must be a member of the
organization that owns the parking lot.

## Request Body

This request must contain the relevant portions of a
[Parking Lot resource](README.md#resource-representation).

## Response

If successful, this method returns a
[Parking Lot resource](README.md#resource-representation).

## Example

*Request*

```HTTP
PATCH /parking-lots/sampleParkingLotId HTTP/1.1
Host: example.com

{
  "name": "Sample Parking Lot Modified"
}
```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleParkingLotId",
  "name": "Sample Parking Lot Modified",
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
