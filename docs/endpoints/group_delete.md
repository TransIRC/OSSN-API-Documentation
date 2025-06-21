# Delete Group

Permanently delete a specific OSSN group from the system.  
This action will remove the group along with all its associated content, including posts, comments, and member interactions. **Once deleted, the group cannot be restored, and all data will be lost.**  
**Available since OssnServices v9.4.**

---

## Endpoint

```
/api/v2.0/group/delete
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                           |
|---------------|----------|---------|---------------------------------------|
| api_key_token | Yes      | string  | Your API key                          |
| uguid         | Yes      | integer | User ID performing the deletion       |
| group_guid    | Yes      | integer | Group GUID to delete                  |

## Example Response (Success)

```json
{
    "merchant": "OSSN 7.3",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1712576126,
    "payload": {
        "status": "success",
        "message": "Group and group contents deleted"
    },
    "code": "100",
    "message": "Request successfully executed"
}
```

## Example Response (Failure)

```json
{
    "merchant": "OSSN 7.3",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1712576325,
    "payload": false,
    "code": "200",
    "message": "Invalid group"
}
```

---

**Notes:**
- All associated content (posts, comments, member interactions) will be deleted.
- This action is irreversible.
- All requests must include your API key.
