# Comment Edit

Edit the text of an existing comment.  
**Available since OssnServices v7.0.**

---

## Endpoint

```
/api/v1.0/comment_edit
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                 |
|---------------|----------|---------|-----------------------------|
| api_key_token | Yes      | string  | Your API key                |
| guid          | Yes      | integer | Comment ID                  |
| comment       | Yes      | string  | New comment text            |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1632743559,
    "payload": {
        "success": "Comment has been edited successfully"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

---

**Note:**
- The API does not validate comment ownership; any comment specified by ID can be edited.  
  **You must implement your own ownership validation.**
- All requests must include your API key.
