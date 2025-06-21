````markdown name=docs/endpoints/groups_requests.md
# Group Member Requests

Retrieve pending group member requests via API – manage join applications, review profiles, and approve/decline members programmatically.

---

## Endpoint

```
/api/v1.0/groups_requests
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                  |
|---------------|----------|---------|------------------------------|
| api_key_token | Yes      | string  | Your API key                 |
| group_guid    | Yes      | integer | The group ID                 |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1569330004,
    "payload": {
        "requests": [
            {
                "guid": "27",
                "first_name": "Meagan",
                "last_name": "McLaughlin",
                "fullname": "Meagan McLaughlin"
                // ... additional fields ...
            }
        ]
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name     | Description                                  |
|----------|----------------------------------------------|
| requests | Array of pending member requests, or `false` if none |

---

**Notes:**
- All requests must include your API key.
- Each pending request includes user details of the requesting member.
````
