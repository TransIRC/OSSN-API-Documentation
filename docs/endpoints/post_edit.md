# Edit Wall Post

Allows you to edit an existing wall post—only the text content can be modified.  
If the post does not contain an image, text is required for the post to remain valid.  
**Available since OssnServices v9.4.**

---

## Endpoint

```
/api/v2.0/post/edit
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                     |
|---------------|----------|---------|-----------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                    |
| uguid         | Yes      | integer | User ID attempting to edit the post (must be the post owner)    |
| post_guid     | Yes      | integer | The GUID of the post to edit                                    |
| text          | Yes      | string  | New post text                                                   |

## Example Response

```json
{
    "merchant": "OSSN 7.5",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1712576881,
    "payload": {
        "status": "success",
        "message": "Post successfully saved"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Failed Response Example

```json
{
    "merchant": "OSSN 7.5",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1712577179,
    "payload": false,
    "code": "200",
    "message": {
        "status": "failed",
        "message": "Can not save post"
    }
}
```

---

**Notes:**
- Only the post owner (specified by `uguid`) can edit a post.
- If the post does not include an image, text content is mandatory.
- All requests must include your API key.
