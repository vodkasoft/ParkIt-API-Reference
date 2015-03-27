# create

Creates a parking lot.

## HTTP Request

POST /locations/:locId/parking-lots

## Parameters

| Parameter name | Data Type | Description       |
|:---------------|:----------|:------------------|
| locId          | string    | The location id.  |

## Authorization

This request requires admin user authorization.

## Request Body

The request body must be a
[Parking Lots resource](README.md#resource-representation) with the
following properties:

| Property name     | Data Type | Description                                             |
|:------------------|:----------|:--------------------------------------------------------|
| boundaries[]      | list      | List of coordinates that defines a parking lot polygon. |
| boundaries[].lat  | float     | Latitude of a vertex of a parking lot polygon.          |
| boundaries[].lng  | float     | Longitude of a vertex of a parking lot polygon.         |
| name              | string    | Parking lot name.                                       |

##### Response

If successful, this method returns a
[Parking Lots resource](README.md#resource-representation).

##### Example

*Request*

```HTTP
POST /locations/sampleLocationId/parking-lots HTTP/1.1
Host: example.com

{
  "name": "Sample Parking Lot",
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

*Response*

```HTTP
HTTP/1.1 201 CREATED
Content-Type: application/json; charset=utf-8
Location: https://example.com/parking-lots/sampleParkingLotId

{
  "id": "sampleParkingLotId",
  "name": "Sample Parking Lot",
  "totalSpaces": 0,
  "availableSpaces": 0,
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
