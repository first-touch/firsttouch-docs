# Notes

## Create

```ruby
::V1::Note::Create.(params: params, current_user: user)
```

> The above command returns JSON structured like this:

```json
{
  "id": 4,
  "user_id": 8,
  "name": "test",
  "content": "hello",
  "labels": [
    "one",
    "two",
    "three"
  ]
}
```

This endpoint allows user to create a note under his account

### HTTP Request

`POST http://example.com/api/v1/notes`

### Query Parameters

These params should be passed inside key `note`

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
labels | N | [] | Array of labels associated with the note
name | Y | | Note name
content | Y | | Note contents

## Update

```ruby
::V1::Note::Update.(params: params)
```

> The above command returns JSON structured like this:

```json
{
  "id": 4,
  "user_id": 8,
  "name": "test",
  "content": "hello",
  "labels": [
    "one",
    "two",
    "three"
  ]
}
```

### HTTP Request

`PUT http://example.com/api/v1/notes/4`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
id | Y |  | Server id of note to be updated. Passed as part of the URL
labels | N | [] | Array of labels associated with the note
name | Y | | Note name
content | Y | | Note contents

## Delete

```ruby
::V1::Note::Delete.(params: params)
```

> The above command returns JSON structured like this:

```json
{
  "note": {
    "id": 10
  }
}
```

This endpoint allows a new user to be registered.

### HTTP Request

`DELETE http://example.com/api/v1/notes/10`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
id | Y |  | Server id of note to be deleted. Passed as part of the URL
