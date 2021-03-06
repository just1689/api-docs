# Resource Types

## Get Resource Types

* `GET /v1/:subdomain/resource_types` returns an `Array` of **Resource Types**.
* `GET /v1/:subdomain/resource_types/1` returns a specified **Resource Type**.

### Response

```json
[
  {
    "id": 1,
    "name": "Meeting Room",
    "human": false,
    "custom_fields": [
      {
        "id": 1,
        "name": "Facilities",
        "required": true,
        "custom_field_options": [
          {
            "id": 1,
            "value": "Projector"
          },
          {
            "id": 2,
            "value": "Whiteboard"
          }
        ]
      }
    ],
    "custom_attributes": [
      "capacity"
    ]
  }
]
```

Key | Type | Description
--- | --- | ---
id | integer | Unique identifier for a Resource Type.
name | string | Name of a Resouce Type.
human | boolean | If `true`, then this Resource Type is a person.
custom_fields | array | Custom Fields for this Resource Type. [(Details)](#custom-fields-key)
custom_attributes | array | Custom Attributes for this Resource Type. [(Details)](#custom-attributes-key)

#### Custom Fields Key

Custom fields are created in the UI by users and Custom Field Options are the only allowed values.

Key | Type | Description
--- | --- | ---
id | integer | Unique identifier for a Custom Field.
name | string | Name of a Custom Field.
required | boolean | If `true`, then a value for this field is required.
custom_field_options | array | Custom Field Options for this Custom Field. [(Details)](#custom-field-options-key)

#### Custom Field Options Key

Key | Type | Description
--- | --- | ---
id | integer | Unique identifier for a Custom Field Option.
name | string | Name of a Custom Field Option.

#### Custom Attributes Key

Custom attributes are generated by default once an account is created.

Name | Resource Type | Type | Description
--- | --- | --- | ---
Phone | Person | String | Phone number for a Person.
Capacity | Meeting Room | Integer | Capacity for a Meeting Room.
Registration Number | Vehicle | String | Registration Number for a Vehicle.
