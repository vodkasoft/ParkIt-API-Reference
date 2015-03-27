# disable

Disables an existing location.

##### HTTP Request

DELETE /locations/:id

## Parameters

| Parameter name | Data Type | Description      |
|:---------------|:----------|:-----------------|
| id             | string    | The location id. |

## Authorization

This request requires admin user authorization.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns an empty response body.

## Example

*Request*

```HTTP
DELETE /locations/sampleLocationsId HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 204 NO CONTENT

```
