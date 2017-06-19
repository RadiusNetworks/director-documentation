# Beacons API

- [Listing A Team's Beacons](#listing-a-team's-beacons)
- [Getting A Beacon](#getting-a-beacon)
- [Creating A Beacon](#creating-a-beacon)
- [Updating A Beacon Changing An Attribute](#updating-a-beacon-changing-an-attribute)
- [Updating A Beacon Not Changing An Attribute](#updating-a-beacon-not-changing-an-attribute)
- [Deleting A Beacon](#deleting-a-beacon)

All actions against beacons require at a minimum an authenticated user who
is a member of the team to which the beacons belong.

## Headers <a href="#headers" id="headers" class="headerlink"></a>

### Authorization <a href="#authorization" id="authorization" class="headerlink"></a>

The API Key is passed via the Authorization header:

```
Authorization: Token token="secret"
```

The API Key is associated with your account and has access to all the resources
associated with your account. Account specific API keys have different
permissions than the web login users that can interact with the dashboard, and
the access may be different.

If you do not have an API key, [you can create one here](https://account.radiusnetworks.com/personal_token).

**Note:** Per [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec2.html#sec2.2)
the Authorization Header's token needs to be surrounded by double quotes (`"`).

### Content Type <a href="#content-type" id="content-type" class="headerlink"></a>

The content type is `vnd.rn+json` and should be set in the `Content-Type`
header:

```
Content-Type: application/vnd.rn+json
```

## Listing A Team's Beacons <a href="#listing-a-team's-beacons" class="header-link"></a>

```
GET /api/v1/teams/1/beacons
```

List beacons for the specified team.

Beacons are associated to a specific `Team`. The desired team's `id`
must be provided in the URL.

### Response <a href="#listing-a-team's-beacons-response" class="header-link"></a>

```
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "beacons.team": "https://director.radiusnetworks.com/api/v1/teams/{beacons.team}"
  },
  "beacons": [
    {
      "id": "17794",
      "name": "Beacon bow taxi",
      "uuid": "82a8fa2e-401d-46d3-a648-6fac90da8854",
      "major": 1,
      "minor": 19,
      "description": null,
      "beacon_model": "Generic",
      "transmit_power": 3,
      "measured_power": -66,
      "advertisements_per_second": 10,
      "battery_level": 48,
      "last_seen": null,
      "last_seen_threshold": 259200,
      "offline_at": null,
      "created_at": "2015-04-15T17:56:02.125Z",
      "updated_at": "2015-04-15T17:56:02.125Z",
      "meta": {
      },
      "tags": [
        "tag1",
        "tag2"
      ],
      "links": {
        "team": "1"
      }
    },
    {
      "id": "17795",
      "name": "Beacon taxi ties",
      "uuid": "82a8fa2e-401d-46d3-a648-6fac90da8854",
      "major": 1,
      "minor": 19,
      "description": null,
      "beacon_model": "Generic",
      "transmit_power": 3,
      "measured_power": -66,
      "advertisements_per_second": 10,
      "battery_level": 81,
      "last_seen": null,
      "last_seen_threshold": 259200,
      "offline_at": null,
      "created_at": "2015-04-15T17:56:02.195Z",
      "updated_at": "2015-04-15T17:56:02.195Z",
      "meta": {
      },
      "tags": [
        "tag1",
        "tag2"
      ],
      "links": {
        "team": "1"
      }
    },
    {
      "id": "17796",
      "name": "Beacon ties cool",
      "uuid": "82a8fa2e-401d-46d3-a648-6fac90da8854",
      "major": 1,
      "minor": 19,
      "description": null,
      "beacon_model": "Generic",
      "transmit_power": 3,
      "measured_power": -66,
      "advertisements_per_second": 10,
      "battery_level": 32,
      "last_seen": null,
      "last_seen_threshold": 259200,
      "offline_at": null,
      "created_at": "2015-04-15T17:56:02.223Z",
      "updated_at": "2015-04-15T17:56:02.223Z",
      "meta": {
      },
      "tags": [
        "tag1",
        "tag2"
      ],
      "links": {
        "team": "1"
      }
    }
  ]
}
```

### Curl Example <a href="#listing-a-team's-beacons-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/teams/1/beacons \
  -is \
  -X GET \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"'
```

## Getting A Beacon <a href="#getting-a-beacon" class="header-link"></a>

```
GET /api/v1/beacons/17815
```

List a specific beacon for the authenticated user. The desired beacons's `id` needs to be provided in the URL.

### Response <a href="#getting-a-beacon-response" class="header-link"></a>

```
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "beacons.team": "https://director.radiusnetworks.com/api/v1/teams/{beacons.team}"
  },
  "beacons": [
    {
      "id": "17815",
      "name": "Beacon fez taxi",
      "uuid": "e5fc0073-ab2f-475a-89c0-b90412bdc711",
      "major": 47,
      "minor": 77,
      "description": null,
      "beacon_model": "Generic",
      "transmit_power": 3,
      "measured_power": -66,
      "advertisements_per_second": 10,
      "battery_level": 35,
      "last_seen": null,
      "last_seen_threshold": 259200,
      "offline_at": null,
      "created_at": "2015-04-15T17:56:03.056Z",
      "updated_at": "2015-04-15T17:56:03.056Z",
      "meta": {
      },
      "tags": [
        "tag1",
        "tag2"
      ],
      "links": {
        "team": "3"
      }
    }
  ]
}
```

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0

{
  "links": {
    "beacons.team": "https://director.radiusnetworks.com/api/v1/teams/{beacons.team}"
  },
  "beacons": [
    {
      "id": "17815",
      "name": "Beacon fez taxi",
      "uuid": "e5fc0073-ab2f-475a-89c0-b90412bdc711",
      "major": 47,
      "minor": 77,
      "description": null,
      "beacon_model": "Generic",
      "transmit_power": 3,
      "measured_power": -66,
      "advertisements_per_second": 10,
      "battery_level": 35,
      "last_seen": null,
      "last_seen_threshold": 259200,
      "offline_at": null,
      "created_at": "2015-04-15T17:56:03.056Z",
      "updated_at": "2015-04-15T17:56:03.056Z",
      "meta": {
      },
      "tags": [
        "tag1",
        "tag2"
      ],
      "links": {
        "team": "3"
      }
    }
  ]
}
```

### Curl Example <a href="#getting-a-beacon-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/beacons/17815 \
  -is \
  -X GET \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"'
```

## Creating A Beacon <a href="#creating-a-beacon" class="header-link"></a>

```
POST /api/v1/teams/3/beacons
```

Create a beacon for the specified team. The desired team's `id` must be
provided in the URL. In order to create a beacon, the authenticated
user must be a member of the team.

### Parameters <a href="#creating-a-beacon-parameters" class="header-link"></a>

All beacons **must** be sent in an array nested under a top level
`beacons` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `name` | `string` | Display name of the beacon (e.g. Front Door, Register, Loading Dock) |
| `uuid` | `string` | **Required.** The proximity UUID of the beacon |
| `major` | `integer` | **Required.** The major value of the beacon |
| `minor` | `integer` | **Required.** The minor value of the beacon |
| `description` | `string` | Description or notes of install location for the beacon |
| `transmit_power` | `integer` | The transmit power level of the beacon (in dBm) |
| `measured_power` | `integer` | The measured power level of the beacon (in dBm) |
| `advertisements_per_second` | `integer` | The number of advertisments the beacon transmits per second |
| `last_seen` | `string` | The timestamp the beacon was last seen in ISO 8601 format |
| `last_seen_threshold` | `integer` | Number of seconds that must elapse since the beacon was last seen before it is considered offline |
| `beacon_model` | `string` | The type of the beacon |
| `tags` | `array` | List of `string` tags associated with the beacon |

### Example <a href="#creating-a-beacon-example" class="header-link"></a>

A successful beacon creation returns the generated beacon document with
updated timestamps. The response includes a `Location` header with
created beacon's canonical resource URL.

```json
{
  "beacons": {
    "name": "RSpec Beacon 1",
    "uuid": "542d222f-e6b3-4832-8fd1-90bf04a38a3c",
    "major": 48,
    "minor": 44,
    "description": "Testing beacon 1 creation",
    "beacon_model": "Generic",
    "transmit_power": 8,
    "measured_power": -58,
    "advertisements_per_second": 11,
    "last_seen": "2015-04-15T14:56:04.261Z",
    "last_seen_threshold": 32400,
    "tags": [
      "tag3"
    ]
  }
}
```

### Response <a href="#creating-a-beacon-response" class="header-link"></a>

```
Status: 201 Created
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
Location: https://director.radiusnetworks.com/api/v1/beacons/17850
```
```json
{
  "links": {
    "beacons.team": "https://director.radiusnetworks.com/api/v1/teams/{beacons.team}"
  },
  "beacons": [
    {
      "id": "17850",
      "name": "RSpec Beacon 1",
      "uuid": "542d222f-e6b3-4832-8fd1-90bf04a38a3c",
      "major": 48,
      "minor": 44,
      "description": "Testing beacon 1 creation",
      "beacon_model": "Generic",
      "transmit_power": 8,
      "measured_power": -58,
      "advertisements_per_second": 11,
      "battery_level": null,
      "last_seen": "2015-04-15T14:56:04.261Z",
      "last_seen_threshold": 32400,
      "offline_at": "2015-04-15T23:56:04.261Z",
      "created_at": "2015-04-15T17:56:04.274Z",
      "updated_at": "2015-04-15T17:56:04.274Z",
      "meta": {
      },
      "tags": [
        "tag3"
      ],
      "links": {
        "team": "3"
      }
    }
  ]
}
```

### Curl Example <a href="#creating-a-beacon-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/teams/3/beacons \
  -is \
  -X POST \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "beacons": {
      "name": "RSpec Beacon 1",
      "uuid": "542d222f-e6b3-4832-8fd1-90bf04a38a3c",
      "major": 48,
      "minor": 44,
      "description": "Testing beacon 1 creation",
      "beacon_model": "Generic",
      "transmit_power": 8,
      "measured_power": -58,
      "advertisements_per_second": 11,
      "last_seen": "2015-04-15T14:56:04.261Z",
      "last_seen_threshold": 32400,
      "tags": [
        "tag3"
      ]
    }
  }'
```

## Updating A Beacon Changing An Attribute <a href="#updating-a-beacon-changing-an-attribute" class="header-link"></a>

```
PUT /api/v1/beacons/17875
```

In order to update a beacon, the authenticated user must be a member of
the team that the beacon is associated with.

### Parameters <a href="#updating-a-beacon-changing-an-attribute-parameters" class="header-link"></a>

All beacons **must** be sent in an array nested under a top level
`beacons` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `id` | `string` | **Required.** The id of the beacon |
| `name` | `string` | Display name of the beacon (e.g. Front Door, Register, Loading Dock) |
| `uuid` | `string` | **Required.** The proximity UUID of the beacon |
| `major` | `integer` | **Required.** The major value of the beacon |
| `minor` | `integer` | **Required.** The minor value of the beacon |
| `description` | `string` | Description or notes of install location for the beacon |
| `transmit_power` | `integer` | The transmit power level of the beacon (in dBm) |
| `measured_power` | `integer` | The measured power level of the beacon (in dBm) |
| `advertisements_per_second` | `integer` | The number of advertisments the beacon transmits per second |
| `last_seen` | `string` | The timestamp the beacon was last seen in ISO 8601 format |
| `last_seen_threshold` | `integer` | Number of seconds that must elapse since the beacon was last seen before it is considered offline |
| `beacon_model` | `string` | The type of the beacon |
| `tags` | `array` | List of `string` tags associated with the beacon |

### Example <a href="#updating-a-beacon-changing-an-attribute-example" class="header-link"></a>

A successful update modifies the beacon's `updated_at` field. If the
update modifies the `last_seen_threshold` and the beacon has been seen
the response document contains an updated `offline_at` field.

```json
{
  "beacons": {
    "id": 17875,
    "transmit_power": 4
  }
}
```

### Response <a href="#updating-a-beacon-changing-an-attribute-response" class="header-link"></a>

```
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "beacons.team": "https://director.radiusnetworks.com/api/v1/teams/{beacons.team}"
  },
  "beacons": [
    {
      "id": "17875",
      "name": "Beacon bow service",
      "uuid": "92492a2d-e3be-4759-a3ca-dd09eb56d251",
      "major": 34,
      "minor": 0,
      "description": null,
      "beacon_model": "Generic",
      "transmit_power": 4,
      "measured_power": -66,
      "advertisements_per_second": 10,
      "battery_level": 40,
      "last_seen": "2015-04-14T17:56:05.259Z",
      "last_seen_threshold": 259200,
      "offline_at": "2015-04-17T17:56:05.259Z",
      "created_at": "2015-04-15T17:56:05.264Z",
      "updated_at": "2015-04-15T17:56:05.460Z",
      "meta": {
      },
      "tags": [
        "tag1",
        "tag2"
      ],
      "links": {
        "team": "3"
      }
    }
  ]
}
```

### Curl Example <a href="#updating-a-beacon-changing-an-attribute-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/beacons/17875 \
  -is \
  -X PUT \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "beacons": {
      "id": 17875,
      "transmit_power": 4
    }
  }'
```

## Updating A Beacon Not Changing An Attribute <a href="#updating-a-beacon-not-changing-an-attribute" class="header-link"></a>

```
PUT /api/v1/beacons/17899
```

In order to update a beacon, the authenticated user must be a member of
the team that the beacon is associated with.

### Parameters <a href="#updating-a-beacon-not-changing-an-attribute-parameters" class="header-link"></a>

All beacons **must** be sent in an array nested under a top level
`beacons` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `id` | `string` | **Required.** The id of the beacon |
| `name` | `string` | Display name of the beacon (e.g. Front Door, Register, Loading Dock) |
| `uuid` | `string` | **Required.** The proximity UUID of the beacon |
| `major` | `integer` | **Required.** The major value of the beacon |
| `minor` | `integer` | **Required.** The minor value of the beacon |
| `description` | `string` | Description or notes of install location for the beacon |
| `transmit_power` | `integer` | The transmit power level of the beacon (in dBm) |
| `measured_power` | `integer` | The measured power level of the beacon (in dBm) |
| `advertisements_per_second` | `integer` | The number of advertisments the beacon transmits per second |
| `last_seen` | `string` | The timestamp the beacon was last seen in ISO 8601 format |
| `last_seen_threshold` | `integer` | Number of seconds that must elapse since the beacon was last seen before it is considered offline |
| `beacon_model` | `string` | The type of the beacon |
| `tags` | `array` | List of `string` tags associated with the beacon |

### Example <a href="#updating-a-beacon-not-changing-an-attribute-example" class="header-link"></a>

If you do not provide attributes, or if all of the provided attributes
for a are the same, the beacon is not updated. In these cases a
`204 No Content` response is returned.

This response will have an empty body per HTTP schemantics.

```json
{
  "beacons": {
    "id": 17899,
    "transmit_power": 3
  }
}
```

### Response <a href="#updating-a-beacon-not-changing-an-attribute-response" class="header-link"></a>

```
Status: 204 No Content
Director-Media-Type: director.v1
Director-API-Version: 1.0
```

### Curl Example <a href="#updating-a-beacon-not-changing-an-attribute-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/beacons/17899 \
  -is \
  -X PUT \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "beacons": {
      "id": 17899,
      "transmit_power": 3
    }
  }'
```

## Deleting A Beacon <a href="#deleting-a-beacon" class="header-link"></a>

```
DELETE /api/v1/beacons/17922
```

In order to delete a beacon, the authenticated user must be a member of
the team that the beacon is associated with.

### Response <a href="#deleting-a-beacon-response" class="header-link"></a>

```
Status: 204 No Content
Director-Media-Type: director.v1
Director-API-Version: 1.0
```

### Curl Example <a href="#deleting-a-beacon-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/beacons/17922 \
  -is \
  -X DELETE \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"'
```
