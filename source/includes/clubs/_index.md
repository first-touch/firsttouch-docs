# Clubs

## Search

```ruby
::V1::Club::Index.(params)
```

> The above command returns JSON structured like this:

```json
{
  "clubs": [{
    "id": 1,
    "name": "Bananas",
    "city": "City",
    "country_code": "PT"
  }]
}

```

This endpoint to search for a club. It allows searching by a keyword using `q` param
or a country code using `country` param, or both combined

### HTTP Request

`GET http://example.com/api/v1/clubs/search`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
q | N | | Keyword to match club's name
country | N | | ISO Country Code to filter the clubs

## Countries

```ruby
::V1::Club::Countries.()
```

> The above command returns JSON structured like this:

```json
{
  "countries": [{
      "country_name": "Portugal",
      "country_code": "PT"
    },
    {
      "country_name": "United States of America",
      "country_code": "US"
    }
  ]
}
```

This endpoint is used to fetch the countries for which we have clubs available in the
database.

### HTTP Request

`GET http://example.com/api/v1/clubs/countries`

### Query Parameters

Parameter | Mandatory | Default | Description
--------- | --------- | ------- | -----------
