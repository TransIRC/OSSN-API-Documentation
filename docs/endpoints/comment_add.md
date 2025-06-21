
Comment Add

Brief description:

    Add comment to posts, entities, or objects via API – enable discussions, manage threads, and boost engagement with structured replies.

Endpoint

    https://www.mywebsite.com/api/v1.0/comment_add 

Method:

    POST / GET

Parameter:
Parameter name 	Required 	Type 	Explain
api_key_token 	Yes 	string 	Your API key
subject_guid 	Yes 	integer 	Wall post guid or entity guid
comment 	Yes 	string 	Comment text
type 	No 	string 	entity or post default post
uguid 	Yes 	integer 	UserID who is posting the comment`
image_file 	No 	array 	A standard image file, will be accessed by $_FILE['image_file]
Example Response 			

{
    "merchant": "Open Source Social Network",
    "url": "http:\/\/www.mywebsite.com\/",
    "time_token": 1569319643,
    "payload": {
        "comment": {
            "id": "99",
            "time_created": "1569319643",
            "owner_guid": "1",
            "subject_guid": "113",
            "type": "comments:post",
            "comments:post": "New Comment"
        },
        "user": {
            "guid": "1",
            "first_name": "System",
            "last_name": "Administrator",
            "fullname": "System Administrator",
            ...
            ...
            ...
        }
    },
    "code": "100",
    "message": "Request successfully executed"
}

Return payload parameter description
Parameter name 	Explain
comment 	Recently added comment object
user 	User who posted the comment
file:comment:photo 	If the comment have picture

To access the image you may use following:

$image = sr_replace('comment/photo/', '', $comment['file:comment:photo']);
$url = "https://www.mywebstie.com/comment/image/{$comment->id}/{$image}";

Remakrs

    if comment is failed to add you will get error code 200
    If type is post comment will be stored in comments:post if it is entity it will be stored in comments:entity

