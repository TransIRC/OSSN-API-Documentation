````markdown name=docs/endpoints/photos_view.md
# Photo Details (Album Photo)

Get details for a standard album photo (not profile or cover).

---

## Endpoint

```
/api/v1.0/photos_view
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                  |
|---------------|----------|---------|----------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                 |
| photo_guid    | Yes      | integer | Photo GUID you want to get details for       |
| uguid         | Yes      | integer | UserID of the viewer                         |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569324531,
    "payload": {
        "album": {
            "data": {},
            "guid": "112",
            "time_created": "1569237368",
            "owner_guid": "1",
            "description": "",
            "title": "Test",
            "type": "user",
            "subtype": "ossn:album",
            "access": "3",
            "file:ossn:aphoto": "album/photos/8e00ae2e2f3c27a33693cf8d00bd0792.jpg"
        },
        "photo": {
            "guid": "700",
            "is_liked_by_user": false,
            "total_likes": 0,
            "image_url": "http://www.mywebsite.com/album/getphoto/112/8e00ae2e2f3c27a33693cf8d00bd0792.jpg",
            "time_created": "1569323833"
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name                   | Description                                               |
|------------------------|-----------------------------------------------------------|
| photo                  | Contains photo details                                    |
| album                  | Contains album details                                    |
| photo.is_liked_by_user | `true` if liked by the viewing user (`uguid`)             |

---

**Remarks:**
- If the photo does not exist, error code `103` will be returned.
- All requests must include your API key.
````
