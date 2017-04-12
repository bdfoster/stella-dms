# Tokens
Any token issued by the system is actually in the form of a JSON Web Token (JWT). Tokens
are issued to clients for the purposes of acting on behalf of a `user`.

Encoded JWTs will have 3 sections, each of which are encoded as base 64:
```
<header>.<payload>.<signature>
```

### Headers
|Parameter|JSON Type|Description|
|---|---|---|
|`typ`|`string`|Used to declare structural information about the JWT. It will always have a value of `JWT`.|
|`alg`|`string`|Used to declare the algorithm used when signing.|

**NOTICE:** The `alg` header WILL NEVER have a value of `none`, and the system will never accept such a token for authentication.

A typical decoded JWT header looks like this:
```json
{
  "typ": "JWT",
  "alg": "HS256"
}
```
When the bytes of the UTF-8 representation of that header is encoded as base 64: 
```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9
```
### Payload
|Claim|JSON Type|Description|
|---|---|---|
|`sub`|`string`|The identifier of the user. Any requests using the token will be in the context of the specified user.|
|`iss`|`string`|The issuer of the JWT, which will always be the URI of the StellaDMS server.|
|`aud`|`string`|The identifier of the client who requested the token.|
|`nbf`|`number`|The epoch timestamp with respect to when the JWT becomes valid. It is intentionally set to 30 seconds before `iat` to help with differences in server times.|
|`iat`|`number`|The epoch timestamp with respect to when the JWT was issued.|
|`exp`|`number`|The epoch timestamp with respect to when the JWT will expire. Default: 4 hours after `iat`.|
|`jti`|`string`|The token's identifier, which is tied to a database record.|

A typical decoded JWT payload looks like this:
```json
{
  "sub": "bdfoster",
  "iss": "https://dms.example.org",
  "aud": "5c4f32ae-a2d2-406f-8771-1e238aeb550c",
  "nbf": 1492002802,
  "iat": 1492002832,
  "exp": 1492017232,
  "jti": "6deeb85d-3195-4185-96db-72f70ea01e4e"
}
```

When the bytes of the UTF-8 representation of that payload is encoded as base64 (with line breaks for readability):
```
eyJzdWIiOiJiZGZvc3RlciIsImlzcyI6Imh0dHBzOi8vZG1zLmV4YW1wbG
Uub3JnIiwiYXVkIjoiNWM0ZjMyYWUtYTJkMi00MDZmLTg3NzEtMWUyMzhh
ZWI1NTBjIiwibmJmIjoxNDkyMDAyODAyLCJpYXQiOjE0OTIwMDI4MzIsIm
V4cCI6MTQ5MjAxNzIzMiwianRpIjoiNmRlZWI4NWQtMzE5NS00MTg1LTk2
ZGItNzJmNzBlYTAxZTRlIn0
```
### Signature
Each token has a signature. The signature uses the base 64-encoded header and payload of the JWT as the input, and
the requesting client's `secret`.

A `client` will have a `secret` associated with their account. 
For example, `client` "5c4f32ae-a2d2-406f-8771-1e238aeb550c" has this `secret` (which IS issued to the client as 
base 64-encoded):
```
M3NQR3E4aHRUQHEzeUF0JTdOVFl2IWZGXmRoVm1fQ0YyZ1ojcjk5S2htTCRER2ZWeV9iR05fYy1FQEhCTVYyTA
```
The base 64-encoded signature will look like this:
```
ckrE4sRKnagBmR4VjLatkwMiqeZW7UZ6lnEs8FhmONY
```

### Example Token
Using the header, payload, and signature in the examples above, the entire token
looks like this (with line breaks for readability):
```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9
.eyJzdWIiOiJiZGZvc3RlciIsImlzcyI6Imh0dHBzOi8vZG1zLmV4YW1wb
GUub3JnIiwiYXVkIjoiNWM0ZjMyYWUtYTJkMi00MDZmLTg3NzEtMWUyMzh
hZWI1NTBjIiwibmJmIjoxNDkyMDAyODAyLCJpYXQiOjE0OTIwMDI4MzIsI
mV4cCI6MTQ5MjAxNzIzMiwianRpIjoiNmRlZWI4NWQtMzE5NS00MTg1LTk
2ZGItNzJmNzBlYTAxZTRlIn0
.ckrE4sRKnagBmR4VjLatkwMiqeZW7UZ6lnEs8FhmONY
```
