# SDK Access Tokens API

- [Listing A Team's Tokens](#listing-a-team's-tokens)
- [Creating A Token](#creating-a-token)
- [Updating A Token Changing An Attribute](#updating-a-token-changing-an-attribute)
- [Updating A Token Not Changing An Attribute](#updating-a-token-not-changing-an-attribute)
- [Deleting A Token](#deleting-a-token)

SDK access tokens are used to authenticate to the SDK API over HTTPS via
Token Authentication.

All actions against SDK tokens require at a minimum an authenticated user
who is a member of the team to which the tokens belong.

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

**Note:** Per [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec2.html#sec2.2) the Authorization Header's token needs to be
surrounded by double quotes (`"`).

### Content Type <a href="#content-type" id="content-type" class="headerlink"></a>

The content type is `vnd.rn+json` and should be set in the `Content-Type`
header:

```
Content-Type: application/vnd.rn+json
```

## Listing A Team's Tokens <a href="#listing-a-team's-tokens" class="header-link"></a>

Access the list of SDK access tokens for a team by
[requesting the team](teams#getting-a-team). The tokens are listed
under the `credentials` key.


## Creating A Token <a href="#creating-a-token" class="header-link"></a>

```
POST /api/v1/teams/1/tokens
```

Create an SDK access token for the specified team. The desired team's
`id` must be provided in the URL. In order to create a token, the
authenticated user must be a member of the team.

### Parameters <a href="#creating-a-token-parameters" class="header-link"></a>

All tokens **must** be sent in an array nested under a top level
`tokens` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `description` | `string` | Description of the purpose for this token |

### Example <a href="#creating-a-token-example" class="header-link"></a>

A successful SDK access token creation returns the generated token
document with server generated authorization token unique to the team.
The response includes a `Location` header with the created token's
canonical resource URL.

```json
{
  "tokens": {
    "description": "RSpec SDK Credentials 1"
  }
}
```

### Response <a href="#creating-a-token-response" class="header-link"></a>

```
Status: 201 Created
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
Location: https://director.radiusnetworks.com/api/v1/tokens/20172
```
```json
{
  "links": {
    "tokens.team": "https://director.radiusnetworks.com/api/v1/teams/{tokens.team}"
  },
  "tokens": [
    {
      "id": "20172",
      "description": "RSpec SDK Credentials 1",
      "token": "c2a4065de32add9a80b0c5aca214be27cff1ad301bb59e04",
      "last_used_at": null,
      "created_at": "2015-05-01T16:13:40.087Z",
      "updated_at": "2015-05-01T16:13:40.087Z",
      "links": {
        "team": "1"
      }
    }
  ]
}
```

### Curl Example <a href="#creating-a-token-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/teams/1/tokens \
  -is \
  -X POST \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "tokens": {
      "description": "RSpec SDK Credentials 1"
    }
  }'
```

## Updating A Token Changing An Attribute <a href="#updating-a-token-changing-an-attribute" class="header-link"></a>

```
PUT /api/v1/tokens/20234
```

In order to update an SDK access token, the authenticated user must be
a member of the team that the token is associated with.

### Parameters <a href="#updating-a-token-changing-an-attribute-parameters" class="header-link"></a>

All tokens **must** be sent in an array nested under a top level
`tokens` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `id` | `string` | **Required.** The id of the token |
| `description` | `string` | Description of the purpose for this token |

### Example <a href="#updating-a-token-changing-an-attribute-example" class="header-link"></a>

Updates ignore any changes to the secret `"token"` field.

A successful update modifies the token's `updated_at` field.

```json
{
  "tokens": {
    "id": 20234,
    "token": "this is ignored",
    "description": "This description is modified"
  }
}
```

### Response <a href="#updating-a-token-changing-an-attribute-response" class="header-link"></a>

```
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "tokens.team": "https://director.radiusnetworks.com/api/v1/teams/{tokens.team}"
  },
  "tokens": [
    {
      "id": "20234",
      "description": "This description is modified",
      "token": "a4dbf6a8ea6e582583206896024a87e3b98c21124d629eb7",
      "last_used_at": null,
      "created_at": "2015-05-01T16:13:40.593Z",
      "updated_at": "2015-05-01T16:13:40.631Z",
      "links": {
        "team": "3"
      }
    }
  ]
}
```

### Curl Example <a href="#updating-a-token-changing-an-attribute-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/tokens/20234 \
  -is \
  -X PUT \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "tokens": {
      "id": 20234,
      "token": "this is ignored",
      "description": "This description is modified"
    }
  }'
```

## Updating A Token Not Changing An Attribute <a href="#updating-a-token-not-changing-an-attribute" class="header-link"></a>

```
PUT /api/v1/tokens/20264
```

In order to update an SDK access token, the authenticated user must be
a member of the team that the token is associated with.

### Parameters <a href="#updating-a-token-not-changing-an-attribute-parameters" class="header-link"></a>

All tokens **must** be sent in an array nested under a top level
`tokens` parameter.

| **Name** | **Type** | **Description** |
| -------- | -------- | --------------- |
| `id` | `string` | **Required.** The id of the token |
| `description` | `string` | Description of the purpose for this token |

### Example <a href="#updating-a-token-not-changing-an-attribute-example" class="header-link"></a>

If you do not provide attributes, or if all of the provided attributes
are the same, the token is not updated. In these cases a
`204 No Content` response is returned.

This response will have an empty body per HTTP schemantics.

```json
{
  "tokens": {
    "id": 20264,
    "description": "RSpec Spec - Generated Token"
  }
}
```

### Response <a href="#updating-a-token-not-changing-an-attribute-response" class="header-link"></a>

```
Status: 204 No Content
Director-Media-Type: director.v1
Director-API-Version: 1.0
```

### Curl Example <a href="#updating-a-token-not-changing-an-attribute-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/tokens/20264 \
  -is \
  -X PUT \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"' \
  -d '{
    "tokens": {
      "id": 20264,
      "description": "RSpec Spec - Generated Token"
    }
  }'
```

## Deleting A Token <a href="#deleting-a-token" class="header-link"></a>

```
DELETE /api/v1/tokens/20277
```

In order to delete an SDK access token, the authenticated user must be
a member of the team that the token is associated with.

### Response <a href="#deleting-a-token-response" class="header-link"></a>

```
Status: 204 No Content
Director-Media-Type: director.v1
Director-API-Version: 1.0
```

### Curl Example <a href="#deleting-a-token-curl-example" class="header-link"></a>

```
curl https://director.radiusnetworks.com/api/v1/tokens/20277 \
  -is \
  -X DELETE \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"'
```
