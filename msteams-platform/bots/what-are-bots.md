---
title: What are conversational bots?
author: clearab
description: An overview of conversational bots in Microsoft Teams.
ms.topic: overview
ms.author: anclear
---
# What are conversational bots?

Conversational bots allow users to interact with your web service through text, interactive cards, and task modules. They're incredibly flexible — conversational bots can be scoped to handling a few simple commands or complex, artificial intelligence powered and natural language processing virtual assistants. They can be one aspect of a larger application, or completely stand alone.

The GIF below shows a user conversing with a bot in a one-to-one chat using both text and interactive cards. Finding the right mix of cards, text, and task modules is key to creating a useful bot. Don't forget, bots are much more than just text!

![FAQ Plus gif](~/assets/images/FAQPlusEndUser.gif)

## What tasks are best handled by bots?

Bots in Microsoft Teams can be part of a one-to-one conversation, a group chat, or a channel in a Team. Each scope will provide unique opportunities, and challenges, for your conversational bot.

### In a channel

Channels contain threaded conversations between multiple people — potentially lots of people (currently, up to two thousand). This potentially gives your bot massive reach, but individual interactions need to be concise. Traditional multi-turn interactions probably won't work well. Instead, look to use interactive cards or task modules, or potentially move the conversation to a one-to-one conversation if you need to collect lots of information. Your bot will also only have access to messages where it's `@mentioned` directly, you cannot retrieve additional messages from the conversation using Microsoft Graph and elevated organization-level permissions.

Some scenarios where bots excel in a channel include:

* **Notifications**, particularly if you provide an interactive card for users to take additional information.
* **Feedback scenarios** like polls and surveys.
* Interactions that can be resolved in a **single request/response cycle**, where the results are useful for multiple members of the conversation.
* **Social/fun bots** — get an awesome cat image, randomly pick a winner, etc.

### In a group chat

Group chats are non-threaded conversations between three or more people. They tend to have fewer members than a channel, and are more transient. Similar to a channel, your bot will only have access to messages where it's `@mentioned` directly.

Scenarios that work well in a channel will usually work just as well in a group chat.

### In a one-to-one chat

This is the traditional way for a conversational bot to interact with a user. They can enable incredibly diverse workloads. Q&A bots, bots that initiate workflows in other systems, bots that tell jokes, and bots that take notes are just a few examples. Just remember to consider whether a conversation-based interface is the best way to present your functionality.

## How do bots work?

Your bot consists of three pieces:

* A publicly accessible web service that you host.
* Your bot registration that registers your bot with the Bot Framework.
* Your Teams app package that contains your app manifest. This is what your users install and connects the Teams client to your web service (routed through the Bot Service).

Bots for Microsoft Teams are built on the [Microsoft Bot Framework](https://dev.botframework.com/). (If you already have a bot that's based on the Bot Framework, you can easily adapt it to work in Microsoft Teams.) We recommend you use either C# or Node.js to take advantage of our [SDKs](/microsoftteams/platform/#pivot=sdk-tools). These packages extend the basic Bot Builder SDK classes and methods:

* Using specialized card types like the Office 365 Connector card.
* Consuming and setting Teams-specific channel data on activities.
* Processing messaging extension requests.

> [!IMPORTANT]
> You can develop Teams apps in any web-programming technology and call the [Bot Framework REST APIs](/bot-framework/rest-api/bot-framework-rest-overview) directly, but you must perform all token handling yourself.

*Teams App Studio* helps you create and configure your app manifest, and can register your web service as a bot on the Bot Framework. It also contains a React control library and an interactive card builder. *See* [Getting started with Teams App Studio](~/concepts/build-and-test/app-studio-overview.md).

## Webhooks and connectors

Webhooks and connectors allow you to create a simple bot for basic interaction, like kicking off a workflow or other simple commands. They live only in the team in which you create them and are intended for simple processes specific to your company's workflow. *See* [What are webhooks and connectors?](~/webhooks-and-connectors/what-are-webhooks-and-connectors.md) for more information.

## Get started

* [Teams conversation bot in C#/dotnet](https://github.com/microsoft/BotBuilder-Samples/tree/master/samples/csharp_dotnetcore/57.teams-conversation-bot)
* [Teams conversation bot in JavaScript](https://github.com/microsoft/BotBuilder-Samples/tree/master/samples/javascript_nodejs/57.teams-conversation-bot)

## Learn more

* [The basics of bots in Teams](~/bots/bot-basics.md)
* [Create a bot for Teams](~/bots/how-to/create-a-bot-for-teams.md)
