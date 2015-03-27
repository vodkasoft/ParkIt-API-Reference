# Authentication

All endpoints that manage resources (organizations, locations, parking spaces
and parking lots) require authentication. The password challenge mechanism is
insecure and expensive if performed for every request; therefore, the system
utilizes a token-based authentication scheme for these endpoints.

## Token Request

To obtain an access token the client must create a POST request to the
authentication endpoint */auth/token*. The client must include the user's
credentials in the *Authorization* header of the request as required by the
[basic authentication scheme](http://en.wikipedia.org/wiki/Basic_access_authentication).
A token request should look like follows:

```HTTP
POST /auth/token HTTP/1.1
Host: example.com
Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==

```

The response for this request will be a message containing the access token. The
message also indicates the type of access token and the number of seconds before
the access token expires.

```HTTP
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8

{
  "token_type": "bearer",
  "access_token": "e72e16c7e42f292d6912e7710c838347af178b4a",
  "expires_in": 3600
}
```

## Request Authentication

All requests that require authentication (apart from the access token creation)
require an access token. The client must include the access token in the
request's *Authorization* header. The client must also indicate that it wishes
to authentication using an access token by including the work *Bearer* before
the token. An authenticated request using an access token should look like
follows:

```HTTP
GET /organizations HTTP/1.1
Host: example.com
Authorization: Bearer e72e16c7e42f292d6912e7710c838347af178b4a

```

## Token Expiration

The access token will eventually expire. The expiration time is added to the
token to ensure that authenticated access is not compromised indefinitely if
an access token is compromised. The access token should expire an hour after
it has been generated, but the actual expiration should be decided by the
backend.
