# Comments List

Retrieve comments for any entity, object, or post via API.  
Fetch threaded discussions, apply filters, and paginate results seamlessly.  
Each comment includes its total likes and whether it is liked by the current user.

---

## Endpoint

```
/api/v1.0/comments_list
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                             |
|---------------|----------|---------|---------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                            |
| uguid         | Yes      | integer | Logged-in user's UserID                                 |
| type          | Yes      | string  | "post" or "entity"                                      |
| guid          | Yes      | integer | The post or entity GUID                                 |
| page_limit    | No       | integer | Page offset                                             |
| limit         | No       | integer | Total comments per page (default: 5)                    |
| offset        | No       | integer | Pagination offset                                       |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "https://local.opensource-socialnetwork.org/",
    "time_token": 1603134874,
    "payload": {
        "count": 2,
        "comments": [
            {
                "id": 10,
                "time_created": 1601773807,
                "owner_guid": 2,
                "subject_guid": 71,
                "type": "comments:post",
                "comments:post": "ABC",
                "user": {
                    "guid": 2,
                    "first_name": "Leonard",
                    "icon": {
                        "topbar": "https://local.opensource-socialnetwork.org/avatar/leonardwalter/topbar/5ae9ce317e3df5ed0002d1bedd85f534.jpeg"
                    },
                    "cover_url": false,
                    "language": null
                },
                "total_likes": 0,
                "is_liked_by_user": false
            },
            {
                "id": 11,
                "time_created": 1601775113,
                "owner_guid": 1,
                "subject_guid": 71,
                "type": "comments:post",
                "comments:post": "Test Comment",
                "user": {
                    "guid": 1,
                    "first_name": "System",
                    "last_name": "Administrator",
                    "fullname": "System Administrator",
                    "gender": "male",
                    "icon": {
                        "topbar": "https://local.opensource-socialnetwork.org/avatar/arsalanshah/topbar/767d1cc38759cb9b80b6eb32d4b12b09.jpeg"
                    },
                    "cover_url": "https://local.opensource-socialnetwork.org/cover/arsalanshah/d114ffdffc7189decd0368deb86b9a49.jpg",
                    "language": "en"
                },
                "total_likes": 1,
                "is_liked_by_user": false
            }
        ],
        "offset": 1
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name             | Description                                         |
|------------------|-----------------------------------------------------|
| is_liked_by_user | If the comment is liked by the logged-in user       |
| total_likes      | Total comment likes                                 |
| count            | Total comments                                      |
| offset           | Current pagination number                           |

---

**Note:**
- The actual comment text will be inside `comments:post` for posts and `comments:entity` for entities.
- All requests must include your API key.
