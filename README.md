# WebSockets

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

WebSockets is a communication protocol providing full-duplex communication channels over a single TCP connection, enabling real-time data exchange between client and server. Standardized by RFC 6455 and the WHATWG Living Standard, it is fundamental to modern web architecture and enables reliable bidirectional communication between systems.

**Type:** Topic Index
**Specification:** [RFC 6455](https://www.rfc-editor.org/rfc/rfc6455)
**Living Standard:** [websockets.spec.whatwg.org](https://websockets.spec.whatwg.org/)
**MDN:** [WebSockets API](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)

## Protocol Overview

WebSocket establishes a persistent connection via an HTTP Upgrade handshake, then provides a lightweight framing layer for bidirectional messages. Key properties:

- **Full-duplex** — Both client and server can send at any time
- **Low overhead** — 2-10 byte frame headers vs full HTTP headers per request
- **Real-time** — Push data from server to client without polling
- **Subprotocols** — STOMP, MQTT, GraphQL-WS, JSON-RPC layered on top

## Artifacts

### AsyncAPI Specifications
- [websockets.yml](asyncapi/websockets.yml) — WebSocket communication channels per RFC 6455

### JSON Schemas
- [websocket-handshake-request.json](json-schema/websocket-handshake-request.json) — HTTP Upgrade request schema
- [websocket-handshake-response.json](json-schema/websocket-handshake-response.json) — HTTP 101 response schema
- [websocket-frame.json](json-schema/websocket-frame.json) — WebSocket frame structure
- [websocket-message.json](json-schema/websocket-message.json) — WebSocket message schema
- [websocket-close-code.json](json-schema/websocket-close-code.json) — Close status codes

### JSON Structures
- [websocket-message-structure.json](json-structure/websocket-message-structure.json) — Frame field documentation

### JSON-LD Contexts
- [websockets-context.jsonld](json-ld/websockets-context.jsonld) — Linked data context for WebSocket concepts

### Examples
- [websocket-handshake-example.json](examples/websocket-handshake-example.json) — Opening handshake request/response
- [websocket-close-example.json](examples/websocket-close-example.json) — Close handshake and status codes

### Vocabulary
- [websockets-vocabulary.yml](vocabulary/websockets-vocabulary.yml) — WebSocket protocol terminology

## Frame Types

| Opcode | Type | Description |
|--------|------|-------------|
| 0x0 | Continuation | Continuation of a fragmented message |
| 0x1 | Text | UTF-8 encoded text data |
| 0x2 | Binary | Raw binary data |
| 0x8 | Close | Connection close control frame |
| 0x9 | Ping | Keep-alive ping |
| 0xA | Pong | Keep-alive pong (reply to ping) |

## Use Cases

- Real-time chat and collaboration applications
- Live financial data feeds and trading platforms
- Online gaming with real-time state synchronization
- IoT device telemetry and command-and-control
- Live dashboards and monitoring interfaces
- Push notifications replacing long-polling

## Related Technologies

- **Socket.IO** — WebSocket library with fallback transports
- **STOMP** — Messaging subprotocol over WebSocket
- **MQTT over WebSocket** — IoT messaging
- **GraphQL Subscriptions** — Real-time GraphQL over WebSocket
- **Server-Sent Events** — One-way server push (lighter alternative)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
