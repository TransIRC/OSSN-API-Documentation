````markdown name=docs/endpoints/photos_album_add.md
# Add Photo to Album

Add a photo to an album.

---

## Endpoint

```
/api/v1.0/photos_album_add
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                |
|---------------|----------|---------|------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                               |
| album_guid    | Yes      | integer | Album GUID in which the photo will be added                |
| guid          | Yes      | integer | UserID (Album owner)                                       |
| ossnphoto     | Yes      | array   | Photo file, accessed by `$_FILES['ossnphoto']`             |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569319643,
    "payload": {
        "guid": 123
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name | Type    | Description                         |
|------|---------|-------------------------------------|
| guid | integer | The GUID of the newly created photo |

---

**Remarks:**
- If the photo fails to be created, you will receive error code `200`.
- All requests must include your API key.
````
