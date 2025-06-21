````markdown name=docs/endpoints/message_add.md
# Message Send

Send a message to a user, with the option to include an attachment.

---

## Endpoint

```
/api/v1.0/message_add
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                 |
|---------------|----------|---------|---------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                |
| from          | Yes      | integer | User ID sending the message                 |
| to            | Yes      | integer | User ID receiving the message               |
| message       | Yes      | string  | The message text                            |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569337165,
    "payload": {
        "id": "46",
        "message_from": {
            "guid": "1",
            "fullname": "System Administrator",
            "username": "administrator",
            "icon": {
                "small": "http://www.mywebsite.com/avatar/administrator/small/ddfbc9f412fca49cd89c8592b6500269.jpeg"
            }
        },
        "message_to": {
            "guid": "27",
            "fullname": "Meagan McLaughlin",
            "username": "zKutch",
            "icon": {
                "small": "http://www.mywebsite.com/avatar/zKutch/small/8715c874616ebf0391af044f974b554e.jpeg"
            }
        },
        "message": "test message",
        "viewed": "0",
        "time": "1569337165"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name    | Description                     |
|---------|---------------------------------|
| message | Contains the actual message text|

---

## Response Codes

| Code | Description                                   |
|------|-----------------------------------------------|
| 201  | OssnMessages component not found              |
| 106  | Message text cannot be blank                  |
| 106  | Either 'to' or 'from' is blank                |
| 103  | Either user not found                         |
| 200  | Message send failed                           |

---

**Notes:**
- All requests must include your API key.
````
