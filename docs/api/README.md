# API
StellaDMS uses a RESTful API for external access to all resources in the system. Below, 
you'll find an overview of all system 

### Users API
**Resource Type:** `user`

|HTTP Method|Endpoint                      |Function                                         |Action Class(es)|
|-----------|------------------------------|-------------------------------------------------|----------------|
|`POST`     |`/api/v1/users`               |Create a user account.                           |`create`        |
|`GET`      |`/api/v1/users/:id`           |Get a specific user account.                     |`read`          |
|`GET`      |`/api/v1/users`               |Get a list of users, with optional filtering.    |`search`        |
|`PATCH`    |`/api/v1/users/:id`           |Update a specific user account.                  |`update`        |
|`DELETE`   |`/api/v1/users/:id`           |Delete a specific user account.                  |`delete`        |
|`POST`     |`/api/v1/auth/user`           |Authenticate/Authorize a user account.           |`auth`          |


### Clients API
**Resource Type:** `client`

|HTTP Method|Endpoint                      |Function                                         |Action Class(es)|
|-----------|------------------------------|-------------------------------------------------|----------------|
|`POST`     |`/api/v1/clients`             |Create a client account.                         |`create`        |
|`GET`      |`/api/v1/clients/:id`         |Get a specific client account.                   |`read`          |
|`GET`      |`/api/v1/clients`             |Get a list of clients, with optional filtering.  |`search`        |
|`PATCH`    |`/api/v1/clients/:id`         |Update a specific client account.                |`update`        |
|`DELETE`   |`/api/v1/clients/:id`         |Delete a specific client account.                |`delete`        |

### Tags API
**Resource Type:** `tag`

|HTTP Method|Endpoint                      |Function                                         |Action Class(es)|
|-----------|------------------------------|-------------------------------------------------|----------------|
|`POST`     |`/api/v1/tags`                |Create a tag.                                    |`create`        |
|`GET`      |`/api/v1/tags/:id`            |Get a specific tag and all linked documents.     |`read`          |
|`GET`      |`/api/v1/tags`                |Get a list of tags, with optional filtering.     |`search`        |
|`PATCH`    |`/api/v1/tags/:id`            |Update a specific tag's data.                    |`update`        |
|`DELETE`   |`/api/v1/tags/:id`            |Delete a specific tag.                           |`delete`        |

### Documents API
**Resource Type:** `doc`

|HTTP Method|Endpoint                      |Function                                         |Action Class(es)|
|-----------|------------------------------|-------------------------------------------------|----------------|
|`POST`     |`/api/v1/docs`                |Create a document.                               |`create`        |
|`GET`      |`/api/v1/docs/:id`            |Get a specific document's data.                  |`read`          |
|`GET`      |`/api/v1/docs`                |Get a list of documents, with optional filtering.|`search`        |
|`PATCH`    |`/api/v1/docs/:id`            |Update a specific document's data.               |`update`        |
|`DELETE`   |`/api/v1/docs/:id`            |Delete a specific document.                      |`delete`        |

### Groups API
**Resource Type:** `group`

|HTTP Method|Endpoint                      |Function                                         |Action Class(es)|
|-----------|------------------------------|-------------------------------------------------|----------------|
|`POST`     |`/api/v1/groups`              |Create a group.                                  |`create`        |
|`GET`      |`/api/v1/groups/:id`          |Get a specific groups's data.                    |`read`          |
|`GET`      |`/api/v1/groups`              |Get a list of groups, with optional filtering.   |`search`        |
|`PATCH`    |`/api/v1/groups/:id`          |Update a specific group's data.                  |`update`        |
|`DELETE`   |`/api/v1/groups/:id`          |Delete a specific document.                      |`delete`        |
