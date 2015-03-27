# ParkIt API Reference

API reference for the backend service for the ParkIt system. The following is a
list of the most important resources that are made available:

* [Organizations](organizations/README.md)
* [Locations](locations/README.md)
* [Parking Lots](parking-lots/README.md)
* [Parking Spaces](parking-spaces/README.md)

Before accessing these resources the client must request an authorization token.
The authorization token will eventually expire and a new one must be requested.
A more thorough explanation can be found in the
[Authentication](authentication.md) page.

## User Roles

There are two mutually exclusive user roles defined in the system. The first
role is called the *super user*, users under this role can manage organizations
without any restrictions but are not allow to view or manage the resources that
belong to these organizations (locations, parking lots and parking spaces). The
other possible role that a user can have is the *admin user* role. An admin user
can manage all the resources of an organization; nevertheless, the admin user
is limited to a single organization, it has no knowledge of the existence of
other organizations.

## User and Organization Data

When logged as an admin user the client does not need to specify the
organization id. The backend will get this data from the authorization token
that is sent in every request.

## Error Responses

In case of an error the backend will send the appropriate
[HTTP status code](http://httpstatus.es/) along with an error object in the
response body with the following structure:

```JSON5
{
  "error": {
    "type": string,
    "message": string
  }
}
```

| Property name | Data Type | Description                                |
|:--------------|:----------|:-------------------------------------------|
| message       | string    | Message explaining the cause of the error. |
| type          | string    | The type of error that occurred.           |


## Notes

The JSON objects in the requests and responses in this API reference have been
formatted with proper indentation to aid legibility; the objects in the actual
requests and responses will appear in a compressed format.
