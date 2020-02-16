---
title: What are custom tabs in Microsoft Teams?
author: laujan
description: An overview of custom tabs on the Microsoft Teams platform
ms.topic: overview
ms.author: v-laujan
ms.topic: overview
---
# What are Microsoft Teams custom tabs?

Tabs are Teams-aware webpages embedded in Microsoft Teams. They can be added as part of a channel inside a team, a group chat or as a personal app for an individual user. As part of your app you can add custom tabs to embed your own web content in Teams, and using the [Teams JavaScript client SDK](/javascript/api/overview/msteams-client), add Teams-specific functionality to your web content.

> [!NOTE]
> Chrome 80, scheduled for release in early 2020, introduces new cookie values and imposes cookie policies by default. It's recommended that you set the intended use for your cookies rather than rely on default browser behavior. *See* [SameSite cookie attribute (2020 update)](../resources/samesite-cookie-update.md).

There are two types of tabs available in Teams - channel/group and personal. A channel/group tab delivers content to channels and group chats, and are a great way to create collaborative spaces around dedicated web-based content. Personal tabs, along with personally-scoped bots, are part of personal apps and are scoped to a single user. They can be pinned to the left navigation bar for easy access.

## Tabs user scenarios

**Scenario:** Bring an existing web-based resource inside Teams. \
**Example:** You create a personal tab in your Teams app that presents an informational corporate website to users.

**Scenario:** Add support pages to a Teams bot or messaging extension. \
**Example:** You create personal tabs that provide about and help webpage content to users.

**Scenario:** Provide access to items that your users interact with regularly for cooperative dialogue and collaboration. \
**Example:** You create a channel/group tab with deep linking to individual items.

## How do tabs work?

A custom tab is declared in the app manifest of your app package. For each webpage you want included as a tab in your app you define a URL and a scope. Additionally, you need to add the [Teams JavaScript client SDK](/javascript/api/overview/msteams-client) to your page, and call `microsoftTeams.initialize()` after your page loads. Doing so will tell Teams to display your page, give you access to Teams-specific information (for example if the Teams client is running the Dark Theme), and allow you to take action based on the results.

Whether you choose to expose your tab within the channel/group or personal scope, you'll need to present an IFramed HTML [content page](~/tabs/how-to/create-tab-pages/content-page.md) in your tab. For personal tabs, the content URL is set directly in your manifest by the `contentUrl` property in the `staticTabs` array. Your tab's content will be the same for all users.

For channel/group tabs, you also need to create an additional configuration page that allows your users to configure your content page URL, typically by using URL query string parameters to load the appropriate content for that context. This is because your channel/group tab can be added to multiple different teams or group chats. On each subsequent install, your users will be able to configure the tab allowing you to tailor the experience as needed. For example, when you add the Azure DevOps board tab the configuration page allows you to choose which board the tab will load. The configuration page URL is specified by the  `configurationUrl` property in the `configurableTabs` array in your app manifest.

You can have a maximum of one (1) channel/group tab and up to sixteen (16) personal tabs per app.

## Mobile clients

If you choose to have your channel/group tab appear on Teams mobile clients, the `setSettings()` configuration must have a value for the `websiteUrl` property (see below). Personal tabs are currently available in [developer preview](~/resources/dev-preview/developer-preview-intro.md). Full support for tabs on mobile clients will be released soon. To prepare for the update, you should follow the [guidance for tabs on mobile](~/tabs/design/tabs-mobile.md) when creating your tabs.
