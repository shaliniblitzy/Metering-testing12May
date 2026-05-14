# Getting Started

This guide walks you through running the `Metering-testing12May` Node.js + Express.js tutorial server on your local machine. By the end you will have installed dependencies, started the server, called both endpoints, and learned how to recover from the two most common failures.

## Prerequisites

Before you begin, make sure you have the following tools installed:

- **Node.js >= 18** — Express.js 5.x requires Node.js 18 or higher. Verify with `node --version`.
- **npm >= 9** — bundled with Node.js 18+. Verify with `npm --version`.

The version requirement is enforced declaratively by the `engines.node` field of `package.json`, so npm will warn you if the runtime is too old.

_Source: package.json:engines.node_

## Installation

Clone the repository and install its production dependency (Express.js 5.2.1). The first install command writes `node_modules/` and `package-lock.json` into your working directory.

```bash
# From the repository root
npm install
```

For a reproducible install that respects the locked dependency tree (recommended for CI), use `npm ci` instead of `npm install`.

_Source: package.json:dependencies.express_

## Running the server

Start the HTTP server with the default Node.js launcher:

```bash
node server.js
```

If `package.json` declares a `start` script, the equivalent `npm start` command also works.

_Expected output:_

```bash
Server is running on http://localhost:3000
```

### Configuration

| Variable | Default | Purpose |
| -------- | ------- | ------- |
| `PORT` | `3000` | TCP port the HTTP server binds to. Override with `PORT=8080 node server.js` to listen on a different port. |

No `.env` file is loaded; the variable is read directly from `process.env.PORT` at startup.

_Source: server.js:<line of app.listen()>_

## Verifying the endpoints

With the server running, open a second terminal and call each endpoint:

```bash
curl http://localhost:3000/hello
# => Hello world

curl http://localhost:3000/good-evening
# => Good evening
```

See the [API Reference](api/endpoints.md) for the full per-endpoint specification (method, status, content-type, response body).

## Troubleshooting

If the server fails to start or you cannot reach an endpoint, check these two most common issues first:

### Error: listen EADDRINUSE: address already in use :::3000

Another process on your machine is already bound to TCP port `3000`. Either stop the other process or run the server on a different port by overriding the `PORT` environment variable:

```bash
PORT=8080 node server.js
```

### Error: Cannot find module 'express'

The `node_modules/` directory is missing or incomplete. Run `npm install` (or `npm ci`) from the repository root before starting the server.

```bash
npm install
node server.js
```

For the full Express.js documentation, visit the official site at [https://expressjs.com/](https://expressjs.com/).
