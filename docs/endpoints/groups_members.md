````markdown name=docs/endpoints/groups_members.md
# Group Members

Get a list of group members.

---

## Endpoint

```
/api/v1.0/groups_members
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                              |
|---------------|----------|---------|----------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                             |
| group_guid    | Yes      | integer | The group ID                                             |
| offset        | No       | integer | Pagination offset (if count > 10, set to 1, 2, 3...)     |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1569330120,
    "payload": {
        "members": [
            {
                "guid": "26",
                "first_name": "Eldridge",
                "last_name": "Runte",
                "fullname": "Eldridge Runte"
                // ... additional fields ...
            },
            {
                "guid": "29",
                "first_name": "Aniyah",
                "last_name": "Ondricka",
                "fullname": "Aniyah Ondricka"
                // ... additional fields ...
            },
            {
                "guid": "1",
                "first_name": "System",
                "last_name": "Administrator",
                "fullname": "System Administrator"
                // ... additional fields ...
            }
        ],
        "count": "3",
        "offset": 1
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name    | Description                           |
|---------|---------------------------------------|
| members | Array of members, or `false` if none  |
| count   | Total number of members               |
| offset  | Current pagination number             |

---

**Notes:**
- All requests must include your API key.
- Use `offset` for pagination when there are more than 10 members.
````
