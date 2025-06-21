````markdown name=docs/endpoints/user_remove_friend.md
# User Remove Friend

Remove friends or connections using the API – easily unfriend users, manage relationships, and keep social graphs updated.

---

## Endpoint

```
/api/v1.0/user_remove_friend
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                      |
|---------------|----------|---------|----------------------------------|
| api_key_token | Yes      | string  | Your API key                     |
| user_a        | Yes      | integer | UserA ID                         |
| user_b        | Yes      | integer | UserB ID                         |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569249655,
    "payload": {
        "success": true,
        "is_friend": false,
        "request_exists": false
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name          | Type    | Description                                   |
|---------------|---------|-----------------------------------------------|
| success       | boolean | `true` if friend removal was successful       |
| is_friend     | boolean | `false` after removal                         |
| request_exists| boolean | `false` after removal                         |

---

**Remarks:**
- If the request succeeds, you should get code `100` besides the payload.
- All requests must include your API key.
- If you have any questions, you may start a new topic on the community.
````
