````markdown name=docs/endpoints/user_add.md
# User Add

Add a user into the system.

---

## Endpoint

```
/api/v1.0/user_add
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                 |
|---------------|----------|---------|---------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                |
| firstname     | Yes      | string  | First name                                  |
| lastname      | Yes      | string  | Last name                                   |
| email         | Yes      | string  | User email                                  |
| reemail       | Yes      | string  | User email (again for verification)         |
| gender        | Yes      | string  | Gender (`male`/`female`)                    |
| birthdate     | Yes      | string  | Date of birth (format: `dd/mm/yyyy`)        |
| username      | Yes      | string  | Username (alphanumeric, > 6 characters)     |
| password      | Yes      | string  | User password (> 6 characters)              |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569249655,
    "payload": {
        "guid": "2",
        "first_name": "System",
        "last_name": "Administrator",
        "fullname": "System Administrator",
        "username": "administrator",
        "email": "admin@opensource-socialnetwork.org",
        "birthdate": "03/02/1988",
        "gender": "male"
        // ... additional fields ...
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

If the user could not be added, `payload` will be set to `false`.

## Payload Parameter Description

| Name        | Type   | Description                                             |
|-------------|--------|---------------------------------------------------------|
| guid        | string | User GUID (ID)                                          |
| first_name  | string | User first name                                         |
| last_name   | string | User last name                                          |
| fullname    | string | First + Last name                                       |
| username    | string | Username                                                |
| email       | string | User email                                              |
| birthdate   | string | Date of birth (dd/mm/yyyy)                              |
| gender      | string | `male`/`female`                                         |
| icon        | string | User icon size (small/smaller/large/larger/topbar)      |
| cover_url   | string | URL of cover if set                                     |
| language    | string | ISO 639-1 language code                                 |

---

**Remarks:**
- If the request succeeds, you should get code `100` besides the payload.
- All requests must include your API key.
- If you have any questions, you may start a new topic on the community.
````
