# Metering-testing12May

## Overview

This project is a beginner-friendly tutorial that demonstrates how to build a minimal Node.js HTTP service using Express.js 5.2.1. The service exposes two HTTP endpoints: `GET /hello` returning the plain-text response body `Hello world`, and `GET /good-evening` returning the plain-text response body `Good evening`. It is intended as a tutorial introduction to Express.js routing, so the source surface is intentionally kept small — a single `server.js` entry point declaring the two endpoint handlers, and a `package.json` declaring Express.js as the only runtime dependency.

_Source: server.js_

## Prerequisites

- `Node.js >= 18` (required by Express 5.x)
- `npm >= 9` (bundled with Node.js 18+)

The version requirement is enforced declaratively by the `engines.node` field of `package.json`, so the package manager will warn you when the installed runtime is too old.

_Source: package.json:engines.node_

## Quick Start

Get the server running in under a minute:

```bash
# 1. Install dependencies
npm install

# 2. Start the server
node server.js
```

The server listens on `http://localhost:3000` by default.

### Verify

```bash
curl http://localhost:3000/hello
# => Hello world

curl http://localhost:3000/good-evening
# => Good evening
```

_Source: server.js:<line of app.listen()>_

## Endpoints

The service exposes two HTTP endpoints, both returning plain-text response bodies.

| Method | Path | Status | Response Body | Reference |
| ------ | ---- | ------ | ------------- | --------- |
| `GET` | `/hello` | `200 OK` | `Hello world` | [API Reference](docs/api/endpoints.md#get-hello) |
| `GET` | `/good-evening` | `200 OK` | `Good evening` | [API Reference](docs/api/endpoints.md#get-good-evening) |

## Documentation

Detailed documentation lives in the [`docs/`](docs/) directory:

| Document | Description |
| -------- | ----------- |
| [Getting Started](docs/getting-started.md) | Prerequisites, installation, running the server, verifying endpoints, troubleshooting |
| [API Reference](docs/api/endpoints.md) | Per-endpoint reference: method, path, status, response body, `curl` examples |
| [Architecture Overview](docs/architecture/overview.md) | Request lifecycle narrative and Mermaid sequence diagram |
| [Changelog](CHANGELOG.md) | Version history (Keep a Changelog 1.1.0 format) |

## License

_No license file has been added to the repository yet._
