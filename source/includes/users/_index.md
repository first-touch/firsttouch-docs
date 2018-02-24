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
      "middle_name": "Pedro",
      "last_name": "Baltazar",
      "birthday": "1998-02-10",
      "nationality_country_code": "PT",
      "residence_country_code": "SG",
      "place_of_birth": "Coimbra",
      "weight": "37",
      "height": "137",
      "preferred_foot": "both",
      "languages": ["PT", "EN", "IT"],
      "playing_position": "Goalkeeper",
      "pro_status": "Amateur",
      "total_caps": 0
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

`GET http://example.com/api/v1/users/:id/profile`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
id | Y | | Requested User Id
