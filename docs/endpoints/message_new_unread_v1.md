# Unread Messages

Fetch unread messages between two users via API.  
Retrieve pending chats, track new activity, and sync conversation states in real-time.

---

## Endpoint

```
/api/v1.0/message_new
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                              |
|---------------|----------|---------|----------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                             |
| to            | Yes      | integer | The UserID whose messages will be listed (UserA)         |
| from          | Yes      | integer | The UserID UserA is talking with (UserB)                 |
| markallread   | No       | integer | Set to `1` to mark all messages as read                  |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569337647,
    "payload": {
        "list": [
            {
                "data": {},
                "id": "30",
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
                "message": "Unread Message",
                "viewed": "false",
                "time": "1569063785"
            }
        ],
        "withuser": {
            "guid": "27",
            "fullname": "Meagan McLaughlin",
            "username": "zKutch",
            "icon": {
                "small": "http://local.opensource-socialnetwork.org/avatar/zKutch/small/8715c874616ebf0391af044f974b554e.jpeg"
            }
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name      | Description                                            |
|-----------|--------------------------------------------------------|
| list      | Contains all unread messages, or `false` if none exist |
| withuser  | User details for the user being talked to              |

---

**Notes:**
- All requests must include your API key.
