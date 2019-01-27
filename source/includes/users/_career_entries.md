# Career Entries

## Create

```ruby
::V1::CareerEntry::Create.(params: params)
```

> The above command returns JSON structured like this:

```json
{
  "career_entry": {
    "id": 10,
    "start_date": "1998-02-10",
    "end_date": "1999-02-10",
    "club": {
      "id" : 2,
      "name": "F. C. Barcelona"
    }
  }
}
```

This endpoint allows a new user to be registered.

### HTTP Request

`POST http://example.com/api/v1/career_entries`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
club_id | Y | | Club which the user represented
start_date | Y | | Career entry Start date
end_date | N |  | Career entry End date. Might be nil which would mean ongoing
role_name | Y | | Which role the user was representing: `player`, `manager`, `coach`, `scout`, `director`

## Update

```ruby
::V1::CareerEntry::Update.(params: params)
```

> The above command returns JSON structured like this:

```json
{
  "career_entry": {
    "id": 10,
    "start_date": "1998-02-10",
    "end_date": "1999-02-10",
    "club": {
      "id" : 2,
      "name": "F. C. Barcelona"
    }
  }
}
```

This endpoint allows a new user to be registered.

### HTTP Request

`PUT http://example.com/api/v1/career_entries/10`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
id | Y |  | Server id of career entry to be updated. Passed as part of the URL
club_id | Y | | Club which the user represented
start_date | Y | | Career entry Start date
end_date | N |  | Career entry End date. Might be nil which would mean ongoing
role_name | Y | | Which role the user was representing: `player`, `manager`, `coach`, `scout`, `director`

## Delete

```ruby
::V1::CareerEntry::Delete.(params: params)
```

> The above command returns JSON structured like this:

```json
{
  "career_entry": {
    "id": 10
  }
}
```

This endpoint allows a new user to be registered.

### HTTP Request

`DELETE http://example.com/api/v1/career_entries/10`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
id | Y |  | Server id of career entry to be deleted. Passed as part of the URL
