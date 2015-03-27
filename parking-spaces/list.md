# list

Retrieves a subset of the parking spaces in a parking lot.

## HTTP Request

GET /parking-lots/:lotId/spaces

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| lotId          | string    | The parking lot id.  |

## Optional Parameters

| Parameter name | Data Type        | Description                                                                       |
|:---------------|:-----------------|:----------------------------------------------------------------------------------|
| page           | unsigned integer | Number of the page that should be returned. If not set, the default is 1.         |
| per_page       | unsigned integer | Maximum number of entries that should be returned. If not set, the default is 30. |

## Authorization

This request requires admin user authorization. The user must be a member of the
organization that owns the parking lot.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns a response body with the following structure:

```JSON5
{
  "spaces": [
    parking spaces Resource
  ]
}
```

| Property name | Data Type | Description                                                   |
|:--------------|:----------|:--------------------------------------------------------------|
| spaces[]      | list      | A list of [parking spaces](README.md#resource-representation) |

## Example

*Request*

```HTTP
GET /parking-lots/sampleParkingLot/spaces?page=7&per_page=10 HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "spaces": [
    {
      "id": "sampleParkingSpaceId",
      "number": "50",
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
    },
    {
      "id": "anotherParkingSpaceId",
      "number": "51",
      "state": "vacant",
      "reserved": true,
      "sensor": {
        "id": "anotherSensorId",
        "serialNumber": "anotherSensorSerialNumber",
      },
      "location": {
        "lat": 37.2217550,
        "lng": -122.0856330
      }
    }
  ]
}
```
