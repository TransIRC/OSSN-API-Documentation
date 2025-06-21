# Message List

Retrieve and paginate messages between users via API.  
Fetch chat history, sort by date, and load conversations in batches.

---

## Endpoint

```
/api/v1.0/message_list
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                     |
|---------------|----------|---------|---------------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                    |
| guid          | Yes      | integer | A UserID whose messages will be listed (UserA)                                  |
| to            | Yes      | integer | A UserID UserA is messaging (UserB)                                             |
| markallread   | No       | integer | Set to `1` to mark all messages as viewed to UserA (not UserB); default is `0`  |
| offset        | No       | integer | Pagination offset                                                               |

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
                "message": "Some Message",
                "viewed": "1",
                "is_deleted": "1",
                "time": "1569063785"
            },
            {
                "data": {},
                "id": "31",
                "message_from": {
                    "guid": "27",
                    "fullname": "Meagan McLaughlin",
                    "username": "zKutch",
                    "icon": {
                        "small": "http://www.mywebsite.com/avatar/zKutch/small/8715c874616ebf0391af044f974b554e.jpeg"
                    }
                },
                "message_to": {
                    "guid": "1",
                    "fullname": "System Administrator",
                    "username": "administrator",
                    "icon": {
                        "small": "http://www.mywebsite.com/avatar/administrator/small/ddfbc9f412fca49cd89c8592b6500269.jpeg"
                    }
                },
                "message": "Hi There",
                "viewed": "1",
                "time": "1569068396"
            }
        ],
        "withuser": {
            "guid": "27",
            "fullname": "Meagan McLaughlin",
            "username": "zKutch",
            "icon": {
                "small": "http://www.mywebsite.com/avatar/zKutch/small/8715c874616ebf0391af044f974b554e.jpeg"
            }
        },
        "count": "39",
        "offset": false
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name      | Description                                              |
|-----------|----------------------------------------------------------|
| list      | Contains all messages, or will contain `false`           |
| is_deleted| Present only if the message is deleted (`1` if deleted)   |
| count     | Total number of messages                                 |
| offset    | Current pagination number or `false` if none             |

---

**Notes:**
- All requests must include your API key.
- Use `offset` to paginate through messages.
