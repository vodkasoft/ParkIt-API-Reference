# disable

Disables an existing parking lot.

##### HTTP Request

DELETE /parking-lots/:id

## Parameters

| Parameter name | Data Type | Description          |
|:---------------|:----------|:---------------------|
| id             | string    | The parking lot id.  |

## Authorization

This request requires admin user authorization. The user must be a member of the
organization that owns the parking lot.

## Request Body

This request should not contain a request body.

## Response

If successful, this method returns an empty response body.

## Example

*Request*

```HTTP
DELETE /parking-lots/sampleParkingLotId HTTP/1.1
Host: example.com

```

*Response*

```HTTP
HTTP/1.1 204 NO CONTENT

```
