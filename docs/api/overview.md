# Director API

This document describes the API designed to integrate Director with other
systems. It is specifically intended to provide access to the features and
functionality available through the web interface.

Data synchronization, communicating with the SDKs, and configuring hardware is
not part of this API. Radius Networks has [other
resources](http://developer.radiusnetworks.com/) for many of those needs.

## Overview

We use IDs for linkage between objects. This makes it possible to cache
documents from compound responses and then limit subsequent requests to only
the documents that aren't already present locally.

Resource relationships are created through the use of URI templates and
resource identifiers. To prevent future breakage we recommend creating the URIs
from the templates over hardcoding to the individual resources.

## Current Version

By default, all requests receive the [**v1** version](#v1) of the API.

## Schema

All API access is over HTTPS, and accessed from the `director.github.com`
domain. All data is sent and received as JSON.

Blank fields are included as `null` instead of being omitted.

All timestamps are returned in ISO 8601 format:

```
YYYY-MM-DDTHH:MM:SSZ
```

## Headers

### Authorization

The API Key is passed via the Authorization header:

```
Authorization: Token token="secret"
```

The API Key is associated with your account and has access to all the resources
associated with your account. Account specific API keys have different
permissions than the web login users that can interact with the dashboard, and
the access may be different.

If you do not have an API key, [you can create one
here](https://account.radiusnetworks.com/personal_token).

**Note:** Per [RFC 2616](http://www.w3.org/Protocols/rfc2616/rfc2616-sec2.html#sec2.2)
the Authorization Header's token needs to be surrounded by double quotes (`"`).

### Content Type

The content type is `vnd.rn+json` and should be set in the `Content-Type`
header:

```
Content-Type: application/vnd.rn+json
```

## Versions

### V1

- [Root Endpoint](docs/api/v1/root_endpoint)
- [Teams](docs/api/v1/teams)
- [Beacons](docs/api/v1/beacons)
