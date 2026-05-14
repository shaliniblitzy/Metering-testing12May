# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- New HTTP endpoint `GET /good-evening` returning the plain-text body `Good evening`. _Source: server.js:<line of app.get('/good-evening')>_
- Express.js 5.2.1 production dependency (`express@^5.2.1`) declared in `package.json`. _Source: package.json:dependencies.express_

### Changed

- HTTP server refactored from the implied raw Node.js `http` module to the Express.js web framework. The original `GET /hello` endpoint returning `Hello world` is preserved and now served via `app.get('/hello', handler)`. _Source: server.js:<line of app.get('/hello')>_

---

<!-- Link references will be added once the first git tag is published. -->
