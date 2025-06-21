
Comment Delete

Brief description:

    Delete a comment list for existing post or entity

Endpoint

    https://www.mywebsite.com/api/v1.0/comment_delete

Method:

    POST / GET

Parameter:
Parameter name 	Required 	Type 	Explain
api_key_token 	Yes 	string 	Your API key
id 	Yes 	integer 	Comment ID
guid 	Yes 	integer 	UserID who is trying to delete the comment`

Example Response

{
    "merchant": "Open Source Social Network",
    "url": "http:\/\/www.mywebsite.com\/",
    "time_token": 1569319643,
    "payload": true,
    "code": "100",
    "message": "Request successfully executed"
}

Return payload parameter description
Parameter name 	Explain
payload 	true or false

Remakrs

    if comment is failed to delete you will get error code 200

