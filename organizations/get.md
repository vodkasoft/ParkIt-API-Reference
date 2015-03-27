# get

Gets one organization by ID.

## HTTP Request

GET /organizations/:id

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| id             | string    | The organization id. |

## Authorization

This request requires super user authorization.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns an
[Organizations resource](README.md#resource-representation).

## Example

*Request*

```HTTP
GET /organizations/sampleOrganizationId HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleOrganizationId",
  "name": "Sample Organization",
  "contact": {
    "email": "sample@example.com",
    "telephone": "00000000"
  }
}
```
