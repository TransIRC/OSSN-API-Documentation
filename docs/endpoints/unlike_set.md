````markdown name=docs/endpoints/unlike_set.md
# Set Unlike

Unlike an existing post, entity, or annotation.

---

## Endpoint

```
/api/v1.0/unlike_set
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                                                 |
|---------------|----------|---------|-----------------------------------------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                                                |
| subject_guid  | Yes      | integer | Wall post GUID or entity GUID to be unliked                                 |
| type          | Yes      | string  | `entity` (for any entity), `post` (for a post), `annotation` (for a comment)|
| uguid         | Yes      | integer | UserID who is unliking                                                      |

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

| Name    | Type    | Description                               |
|---------|---------|-------------------------------------------|
| payload | boolean | `true` if unlike was set successfully     |

---

**Remarks:**
- If the unlike fails, you will receive error code `200`.
- All requests must include your API key.
````
