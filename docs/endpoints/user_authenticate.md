````markdown name=docs/endpoints/user_authenticate.md
# User Authenticate

Authenticate username and password for a user.

---

## Endpoint

```
/api/v1.0/user_authenticate
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                           |
|---------------|----------|---------|---------------------------------------|
| api_key_token | Yes      | string  | Your API key                          |
| username      | Yes      | string  | Username or Email                     |
| password      | Yes      | string  | User password                         |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569249655,
    "payload": {
        "guid": "1",
        "first_name": "System",
        "last_name": "Administrator",
        "fullname": "System Administrator",
        "username": "administrator",
        "email": "admin@opensource-socialnetwork.org",
        "birthdate": "03/02/1988",
        "gender": "male",
        "icon": {
            "topbar": "http://www.mywebsite.com/avatar/administrator/topbar/63607d3306a93f7b46fa6053804fb654.jpeg",
            "smaller": "http://www.mywebsite.com/avatar/administrator/smaller/6fccce7ebeed8588d2d8ea6b1885b2ab.jpeg",
            "small": "http://www.mywebsite.com/avatar/administrator/small/dffbce57613957579d1cb3e4bf75fe15.jpeg",
            "larger": "http://www.mywebsite.com/avatar/administrator/larger/7c98c47e931c1395dceb50ea5d745957.jpeg",
            "large": "http://www.mywebsite.com/avatar/administrator/large/90345a0b905421c38dcb554c465fcca7.jpeg"
        },
        "cover_url": false,
        "language": "en"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name        | Type   | Description                                       |
|-------------|--------|---------------------------------------------------|
| guid        | string | User GUID (ID)                                    |
| first_name  | string | User first name                                   |
| last_name   | string | User last name                                    |
| fullname    | string | First + Last name                                 |
| username    | string | Username                                          |
| email       | string | User email                                        |
| birthdate   | string | Date of birth (dd/mm/yyyy)                        |
| gender      | string | `male`/`female`                                   |
| icon        | object | User icon URLs (small, smaller, large, etc.)      |
| cover_url   | string | URL of cover if it is set                         |
| language    | string | ISO 639-1 language code                           |

---

**Remarks:**
- If the username and password are correct, you will see user details in the payload.
- If not:
    - Error 105: Invalid username and password
    - Error 104: User not validated
- If the request succeeds, you should get code `100` besides the payload.
- All requests must include your API key.
- If you have any questions, you may start a new topic on the community.
````
