# Users

## Sign up/Register

```ruby
::V1::User::Register.(params: params)
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
      "playing_positions": [
        { "position": "Goalkeeper", "skill": "[0-5]" }
      ],
      "pro_status": "Amateur",
      "total_caps": 0
    }
  }
}
```

This endpoint allows a new user to be registered. After being registered,
an email is sent to the user to confirm the email address thus confirming the
account. Only after confirming the email address the user will be able to login.

### HTTP Request

`GET http://example.com/api/v1/users/register`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
email | Y | | User registration email
password | Y | | User's preferred password
password_confirmation | Y |  | Double checking of password
role_name | Y | | Which role is the user registering as. Choice from `player`, `manager`, `coach`, `scout`, `director`
club_ids | Y |  | Which club is the user associated with, if any
personal_profile | Y |  | key for personal profile attributes

The following attributes can/have to be passed in the `personal_profile`

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
first_name | Y | | User's first name
middle_name | N | | User's middle name
last_name | Y | | User's last name
birthday | Y |  | User's birthday
nationality_country_code | N | | Players nationality country code
residence_country_code | N | | Players residence country code
weight | N | | Players weight in Kg
height | N | | Players height in cm
preferred_foot | N | | Preferred foot
playing_positions | N | | JSON Array with the following structure per playing position: { position: <position name>, skill: <0-5> }
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
::V1::User::Show.(params: params)
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

## Personal Profile

> The above command returns JSON structured like this:

```json
{
  "id": 2,
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
    "playing_positions": [
      { "position": "Goalkeeper", "skill": "[0-5]" }
    ],
    "pro_status": "Amateur",
    "total_caps": 0,
    "avatar_url": "https://images.google.com/img1.png"
  }
}

```

This api endpoint should be used to fetch a particular user's profile

### HTTP Request

`GET http://example.com/api/v1/user`

### Query Parameters

N.A

## Update Personal Profile

```ruby
::V1::User::Update.(params: params, current_user: current_user)
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
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
    "playing_positions": [
      { "position": "Goalkeeper", "skill": "[0-5]" }
    ],
    "pro_status": "Amateur",
    "total_caps": 0,
    "avatar_url": "https://images.google.com/img1.png"
  }
}

```

This api endpoint should be used to fetch a particular user's profile

### HTTP Request

`POST http://example.com/api/v1/user`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
personal_profile | Y | | User's personal profile holder. It follows the next table params

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
first_name | Y | | String with First Name
middle_name | | | String with Middle Name
last_name | Y | | String with Last Name
birthday | Y | | String with Birthday. Preferred format: YYYY-MM-DD
nationality_country_code | | | Country code in ISO Format
residence_country_code | | | Country code in ISO Format
place_of_birth | | | String with place of birth
weight | | | Float with weight
height | | | Float with height
preferred_foot | | | Choice between: [`right`, `left`, `both`]
playing_positions | | | Array with playing positions and skill. E.g. `[{ "position": "Goalkeeper", "skill": 5 }]`. Available playing positions: [`Goalkeeper`, `Sweeper (Centre)`, `Defender (Right)`, `Defender (Left)`, `Defender (Centre)`, `Wing-back (Right)`, `Wing-back (Left)`, `Defensive Midfielder (Centre)`, `Midfielder (Right)`, `Midfielder (Left)`, `Midfielder (Centre)`, `Attacking Midfielder (Centre)`, `Winger (Right)`, `Winger (Left)`, `Second Striker (Centre)`, `Striker (Centre)`]
pro_status | | | Choice between: [`professional`, `semi-professional`, `amateur`]
biography | | | Text with user's biography


## Update Personal Avatar

```ruby
::V1::User::Update.(params: params, current_user: current_user)
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
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
    "playing_positions": [
      { "position": "Goalkeeper", "skill": "[0-5]" }
    ],
    "pro_status": "Amateur",
    "total_caps": 0,
    "avatar_url": "https://images.google.com/img1.png"
  }
}

```

This api endpoint should be used to fetch a particular user's profile

### HTTP Request

`POST http://example.com/api/v1/user/avatar`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
avatar | Y | | formData with new image
