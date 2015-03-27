# Organizations

## Resource representation

```JSON5
{
  "id": string,
  "name": string,
  "contact": {
    "email": string,
    "telephone": string
  }
}
```

| Property name     | Data Type | Description                                           |
|:------------------|:----------|:------------------------------------------------------|
| contact.email     | string    | Email address used for contacting the organization    |
| contact.telephone | string    | Telephone number used for contacting the organization |
| id                | string    | Organization ID. Cannot be changed.                   |
| name              | string    | Organization name.                                    |

## Methods

| Method                | HTTP Request              | Description                                             |
|:----------------------|:--------------------------|:--------------------------------------------------------|
| [create](create.md)   | POST /organizations       | Creates an organization.                                |
| [disable](disable.md) | DELETE /organizations/:id | Disables an existing organization.                      |
| [get](get.md)         | GET /organizations/:id    | Gets one organization by ID.                            |
| [list](list.md)       | GET /organizations        | Retrieves a subset of the organizations.                |
| [patch](patch.md)     | PATCH /organizations/:id  | Updates an existing organization. Can use partial data. |
