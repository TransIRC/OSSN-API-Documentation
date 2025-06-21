````markdown name=docs/endpoints/notifications_count.md
# Notifications Count

Count notifications including friend requests, messages, and general notifications for a user.

---

## Endpoint

```
/api/v1.0/notifications_count
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                                   |
|---------------|----------|---------|-----------------------------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                                  |
| guid          | Yes      | integer | The user GUID you want to count notifications for                                             |
| types         | No       | string  | Comma-separated notification types (e.g. `'typedef,typeabc'`). Does not affect friends/messages count. |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569332866,
    "payload": {
        "notifications": "1",
        "messages": "1",
        "friends": 4
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name          | Description                                   |
|---------------|-----------------------------------------------|
| notifications | Number of general notifications               |
| messages      | Number of unread messages                     |
| friends       | Number of pending friend requests             |

---

**Notes:**
- All requests must include your API key.
- The `types` parameter filters notification types but does not affect the count for friend requests or messages.
````
