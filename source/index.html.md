---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - ruby

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, and Python! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Code Structure

Since FirstTouch relies on Trailblazer approach, most of our actions have an operation associated. For each action there will be the explanation on how to run the operation in the terminal.

# Authentication

FirstTouch uses API keys to allow access to the API. You can register a new user to get the FirstTouch API key through [the signup page](#SignUp) or running the [register operation](#RegisterOperation) directly on the rails console.

FirstTouch expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Users

## Sign up/Register

```ruby
::V1::User::Register.(params)
```

> The above command returns JSON structured like this:

```json
{
  "user": {
    "id": 10,
    "career_history": [],
    "personal_profile": {
      "id": 13,
      "first_name": "Rui",
      "middle_name": null,
      "last_name": "Baltazar",
      "birthday": "1998-02-10",
      "nationality_country_code": null,
      "residence_country_code": null,
      "place_of_birth": null,
      "weight": null,
      "height": null,
      "preferred_foot": null,
      "languages": null,
      "playing_position": null,
      "pro_status": null,
      "total_caps": null
    }
  }
}
```

This endpoint allows a new user to be registered.

### HTTP Request

`GET http://example.com/api/v1/users/register`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
email | Y | | User registration email
password | Y | | User's preferred password
password_confirmation | Y |  | Double checking of password
role_name | Y | | Which role is the user registering as. Choice from `player`, `manager`, `coach`, `scout`, `director`
personal_profile | Y |  | key for personal profile attributes

The following attributes can/have to be passed in the `personal_profile`

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
first_name | Y | | User's first name
middle_name | N | | User's middle name
last_name | Y | | User's last name
birthday | Y |  | User's birthday
club_id | Y |  | Which club is the user associated with, if any
nationality_country_code | N | | Players nationality country code
residence_country_code | N | | Players residence country code
weight | N | | Players weight
height | N | | Players height
preferred_foot | N | | Preferred foot
playing_position | N | | Playing position
pro_status | N | | Professional status


## Login

> The above command returns JSON structured like this:

```json
{
 "auth_token": "amazing_api_key"
}
```

This endpoint allows a user to fetch the users authorization key.

### HTTP Request

`GET http://example.com/api/v1/authenticate`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
email | Y | | User email
password | Y | | User's password

## Public Profile

```ruby
::V1::User::Show.(params)
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "following": false,
  "personal_profile": {
    "id": 7
  },
  "connection_status": "pending"
}

```

This api endpoint should be used to fetch a particular user's profile

### HTTP Request

`GET http://example.com/api/v1/users/<:id>/profile`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
id | Y | | Requested User Id
