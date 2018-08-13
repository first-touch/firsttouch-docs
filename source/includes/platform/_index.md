# Platform Generic API endpoints

## Playing Positions

```ruby
FirstTouch::PLAYING_POSITIONS
```

> The above command returns JSON structured like this:

```json
[
  "Goalkeeper",
  "Sweeper (Centre)",
  "Defender (Right)",
  "Defender (Left)",
  "Defender (Centre)",
  "Wing-back (Right)",
  "Wing-back (Left)",
  "Defensive Midfielder (Centre)",
  "Midfielder (Right)",
  "Midfielder (Left)",
  "Midfielder (Centre)",
  "Attacking Midfielder (Centre)",
  "Winger (Right)",
  "Winger (Left)",
  "Second Striker (Centre)",
  "Striker (Centre)"
]
```

This endpoint allows the requester to fetch the possible playing positions.

### HTTP Request

`GET http://example.com/api/v1/settings/playing_positions`
