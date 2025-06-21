````markdown name=docs/endpoints/user_friend_requests.md
# Friend Requests

Get friend requests for a user.

---

## Endpoint

```
/api/v1.0/user_friend_requests
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description        |
|---------------|----------|---------|--------------------|
| api_key_token | Yes      | string  | Your API key       |
| guid          | Yes      | integer | User ID            |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569248807,
    "payload": {
        "total": "9",
        "requests": [
            {
                "guid": "32",
                "first_name": "Gloria",
                "last_name": "Ernser",
                "fullname": "Gloria Ernser",
                "username": "Tyrel32",
                "email": "gBeier@example.org",
                "birthdate": "06/09/2019",
                "gender": "male",
                "icon": {
                    "topbar": "http://www.mywebsite.com/avatar/Tyrel32/topbar/e857e6e8a0c21d69a71f8470c8755232.jpeg",
                    "smaller": "http://www.mywebsite.com/avatar/Tyrel32/smaller/5a9ed4e28c259f3bf6e3861210a697ae.jpeg",
                    "small": "http://www.mywebsite.com/avatar/Tyrel32/small/3e878131e2c154c47e21bd29b94d3f00.jpeg",
                    "larger": "http://www.mywebsite.com/avatar/Tyrel32/larger/9019792ce5a39564a31b69a9773c556f.jpeg",
                    "large": "http://www.mywebsite.com/avatar/Tyrel32/large/6d3ea442868f2fc196a9605b358e5c26.jpeg"
                },
                "cover_url": false,
                "language": null
            },
            {
                "guid": "28",
                "first_name": "Shaun",
                "last_name": "Stracke",
                "fullname": "Shaun Stracke",
                "username": "Kolby51",
                "email": "Dayana.Gottlieb@example.org",
                "birthdate": "06/09/2019",
                "gender": "male",
                "icon": {
                    "topbar": "http://www.mywebsite.com/avatar/Kolby51/topbar/cec7c33bd14ad1bc7494f7136d21d113.jpeg",
                    "smaller": "http://www.mywebsite.com/avatar/Kolby51/smaller/50b51920fb50eb7dc34f564f82703712.jpeg",
                    "small": "http://www.mywebsite.com/avatar/Kolby51/small/507b79e629592d33a9aa56626c2415e3.jpeg",
                    "larger": "http://www.mywebsite.com/avatar/Kolby51/larger/8da158846dcd0ee43836d4f725b409cd.jpeg",
                    "large": "http://www.mywebsite.com/avatar/Kolby51/large/b8f05c23726d062393437722a41b16be.jpeg"
                },
                "cover_url": false,
                "language": null
            }
            // ... more requests ...
        ],
        "offset": false
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

Each friend request object contains:

| Name        | Type   | Description                                         |
|-------------|--------|-----------------------------------------------------|
| guid        | string | User GUID (ID)                                      |
| first_name  | string | User first name                                     |
| last_name   | string | User last name                                      |
| fullname    | string | First + Last name                                   |
| username    | string | Username                                            |
| email       | string | User email                                          |
| birthdate   | string | Date of birth (dd/mm/yyyy)                          |
| gender      | string | `male`/`female`                                     |
| icon        | object | User icon URLs (small, smaller, large, etc.)        |
| cover_url   | string | URL of cover if set                                 |
| language    | string | ISO 639-1 language code                             |

---

**Remarks:**
- If the request succeeds, you should get code `100` besides the payload.
- All requests must include your API key.
- If you have any questions, you may start a new topic on the community.
````
