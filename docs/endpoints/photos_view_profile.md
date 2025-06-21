
Photo details profile or cover

Brief description:

    Get a details either for profile or cover photo

Endpoint

    https://www.mywebsite.com/api/v1.0/photos_view_profile

Method:

    POST / GET

Parameter:
Parameter name 	Required 	Type 	Explain
api_key_token 	Yes 	string 	Your API key
photo_guid 	Yes 	integer 	PhotoGuid you wanted to get
uguid 	Yes 	integer 	UserID who is viewing the photo

Example Response

{
    "merchant": "Open Source Social Network",
    "url": "http:\/\/www.mywebsite.com\/",
    "time_token": 1569325087,
    "payload": {
        "user": {
            "guid": "1",
            "first_name": "System",
            "last_name": "Administrator",
            "fullname": "System Administrator",
            ...
            ...
            ...
        },
        "photo": {
            "guid": "707",
            "is_liked_by_user": false,
            "total_likes": 0,
            "image_url": "http:\/\/www.mywebsite.com\/album\/getphoto\/1\/f28c65f85d2ce5677545ae2d953d82a0.jpg?type=1",
            "time_created": "1569324163"
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}

Return payload parameter description
Parameter name 	Explain
photo 	Will contain photo details
user 	Will contain photo owner
photo.is_liked_by_user 	true If it is liked by uguid

Remarks

    If photo did not exist you will get 103 error.

