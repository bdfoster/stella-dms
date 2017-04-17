# API
StellaDMS uses a RESTful API for external access to all resources in the system. Below, 
you'll find a categorical overview of all the endpoints available and some helpful information for each.

### Authentication/Authorization
**Description:** Authenticate and authorize accounts.

|HTTP Method|Endpoint|Function|Scope(s)|
|---|---|---|---|
|`POST`|`/api/v1/auth`|Authenticate and subsequently issue JWT with authorization scopes.|N/A|
|`DELETE`|`/api/v1/auth`|Invalidate previously issued JWT.|N/A|

### Users
**Description:** Manage and configure user accounts.

|HTTP Method|Endpoint|Function|Scope(s)|
|---|---|---|---|
|`POST`|`/api/v1/users`|Create a user account.|`user:create`|
|`GET`|`/api/v1/users/:id`|Get a specific user account.|`user:read`|
|`GET`|`/api/v1/users`|Get a list of users, with optional filtering.|`user:search`|
|`PATCH`|`/api/v1/users/:id`|Update a specific user account.|`user:update`|
|`DELETE`|`/api/v1/users/:id`|Delete a specific user account.|`user:delete`|


### Clients
**Description:** Manage and configure client accounts.

|HTTP Method|Endpoint|Function|Scope(s)|
|---|---|---|---|
|`POST`|`/api/v1/clients`|Create a client account.|`client:create`|
|`GET`|`/api/v1/clients/:id`|Get a specific client account.|`client:read`|
|`GET`|`/api/v1/clients`|Get a list of clients, with optional filtering.|`client:search`|
|`PATCH`|`/api/v1/clients/:id`|Update a specific client account.|`client:update`|
|`DELETE`|`/api/v1/clients/:id`|Delete a specific client account.|`client:delete`|

### Tags
**Description:** Manage and configure document tags.

|HTTP Method|Endpoint|Function|Scope(s)|
|---|---|---|---|
|`POST`|`/api/v1/tags`|Create a tag.|`tag:create`|
|`GET`|`/api/v1/tags/:id`|Get a specific tag and all linked documents.|`tag:read`|
|`GET`|`/api/v1/tags`|Get a list of tags, with optional filtering.|`tag:search`|
|`PATCH`|`/api/v1/tags/:id`|Update a specific tag's data.|`tag:update`|
|`DELETE`|`/api/v1/tags/:id`|Delete a specific tag.|`tag:delete`|

### Documents
**Description:** Create and manage documents.

|HTTP Method|Endpoint|Function|Scope(s)|
|---|---|---|---|
|`POST`|`/api/v1/docs` |Create a document.|`doc:create`|
|`GET`|`/api/v1/docs/:id`|Get a specific document's data.|`doc:read`|
|`GET`|`/api/v1/docs`|Get a list of documents, with optional filtering.|`doc:search`|
|`PATCH`|`/api/v1/docs/:id`|Update a specific document's data.|`doc:update`|
|`DELETE`|`/api/v1/docs/:id`|Delete a specific document.|`doc:delete`|

### Groups
**Description:** Manage and configure account groups.

|HTTP Method|Endpoint|Function|Scope(s)|
|---|---|---|---|
|`POST`|`/api/v1/groups`|Create a group.|`group:create`|
|`GET`|`/api/v1/groups/:id`|Get a specific groups's data.|`group:read`|
|`GET`|`/api/v1/groups`|Get a list of groups, with optional filtering.|`group:search`|
|`PATCH`|`/api/v1/groups/:id`|Update a specific group's data.|`group:update`|
|`DELETE`|`/api/v1/groups/:id`|Delete a specific document.|`group:delete`|
