# Message List 2.0

Get a list of messages exchanged between two users.  
**Note:** In this version, user details are not included in each message; instead, friend details are returned in the `withuser` object. The response also shows the `is_online` status for the user.

---

## Endpoint

```
/api/v2.0/message/list
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                 |
|---------------|----------|---------|-----------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                |
| guid          | Yes      | integer | The UserID whose messages will be listed (UserA)                            |
| to            | Yes      | integer | The UserID that UserA is messaging (UserB)                                  |
| markallread   | No       | integer | Set to `1` to mark all messages as viewed to UserA (not UserB), or leave `0`|
| offset        | No       | integer | Pagination offset                                                           |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://dev.opensource-socialnetwork.org/",
    "time_token": 1744001277,
    "payload": {
        "list": [
            {
                "id": 5,
                "message_from": 2,
                "message_to": 1,
                "message": "Ok sir testing",
                "viewed": "1",
                "time": 1743531459,
                "is_deleted_from": "",
                "is_deleted_to": ""
            },
            {
                "id": 7,
                "message_from": 2,
                "message_to": 1,
                "message": "File Attachment",
                "viewed": "1",
                "time": 1743593492,
                "is_deleted_from": "",
                "is_deleted_to": "",
                "attachment_guid": "1348",
                "attachment_name": "screencapture-2025-04-01-12-40-48",
                "type_of_attachment": "file",
                "attachment_url": "http://dev.opensource-socialnetwork.org/messages_attachment_view/1348/screencapture-2025-04-01-12-40-48.pdf"
            }
        ],
        "withuser": {
            "guid": 2,
            "fullname": "Test User",
            "username": "testuser",
            "is_verified_user": true,
            "icon": {
                "small": "http://dev.opensource-socialnetwork.org/avatar/testuser/small/4e6e4ad87ecf05ce879d9d1e95964a99.jpeg?ossn_cache=0c2afb23",
                "smaller": "http://dev.opensource-socialnetwork.org/avatar/testuser/smaller/1b80a3837602f864c8238152e5773e4b.jpeg?ossn_cache=0c2afb23"
            },
            "is_online": false
        },
        "count": 8,
        "offset": false
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameters

| Name        | Description                                                             |
|-------------|-------------------------------------------------------------------------|
| list        | Contains all messages (array) or `false` if there are no messages       |
| is_deleted  | Present only if the message is deleted, value will be `1`               |
| is_online   | Indicates if the user is online                                         |
| count       | Total number of messages                                                |
| offset      | Current pagination number (or `false` if no further pages)              |

---

**Note:**  
You must include your API key as a parameter in all requests.
