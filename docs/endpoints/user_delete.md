# Delete User

Permanently remove or delete a non-admin user from the system.  
This action deletes the user and all associated data, ensuring they no longer have access or presence within the platform.

---

## Endpoint

```
/api/v2.0/user/delete
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description              |
|---------------|----------|---------|--------------------------|
| api_key_token | Yes      | string  | Your API key             |
| guid          | Yes      | integer | User ID to delete        |

## Example Request

### cURL

```bash
curl https://dev.opensource-socialnetwork.org/api/v2.0/delete/user \
  -F api_key_token=myapikeytoken \
  -F guid=1
```

## Example Response

```json
{
    "merchant": "OPEN SOURCE SOCIAL NETWORK",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1737645539,
    "payload": {
        "success": true
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

---

**Notes:**
- Only non-admin users can be deleted.
- All user data will be completely removed.
- Available since OssnServices v9.10
