````markdown name=docs/endpoints/photos_delete_cover.md
# Delete Profile Cover Photo

Delete a specific profile cover photo.

---

## Endpoint

```
/api/v1.0/photos_delete_cover
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                          |
|---------------|----------|---------|--------------------------------------|
| api_key_token | Yes      | string  | Your API key                         |
| photoid       | Yes      | integer | Photo ID you want to delete          |
| guid          | Yes      | integer | Photo owner GUID                     |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569325087,
    "payload": {
        "status": true
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name   | Description                    |
|--------|--------------------------------|
| status | `true` if deleted, else `false`|

---

**Notes:**
- All requests must include your API key.
- The `status` field indicates whether the cover photo was successfully deleted.
````
