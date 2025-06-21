````markdown name=docs/endpoints/photos_list_albums.md
# Albums List

List the albums owned by a user.

---

## Endpoint

```
/api/v1.0/photos_list_albums
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                     |
|---------------|----------|---------|-------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                    |
| guid          | Yes      | integer | UserID of the user whose albums you want to list|
| uguid         | Yes      | integer | UserID of the viewer                            |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569323007,
    "payload": {
        "albums": [
            {
                "image_url": "http://www.mywebsite.com/components/OssnPhotos/images/nophoto-album.png",
                "album": {
                    "data": {},
                    "guid": "112",
                    "time_created": "1569237368",
                    "owner_guid": "1",
                    "description": "",
                    "title": "Test",
                    "type": "user",
                    "subtype": "ossn:album",
                    "access": "3"
                }
            }
        ],
        "profile_photo": "http://www.mywebsite.com/avatar/administrator/larger/7c98c47e931c1395dceb50ea5d745957.jpeg",
        "cover_photo": "http://www.mywebsite.com/cover/administrator/9baa8bfb7c5c1b4d331fb8f030e61aa1.jpg",
        "count": "1",
        "offset": 1
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name          | Type   | Description                                                                 |
|---------------|--------|-----------------------------------------------------------------------------|
| albums        | array  | For each album: `album.image_url` (latest image) and the album details      |
| profile_photo | string | User's profile album latest photo URL                                       |
| cover_photo   | string | User's cover album latest photo URL                                         |

---

**Remarks:**
- If there are no albums other than profile and cover, `albums` will be `null` or `false`.
- To get a list of photos in a standard album, see the [photos_list](photos_list.md) endpoint.
- To list photos for user profile or cover albums, see [photos_list_profile_cover](photos_list_profile_cover.md).
- All requests must include your API key.
````
