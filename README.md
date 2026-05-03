# Sendbird

Sendbird provides APIs and SDKs for in-app chat, voice, video, AI chatbots, and omnichannel business messaging. Used by over 4,000 companies to build real-time communication experiences for customer support, communities, and marketplace platforms.

**URL:** [https://sendbird.com](https://sendbird.com)

## Timestamps

- **Created:** 2025-01-14
- **Modified:** 2026-05-02

## APIs

### Sendbird Platform API

The Sendbird Platform API provides server-side access to manage users, channels, messages, and moderation for in-app chat applications.

**Human URL:** [https://sendbird.com/docs/chat/platform-api/](https://sendbird.com/docs/chat/platform-api/)

#### Tags

- Chat, Messaging, Real-Time Communication, Push Notifications

#### Properties

- [Documentation](https://sendbird.com/docs/chat/platform-api/)
- [OpenAPI](openapi/sendbird-platform-openapi.yml)
- [JSONSchema - User](json-schema/sendbird-user-schema.json)
- [JSONSchema - Group Channel](json-schema/sendbird-group-channel-schema.json)
- [JSONSchema - Message](json-schema/sendbird-message-schema.json)

---

## Artifacts

### OpenAPI Specifications

| API | File |
|---|---|
| Sendbird Platform API | [openapi/sendbird-platform-openapi.yml](openapi/sendbird-platform-openapi.yml) |

### JSON Schemas

| Schema | File |
|---|---|
| User | [json-schema/sendbird-user-schema.json](json-schema/sendbird-user-schema.json) |
| Group Channel | [json-schema/sendbird-group-channel-schema.json](json-schema/sendbird-group-channel-schema.json) |
| Message | [json-schema/sendbird-message-schema.json](json-schema/sendbird-message-schema.json) |

### JSON Structures

| Structure | File |
|---|---|
| User | [json-structure/sendbird-user-structure.json](json-structure/sendbird-user-structure.json) |

### Rules

| Ruleset | File |
|---|---|
| Sendbird API Rules | [rules/sendbird-rules.yml](rules/sendbird-rules.yml) |

### Capabilities

#### Workflow Capabilities

| Workflow | Description | File |
|---|---|---|
| Customer Support Messaging | Support conversation management for customer service teams | [capabilities/customer-support-messaging.yaml](capabilities/customer-support-messaging.yaml) |
| Community Chat | Community building and moderation workflow | [capabilities/community-chat.yaml](capabilities/community-chat.yaml) |

#### Shared Per-API Definitions

| API | File |
|---|---|
| Platform API | [capabilities/shared/platform-api.yaml](capabilities/shared/platform-api.yaml) |

### JSON-LD Context

- [json-ld/sendbird-context.jsonld](json-ld/sendbird-context.jsonld)

### Examples

| Example | File |
|---|---|
| Create User | [examples/sendbird-create-user-example.json](examples/sendbird-create-user-example.json) |
| Send Message | [examples/sendbird-send-message-example.json](examples/sendbird-send-message-example.json) |

### Vocabulary

- [vocabulary/sendbird-vocabulary.yml](vocabulary/sendbird-vocabulary.yml)

## Maintainers

- **Kin Lane** — [kin@apievangelist.com](mailto:kin@apievangelist.com)
