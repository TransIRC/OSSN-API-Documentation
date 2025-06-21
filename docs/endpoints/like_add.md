````markdown name=docs/endpoints/like_add.md
# Create a Like

Create a like for an existing post or entity.

---

## Endpoint

```
/api/v1.0/like_add
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                    |
|---------------|----------|---------|----------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                   |
| subject_guid  | Yes      | integer | Wall post GUID or entity GUID to be liked                      |
| type          | Yes      | string  | `entity` (for any entity), `post` (for a post), `annotation` (for a comment) |
| uguid         | Yes      | integer | UserID who is liking                                          |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://www.mywebsite.com/",
    "time_token": 1569318908,
    "payload": true,
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name    | Type    | Description                              |
|---------|---------|------------------------------------------|
| payload | boolean | `true` if like was created successfully  |

---

**Remarks:**
- If the like fails to be added, you will receive error code `200`.
- All requests must include your API key.
````
