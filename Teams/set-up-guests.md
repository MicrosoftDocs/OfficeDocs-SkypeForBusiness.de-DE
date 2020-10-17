---
title: Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
localization_priority: Normal
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
description: Hier erfahren Sie, wie Sie das Feature "Gastzugriff" in Microsoft Teams als Office 365-Administrator aktivieren oder deaktivieren.
ms.openlocfilehash: 54d7461e9e03cd22900e07aca7ad2d12712faab7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508062"
---
# <a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="a10a9-103">Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a10a9-103">Turn on or turn off guest access to Microsoft Teams</span></span>

<span data-ttu-id="a10a9-104">Der Gastzugriff ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a10a9-104">By default, guest access is turned off.</span></span> <span data-ttu-id="a10a9-105">Sie müssen den Gastzugriff für Teams aktivieren, bevor Administratoren oder Teambesitzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="a10a9-105">You must turn on guest access for Teams before admins or team owners can add guests.</span></span>

<span data-ttu-id="a10a9-106">Nachdem Sie den Gastzugriff aktiviert haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="a10a9-106">After you turn on guest access, it may take a few hours for the changes to take effect.</span></span> <span data-ttu-id="a10a9-107">Wenn ein Benutzer die Meldung "wenden Sie sich an Ihren Administrator" an, wenn er versucht, dem Team einen Gast hinzuzufügen, ist es wahrscheinlich, dass entweder der Gastzugriff nicht aktiviert wurde oder die Einstellungen noch nicht wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="a10a9-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either guest access hasn't been turned on or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a10a9-108">Das Aktivieren des Gastzugriffs hängt von den Einstellungen in Azure Active Directory, Microsoft 365, SharePoint und Teams ab.</span><span class="sxs-lookup"><span data-stu-id="a10a9-108">Turning on guest access depends on settings in Azure Active Directory, Microsoft 365, SharePoint, and Teams.</span></span> <span data-ttu-id="a10a9-109">Weitere Informationen finden Sie unter [zusammenarbeiten mit Gästen in einem Team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="a10a9-109">For more information, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>

## <a name="configure-guest-access-in-the-teams-admin-center"></a><span data-ttu-id="a10a9-110">Konfigurieren des Gastzugriffs im Team Admin Center</span><span class="sxs-lookup"><span data-stu-id="a10a9-110">Configure guest access in the Teams admin center</span></span>

1. <span data-ttu-id="a10a9-111">Anmelden beim [Microsoft Teams Admin Center](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="a10a9-111">Sign in to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

2. <span data-ttu-id="a10a9-112">Wählen Sie **Organisationsweite Einstellungen** > **Gastzugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="a10a9-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="a10a9-113">**Aktivieren Sie "** **Gastzugriff in Microsoft Teams zulassen** ".</span><span class="sxs-lookup"><span data-stu-id="a10a9-113">Set **Allow guest access in Microsoft Teams** to **On**.</span></span>

    ![<span data-ttu-id="a10a9-114">Schalter für „Gastzugriff in Teams ermöglichen“ ist auf „An“ eingestellt</span><span class="sxs-lookup"><span data-stu-id="a10a9-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4. <span data-ttu-id="a10a9-115">Wählen Sie unter **anrufen**, **Besprechungen**und nach **richten**für jede Funktion **ein** oder **aus** , je nachdem, was Sie für Gastbenutzer zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="a10a9-115">Under **Calling**, **Meeting**, and **Messaging**, select **On** or **Off** for each capability, depending on what you want to allow for guest users.</span></span>

      - <span data-ttu-id="a10a9-116">**Private Anrufe führen**: **Aktivieren** Sie diese Einstellung, um Gästen Peer-to-Peer-Anrufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-116">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
      - <span data-ttu-id="a10a9-117">**IP-Video zulassen**: **Aktivieren** Sie diese Einstellung, damit Gäste Video in ihren Anrufen und Besprechungen verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-117">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
      - <span data-ttu-id="a10a9-118">**Bildschirmübertragungsmodus**: Diese Einstellung steuert die Verfügbarkeit der Bildschirmübertragung für Gastbenutzer.</span><span class="sxs-lookup"><span data-stu-id="a10a9-118">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
          - <span data-ttu-id="a10a9-119">Legen Sie diese Einstellung auf **Deaktiviert** fest, wenn Sie möchten, dass Gäste ihren Bildschirm in Teams nicht übertragen können.</span><span class="sxs-lookup"><span data-stu-id="a10a9-119">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
          - <span data-ttu-id="a10a9-120">Legen Sie diese Einstellung auf **Einzelne Anwendung** fest, um die Übertragung einzelner Anwendungen zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="a10a9-120">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
          - <span data-ttu-id="a10a9-121">Legen Sie diese Einstellung auf **Vollbild** fest, um die vollständige Bildschirmübertragung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-121">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
      - <span data-ttu-id="a10a9-122">**Sofortbesprechungen zulassen**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung des Features „Sofortbesprechung“ in Microsoft Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-122">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
      - <span data-ttu-id="a10a9-123">**Gesendete Nachrichten bearbeiten**: **Aktivieren** Sie diese Einstellung, um Gästen die Bearbeitung von zuvor gesendeten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-123">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
      - <span data-ttu-id="a10a9-124">**Gäste können gesendete Nachrichten löschen**: **Aktivieren** Sie diese Einstellung, um Gästen das Löschen von zuvor gesendeten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-124">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
      - <span data-ttu-id="a10a9-125">**Chat**: **Aktivieren** Sie diese Einstellung, um Gästen den Zugriff auf den Chat in Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-125">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
      - <span data-ttu-id="a10a9-126">**Giphys in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Giphys in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-126">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="a10a9-127">Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-127">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="a10a9-128">Jedem Giphy wird eine Inhaltsbewertung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-128">Each Giphy is assigned a content rating.</span></span>
      - <span data-ttu-id="a10a9-129">**Giphy-Inhaltsbewertung**: Wählen Sie eine Bewertung aus der Dropdown-Liste aus:</span><span class="sxs-lookup"><span data-stu-id="a10a9-129">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
          - <span data-ttu-id="a10a9-130">**Alle Inhalte zulassen**: Gäste können alle Giphys in Chats einfügen, unabhängig von der Inhaltsbewertung.</span><span class="sxs-lookup"><span data-stu-id="a10a9-130">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
          - <span data-ttu-id="a10a9-131">**Moderat**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber moderat eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="a10a9-131">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
          - <span data-ttu-id="a10a9-132">**Streng**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="a10a9-132">**Strict** – Guests will be able to insert Giphys in chats, but will be restricted from inserting adult content.</span></span>
      - <span data-ttu-id="a10a9-133">**Memes in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Memes in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-133">**Use memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
      - <span data-ttu-id="a10a9-134">**Sticker in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Stickern in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a10a9-134">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 

    ![Einstellungen von Gastberechtigungen in Teams](media/manage-guest-access-image1.png)

5. <span data-ttu-id="a10a9-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a10a9-136">Click **Save**.</span></span>

## <a name="external-access-federation-vs-guest-access"></a><span data-ttu-id="a10a9-137">Externer Zugriff (Partnerverbund) und Gastzugriff im Vergleich</span><span class="sxs-lookup"><span data-stu-id="a10a9-137">External access (federation) vs. guest access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="see-also"></a><span data-ttu-id="a10a9-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a10a9-138">See also</span></span>

[<span data-ttu-id="a10a9-139">Einrichten einer sicheren Zusammenarbeit mit Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a10a9-139">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

[<span data-ttu-id="a10a9-140">Sperren von Gastbenutzern aus einem bestimmten Team</span><span class="sxs-lookup"><span data-stu-id="a10a9-140">Block guest users from a specific team</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="a10a9-141">Satz-CsTeamsClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="a10a9-141">Set-CsTeamsClientConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration)