````markdown name=docs/endpoints/photos_list_profile_cover.md
# Photos List (Profile or Cover)

List photos for the user's profile photo album or profile cover photos.

---

## Endpoint

```
/api/v1.0/photos_list_profile_cover
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                  |
|---------------|----------|---------|----------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                 |
| guid          | Yes      | integer | UserID (owner of the album)                  |
| type          | Yes      | string  | Type of album: `profile` or `cover`          |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569324166,
    "payload": {
        "list": [
            {
                "guid": "707",
                "image_url": "http://www.mywebsite.com/album/getphoto/1/f28c65f85d2ce5677545ae2d953d82a0.jpg?size=larger&type=1"
            },
            {
                "guid": "681",
                "image_url": "http://www.mywebsite.com/album/getphoto/1/ae99d38c725c2bfc8d7df8f6be057193.jpeg?size=larger&type=1"
            }
        ]
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name | Description                      |
|------|----------------------------------|
| list | Contains photos in the album     |

---

**Remarks:**
- If there are no photos, `list` will be `null` or `false`.
- If the album doesn't exist, error code `103` will be returned.
- All requests must include your API key.
````
