# Person
A reference to a human.

### Properties
|Key|Type|Description|Required|
|---|---|---|---|
|`id`|`string`|Primary key, must be in UUIDv4 format.|Yes|
|`given_name`|`string`|The person's given (or first) name.|Yes|
|`middle_name`|`string`|The person's middle name.|No|
|`family_name`|`string`|The person's family (or last) name.|Yes|
|`display_name`|`string`|Computed based on `given_name`, `family_name`, and optionally `middle_name`.|N/A|
|`birth_date`|`date`|The person's birth date.|No|
|`picture`|`string`|A URL or URI pointing to the person's picture.|No|
