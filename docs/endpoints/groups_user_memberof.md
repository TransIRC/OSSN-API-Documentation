````markdown name=docs/endpoints/groups_user_memberof.md
# User Member of Groups List

Retrieve all groups a user is a member of via API.

---

## Endpoint

```
/api/v1.0/groups_user_memberof
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description       |
|---------------|----------|---------|-------------------|
| api_key_token | Yes      | string  | Your API key      |
| guid          | Yes      | integer | User GUID         |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569328753,
    "payload": {
        "groups": [
            {
                "data": {},
                "guid": "7",
                "time_created": "1568224071",
                "owner_guid": "2",
                "description": "New group about",
                "title": "Test Group",
                "type": "user",
                "subtype": "ossngroup",
                "membership": "1",
                "file:cover": "cover/34a90cd7181716160fe5751a3862167b.jpg",
                "cover": "[\"-329\",\"0\"]",
                "coverurl": "http://www.mywebsite.com/groups/cover/214/34a90cd7181716160fe5751a3862167b.jpg"
            }
        ]
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name   | Description                                  |
|--------|----------------------------------------------|
| groups | Array of groups, or null/false if no groups  |

---

**Notes:**
- All requests must include your API key.
- Each group object contains details such as group ID, title, description, owner GUID, cover image, and more.
````
