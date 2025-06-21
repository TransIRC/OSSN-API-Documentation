# OSSN Services API Documentation

This repository hosts the un-official API documentation for OSSN (Open Source Social Network) Services. It provides detailed information on all available endpoints, their methods, parameters, and example responses, enabling developers to build powerful applications on top of the OSSN platform.

## Table of Contents

* [About](#about)
* [API Versioning](#api-versioning)
* [Authentication](#authentication)
* [Available Endpoints](#available-endpoints)
    * [User Management](#user-management)
    * [Content (Posts & Photos)](#content-posts--photos)
    * [Interaction (Likes & Comments)](#interaction-likes--comments)
    * [Messaging](#messaging)
    * [Groups](#groups)
    * [Notifications](#notifications)
    * [Core Components](#core-components)
* [Getting Started](#getting-started)


## About

The OSSN Services API provides programmatic access to the core functionalities of the Open Source Social Network platform. This documentation aims to be a comprehensive guide for developers looking to integrate with or build applications that leverage OSSN's user management, content sharing, interaction, messaging, and group features.

## API Versioning

The API currently supports versions `v1.0` and `v2.0` of certain endpoints.
* **`v1.0`**: Standard API endpoints.
* **`v2.0`**: Introduces enhancements and sometimes breaking changes for specific functionalities (e.g., `message/send`, `message/list`, `message/new`, `user/blocklist`, `group/delete`, `post/edit`). Please refer to individual endpoint documentation for specific version details and any differences.

## Authentication

All API requests **must** include your `api_key_token` as a parameter (either via `GET` or `POST`). This API key is essential for authenticating your requests.

## Available Endpoints

The API is organized into several categories for easier navigation:

### User Management
* [`user_add`](docs/endpoints/user_add.md): Add a new user to the system.
* [`user_authenticate`](docs/endpoints/user_authenticate.md): Authenticate a user with username/email and password.
* [`user_details`](docs/endpoints/user_details.md): Retrieve basic profile details for a user.
* [`user_edit`](docs/endpoints/user_edit.md): Edit a user's profile information.
* [`user_delete`](docs/endpoints/user_delete.md): Permanently delete a non-admin user. (v2.0)
* [`user_friends`](docs/endpoints/user_friends.md): Get a list of a user's friends.
* [`user_add_friend`](docs/endpoints/user_add_friend.md): Send or accept a friend request.
* [`user_remove_friend`](docs/endpoints/user_remove_friend.md): Remove a friend connection.
* [`user_friend_requests`](docs/endpoints/user_friend_requests.md): Get pending friend requests for a user.
* [`user_is_friend`](docs/endpoints/user_is_friend.md): Check if two users are friends.
* [`user_blocklist`](docs/endpoints/user_blocklist.md): Get a list of users blocked by a specific user. (v2.0)

### Content (Posts & Photos)
* [`wall_add`](docs/endpoints/wall_add.md): Add a new wall post (text and/or photo) for a user or group.
* [`wall_edit`](docs/endpoints/post_edit.md): Edit the text content of an existing wall post. (v2.0, original file `post_edit.md`)
* [`wall_delete`](docs/endpoints/wall_delete.md): Delete an existing wall post.
* [`wall_list_home`](docs/endpoints/wall_list_home.md): List newsfeed wall posts.
* [`wall_list_user`](docs/endpoints/wall_list_user.md): List wall posts for a user's profile.
* [`wall_list_group`](docs/endpoints/wall_list_group.md): List wall posts for a specific group.
* [`wall_view`](docs/endpoints/wall_view.md): Retrieve details of a single wall post.
* [`photos_album_create`](docs/endpoints/photos_album_create.md): Create a new photo album for a user.
* [`photos_album_add`](docs/endpoints/photos_album_add.md): Add a photo to an existing album.
* [`photos_list_albums`](docs/endpoints/photos_list_albums.md): List all albums owned by a user.
* [`photos_list`](docs/endpoints/photos_list.md): List photos within a specific album (excluding profile/cover).
* [`photos_view`](docs/endpoints/photos_view.md): Get details for a standard album photo.
* [`photos_view_profile`](docs/endpoints/photos_view_profile.md): Get details for a profile or cover photo.
* [`photos_list_profile_cover`](docs/endpoints/photos_list_profile_cover.md): List photos from a user's profile or cover photo albums.
* [`photos_profile_add`](docs/endpoints/photos_profile_add.md): Change a user's profile photo.
* [`photos_cover_add`](docs/endpoints/photos_cover_add.md): Change a user's cover photo.
* [`photos_delete`](docs/endpoints/photos_delete.md): Delete a standard album photo.
* [`photos_delete_profile`](docs/endpoints/photos_delete_profile.md): Delete a specific profile photo.
* [`photos_delete_cover`](docs/endpoints/photos_delete_cover.md): Delete a specific profile cover photo.

### Interaction (Likes & Comments)
* [`like_add`](docs/endpoints/like_add.md): Create a like for a post, entity, or annotation.
* [`unlike_set`](docs/endpoints/unlike_set.md): Remove a like from a post, entity, or annotation.
* [`comment_add`](docs/endpoints/comment_add.md): Add a comment to a post, entity, or object.
* [`comment_edit`](docs/endpoints/comment_edit.md): Edit the text of an existing comment.
* [`comment_delete`](docs/endpoints/comment_delete.md): Delete a comment.
* [`comments_list`](docs/endpoints/comments_list.md): Retrieve comments for an entity, object, or post.

### Messaging
* [`message_add`](docs/endpoints/message_add.md): Send a message to a user.
* [`message_send_2_0`](docs/endpoints/message_send_2_0.md): Send a message with attachment support. (v2.0)
* [`message_list`](docs/endpoints/message_list.md): Get a paginated list of messages exchanged between two users.
* [`message_list_2_0`](docs/endpoints/message_list_2_0.md): Get a paginated list of messages (v2.0, includes `is_online` status).
* [`message_recent`](docs/endpoints/message_recent.md): Get a list of recent message conversations.
* [`message_new_unread`](docs/endpoints/message_new_unread.md): Get unread messages between two users. (v2.0, includes `is_online` status)
* [`message_new_unread_v1`](docs/endpoints/message_new_unread_v1.md): Get unread messages between two users. (v1.0)

### Groups
* [`groups_add`](docs/endpoints/groups_add.md): Create a new group.
* [`groups_edit`](docs/endpoints/groups_edit.md): Edit an existing group's details.
* [`group_delete`](docs/endpoints/group_delete.md): Permanently delete a group and its content. (v2.0)
* [`groups_members`](docs/endpoints/groups_members.md): Get a list of members for a group.
* [`groups_user_memberof`](docs/endpoints/groups_user_memberof.md): Retrieve all groups a user is a member of.
* [`groups_unjoin`](docs/endpoints/groups_unjoin.md): Unjoin a specific group.
* [`groups_requests`](docs/endpoints/groups_requests.md): Retrieve pending group member requests.
* [`groups_request_accept`](docs/endpoints/groups_request_accept.md): Accept a member request for a group.
* [`groups_request_decline`](docs/endpoints/groups_request_decline.md): Decline a member request for a group.

### Notifications
* [`notifications_count`](docs/endpoints/notifications_count.md): Count notifications (general, messages, friend requests) for a user.
* [`notifications_list_user`](docs/endpoints/notifications_list_user.md): Fetch a list of user notifications.
* [`notifications_mark_viewed`](docs/endpoints/notifications_mark_viewed.md): Mark a specific notification as viewed.

### Core Components
* [`components_list_enabled`](docs/endpoints/components_list_enabled.md): List all enabled (active) components for the OSSN installation.

## Getting Started

To utilize this API, you will need:

1.  **An OSSN Installation:** The API endpoints refer to your OSSN installation's base URL (e.g., `http://www.mywebsite.com/`).
2.  **An API Key:** All requests require an `api_key_token`. Refer to your OSSN Services configuration to obtain this key.

Detailed usage examples, including parameters and example responses, can be found within each endpoint's respective Markdown file in the `docs/endpoints/` directory.
