---
title: Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Hier erfahren Sie, wie Sie das Feature "Gastzugriff" in Microsoft Teams als Office 365-Administrator aktivieren oder deaktivieren.
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 297a101389de2e1609697ffa2c30a2a8b7a84080
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042777"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="57298-103">Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57298-103">Turn on or turn off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="57298-104">Der Gastzugriff ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="57298-104">By default, guest access is turned off.</span></span> <span data-ttu-id="57298-105">Als Microsoft 365-oder Office 365-Administrator müssen Sie den Gastzugriff für Teams aktivieren, bevor die Administratoren oder Teambesitzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="57298-105">As the Microsoft 365 or Office 365 admin, you must turn on guest access for Teams before the admin or team owners can add guests.</span></span> <span data-ttu-id="57298-106">Verwenden Sie die [Checkliste für den Gastzugriff](guest-access-checklist.md), um den Gastzugriff zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="57298-106">To turn on guest access, use the [Guest access checklist](guest-access-checklist.md).</span></span> 

<span data-ttu-id="57298-107">Nachdem Sie den Gastzugriff aktiviert haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="57298-107">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="57298-108">Wenn ein Benutzer die Meldung "wenden Sie sich an Ihren Administrator" an, wenn er versucht, dem Team einen Gast hinzuzufügen, ist es wahrscheinlich, dass entweder der Gastzugriff nicht aktiviert wurde oder die Einstellungen noch nicht wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="57298-108">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57298-109">Das Aktivieren des Gastzugriffs hängt von den Einstellungen in Azure Active Directory, Microsoft 365 oder Office 365, SharePoint Online und Teams ab.</span><span class="sxs-lookup"><span data-stu-id="57298-109">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365 or Office 365, SharePoint Online, and Teams.</span></span> <span data-ttu-id="57298-110">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="57298-110">For more information, see [Authorize guest access in Teams](Teams-dependencies.md).</span></span>



## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="57298-111">Konfigurieren des Gastzugriffs im Team Admin Center</span><span class="sxs-lookup"><span data-stu-id="57298-111">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="57298-112">Melden Sie sich beim Admin Center für Microsoft Teams an.</span><span class="sxs-lookup"><span data-stu-id="57298-112">Sign in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="57298-113">Wählen Sie **Organisationsweite Einstellungen** > **Gastzugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="57298-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="57298-114">**Aktivieren Sie "** **Gastzugriff in Microsoft Teams zulassen** ".</span><span class="sxs-lookup"><span data-stu-id="57298-114">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="57298-115">Schalter für „Gastzugriff in Teams ermöglichen“ ist auf „An“ eingestellt</span><span class="sxs-lookup"><span data-stu-id="57298-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="57298-116">Wählen Sie unter **anrufen**, **Besprechungen**und nach **richten**für jede Funktion **ein** oder **aus** , je nachdem, was Sie für Gastbenutzer zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="57298-116">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="57298-117">**Private Anrufe führen**: **Aktivieren** Sie diese Einstellung, um Gästen Peer-to-Peer-Anrufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="57298-118">**IP-Video zulassen**: **Aktivieren** Sie diese Einstellung, damit Gäste Video in ihren Anrufen und Besprechungen verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="57298-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="57298-119">**Bildschirmübertragungsmodus**: Diese Einstellung steuert die Verfügbarkeit der Bildschirmübertragung für Gastbenutzer.</span><span class="sxs-lookup"><span data-stu-id="57298-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="57298-120">Legen Sie diese Einstellung auf **Deaktiviert** fest, wenn Sie möchten, dass Gäste ihren Bildschirm in Teams nicht übertragen können.</span><span class="sxs-lookup"><span data-stu-id="57298-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="57298-121">Legen Sie diese Einstellung auf **Einzelne Anwendung** fest, um die Übertragung einzelner Anwendungen zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="57298-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="57298-122">Legen Sie diese Einstellung auf **Vollbild** fest, um die vollständige Bildschirmübertragung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="57298-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="57298-123">**Sofortbesprechungen zulassen**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung des Features „Sofortbesprechung“ in Microsoft Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="57298-124">**Gesendete Nachrichten bearbeiten**: **Aktivieren** Sie diese Einstellung, um Gästen die Bearbeitung von zuvor gesendeten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="57298-125">**Gäste können gesendete Nachrichten löschen**: **Aktivieren** Sie diese Einstellung, um Gästen das Löschen von zuvor gesendeten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="57298-126">**Chat**: **Aktivieren** Sie diese Einstellung, um Gästen den Zugriff auf den Chat in Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="57298-127">**Giphys in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Giphys in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="57298-128">Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen.</span><span class="sxs-lookup"><span data-stu-id="57298-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="57298-129">Jedem Giphy wird eine Inhaltsbewertung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="57298-129">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="57298-130">**Giphy-Inhaltsbewertung**: Wählen Sie eine Bewertung aus der Dropdown-Liste aus:</span><span class="sxs-lookup"><span data-stu-id="57298-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="57298-131">**Alle Inhalte zulassen**: Gäste können alle Giphys in Chats einfügen, unabhängig von der Inhaltsbewertung.</span><span class="sxs-lookup"><span data-stu-id="57298-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="57298-132">**Moderat**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber moderat eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="57298-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="57298-133">**Streng**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="57298-133">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="57298-134">**Memes in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Memes in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-134">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="57298-135">**Sticker in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Stickern in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="57298-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

5. <span data-ttu-id="57298-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57298-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="57298-137">Verwenden Sie PowerShell zum Aktivieren oder Deaktivieren von Gastzugriff.</span><span class="sxs-lookup"><span data-stu-id="57298-137">Use PowerShell to turn guest access on or off</span></span>

<span data-ttu-id="57298-138">Lesen [Verwenden von PowerShell zum Aktivieren oder Deaktivieren des Gastzugriffs](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="57298-138">Read [Use PowerShell to turn guest access on or off](guest-access-PowerShell.md#use-powershell-to-turn-guest-access-on-or-off)</span></span>


## <a name="video-adding-guests-in-teams"></a><span data-ttu-id="57298-139">Video: Hinzufügen von Gästen in Teams</span><span class="sxs-lookup"><span data-stu-id="57298-139">Video: Adding guests in Teams</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="57298-140">Hinzufügen von Gästen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="57298-140">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 


## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="57298-141">Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich</span><span class="sxs-lookup"><span data-stu-id="57298-141">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]