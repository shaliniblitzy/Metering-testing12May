# API Reference

## Overview

The service exposes two HTTP endpoints, both returning plain-text response bodies via the Express.js `res.send(string)` method, which defaults to a `Content-Type` of `text/html; charset=utf-8`.

## GET /hello

- **Method**: `GET`
- **Path**: `/hello`
- **Status**: `200 OK`
- **Content-Type**: `text/html; charset=utf-8`
- **Response Body**: `Hello world`

```bash
curl http://localhost:3000/hello
# => Hello world
```

_Source: server.js:<line of app.get('/hello')>_

## GET /good-evening

- **Method**: `GET`
- **Path**: `/good-evening`
- **Status**: `200 OK`
- **Content-Type**: `text/html; charset=utf-8`
- **Response Body**: `Good evening`

```bash
curl http://localhost:3000/good-evening
# => Good evening
```

_Source: server.js:<line of app.get('/good-evening')>_

See the [Architecture Overview](../architecture/overview.md) for the request lifecycle.
