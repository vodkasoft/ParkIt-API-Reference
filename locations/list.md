# list

Retrieves a subset of the locations.

## HTTP Request

GET /locations

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
  "locations": [
    locations Resource
  ]
}
```

| Property name | Data Type | Description                                              |
|:--------------|:----------|:---------------------------------------------------------|
| locations[]   | list      | A list of [locations](README.md#resource-representation) |

## Example

*Request*

```HTTP
GET /locations?page=7&per_page=10 HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "locations": [
    {
      "id": "sampleLocationId",
      "name": "Sample Location",
      "location": {
        "lat": 37.4217550,
        "lng": -122.0846330
      }
    },
    {
      "id": "anotherLocationId",
      "name": "Another Location",
      "location": {
        "lat": 47.4217550,
        "lng": -112.0846330
      }
    }
  ]
}
```
