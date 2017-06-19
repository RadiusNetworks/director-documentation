# Director API Root Endpoint

- [Requesting Resource Endpoints](#requesting-resource-endpoints)

This describes the resources that make up the official Director API v1. If
you have any problems or requests please contact
[support](http://www.radiusnetworks.com/support.html). Issue a `GET`
request to the root endpoint to get a list of all the resource endpoints
this API supports.

## Headers <a href="#headers" id="headers" class="headerlink"></a>

### Authorization <a href="#authorization" id="authorization" class="headerlink"></a>

The API Key is passed via the Authorization header:

```properties
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

```properties
Content-Type: application/vnd.rn+json
```

## Requesting Resource Endpoints <a href="#requesting-resource-endpoints" class="header-link"></a>

```http
GET /api/v1
```

### Response <a href="#requesting-resource-endpoints-response" class="header-link"></a>

```http
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```nginx
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```yaml
Status: 200 OK
Content-Type: application/json; charset=utf-8
Director-Media-Type: director.v1
Director-API-Version: 1.0
```
```json
{
  "links": {
    "users.teams": "https://director.radiusnetworks.com/api/v1/teams/{users.teams}",
    "teams.beacons": "https://director.radiusnetworks.com/api/v1/beacons/{teams.beacons}"
  }
}
```

### Curl Example <a href="#requesting-resource-endpoints-curl-example" class="header-link"></a>

```shell
curl https://director.radiusnetworks.com/api/v1 \
  -is \
  -X GET \
  -H 'Accept: application/vnd.rn+json' \
  -H 'Content-Type: application/vnd.rn+json' \
  -H 'Authorization: Token token="c0decafe1111180a29c8696adbd5307ccdcdaa6468c0ffee"'
```
