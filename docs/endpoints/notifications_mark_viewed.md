````markdown name=docs/endpoints/notifications_mark_viewed.md
# Notifications Mark Viewed

Mark a notification as viewed.

---

## Endpoint

```
/api/v1.0/notifications_mark_viewed
```

## Methods

- `GET`
- `POST`

## Parameters

| Name              | Required | Type    | Description                      |
|-------------------|----------|---------|----------------------------------|
| api_key_token     | Yes      | string  | Your API key                     |
| notification_guid | Yes      | integer | The GUID of the notification     |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569332608,
    "payload": {
        "notification": {
            "guid": "4",
            "type": "like:post",
            "poster_guid": "27",
            "owner_guid": "1",
            "subject_guid": "110",
            "viewed": "",
            "time_created": "1569331959",
            "item_guid": "110"
        },
        "poster": {
            "guid": "27",
            "fullname": "Meagan McLaughlin",
            "icon": "http://www.mywebsite.com/avatar/zKutch/small/8715c874616ebf0391af044f974b554e.jpeg"
        },
        "entity": false,
        "post": false
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name     | Description                                                                      |
|----------|----------------------------------------------------------------------------------|
| entity   | If related to any entity except profile/cover photo update, contains entity info |
| group    | If related to group member requests, contains group details                      |
| post     | If related to a post, contains wall post details                                 |

---

**Remarks:**
- On failure, you will get error code `200`.
- All requests must include your API key.
````
