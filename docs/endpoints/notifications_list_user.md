````markdown name=docs/endpoints/notifications_list_user.md
# Notifications List

Fetch user notifications for likes, comments, photos, blogs, and videos via API.  
Track engagement, filter by type, and manage alerts programmatically.

---

## Endpoint

```
/api/v1.0/notifications_list_user
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                 |
|---------------|----------|---------|-----------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                |
| owner_guid    | Yes      | integer | The notification owner's GUID                                               |
| types         | No       | string  | Comma-separated notification types (e.g. `'typedef,typeabc'`)               |
| offset        | No       | integer | Pagination offset (default: 1, increments for next 10 records)              |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569331965,
    "payload": {
        "list": [
            {
                "notification": {
                    "guid": "4",
                    "type": "like:post",
                    "poster_guid": "27",
                    "owner_guid": "1",
                    "subject_guid": "110",
                    "viewed": null,
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
            {
                "notification": {
                    "guid": "3",
                    "type": "like:entity:file:profile:photo",
                    "poster_guid": "27",
                    "owner_guid": "1",
                    "subject_guid": "707",
                    "viewed": null,
                    "time_created": "1569331957",
                    "item_guid": "707"
                },
                "poster": {
                    "guid": "27",
                    "fullname": "Meagan McLaughlin",
                    "icon": "http://www.mywebsite.com/avatar/zKutch/small/8715c874616ebf0391af044f974b554e.jpeg"
                },
                "entity": false,
                "post": false
            }
        ],
        "count": "2",
        "offset": 1
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name     | Description                                                                      |
|----------|----------------------------------------------------------------------------------|
| list     | Array of notifications, or `false` if none exist                                 |
| entity   | If related to any entity other than profile/cover photo update, contains entity info |
| group    | If related to group member requests, contains group details                      |
| post     | If related to a post, contains wall post details                                 |
| count    | Total number of notifications                                                    |
| offset   | Current pagination number                                                        |

---

**Notes:**
- All requests must include your API key.
- Use the `types` parameter to filter by notification types.
- Use `offset` for pagination (increments of 10 per page).
````
