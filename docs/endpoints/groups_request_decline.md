````markdown name=docs/endpoints/groups_request_decline.md
# Group Request Decline

Decline a member request for a group.

---

## Endpoint

```
/api/v1.0/groups_request_decline
```

## Methods

- `GET`
- `POST`

## Parameters

| Name          | Required | Type    | Description                                  |
|---------------|----------|---------|----------------------------------------------|
| api_key_token | Yes      | string  | Your API key                                 |
| group_guid    | Yes      | integer | The group ID                                 |
| guid          | Yes      | integer | The member GUID you want to decline          |
| uguid         | Yes      | integer | The group owner GUID                         |

## Example Response

```json
{
    "merchant": "Open Source Social Network",
    "url": "http://local.opensource-socialnetwork.org/",
    "time_token": 1569330120,
    "payload": true,
    "code": "100",
    "message": "Request successfully executed"
}
```

## Payload Parameter Description

| Name    | Description                   |
|---------|-------------------------------|
| payload | `true` if declined, else `false`|

---

**Remarks:**
- Error code `200` if the owner does not match or group not found.
- Error code `103` if the user you are trying to decline is not a valid user.
- All requests must include your API key.
````
