 Delete album photo

Brief description:

    Delete photo other than profile or cover photo.

Endpoint

    https://www.mywebsite.com/api/v1.0/photos_delete

Method:

    POST / GET

Parameter:
Parameter name 	Required 	Type 	Explain
api_key_token 	Yes 	string 	Your API key
photoid 	Yes 	integer 	photoid you wanted to get
guid 	Yes 	integer 	Photo Alum Owner GUID

Example Response

{
    "merchant": "Open Source Social Network",
    "url": "http:\/\/www.mywebsite.com\/",
    "time_token": 1569325087,
    "payload": {
		'status': true,
	},
    "code": "100",
    "message": "Request successfully executed"
}

Return payload parameter description
Parameter name 	Explain
status 	true or false
