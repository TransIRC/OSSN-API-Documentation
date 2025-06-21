
Check if user is friend of other user

Brief description:

    Determine if users are friends in your app – integrate real-time relationship checks for feeds, messaging, and networking features.

Endpoint

    https://www.mywebsite.com/api/v1.0/user_is_friend 

Method:

    POST / GET

Parameter:
Parameter name 	Required 	Type 	Explain
api_key_token 	Yes 	string 	Your API key
user_a 	Yes 	integer 	UserA For who you wanted check
user_b 	Yes 	integer 	UserB

Example Response

{
    "merchant": "Open Source Social Network",
    "url": "http:\/\/www.mywebsite.com\/",
    "time_token": 1569249655,
    "payload": {
        "is_friend": true,
        "request_exists": true
    },
    "code": "100",
    "message": "Request successfully executed"
}

Return payload parameter description
Parameter name 	Type 	Explain
is_friend 	boolean 	true if users are friend with each other
request_exists 	boolean 	true if friend request exists

Remark

    if is_friend is true request_exists will be true
    If the request succeed you should get the code 100 besides the payload.
    If you have any question you may create start a new topic on community.

