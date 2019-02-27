---
title: Verwalten von Messagingrichtlinien
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.messagingpolicies.overview
description: Informationen Sie zu Richtlinien für Messaging und wie sie Chat in Teams messaging steuern verwendet werden können.
ms.openlocfilehash: 6349bd8299883fe213797a51e7051411c74298ef
ms.sourcegitcommit: baca91b0e022a1d2b5a522ef749a97463d61f560
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2019
ms.locfileid: "30302665"
---
# <a name="what-are-messaging-policies-in-teams"></a><span data-ttu-id="f5367-103">Was sind Messaging-Richtlinien in Teams?</span><span class="sxs-lookup"><span data-stu-id="f5367-103">What are Messaging policies in Teams?</span></span>

::: zone target="docs"
<span data-ttu-id="f5367-104">Messaging-Richtlinien dienen zum Steuern, welche Chat und Channel messaging-Funktionen für Benutzer in Microsoft-Teams verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f5367-104">Messaging policies are used to control which chat and channel messaging features are available to users in Microsoft Teams.</span></span> <span data-ttu-id="f5367-105">Sie können die Standardrichtlinie, die erstellt wird, oder erstellen Sie eine oder mehrere benutzerdefinierte messaging Richtlinien für die Personen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="f5367-105">You can use the default policy that is created or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="f5367-106">Nachdem Sie eine Richtlinie erstellen, weisen es einem Benutzer oder Gruppen von Benutzern in Ihrer Organisation Sie.</span><span class="sxs-lookup"><span data-stu-id="f5367-106">After you create a policy, you will assign it a user or groups of users in your organization.</span></span>

<span data-ttu-id="f5367-107">Richtlinien können auf einfache Weise verwaltet werden, in der Verwaltungskonsole von Microsoft-Teams (http://admin.teams.microsoft.com) , sich mit Administratoranmeldeinformationen anmelden und **Messaging Richtlinien** im linken Navigationsbereich.</span><span class="sxs-lookup"><span data-stu-id="f5367-107">Policies can be easily managed in the Microsoft Teams admin center (http://admin.teams.microsoft.com) by logging in with administrator credentials and choosing **Messaging Policies** in the left navigation pane.</span></span> 

![Messagingrichtlinien in Teams](media/messaging-policies-image1.png)

<span data-ttu-id="f5367-109">Um die vorhandenen Messaging-Standardrichtlinie für Ihre Organisation zu bearbeiten, klicken Sie auf die Zeile **Global (Org geltende Standard)** , und nehmen Sie dann die Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="f5367-109">To edit the existing default Messaging policy for your organization, click the **Global (Org-wide default)** row, and then make your changes.</span></span> <span data-ttu-id="f5367-110">Um eine neue benutzerdefinierte messaging-Richtlinie zu erstellen, klicken Sie auf **neue Richtlinie** , und wählen Sie Ihre Einstellungen aus.</span><span class="sxs-lookup"><span data-stu-id="f5367-110">To create a new custom messaging policy, click **New policy** and select your settings.</span></span> <span data-ttu-id="f5367-111">Wählen Sie **Speichern** aus, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="f5367-111">Choose **Save** when you are done.</span></span>

![Messaging Policy Settings in Teams](media/messaging-policies-image2.png)
::: zone-end

::: zone target="chromeless"
<span data-ttu-id="f5367-113">Verwenden Sie die folgenden Einstellungen zum Ändern der globalen Richtlinie Messaging oder erstellen eine neue benutzerdefinierte Richtlinie an:</span><span class="sxs-lookup"><span data-stu-id="f5367-113">Use the following settings to change the global Messaging policy or create a new custom policy:</span></span>

- <span data-ttu-id="f5367-114">**Websitebesitzer können gesendete Nachrichten löschen**  Verwenden Sie diese Einstellung Besitzer Nachrichten löschen können, die Benutzer in Chat gesendet.</span><span class="sxs-lookup"><span data-stu-id="f5367-114">**Owners can delete sent messages**  Use this setting to let owners delete messages that users sent in chat.</span></span>
- <span data-ttu-id="f5367-115">**Benutzer können gesendete Nachrichten löschen** Verwenden Sie diese Einstellung, damit Benutzer Nachrichten löschen, die sie im Chat gesendet.</span><span class="sxs-lookup"><span data-stu-id="f5367-115">**Users can delete sent messages** Use this setting to let users delete messages that they sent in chat.</span></span>
- <span data-ttu-id="f5367-116">**Benutzer können gesendete Nachrichten bearbeiten** Verwenden Sie diese Einstellung, damit Benutzer die Nachrichten zu bearbeiten, die sie im Chat gesendet.</span><span class="sxs-lookup"><span data-stu-id="f5367-116">**Users can edit sent messages** Use this setting to let users edit the messages that they sent in chat.</span></span>
- <span data-ttu-id="f5367-117">**Lesebestätigungen** Verwenden Sie diese Einstellung an, ob Lese-Empfangsbestätigungen Benutzer gesteuert, für alle Benutzer aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f5367-117">**Read receipts** Use this setting to specify whether read receipts are user controlled, enabled for everyone, or disabled.</span></span>

<span data-ttu-id="f5367-118"><a name="bkchat"> </a></span><span class="sxs-lookup"><span data-stu-id="f5367-118"></span></span>

- <span data-ttu-id="f5367-119">**Chat**  Aktivieren Sie diese Einstellung, wenn die Benutzer in Ihrer Organisation die Teams app verwenden, um mit anderen Teilnehmern zu chatten können sollen.</span><span class="sxs-lookup"><span data-stu-id="f5367-119">**Chat**  Turn this setting on if you want users in your organization to be able to use the Teams app to chat with other people.</span></span>
- <span data-ttu-id="f5367-120">**Verwendung Giphys Unterhaltungen**  Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Giphys einschließen.</span><span class="sxs-lookup"><span data-stu-id="f5367-120">**Use Giphys in conversations**  If you turn this on, users can include Giphys in chat conversations with other people.</span></span> <span data-ttu-id="f5367-121">Giphy ist ein online-Datenbank und die Suchmaschine, mit dem Benutzer suchen und Freigeben von animierte GIF-Dateien.</span><span class="sxs-lookup"><span data-stu-id="f5367-121">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="f5367-122">Jede Giphy wird eine Content Bewertung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f5367-122">Each Giphy is assigned a content rating.</span></span>
- <span data-ttu-id="f5367-123">**Giphy zum Bewerten**</span><span class="sxs-lookup"><span data-stu-id="f5367-123">**Giphy content rating**</span></span> 
    - <span data-ttu-id="f5367-124">**Keine Einschränkung** Dies bedeutet, dass Ihre Benutzer alle Giphy in Chats unabhängig von der zum Bewerten einfügen können.</span><span class="sxs-lookup"><span data-stu-id="f5367-124">**No restriction** This means that your users will be able to insert any Giphy in chats regardless of the content rating.</span></span>
    - <span data-ttu-id="f5367-125">**Moderater**  Dies bedeutet, dass Ihre Benutzer in Chats Giphys einfügen können, aber einigermaßen aus Versender nicht jugendfreier Inhalte eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="f5367-125">**Moderate**  This means that your users will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
    - <span data-ttu-id="f5367-126">**Strict**  Dies bedeutet, dass Ihre Benutzer Giphys in Chats einfügen können, aber unbedingt aus Versender nicht jugendfreier Inhalte eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="f5367-126">**Strict**  This means that your users will be able to insert Giphys in chats, but will be strictly restricted from adult content.</span></span>
- <span data-ttu-id="f5367-127">**Verwendung Memes Unterhaltungen** Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Memes einschließen.</span><span class="sxs-lookup"><span data-stu-id="f5367-127">**Use Memes in conversations** If you turn this on, users can include Memes in chat conversations with other people.</span></span> 
- <span data-ttu-id="f5367-128">**Verwendung Aufkleber Unterhaltungen** Wenn Sie diese aktivieren, können Benutzer in Chat Gespräche mit anderen Personen Aufkleber einschließen.</span><span class="sxs-lookup"><span data-stu-id="f5367-128">**Use Stickers in conversations** If you turn this on, users can include Stickers in chat conversations with other people.</span></span>
- <span data-ttu-id="f5367-129">**Zulassen von URL-Vorschau** Verwenden Sie diese Einstellung, um die automatische URL Anzeigen der Vorschau aktiviert oder deaktiviert in Nachrichten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5367-129">**Allow URL previews** Use this setting to turn automatic URL previewing on or off in messages.</span></span>
- <span data-ttu-id="f5367-130">**Übersetzen von Nachrichten durch Benutzer zulassen** Aktivieren Sie diese Einstellung Benutzer Teams Nachrichten automatisch in die Sprache, die durch ihre persönliche Sprachoptionen für Office 365 angegebenen übersetzen können.</span><span class="sxs-lookup"><span data-stu-id="f5367-130">**Allow users to translate messages** Turn this setting on to let users automatically translate Teams messages into the language specified by their personal language settings for Office 365.</span></span> 

[<span data-ttu-id="f5367-131">Vollständigen Artikel</span><span class="sxs-lookup"><span data-stu-id="f5367-131">Full article</span></span>](messaging-policies-in-teams.md)
::: zone-end

::: zone target="docs"
<span data-ttu-id="f5367-132">Wenn Sie eine benutzerdefinierte Richtlinie an Messaging erstellt haben, werden es nur aktive für einen Benutzer wenn diese Richtlinie, die einem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f5367-132">If you have created a custom Messaging policy, it will only be active for a user if that policy is assigned to a user.</span></span> <span data-ttu-id="f5367-133">Wenn eine benutzerdefinierte Richtlinie für einen Benutzer in der Verwaltungskonsole von Microsoft-Teams zuweisen möchten, wählen Sie im linken Navigationsbereich **Benutzer** , und wählen Sie den Benutzer, dem Sie die Richtlinie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="f5367-133">To assign a custom policy to a user in the Microsoft Teams admin center, choose **Users** in the left navigation, and select the user you want to assign the policy to.</span></span> <span data-ttu-id="f5367-134">Wählen Sie der Benutzer auf Seite **Bearbeiten** , neben **Richtlinien zugewiesen**.</span><span class="sxs-lookup"><span data-stu-id="f5367-134">On the user's page, choose **Edit** next to **Assigned Policies**.</span></span>
::: zone-end

### <a name="related-topics"></a><span data-ttu-id="f5367-135">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f5367-135">Related topics</span></span>
[<span data-ttu-id="f5367-136">Besprechungsrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5367-136">Meeting policies in Teams</span></span>](meeting-policies-in-teams.md)



