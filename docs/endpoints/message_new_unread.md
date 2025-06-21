# Unread Messages 2.0

Get a list of unread messages between two users.

**Version 2.0 differences:**
- Does not include user details in the `message_from` and `message_to` parameters.
- User information is instead provided through the `withuser` parameter.
- Includes an `is_online` status for the user.

---

## Endpoint

```
/api/v2.0/message/new
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                         |
|---------------|----------|---------|---------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                        |
| to            | Yes      | integer | The UserID for the user whose messages will be listed (UserA)       |
| from          | Yes      | integer | The UserID of the user who is talking to `to` (UserB)               |
| markallread   | No       | integer | Set to `1` to mark all messages as read                             |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://dev.opensource-socialnetwork.org/",
    "time_token": 1744001710,
    "payload": {
        "list": false,
        "withuser": {
            "guid": 1,
            "fullname": "Arsalan Shah",
            "username": "arsalanshah",
            "is_verified_user": true,
            "icon": {
                "small": "http://dev.opensource-socialnetwork.org/avatar/arsalanshah/small/2bf5d247be47342ce89a231ee477eafa.jpeg?ossn_cache=0c2afb23"
            },
            "is_online": true
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

### Payload Parameter Description

| Name     | Description                        |
|----------|------------------------------------|
| message  | Contains actual message text       |

---

## Response Codes

| Code | Description                                      |
|------|--------------------------------------------------|
| 201  | OssnMessages component not found                  |
| 106  | Message text cannot be blank                      |
| 106  | Either `to` or `from` is blank                    |
| 103  | Either user not found                             |
| 200  | Message send failed                               |

---

**Note:**  
You must include your API key as a parameter in all requests.
