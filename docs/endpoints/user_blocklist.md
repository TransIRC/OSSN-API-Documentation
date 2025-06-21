# Get List of Blocked Users

Get a list of members that a user has blocked.  
**All blocked members are returned with no pagination.**  
**Available since OssnServices v9.0.**

---

## Endpoint

```
/api/v2.0/user/blocklist
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                     |
|---------------|----------|---------|---------------------------------|
| api_key_token | Yes      | string  | Your API key                    |
| guid          | Yes      | integer | User ID to get block list for   |

---

**Notes:**
- All requests must include your API key.
- The response contains all blocked users for the given user ID, with no pagination.
