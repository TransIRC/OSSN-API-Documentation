# Recent Messages List

Get a list of recent messages sent to a user.  
This endpoint provides a summary of the most recent message from each conversation, including who sent it and the message content.  
**Note:** This does not return all messages between two users, only the latest message summary for each conversation.

---

## Endpoint

```
/api/v1.0/message_recent
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                   |
|---------------|----------|---------|-----------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                  |
| guid          | Yes      | integer | User ID for whom to list recent messages      |
| offset        | No       | integer | Pagination offset                             |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1569338350,
    "payload": {
        "list": [
            {
                "data": {},
                "id": "43",
                "message_from": {
                    "guid": "29",
                    "fullname": "Aniyah Ondricka",
                    "username": "Jarred99",
                    "icon": {
                        "small": "http://local.opensource-socialnetwork.org/avatar/Jarred99/small/b7d6cc9273e471fceb4d77cc2c350bba.jpeg"
                    }
                },
                "message_to": {
                    "guid": "1",
                    "fullname": "System Administrator",
                    "username": "administrator",
                    "icon": {
                        "small": "http://local.opensource-socialnetwork.org/avatar/administrator/small/ddfbc9f412fca49cd89c8592b6500269.jpeg"
                    }
                },
                "message": "Some Message",
                "viewed": "1",
                "time": "1569079953",
                "answered": 1
            },
            {
                "data": {},
                "id": "39",
                "message_from": {
                    "guid": "28",
                    "fullname": "Shaun Stracke",
                    "username": "Kolby51",
                    "icon": {
                        "small": "http://local.opensource-socialnetwork.org/avatar/Kolby51/small/507b79e629592d33a9aa56626c2415e3.jpeg"
                    }
                },
                "message_to": {
                    "guid": "1",
                    "fullname": "System Administrator",
                    "username": "administrator",
                    "icon": {
                        "small": "http://local.opensource-socialnetwork.org/avatar/administrator/small/ddfbc9f412fca49cd89c8592b6500269.jpeg"
                    }
                },
                "message": "Hello",
                "viewed": "0",
                "time": "1569079793",
                "answered": 0
            },
            {
                "data": {},
                "id": "38",
                "message_from": {
                    "guid": "27",
                    "fullname": "Meagan McLaughlin",
                    "username": "zKutch",
                    "icon": {
                        "small": "http://local.opensource-socialnetwork.org/avatar/zKutch/small/8715c874616ebf0391af044f974b554e.jpeg"
                    }
                },
                "message_to": {
                    "guid": "1",
                    "fullname": "System Administrator",
                    "username": "administrator",
                    "icon": {
                        "small": "http://local.opensource-socialnetwork.org/avatar/administrator/small/ddfbc9f412fca49cd89c8592b6500269.jpeg"
                    }
                },
                "message": "oh",
                "viewed": "1",
                "time": "1569079729",
                "answered": 1
            }
        ],
        "offset": 1,
        "count": "3"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name      | Description                                              |
|-----------|----------------------------------------------------------|
| list      | Contains summary of the most recent message per user     |
| is_deleted| Present only if the message is deleted (value `1`)       |
| count     | Total number of recent message threads                   |
| offset    | Current pagination number                                |

---

**Notes:**
- The list contains only the most recent message per conversation, not the entire chat history.
- All requests must include your API key.
