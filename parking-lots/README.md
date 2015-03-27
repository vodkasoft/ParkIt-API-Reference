# Parking Lots

## Resource representation

```JSON5
{
  "id": string,
  "name": string,
  "totalSpaces": int,
  "availableSpaces": int,
  "boundaries": [
    {
      "lat": float,
      "lng": float
    }
  ]
}
```

| Property name    | Data Type | Description                                                                        |
|:-----------------|:----------|:-----------------------------------------------------------------------------------|
| availableSpaces  | integer   | Number of spaces marked as available in a parking lot. Cannot be changed directly. |
| boundaries[]     | list      | List of coordinates that defines a parking lot polygon.                            |
| boundaries[].lat | float     | Latitude of a vertex of a parking lot polygon.                                     |
| boundaries[].lng | float     | Longitude of a vertex of a parking lot polygon.                                    |
| id               | string    | Parking lot ID. Cannot be changed.                                                 |
| name             | string    | Parking lot name.                                                                  |
| totalSpaces      | integer   | Number of spaces in a parking lot. Cannot be changed directly.                     |

## Methods

| Method                | HTTP Request                        | Description                                            |
|:----------------------|:------------------------------------|:-------------------------------------------------------|
| [create](create.md)   | POST /locations/:locId/parking-lots | Creates a parking lot.                                 |
| [disable](disable.md) | DELETE /parking-lots/:id            | Disables an existing parking lot.                      |
| [get](get.md)         | GET /parking-lots/:id               | Gets one parking lot by ID.                            |
| [list](list.md)       | GET /locations/:locId/parking-lots  | Retrieves a subset of the parking lots.                |
| [patch](patch.md)     | PATCH /parking-lots/:id             | Updates an existing parking lot. Can use partial data. |
