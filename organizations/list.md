# list

Retrieves a subset of the organizations.

## HTTP Request

GET /organizations

## Optional Parameters

| Parameter name | Data Type        | Description                                                                       |
|:---------------|:-----------------|:----------------------------------------------------------------------------------|
| page           | unsigned integer | Number of the page that should be returned. If not set, the default is 1.         |
| per_page       | unsigned integer | Maximum number of entries that should be returned. If not set, the default is 30. |

## Authorization

This request requires super user authorization.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns a response body with the following structure:

```JSON5
{
  "organizations": [
    organizations Resource
  ]
}
```

| Property name     | Data Type | Description                                                       |
|:------------------|:----------|:------------------------------------------------------------------|
| organizations[]   | list      | A list of [organizations](README.md#resource-representation) |

## Example

*Request*

```HTTP
GET /organizations?page=7&per_page=10 HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "organizations": [
    {
      "id": "sampleOrganizationId",
      "name": "Sample Organization",
      "contact": {
        "email": "sample@example.com",
        "telephone": "00000000"
      }
    },
    {
      "id": "anotherOrganizationId",
      "name": "Another Organization",
      "contact": {
        "email": "another@example.com",
        "telephone": "11111111"
      }
    }
  ]
}
```
