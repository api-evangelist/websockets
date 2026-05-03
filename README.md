# WebSockets

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
