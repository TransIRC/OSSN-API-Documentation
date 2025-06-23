# Wall Post Add

Add a wall post for a user.

---

## Endpoint

```
/api/v1.0/wall_add
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                                   |
|---------------|----------|---------|-----------------------------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                                  |
| owner_guid    | Yes      | integer | User ID or Group ID (in case of group post)                                                   |
| poster_guid   | Yes      | integer | User ID of the person posting                                                                 |
| post          | No       | string  | Text content of the post                                                                      |
| friends       | No       | string  | Friends' IDs separated by commas, for tagging in the post                                     |
| location      | No       | string  | Location                                                                                      |
| privacy       | No       | integer | 3 for Friends only, 2 for Public. Default: 2 (Public)                                         |
| type          | Yes      | string  | `user` or `group` (in lowercase). Use `group` if creating a post for a group                  |
| ossn_photo    | Optional | file    | A photo for the wall post, accessed via `$_FILES['ossn_photo']`                               |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569253135,
    "payload": {
        "post": {
            "data": {},
            "guid": "113",
            "time_created": "1569253135",
            "owner_guid": "1",
            "description": "{\"post\":\"Hello How are you\"}",
            "title": "",
            "type": "user",
            "subtype": "wall",
            "poster_guid": "1",
            "access": "3",
            "time_updated": "0",
            "total_likes": 0,
            "is_liked_by_user": false
        },
        "friends": [],
        "text": "Hello How are you",
        "location": "",
        "user": {
            "guid": "1",
            "first_name": "System",
            "last_name": "Administrator",
            "fullname": "System Administrator",
            "username": "administrator",
            "email": "admin@opensource-socialnetwork.org",
            "birthdate": "03/02/1988",
            "gender": "male"
            // ... additional user fields ...
        },
        "image": ""
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name                  | Type    | Description                                                                                               |
|-----------------------|---------|-----------------------------------------------------------------------------------------------------------|
| image                 | string  | Image file name, if set                                                                                   |
| post.total_likes      | integer | Number of likes post has (always 0/false for new post)                                                    |
| post.is_liked_by_user | boolean | Will always be `false` for a new post                                                                     |

---

**Remarks:**
- If an image is set, you can view it by visiting: `https://www.mywebstie.com/post/photo/<post.guid>/<image>`
- If the request succeeds, you should get code `100` besides the payload.
- All requests must include your API key.
- If you have any questions, you may start a new topic on the community.
