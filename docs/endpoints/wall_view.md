````markdown name=docs/endpoints/wall_view.md
# Wall View Post

Retrieve user wall posts via API – fetch updates, comments, and activity feeds with seamless integration and real-time data.

---

## Endpoint

```
/api/v1.0/wall_view
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                    |
|---------------|----------|---------|------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                   |
| post_guid     | Yes      | integer | The wall post ID to view                       |
| guid          | Yes      | integer | User ID of the user viewing the wall post      |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569253877,
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
            "fullname": "System Administrator"
            // ... additional user fields ...
        },
        "image": ""
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

- If no post is found, `payload` will return `false`.
- Otherwise, `payload` will return an object/array with the post details.

---

**Remarks:**
- If the request succeeds, you should get code `100` besides the payload.
- If you have any questions, you may start a new topic on the community.
- All requests must include your API key.
````
