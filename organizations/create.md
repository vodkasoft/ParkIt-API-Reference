# create

Creates an organization.

## HTTP Request

POST /organizations

## Authorization

This request requires super user authorization.

## Request Body

The request body must be an
[Organizations resource](README.md#resource-representation) with the
following properties:

| Property name     | Data Type | Description                                           |
|:------------------|:----------|:------------------------------------------------------|
| contact.email     | string    | Email address used for contacting the organization    |
| contact.telephone | string    | Telephone number used for contacting the organization |
| name              | string    | Organization name.                                    |

##### Response

If successful, this method returns an
[Organizations resource](README.md#resource-representation).

##### Example

*Request*

```HTTP
POST /organizations HTTP/1.1
Host: example.com

{
  "name": "Sample Organization",
  "contact": {
    "email": "sample@example.com",
    "telephone": "00000000"
  }
}
```

*Response*

```HTTP
HTTP/1.1 201 CREATED
Content-Type: application/json; charset=utf-8
Location: https://example.com/organizations/sampleOrganizationId

{
  "id": "sampleOrganizationId",
  "name": "Sample Organization",
  "contact": {
    "email": "sample@example.com",
    "telephone": "00000000"
  }
}
```
