## Scopes

StellaDMS uses scopes to define access levels granted to a specific `user` or `client`.
A scope is a combination of a resource type, action class, and optionally a resource identifier.
Each resource type has a defined set of action classes, and optionally those action classes
can be specific to a resource. Scopes take the format of:
```
<RESOURCE_TYPE>:<ACTION_CLASS>[:<RESOURCE_ID>]
```
For example, an account that is given a `user:create` scope can create `user` resource 
types in the system through the User API. However, an account that is given a 
`user:read:bdfoster` scope can only get the information of a particular `user`
(in this case, the user with an ID of `bdfoster`).

All API endpoints are associated with a particular scope, and resource types
will never take a plural form. Scopes which map to an endpoint containing `:id`
will respect the optional resource identifier (`RESOURCE_ID`, the third section in the scope).

### Resource Types
#### `user`
Representation of an account that is mappable to a human.

##### Action Classes
|Name|Endpoints|
|--- |---      |
|`create`|`POST /api/v1/user`|
|`read`|`GET /api/v1/user`, `GET /api/v1/user/:id`|
|`update`|`PUT /api/v1/user/:id`|
|`delete`|`DELETE /api/v1/user/:id`|
|`identify`|`POST /api/v1/user/auth`|

#### `client`
Representation of an account that is mappable to an application.

##### Action Classes
|Name|Endpoints|
|--- |---      |
|`create`|`POST /api/v1/client`|
|`read`|`GET /api/v1/client/:id`|
|`search`|`GET /api/v1/client`|
|`update`|`PUT /api/v1/client/:id`|
|`delete`|`DELETE /api/v1/client/:id`|
|`auth`|`POST /api/v1/client/auth`|

#### `group`
Representation of a set of accounts and permissions assigned to each.

##### Action Classes
|Name|Endpoints|
|--- |---      |
|`create`|`POST /api/v1/group`|
|`read`|`GET /api/v1/group`, `GET /api/v1/group/:id`|
|`update`|`PUT /api/v1/group/:id`|
|`delete`|`DELETE /api/v1/group/:id`|
|`assign`|`POST /api/v1/group/:id/user`|

#### `tag`
Representation of a group of `document` resource types.

#### `document`
Representation of a database record with an associated MIME type.
