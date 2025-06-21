````markdown name=docs/endpoints/groups_unjoin.md
# Group Unjoin

Unjoin a specific group.

---

## Endpoint

```
/api/v1.0/groups_unjoin
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                               |
|---------------|----------|---------|-------------------------------------------|
| api_key_token | Yes      | string  | Your API key                              |
| group_guid    | Yes      | integer | The group ID                              |
| guid          | Yes      | integer | User GUID who is unjoining the group      |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569329343,
    "payload": {
        "group": {
            "guid": "7",
            "title": "Test Group",
            // ... additional group fields ...
            "ismember": false,
            "request_exists": false
            // ... additional group fields ...
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name                | Description                        |
|---------------------|------------------------------------|
| group.ismember      | Always `false` (not a member)      |
| group.request_exists| Always `false` (no join request)   |

---

**Notes:**
- All requests must include your API key.
- This endpoint can be used to remove a user from a group.
````
