# create

Creates a location.

## HTTP Request

POST /locations

## Authorization

This request requires admin user authorization.

## Request Body

The request body must be a
[Locations resource](README.md#resource-representation) with the
following properties:

| Property name  | Data Type | Description                                                      |
|:---------------|:----------|:-----------------------------------------------------------------|
| location.lat   | float     | Latitude of the geocoded location of the organization location.  |
| location.lng   | float     | Longitude of the geocoded location of the organization location. |
| name           | string    | Organization name.                                               |

##### Response

If successful, this method returns a
[Locations resource](README.md#resource-representation).

##### Example

*Request*

```HTTP
POST /locations HTTP/1.1
Host: example.com

{
  "name": "Sample Location",
  "location": {
    "lat": 37.4217550,
    "lng": -122.0846330
  }
}
```

*Response*

```HTTP
HTTP/1.1 201 CREATED
Content-Type: application/json; charset=utf-8
Location: https://example.com/locations/sampleLocationId

{
  "id": "sampleLocationId",
  "name": "Sample Location",
  "location": {
    "lat": 37.4217550,
    "lng": -122.0846330
  }
}
```
