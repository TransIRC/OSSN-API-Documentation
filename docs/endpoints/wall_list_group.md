````markdown name=docs/endpoints/wall_list_group.md
# Group Wall Posts List

List wall posts for a group page.

---

## Endpoint

```
/api/v1.0/wall_list_group
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                                         |
|---------------|----------|---------|-----------------------------------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                                        |
| group_guid    | Yes      | integer | Group ID                                                                                            |
| guid          | Yes      | integer | UserID of the user who is viewing the group                                                         |
| offset        | Yes      | integer | The page number (for pagination). Each response contains 10 posts. Use 0 for the first page, 1 for the next, etc. |
| count         | Yes      | integer | The total number of posts                                                                           |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569255645,
    "payload": {
        "posts": [
            {
                "post": {
                    "data": {},
                    "guid": "114",
                    "time_created": "1569255618",
                    "owner_guid": "7",
                    "description": "{\"post\":\"Hello!\"}",
                    "title": "",
                    "type": "group",
                    "subtype": "wall",
                    "poster_guid": "1",
                    "access": "1",
                    "time_updated": "0",
                    "total_likes": 0,
                    "is_liked_by_user": false
                },
                "friends": [],
                "text": "Hello!",
                "location": "",
                "user": {
                    "guid": "1",
                    "first_name": "System",
                    "last_name": "Administrator"
                    // ... additional user fields ...
                },
                "image": ""
            }
        ],
        "count": "1",
        "offset": 1,
        "group": {
            "data": {},
            "guid": "7",
            "time_created": "1568224071",
            "owner_guid": "2",
            "description": "New group about",
            "title": "Test Group"
            // ... additional group fields ...
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name                  | Type    | Description                                                        |
|-----------------------|---------|--------------------------------------------------------------------|
| group                 | object  | Contains group details                                             |
| posts                 | array   | List of group wall posts                                           |
| post.is_liked_by_user | boolean | `true` if the post is liked by the viewer                          |
| post.total_likes      | integer | Number of total likes on the post                                  |
| user                  | object  | The user who created the post (`posted_user` in classic docs)      |

---

**Remarks:**
- If the request succeeds, you should get code `100` besides the payload.
- Each page contains up to 10 posts. Use the `offset` parameter to paginate.
- If you have any questions, you may start a new topic on the community.
- All requests must include your API key.
````
