# create

Creates a parking space.

## HTTP Request

POST /parking-lots/:lotId/spaces

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| lotId          | string    | The parking lot id.  |

## Authorization

This request requires admin user authorization.

## Request Body

The request body must be a
[Parking Spaces resource](README.md#resource-representation) with the
following properties:

| Property name       | Data Type | Description                                                                    |
|:--------------------|:----------|:-------------------------------------------------------------------------------|
| location.lat        | float     | Latitude of the geocoded location of the parking space.                        |
| location.lng        | float     | Longitude of the geocoded location of the parking space.                       |
| number              | string    | Number assigned to the parking space. Should be unique in each parking lot.    |
| reserved            | boolean   | Whether the parking space is marked as reserved or not.                        |
| sensor.id           | string    | Sensor ID. Should only be changed when a sensor is replaced.                   |
| sensor.serialNumber | string    | Serial number of the sensor that is placed at the parking space.               |
| state               | string    | Current state of the parking space. Can be "vacant", "occupied" or "disabled". |


##### Response

If successful, this method returns a
[Parking Spaces resource](README.md#resource-representation).

##### Example

*Request*

```HTTP
POST /parking-lots/sampleParkingLot/spaces HTTP/1.1
Host: example.com

{
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

*Response*

```HTTP
HTTP/1.1 201 CREATED
Content-Type: application/json; charset=utf-8
Location: https://example.com/spaces/sampleParkingSpaceId

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
