# User Profile Wall Posts List

List wall posts for a user profile page.

---

## Endpoint

/api/v1.0/wall_list_user


## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                                                   |
|---------------|----------|---------|---------------------------------------------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                                                  |
| uguid         | Yes      | integer | UserID for the profile wall you want to retrieve posts from.                                                    |
| guid          | Yes      | integer | UserID of the user who is viewing the profile (the logged-in user).                                           |
| offset        | Yes      | integer | The page number for pagination. **Note: This is 1-based. Use `1` for the first page, `2` for the second, etc.** |
| count         | Yes      | integer | The number of posts to retrieve per page (e.g., 10).                                                          |

## Developer Note on Pagination

>⚠️ **Important:** The `offset` parameter is **1-based**, not 0-based. Sending `offset: 0` will result in a server-side SQL error. Always start pagination with `offset: 1` to retrieve the first page of results.

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "[http://www.mywebsite.com/](http://www.mywebsite.com/)",
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
                },
                "image": ""
            }
        ],
        "count": "1",
        "viewer_is_friend": false,
        "user": {
            "guid": "1",
            "first_name": "System",
            "last_name": "Administrator"
        },
        "offset": 1
    },
    "code": "100",
    "message": "Request successfully executed"
}
