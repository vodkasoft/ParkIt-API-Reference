# disable

Disables an existing organization.

##### HTTP Request

DELETE /organizations/:id

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| id             | string    | The organization id. |

## Authorization

This request requires super user authorization.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns an empty response body.

## Example

*Request*

```HTTP
DELETE /organizations/sampleOrganizationId HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 204 NO CONTENT

```
