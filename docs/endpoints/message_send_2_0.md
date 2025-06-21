# Message Send v2.0

Send a message to a user with the ability to include an attachment.  
This allows you to communicate by sending text along with files, images, documents, or other media—ensuring the recipient receives all necessary information in one seamless interaction.

---

## Endpoint

```
/api/v2.0/message/send
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                     |
|---------------|----------|---------|---------------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                    |
| from          | Yes      | integer | A UserID from where the message will be sent                                    |
| to            | Yes      | integer | A UserID who receives the message                                               |
| attachment    | Optional | File    | Attachment file (`jpg`, `png`, `jpeg`, `jfif`, `gif`, `webp`, `docx`, `pdf`)    |
| message       | Yes      | string  | The message text                                                                |

## Example Request

### cURL

```bash
curl https://dev.opensource-socialnetwork.org/api/v2.0/message/send \
  -F api_key_token=myapikeytoken \
  -F from=1 \
  -F to=2 \
  -F message=Test \
  -F attachment=@/home/user/dummy.pdf
```

## Example Response

```json
{
    "merchant": "OSSN",
    "url": "http://dev.opensource-socialnetwork.org/",
    "time_token": 1714841244,
    "payload": {
        "data": {},
        "id": 4,
        "message_from": {
            "guid": 1,
            "fullname": "Arsalan Shah",
            "username": "arsalanshah",
            "icon": {
                "small": "http://dev.opensource-socialnetwork.org/avatar/arsalanshah/small/c0e15d54735a596d4e16bf1aaa999758.jpeg"
            }
        },
        "message_to": {
            "guid": 2,
            "fullname": "Some Name",
            "username": "testuser",
            "icon": {
                "small": "http://dev.opensource-socialnetwork.org/avatar/testuser/small/fddf4dcc973847d1aeda796356412126.jpeg"
            }
        },
        "message": "Test",
        "viewed": "0",
        "time": 1714841244,
        "file:attachment": "attachment/0fe4d28b98fcdd503f5650560e06e025.pdf",
        "is_deleted_from": "",
        "is_deleted_to": "",
        "attachment_guid": "175",
        "attachment_name": "dummy.pdf",
        "type_of_attachment": "file",
        "attachment_url": "http://dev.opensource-socialnetwork.org/messages/attachment/175/dummy.pdf"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name               | Description                    |
|--------------------|--------------------------------|
| message            | Contains the actual message text|
| attachment_name    | Name of the file attached      |
| type_of_attachment | "file" or "image"              |
| attachment_url     | URL to the attached file/image |

---

## Response Codes

| Code | Description                                 |
|------|---------------------------------------------|
| 201  | OssnMessages component not found            |
| 106  | Message text cannot be blank                |
| 106  | Either `to` or `from` is blank              |
| 103  | Either user not found                       |
| 200  | Message send failed                         |

---

**Notes:**
- Available since OssnServices v9.6
- You must include your API key as a parameter in all requests.
