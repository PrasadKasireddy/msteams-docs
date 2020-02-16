---
title: Notification-only bots
description: Describes what notification-only bots are in Microsoft Teams
keywords: teams bots notification
ms.date: 01/29/2020
---
# Notification-only bots in Microsoft Teams

[!include[v3-to-v4-SDK-pointer](~/includes/v3-to-v4-pointer-bots.md)]

If your bot's sole purpose is to deliver notification to users and is not conversational, you can enable the `isNotificationOnly` field in your app manifest. This produces the following changes:

* Users cannot message your notification-only bot.
* Users cannot @mention the bot.

## App manifest

To enable this, set `isNotificationOnly` to `true`.

> [!NOTE]
> Be aware that the value of `isNotificationOnly` is boolean and not a string.

```json
{
  ⋮
  "bots":[
    {
      "botId":"[Microsoft App ID for your bot]",
      "isNotificationOnly": true,
      "scopes": [
        "personal",
        "team"
      ],
    }
  ],
  ...
}
```

## Best practices and limitations

* Notification-only bots use proactive messaging to communicate with the user. See [Proactive messaging for bots](~/resources/bot-v3/bot-conversations/bots-conv-proactive.md) for more details.
