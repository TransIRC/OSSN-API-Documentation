````markdown name=docs/endpoints/wall_delete.md
# Wall Post Delete

Delete an existing wall post.

---

## Endpoint

```
/api/v1.0/wall_delete
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                  |
|---------------|----------|---------|----------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                 |
| post_guid     | Yes      | integer | Wall post ID to be deleted                   |
| guid          | Yes      | integer | ID of the user who is trying to delete post  |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569249655,
    "payload": true,
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name    | Type    | Description                        |
|---------|---------|------------------------------------|
| payload | boolean | `true` if deleted, else `false`    |

---

**Remarks:**
- All requests must include your API key.
````
