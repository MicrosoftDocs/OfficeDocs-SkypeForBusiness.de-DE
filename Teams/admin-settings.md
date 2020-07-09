---
title: Administratoreinstellungen für Apps in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: ritikag, rarang
description: Informieren Sie sich über die Richtlinien und Einstellungen, die Sie zum Verwalten von Apps für Ihre Organisation in Microsoft Teams verwenden können.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.apppermspolicies.adminsettings
- ms.teamsadmincenter.apppermspolicies.orgwideapps.thirdpartyapps
- ms.teamsadmincenter.apppolicies.adminsettings
f1.keywords:
- CSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f800b92a0663b5c4318022c00cbb9ba022f2e8c3
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085681"
---
<a name="admin-settings-for-apps-in-microsoft-teams"></a><span data-ttu-id="25c57-103">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25c57-103">Admin settings for apps in Microsoft Teams</span></span>
==========================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="25c57-104">Apps bieten integrierte Tools für Ihre Organisation, um mehr von Teams zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="25c57-104">Apps provide out-of-the-box tools for your organization to get more out of Teams.</span></span> <span data-ttu-id="25c57-105">Diese apps kombinieren die Funktionalität von Registerkarten, Messaging Erweiterungen, Connectors und Bots, die von Microsoft bereitgestellt werden, die von einem Drittanbieter oder von Entwicklern in Ihrer Organisation erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="25c57-105">These apps combine the functionality of tabs, messaging extensions, connectors, and bots provided by Microsoft, built by a third-party, or by developers in your organization.</span></span>

<span data-ttu-id="25c57-106">Sie verwalten Apps für Ihre Organisation in den **Teams-apps** im [Admin Center](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="25c57-106">You manage apps for your organization in **Teams apps** in the [admin center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="25c57-107">So können Sie beispielsweise apps auf Organisationsebene zulassen oder blockieren, Richtlinien festlegen, um zu steuern, welche apps für die Benutzer von Teams verfügbar sind, und Teams anpassen, indem Sie die für Ihre Benutzer wichtigsten apps anheften.</span><span class="sxs-lookup"><span data-stu-id="25c57-107">For example, you can allow or block apps at the org level, set policies to control what apps are available to Teams users, and customize Teams by pinning the apps that are most important for your users.</span></span>

<span data-ttu-id="25c57-108">Wir verbessern ständig die APP-Umgebung in Teams und fügen Features und Funktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="25c57-108">We're continually improving the app experience in Teams and adding features and functionality.</span></span> <span data-ttu-id="25c57-109">Im Laufe der Zeit werden wir zusätzliche Funktionen für die APP-Verwaltung erstellen, daher sollten Sie sich über die neuesten Informationen zu app-Richtlinien informieren.</span><span class="sxs-lookup"><span data-stu-id="25c57-109">Over time, we'll be building additional app management capabilities, so check back for the most up-to-date information on app policies.</span></span>

## <a name="manage-apps"></a><span data-ttu-id="25c57-110">Verwalten von apps</span><span class="sxs-lookup"><span data-stu-id="25c57-110">Manage apps</span></span>

<span data-ttu-id="25c57-111">Verwenden Sie die Seite " **apps verwalten** ", um alle Teams-apps im App-Katalog Ihrer Organisation anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="25c57-111">Use the **Manage apps** page to view and manage all Teams apps in your organization's app catalog.</span></span> <span data-ttu-id="25c57-112">Sie können den Status und die Eigenschaften von apps auf Organisationsebene anzeigen, Apps auf org-Ebene blockieren oder zulassen, neue benutzerdefinierte apps in ihren Mandanten Katalog hochladen und organisationsweite App-Einstellungen verwalten.</span><span class="sxs-lookup"><span data-stu-id="25c57-112">You can see the org-level status and properties of apps, block or allow apps at the org level, upload new custom apps to your tenant catalog, and manage org-wide app settings.</span></span>

<span data-ttu-id="25c57-113">Auf der Seite " **apps verwalten** " erhalten Sie einen Überblick über alle verfügbaren apps in Ihrem Mandanten Katalog, in dem Sie die Informationen finden, die Sie benötigen, um zu entscheiden, welche apps in Ihrer Organisation zugelassen oder blockiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="25c57-113">The **Manage apps** page gives you a view into all available apps in your tenant catalog, providing you with the information you need to decide which apps to allow or block across your organization.</span></span> <span data-ttu-id="25c57-114">Sie können dann [App-Berechtigungsrichtlinien](#app-permission-policies), [App-Setup Richtlinien](#app-setup-policies)und [benutzerdefinierte App-Richtlinien und-Einstellungen](#custom-app-policies-and-settings) verwenden, um die APP-Umgebung für bestimmte Benutzer in Ihrer Organisation zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="25c57-114">You can then use [app permission policies](#app-permission-policies), [app setup policies](#app-setup-policies), and [custom app policies and settings](#custom-app-policies-and-settings) to configure the app experience for specific users in your organization.</span></span>

<span data-ttu-id="25c57-115">Weitere Informationen finden Sie unter [Verwalten von apps in Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="25c57-115">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

## <a name="app-permission-policies"></a><span data-ttu-id="25c57-116">App-Berechtigungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="25c57-116">App permission policies</span></span>

<span data-ttu-id="25c57-117">Mit App-Berechtigungsrichtlinien können Sie steuern, welche apps bestimmten Benutzern in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="25c57-117">With app permission policies, you can control what apps are available to specific users in your organization.</span></span> <span data-ttu-id="25c57-118">Sie können alle apps oder bestimmte apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden, zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="25c57-118">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span>

<span data-ttu-id="25c57-119">So können Sie beispielsweise App-Berechtigungsrichtlinien für folgende Zwecke verwenden:</span><span class="sxs-lookup"><span data-stu-id="25c57-119">For example, you can use app permission policies to:</span></span>

- <span data-ttu-id="25c57-120">Schrittweise Einführung neuer Drittanbieter-oder benutzerdefinierter Apps für bestimmte Benutzer.</span><span class="sxs-lookup"><span data-stu-id="25c57-120">Gradually roll out new third-party or custom built apps to specific users.</span></span>
- <span data-ttu-id="25c57-121">Vereinfachen Sie die Benutzerfreundlichkeit, insbesondere wenn Sie mit der Einführung von Teams in Ihrer Organisation beginnen.</span><span class="sxs-lookup"><span data-stu-id="25c57-121">Simplify the user experience, especially when you start rolling out Teams across your organization.</span></span>

<span data-ttu-id="25c57-122">Weitere Informationen hierzu finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="25c57-122">To learn more, go to [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>

## <a name="app-setup-policies"></a><span data-ttu-id="25c57-123">Richtlinien für die APP-Einrichtung</span><span class="sxs-lookup"><span data-stu-id="25c57-123">App setup policies</span></span>

<span data-ttu-id="25c57-124">Mit den Richtlinien für die APP-Einrichtung können Sie die App-Benutzeroberfläche anpassen.</span><span class="sxs-lookup"><span data-stu-id="25c57-124">App setup policies let you customize the app experience for your users.</span></span> <span data-ttu-id="25c57-125">Sie wählen die Apps aus, die Sie an die APP-Leiste in den Teams-Clients anheften möchten, und die Reihenfolge, in der Sie angezeigt werden, auf Web-, Desktop-und mobilen Clients.</span><span class="sxs-lookup"><span data-stu-id="25c57-125">You choose the apps that you want to pin to the app bar in the Teams clients and the order in which they appear, on web, desktop, and mobile clients.</span></span>

<span data-ttu-id="25c57-126">Nachfolgend finden Sie einige Beispiele für die Verwendung von Richtlinien für die APP-Einrichtung:</span><span class="sxs-lookup"><span data-stu-id="25c57-126">Here's some examples of how you can use app setup policies:</span></span>

- <span data-ttu-id="25c57-127">Sensibilisierung und Einführung von Kern-apps.</span><span class="sxs-lookup"><span data-stu-id="25c57-127">Drive awareness and adoption of core apps.</span></span> <span data-ttu-id="25c57-128">So können Sie beispielsweise eine benutzerdefinierte Rekrutierungs-und Talent Verwaltungsanwendung für Benutzer in Ihrem HR-Team anheften.</span><span class="sxs-lookup"><span data-stu-id="25c57-128">For example, pin a custom recruiting and talent management app for users on your HR team.</span></span>
- <span data-ttu-id="25c57-129">Sie können Core Teams-Features wie Chat, Teams und Anrufe selektiv anheften.</span><span class="sxs-lookup"><span data-stu-id="25c57-129">Selectively pin core Teams features, such as Chat, Teams, and Calling.</span></span> <span data-ttu-id="25c57-130">Auf diese Weise können Sie sicherstellen, dass Benutzer an bestimmten Aktivitäten innerhalb von Teams beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="25c57-130">Doing so can help ensure users are engaged in specific activities within Teams.</span></span>

<span data-ttu-id="25c57-131">Weitere Informationen finden Sie unter [Verwalten von App-Setup Richtlinien in Teams](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="25c57-131">To learn more, check out [Manage app setup policies in Teams](teams-app-setup-policies.md).</span></span>

## <a name="custom-app-policies-and-settings"></a><span data-ttu-id="25c57-132">Benutzerdefinierte App-Richtlinien und-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="25c57-132">Custom app policies and settings</span></span>

<span data-ttu-id="25c57-133">Teams ermöglicht es Entwicklern in Ihrer Organisation, benutzerdefinierte Apps für andere Benutzer zu erstellen, zu testen und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="25c57-133">Teams allows developers in your organization to build, test, and deploy custom apps to other users.</span></span> <span data-ttu-id="25c57-134">Benutzerdefinierte Apps können Teams hinzugefügt werden, indem Sie ein App-Paket in einer ZIP-Datei direkt in ein Team oder in den persönlichen Kontext hochladen.</span><span class="sxs-lookup"><span data-stu-id="25c57-134">Custom apps can be added to Teams by uploading an app package in a .zip file directly to a team or in the personal context.</span></span> <span data-ttu-id="25c57-135">Sie können APP-Setup Richtlinien verwenden, um zu steuern, wer in Ihrer Organisation benutzerdefinierte apps hochladen kann.</span><span class="sxs-lookup"><span data-stu-id="25c57-135">You can use app setup policies to control who in your organization can upload custom apps.</span></span> <span data-ttu-id="25c57-136">Sie können auch organisationsweite Einstellungen festlegen, um zu steuern, ob Benutzer mit bestimmten benutzerdefinierten apps interagieren können.</span><span class="sxs-lookup"><span data-stu-id="25c57-136">You can also set org-wide settings to control whether users can interact with specific custom apps.</span></span>

<span data-ttu-id="25c57-137">Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und-Einstellungen in Microsoft Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="25c57-137">To learn more, go to [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>
