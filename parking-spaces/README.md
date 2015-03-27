# Parking Spaces

## Resource representation

```JSON5
{
  "id": string,
  "number": string,
  "state": string,
  "reserved": boolean,
  "sensor": {
    "id": string,
    "serialNumber": string,
  },
  "location": {
    "lat": float,
    "lng": float
  }
}
```

| Property name       | Data Type | Description                                                                    |
|:--------------------|:----------|:-------------------------------------------------------------------------------|
| id                  | string    | Parking space ID. Cannot be changed.                                           |
| location.lat        | float     | Latitude of the geocoded location of the parking space.                        |
| location.lng        | float     | Longitude of the geocoded location of the parking space.                       |
| number              | string    | Number assigned to the parking space. Should be unique in each parking lot.    |
| reserved            | boolean   | Whether the parking space is marked as reserved or not.                        |
| sensor.id           | string    | Sensor ID. Should only be changed when a sensor is replaced.                   |
| sensor.serialNumber | string    | Serial number of the sensor that is placed at the parking space.               |
| state               | string    | Current state of the parking space. Can be "vacant", "occupied" or "disabled". |

## Methods

| Method                | HTTP Request                     | Description                                                |
|:----------------------|:---------------------------------|:-----------------------------------------------------------|
| [create](create.md)   | POST /parking-lots/:lotId/spaces | Creates a parking space.                                   |
| [disable](disable.md) | DELETE /spaces/:id               | Disables an existing parking space.                        |
| [get](get.md)         | GET /spaces/:id                  | Gets one parking space by ID.                              |
| [list](list.md)       | GET /parking-lots/:lotId/spaces  | Retrieves a subset of the parking spaces in a parking lot. |
| [patch](patch.md)     | PATCH /spaces/:id                | Updates an existing parking space. Can use partial data.   |
