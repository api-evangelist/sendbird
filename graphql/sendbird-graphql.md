# Sendbird GraphQL Schema

This document describes a conceptual GraphQL schema for the Sendbird in-app messaging and chat platform. The schema is derived from the [Sendbird Platform API](https://sendbird.com/docs/chat/platform-api/v3/overview) and models the core resources available via the REST API as GraphQL types, queries, mutations, and subscriptions.

## Overview

Sendbird provides in-app chat, messaging, push notifications, moderation, analytics, and AI chatbot capabilities used by over 4,000 companies. This GraphQL schema covers the following capability areas:

- **Users** — user accounts, profiles, friends, blocked users
- **Channels** — open channels, group channels, members, operators, bans, mutes, invites
- **Messages** — user messages, file messages, admin messages, threads, reactions, metadata
- **Notifications** — push notifications, device tokens, templates, settings
- **Webhooks** — webhook endpoints and event delivery
- **Applications** — app configuration, tokens, usage summaries
- **Bots** — bot users, bot messages, bot categories
- **Announcements** — scheduled broadcast announcements
- **Moderation** — content filters, moderation bots
- **AI Features** — AI bots, smart replies, message search
- **Analytics** — channel stats, message stats, delivery/read status, usage summaries

## Base URL

```
https://api-{application_id}.sendbird.com/v3
```

## Authentication

All requests require either an API token (server-side) or a session token (client-side) passed via the `Api-Token` HTTP header.

## Schema Source

- REST API Docs: https://sendbird.com/docs/chat/platform-api/v3/overview
- GitHub Organization: https://github.com/sendbird
- Authentication: https://sendbird.com/docs/chat/platform-api/v3/authentication

## Types Summary

| Category | Types |
|---|---|
| Users | User, UserProfile, UserFriend, UserBlockedUser |
| Channels | Channel, OpenChannel, GroupChannel, ChannelMember, ChannelOperator, ChannelBannedUser, ChannelMutedUser, ChannelInvite |
| Messages | Message, UserMessage, FileMessage, AdminMessage, MessageMeta, MessageReaction, MessageThread, Thread, ThreadedReply |
| Notifications | Notification, NotificationSetting, PushNotification, PushTemplate, DeviceToken |
| Webhooks | Webhook, WebhookEndpoint |
| Applications | Application, AppToken |
| Bots | Bot, BotMessage, BotCategory |
| Announcements | Announcement |
| Discovery | FriendDiscovery |
| Analytics | AnalyticsMetric, ChannelStats, MessageStats, DeliveryStatus, ReadStatus, UsageSummary |
| Moderation | ModerationBot, ContentFilter |
| AI | AIBot, SmartReply, MessageSearch, SearchQuery, SearchResult |

## Queries

- `user(userId: String!)` — fetch a single user by ID
- `users(limit: Int, token: String)` — paginated list of users
- `channel(channelUrl: String!)` — fetch a single channel
- `openChannels(limit: Int, token: String)` — list open channels
- `groupChannels(userId: String, limit: Int, token: String)` — list group channels
- `message(channelType: ChannelType!, channelUrl: String!, messageId: Int!)` — fetch a single message
- `messages(channelType: ChannelType!, channelUrl: String!, limit: Int)` — list channel messages
- `bot(botUserId: String!)` — fetch a bot by user ID
- `bots(limit: Int, token: String)` — list bots
- `announcement(uniqueId: String!)` — fetch an announcement
- `announcements(limit: Int, token: String)` — list announcements
- `application` — fetch current application settings
- `channelStats(channelUrl: String!)` — fetch stats for a channel
- `usageSummary` — fetch overall usage summary
- `searchMessages(query: SearchQuery!)` — full-text message search

## Mutations

- `createUser(input: CreateUserInput!)` — create a new user
- `updateUser(userId: String!, input: UpdateUserInput!)` — update an existing user
- `deleteUser(userId: String!)` — delete a user
- `createOpenChannel(input: CreateOpenChannelInput!)` — create an open channel
- `createGroupChannel(input: CreateGroupChannelInput!)` — create a group channel
- `updateChannel(channelUrl: String!, input: UpdateChannelInput!)` — update channel settings
- `deleteChannel(channelType: ChannelType!, channelUrl: String!)` — delete a channel
- `sendUserMessage(input: SendUserMessageInput!)` — send a user message
- `sendFileMessage(input: SendFileMessageInput!)` — send a file message
- `sendAdminMessage(input: SendAdminMessageInput!)` — send an admin message
- `deleteMessage(channelType: ChannelType!, channelUrl: String!, messageId: Int!)` — delete a message
- `addReaction(input: AddReactionInput!)` — add a reaction to a message
- `removeReaction(input: RemoveReactionInput!)` — remove a reaction
- `banUserFromChannel(input: BanUserInput!)` — ban a user from a channel
- `muteUserInChannel(input: MuteUserInput!)` — mute a user in a channel
- `registerWebhook(input: RegisterWebhookInput!)` — register a webhook endpoint
- `registerDeviceToken(input: RegisterDeviceTokenInput!)` — register a push device token
- `createBot(input: CreateBotInput!)` — create a bot user
- `createAnnouncement(input: CreateAnnouncementInput!)` — create an announcement

## Subscriptions

- `onMessageReceived(channelUrl: String!)` — subscribe to new messages in a channel
- `onChannelUpdated(channelUrl: String!)` — subscribe to channel metadata changes
- `onUserOnlineStatusChanged(userId: String!)` — subscribe to user presence changes
- `onReactionUpdated(channelUrl: String!, messageId: Int!)` — subscribe to reaction updates
