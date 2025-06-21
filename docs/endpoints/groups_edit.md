
Group Edit

Brief description:

    Edit a specific existing group.

Endpoint

    https://www.mywebsite.com/api/v1.0/groups_edit

Method:

    POST / GET

Parameter:
Parameter name 	Required 	Type 	Explain
api_key_token 	Yes 	string 	Your API key
group_guid 	Yes 	integer 	A group ID
uguid 	Yes 	integer 	A group owner UserID
groupname 	Yes 	string 	A new group name
groupdesc 	Yes 	string 	New group description/about
membership 	Yes 	integer 	Group privacy 2 for public, 1 for closed group

Example Response

{
    "merchant": "Open Source Social Network",
    "url": "http:\/\/local.opensource-socialnetwork.org\/",
    "time_token": 1569330120,
    "payload": true,
    "code": "100",
    "message": "Request successfully executed"
}

Return payload parameter description
Parameter name 	Explain
payload 	true or false

Remarks

    Error 200 arises if invalid group, or group owner not specified.
    Error 103 arises if invalid group owner user.

