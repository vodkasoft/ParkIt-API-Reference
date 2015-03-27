# patch

Updates an existing organization. Can use partial data.

## HTTP Request

PATCH /organizations/:id

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| id             | string    | The organization id. |

## Authorization

This request requires super user authorization.

## Request Body

This request must contain the relevant portions of an
[Organizations resource](README.md#resource-representation).

## Response

If successful, this method returns an
[Organizations resource](README.md#resource-representation).

## Example

*Request*

```HTTP
PATCH /organizations/sampleOrganizationId HTTP/1.1
Host: example.com

{
  "name": "Sample Organization Modified"
}
```

*Response*

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "id": "sampleOrganizationId",
  "name": "Sample Organization Modified",
  "contact": {
    "email": "sample@example.com",
    "telephone": "00000000"
  }
}
```
