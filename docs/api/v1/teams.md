# Teams API

- [Listing Your Teams](#listing-your-teams)
- [Getting A Team](#getting-a-team)
- [Updating A Team Changing An Attribute](#updating-a-team-changing-an-attribute)
- [Updating A Team Not Changing An Attribute](#updating-a-team-not-changing-an-attribute)

Teams allow you to share access to Radius Networks services and dashboards.
All actions against teams require an authenticated user who is a member of
the team. Director synchronizes your teams when you sign in.

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

## Listing Your Teams <a href="#listing-your-teams" class="header-link"></a>

```
GET /api/v1/teams
```

List teams for the authenticated user.

### Response <a href="#listing-your-teams-response" class="header-link"></a>

```
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "teams.beacons": "https://director.radiusnetworks.com/api/v1/beacons/{teams.beacons}"
  },
  "teams": [
    {
      "id": "1",
      "name": "alien tardis",
      "default_last_seen_threshold": null,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "855b59b1f1a2d621cd35aeef207d2341e268849b7026849b",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:07.376Z",
      "updated_at": "2015-04-15T17:56:07.376Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/1/beacons"
        }
      }
    },
    {
      "id": "3",
      "name": "hal alien rspec tardis testing",
      "default_last_seen_threshold": null,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "dbfd27a6c8437968a631d05022e98c63144682857ee26c2e",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:07.475Z",
      "updated_at": "2015-04-15T17:56:07.475Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/3/beacons"
        }
      }
    },
    {
      "id": "2",
      "name": "hal tardis alien testing",
      "default_last_seen_threshold": null,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "189afe0616c8ebb6ed0e924f50ee07c6cea1fb61d338029b",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:07.441Z",
      "updated_at": "2015-04-15T17:56:07.441Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/2/beacons"
        }
      }
    },
    {
      "id": "5",
      "name": "rspec hal",
      "default_last_seen_threshold": null,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "7290ca7340d2304a15aae7cd6afd4b6ca0c3c379788b9b1f",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:07.525Z",
      "updated_at": "2015-04-15T17:56:07.525Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/5/beacons"
        }
      }
    },
    {
      "id": "6",
      "name": "tardis hal testing alien rspec",
      "default_last_seen_threshold": null,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "938af838a3380ffb98d06dde2209894bdef6500424cb83bc",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:07.549Z",
      "updated_at": "2015-04-15T17:56:07.549Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/6/beacons"
        }
      }
    },
    {
      "id": "4",
      "name": "testing tardis",
      "default_last_seen_threshold": null,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "7afb0cbdbb9cac99bb65dea9472972f142d7ccf2711fc6b3",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:07.502Z",
      "updated_at": "2015-04-15T17:56:07.502Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/4/beacons"
        }
      }
    }
  ]
}
```

### Curl Example <a href="#listing-your-teams-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/teams \
  -is \
  -X GET \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"'
```

## Getting A Team <a href="#getting-a-team" class="header-link"></a>

```
GET /api/v1/teams/3
```

List a specific team for the authenticated user. The desired team's `id` needs to be provided in the URL.

### Response <a href="#getting-a-team-response" class="header-link"></a>

```
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "teams.beacons": "https://director.radiusnetworks.com/api/v1/beacons/{teams.beacons}"
  },
  "teams": [
    {
      "id": "3",
      "name": "tardis",
      "default_last_seen_threshold": null,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "4e677c63193eba8adef8b6188838df581e8ce5067e443c3f",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:07.982Z",
      "updated_at": "2015-04-15T17:56:07.982Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/3/beacons"
        }
      }
    }
  ]
}
```

### Curl Example <a href="#getting-a-team-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/teams/3 \
  -is \
  -X GET \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"'
```

## Updating A Team Changing An Attribute <a href="#updating-a-team-changing-an-attribute" class="header-link"></a>

```
PUT /api/v1/teams/4
```

Teams are mostly created and managed on the account server. However,
Director has a few internal settings that are specific to a team. Only
these settings can be updated via this API. The remaining settings
must be changed on the account server.

### Parameters <a href="#updating-a-team-changing-an-attribute-parameters" class="header-link"></a>

All teams **must** be sent in an array nested under a top level
`teams` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `id` | `string` | **Required.** The team's id |
| `default_last_seen_threshold` | `integer` | Team's default value, in seconds, that must elapse since a beacon was last seen before it is considered offline. |

### Example <a href="#updating-a-team-changing-an-attribute-example" class="header-link"></a>

Successfully updating a team modifies the `updated_at` field. Since
this field is updated internally, the full team resource is returned in
the response body.

```json
{
  "teams": {
    "id": 4,
    "default_last_seen_threshold": 5547
  }
}
```

### Response <a href="#updating-a-team-changing-an-attribute-response" class="header-link"></a>

```
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "teams.beacons": "https://director.radiusnetworks.com/api/v1/beacons/{teams.beacons}"
  },
  "teams": [
    {
      "id": "4",
      "name": "alien hal testing tardis rspec",
      "default_last_seen_threshold": 5547,
      "beacons_count": 0,
      "beacons_online": 0,
      "beacons_offline": 0,
      "beacons_unknown": 0,
      "credentials": [
        {
          "description": "RSpec Test",
          "token": "750681b8bd7b70f9bdc9d6514c013501e4394b169d17ee6d",
          "last_used_at": null
        }
      ],
      "created_at": "2015-04-15T17:56:08.358Z",
      "updated_at": "2015-04-15T17:56:08.429Z",
      "links": {
        "beacons": {
          "href": "https://director.radiusnetworks.com/api/v1/teams/4/beacons"
        }
      }
    }
  ]
}
```

### Curl Example <a href="#updating-a-team-changing-an-attribute-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/teams/4 \
  -is \
  -X PUT \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "teams": {
      "id": 4,
      "default_last_seen_threshold": 5547
    }
  }'
```

## Updating A Team Not Changing An Attribute <a href="#updating-a-team-not-changing-an-attribute" class="header-link"></a>

```
PUT /api/v1/teams/3
```

### Parameters <a href="#updating-a-team-not-changing-an-attribute-parameters" class="header-link"></a>

All teams **must** be sent in an array nested under a top level
`teams` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `id` | `string` | **Required.** The team's id |
| `default_last_seen_threshold` | `integer` | Team's default value, in seconds, that must elapse since a beacon was last seen before it is considered offline. |

### Example <a href="#updating-a-team-not-changing-an-attribute-example" class="header-link"></a>

If you do not provide attributes, or if all of the provided attributes
are the same, the record is not updated. In these cases a `204 No
Content` response is returned.

This response will have an empty body per HTTP schemantics.

```json
{
  "teams": {
    "id": 3,
    "name": "RN's test",
    "default_last_seen_threshold": null
  }
}
```

### Response <a href="#updating-a-team-not-changing-an-attribute-response" class="header-link"></a>

```
Status: 204 No Content
Director-Media-Type: director.v1
Director-API-Version: 1.0
```

### Curl Example <a href="#updating-a-team-not-changing-an-attribute-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/teams/3 \
  -is \
  -X PUT \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "teams": {
      "id": 3,
      "name": "RN\u0027s test",
      "default_last_seen_threshold": null
    }
  }'
```
