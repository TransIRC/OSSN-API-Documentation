````markdown name=docs/endpoints/photos_profile_add.md
# Change Profile Photo

Add a new profile photo.

---

## Endpoint

```
/api/v1.0/photos_profile_add
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                            |
|---------------|----------|---------|----------------------------------------|
| api_key_token | Yes      | string  | Your API key                           |
| userphoto     | Yes      | array   | An image file (photo to upload)        |
| guid          | Yes      | integer | User GUID for whom to change photo     |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569325087,
    "payload": {
        "guid": 123,
        "user": {
            "guid": "1",
            "first_name": "System",
            "last_name": "Administrator",
            "fullname": "System Administrator"
            // ... additional user fields ...
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name | Description                       |
|------|-----------------------------------|
| guid | The GUID of the newly added photo |
| user | Details of the photo owner user   |

---

**Remarks:**
- Error code `200` will arise if the request fails.
- All requests must include your API key.
- The `userphoto` parameter must be an image file.
````
