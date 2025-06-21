````markdown name=docs/endpoints/wall_list_user.md
# User Profile Wall Posts List

List wall posts for a user profile page.

---

## Endpoint

```
/api/v1.0/wall_list_user
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                                                 |
|---------------|----------|---------|-------------------------------------------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                                                |
| uguid         | Yes      | integer | UserID you want to get wall posts for                                                                       |
| guid          | Yes      | integer | UserID of the user viewing the profile (specify even if `uguid` and `guid` are the same)                    |
| offset        | Yes      | integer | The page number (pagination). Each response contains 10 posts. Use 0 for the first page, 1 for the next, etc.|
| count         | Yes      | integer | The total number of posts                                                                                   |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569254816,
    "payload": {
        "posts": [
            {
                "post": {
                    "data": {},
                    "guid": "110",
                    "time_created": "1569189230",
                    "owner_guid": "1",
                    "description": "{\"post\":\"OK\"}",
                    "title": "",
                    "type": "user",
                    "subtype": "wall",
                    "poster_guid": "1",
                    "access": "2",
                    "time_updated": "0",
                    "total_likes": 1,
                    "is_liked_by_user": true
                },
                "friends": [],
                "text": "OK",
                "location": "",
                "user": {
                    "guid": "1",
                    "first_name": "System"
                    // ... additional user fields ...
                },
                "image": ""
            },
            {
                "post": {
                    "data": {},
                    "guid": "109",
                    "time_created": "1569186720",
                    "owner_guid": "1",
                    "description": "{\"post\":\"some text\"}",
                    "title": "",
                    "type": "user",
                    "subtype": "wall",
                    "poster_guid": "1",
                    "access": "2",
                    "time_updated": "0",
                    "total_likes": 1,
                    "is_liked_by_user": true
                },
                "friends": [],
                "text": "some text",
                "location": "",
                "user": {
                    "guid": "1",
                    "first_name": "System"
                    // ... additional user fields ...
                },
                "image": ""
            }
        ],
        "count": "4",
        "viewer_is_friend": false,
        "user": {
            "guid": "1",
            "first_name": "System",
            "last_name": "Administrator"
            // ... additional user fields ...
        },
        "offset": 1
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name                  | Type    | Description                                                                                      |
|-----------------------|---------|--------------------------------------------------------------------------------------------------|
| posts                 | array   | List of wall posts                                                                               |
| friends               | array   | Will contain the users' friends if they are tagged in the post                                   |
| text                  | string  | Will contain `null:data` if it is a custom wall post (e.g., profile photo update, cover, album)  |
| posted_user           | object  | If `owner_guid` and `poster_guid` differ, contains the user object who created the post          |
| post.is_liked_by_user | boolean | `true` if the post is liked by the viewing user (`guid`)                                         |
| post.total_likes      | integer | Number of total likes on the post                                                                |

---

**Remarks:**
- If the request succeeds, you should get code `100` besides the payload.
- Each page contains up to 10 posts. Use the `offset` parameter to paginate.
- If you have any questions, you may start a new topic on the community.
- All requests must include your API key.
````
