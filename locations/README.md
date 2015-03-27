# Locations

## Resource representation

```JSON5
{
  "id": string,
  "name": string
  "location": {
    "lat": float,
    "lng": float
  }
}
```

| Property name | Data Type | Description                                                      |
|:--------------|:----------|:-----------------------------------------------------------------|
| id            | string    | Organization ID. Cannot be changed.                              |
| location.lat  | float     | Latitude of the geocoded location of the organization location.  |
| location.lng  | float     | Longitude of the geocoded location of the organization location. |
| name          | string    | Organization name.                                               |

## Methods

| Method                | HTTP Request          | Description                                         |
|:----------------------|:----------------------|:----------------------------------------------------|
| [create](create.md)   | POST /locations       | Creates a location.                                 |
| [disable](disable.md) | DELETE /locations/:id | Disables an existing location.                      |
| [get](get.md)         | GET /locations/:id    | Gets one location by ID.                            |
| [list](list.md)       | GET /locations        | Retrieves a subset of the locations.                |
| [patch](patch.md)     | PATCH /locations/:id  | Updates an existing location. Can use partial data. |
