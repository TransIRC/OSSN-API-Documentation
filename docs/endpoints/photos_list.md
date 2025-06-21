````markdown name=docs/endpoints/photos_list.md
# Album Photos List

List photos in an album (other than profile photos and cover photos).

---

## Endpoint

```
/api/v1.0/photos_list
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                 |
|---------------|----------|---------|---------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                |
| album_guid    | Yes      | integer | Album GUID for which you want to list photos |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569323838,
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
        "list": [
            {
                "guid": "700",
                "image_url": "http://www.mywebsite.com/album/getphoto/112/8e00ae2e2f3c27a33693cf8d00bd0792.jpg?size=album"
            }
        ]
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name  | Description                    |
|-------|--------------------------------|
| album | Contains album details         |
| list  | Contains photos in the album   |

---

**Remarks:**
- If there are no photos, `list` will be `null` or `false`.
- If the album doesn't exist, error code `103` will be returned.
- All requests must include your API key.
````
