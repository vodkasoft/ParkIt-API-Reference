# list

Retrieves a subset of the parking lots.

## HTTP Request

GET /locations/:locId/parking-lots

## Parameters

| Parameter name | Data Type | Description       |
|:---------------|:----------|:------------------|
| locId          | string    | The location id.  |

## Optional Parameters

| Parameter name | Data Type        | Description                                                                       |
|:---------------|:-----------------|:----------------------------------------------------------------------------------|
| page           | unsigned integer | Number of the page that should be returned. If not set, the default is 1.         |
| per_page       | unsigned integer | Maximum number of entries that should be returned. If not set, the default is 30. |

## Authorization

This request requires admin user authorization.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns a response body with the following structure:

```JSON5
{
  "parkingLots": [
    parking lots Resource
  ]
}
```

| Property name | Data Type | Description                                                 |
|:--------------|:----------|:------------------------------------------------------------|
| parkingLots[] | list      | A list of [parking lots](README.md#resource-representation) |

## Example

*Request*

```HTTP
GET /locations/sampleLocationId/parking-lots?page=7&per_page=10 HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "parkingLots": [
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
    },
    {
      "id": "anotherParkingLotId",
      "name": "Another Parking Lot",
      "totalSpaces": 50,
      "availableSpaces": 15,
      "boundaries": [
        {
          "lat": 47.4217550,
          "lng": -122.0846330
        },
        {
          "lat": 47.2217550,
          "lng": -122.0846330
        },
        {
          "lat": 47.4217550,
          "lng": -122.1846330
        }
      ]
    }
  ]
}
```
