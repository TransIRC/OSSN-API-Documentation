````markdown name=docs/endpoints/user_add_friend.md
# User Send Friend Request

Dual-purpose API: Send friend requests and accept them with identical parameters.

---

## Endpoint

```
/api/v1.0/user_add_friend
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description           |
|---------------|----------|---------|-----------------------|
| api_key_token | Yes      | string  | Your API key          |
| user_a        | Yes      | integer | UserA ID              |
| user_b        | Yes      | integer | UserB ID              |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569249655,
    "payload": {
        "is_friend": false,
        "request_exists": true
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name           | Type    | Description                                              |
|----------------|---------|----------------------------------------------------------|
| is_friend      | boolean | `true` if users are friends with each other              |
| request_exists | boolean | `true` if a friend request exists between the users      |

---

**Remarks:**
- If the request succeeds, you should get code `100` besides the payload.
- All requests must include your API key.
- If you have any questions, you may start a new topic on the community.
````
