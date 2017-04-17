# User
A reference to a human's account.

### Properties
|Key|Type|Description|Required|
|---|---|---|---|
|`id`|`string`|Primary key, alphanumeric characters only (plus "_").|Yes|
|`profile`|`string`|A reference to the applicable Profile.|Yes|
|`password`|`string`|The user's password (hashed in the database).|Yes|
|`active`|`boolean`|If `true` (default), allows user to authenticate.|Yes|
