# Group Add

Add a group for a user.

**Available since OssnServices v6.4.**

---

## Endpoint

```
/api/v1.0/groups_add
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                |
|---------------|----------|---------|--------------------------------------------|
| api_key_token | Yes      | string  | Your API key                               |
| guid          | Yes      | integer | UserID of the group owner                  |
| name          | Yes      | string  | Name of the group                          |
| privacy       | Yes      | integer | 2 = Public, 1 = Closed                     |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "https://dev.opensource-socialnetwork.org/",
    "time_token": 1600880944,
    "payload": {
        "data": {},
        "guid": 69,
        "time_created": 1600880944,
        "owner_guid": 1,
        "description": "",
        "title": "TestGroup",
        "type": "user",
        "subtype": "ossngroup",
        "membership": "2"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name        | Description          |
|-------------|---------------------|
| title       | Name of the group   |
| guid        | Group ID            |
| owner_guid  | Group Owner UserID  |
| membership  | Group Privacy       |

---

**Notes:**
- You must be running Ossn Services 6.4 or later.
- All requests must include your API key.
