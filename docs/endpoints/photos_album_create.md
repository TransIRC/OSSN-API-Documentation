````markdown name=docs/endpoints/photos_album_create.md
# New Album Create

Create a new album for a user.

---

## Endpoint

```
/api/v1.0/photos_album_create
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                 |
|---------------|----------|---------|---------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                |
| title         | Yes      | string  | Album name                                  |
| guid          | Yes      | integer | UserID (for whom the album will be created) |
| privacy       | Yes      | integer | 3 for Friends only, 2 for Public            |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569319643,
    "payload": {
        "guid": 531
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name | Type    | Description                           |
|------|---------|---------------------------------------|
| guid | integer | The GUID of the newly created album   |

---

**Remarks:**
- If album creation fails, you will receive error code `200`.
- All requests must include your API key.
````
