---
title: Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Aktivieren oder Deaktivieren der Funktion für den Gastzugriff in Microsoft Teams
ms.custom:
- NewAdminCenter_Update
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.turnonguestaccessarticle
appliesto:
- Microsoft Teams
ms.openlocfilehash: f00b585b1473a366769650c2a59f6dee2a9d3bea
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242620"
---
<a name="turn-on-or-turn-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="3c707-103">Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c707-103">Turn on or off guest access to Microsoft Teams</span></span>
===================================================

<span data-ttu-id="3c707-104">Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="3c707-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span>

<span data-ttu-id="3c707-105">Die Gasteinstellungen werden in Azure Active Directory festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3c707-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="3c707-106">Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="3c707-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="3c707-107">Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="3c707-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c707-108">Um die Nutzung der Gastzugriffsfunktion in vollem Umfang zu ermöglichen, müssen Sie die gegenseitige Abhängigkeit bezüglich der Kernautorisierung von Microsoft Teams, Azure Active Directory und Office 365 verstehen.</span><span class="sxs-lookup"><span data-stu-id="3c707-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="3c707-109">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="3c707-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="3c707-110">Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich</span><span class="sxs-lookup"><span data-stu-id="3c707-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="3c707-111">Konfigurieren von Teams im Admin Center für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c707-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="3c707-112">Melden Sie sich beim Admin Center für Microsoft Teams an.</span><span class="sxs-lookup"><span data-stu-id="3c707-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="3c707-113">Wählen Sie **Organisationsweite Einstellungen** > **Gastzugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="3c707-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="3c707-114">Legen Sie **Gastzugriff in Teams ermöglichen** auf **An** fest.</span><span class="sxs-lookup"><span data-stu-id="3c707-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="3c707-115">Schalter für „Gastzugriff in Teams ermöglichen“ ist auf „An“ eingestellt</span><span class="sxs-lookup"><span data-stu-id="3c707-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="3c707-116">Legen Sie die Schalter unter **Anruf**, **Besprechung** und **Messaging** je nach den Funktionen, die Sie Gastbenutzern bereitstellen möchten, auf **An** oder **Aus** fest.</span><span class="sxs-lookup"><span data-stu-id="3c707-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="3c707-117">**Private Anrufe führen**: **Aktivieren** Sie diese Einstellung, um Gästen Peer-to-Peer-Anrufe zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="3c707-118">**IP-Video zulassen**: **Aktivieren** Sie diese Einstellung, damit Gäste Video in ihren Anrufen und Besprechungen verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="3c707-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="3c707-119">**Bildschirmübertragungsmodus**: Diese Einstellung steuert die Verfügbarkeit der Bildschirmübertragung für Gastbenutzer.</span><span class="sxs-lookup"><span data-stu-id="3c707-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="3c707-120">Legen Sie diese Einstellung auf **Deaktiviert** fest, wenn Sie möchten, dass Gäste ihren Bildschirm in Teams nicht übertragen können.</span><span class="sxs-lookup"><span data-stu-id="3c707-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="3c707-121">Legen Sie diese Einstellung auf **Einzelne Anwendung** fest, um die Übertragung einzelner Anwendungen zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="3c707-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="3c707-122">Legen Sie diese Einstellung auf **Vollbild** fest, um die vollständige Bildschirmübertragung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="3c707-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="3c707-123">**Sofortbesprechungen zulassen**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung des Features „Sofortbesprechung“ in Microsoft Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="3c707-124">**Gesendete Nachrichten bearbeiten**: **Aktivieren** Sie diese Einstellung, um Gästen die Bearbeitung von zuvor gesendeten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="3c707-125">**Gäste können gesendete Nachrichten löschen**: **Aktivieren** Sie diese Einstellung, um Gästen das Löschen von zuvor gesendeten Nachrichten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="3c707-126">**Chat**: **Aktivieren** Sie diese Einstellung, um Gästen den Zugriff auf den Chat in Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="3c707-127">**Giphys in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Giphys in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="3c707-128">Giphy ist eine Onlinedatenbank und Suchmaschine, die es Benutzern ermöglicht, nach animierten GIF-Dateien zu suchen und diese zu teilen.</span><span class="sxs-lookup"><span data-stu-id="3c707-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="3c707-129">Jedem Giphy wird eine Inhaltsbewertung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="3c707-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="3c707-130">**Giphy-Inhaltsbewertung**: Wählen Sie eine Bewertung aus der Dropdown-Liste aus:</span><span class="sxs-lookup"><span data-stu-id="3c707-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="3c707-131">**Alle Inhalte zulassen**: Gäste können alle Giphys in Chats einfügen, unabhängig von der Inhaltsbewertung.</span><span class="sxs-lookup"><span data-stu-id="3c707-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="3c707-132">**Moderat**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber moderat eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="3c707-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="3c707-133">**Streng**: Gäste können Giphys in Chats einfügen, der Zugriff auf nicht jugendfreie Inhalte wird aber eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="3c707-133">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="3c707-134">**Memes in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Memes in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-134">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="3c707-135">**Sticker in Unterhaltungen verwenden**: **Aktivieren** Sie diese Einstellung, um Gästen die Verwendung von Stickern in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3c707-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="3c707-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3c707-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="3c707-137">Verwenden Sie PowerShell zum Aktivieren oder Deaktivieren von Gastzugriff.</span><span class="sxs-lookup"><span data-stu-id="3c707-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="3c707-138">Laden Sie das Skype for Business Online PowerShell-Modul unter https://www.microsoft.com/en-us/download/details.aspx?id=39366 herunter.</span><span class="sxs-lookup"><span data-stu-id="3c707-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="3c707-139">Verbinden Sie eine PowerShell-Sitzung mit dem Skype for Business Online-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="3c707-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="3c707-140">Überprüfen Sie Ihre Konfiguration und wenn `AllowGuestUser` ist `$False`, verwenden Sie das Cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) zum Einstellen auf `$True`.</span><span class="sxs-lookup"><span data-stu-id="3c707-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="3c707-141">Sie können jetzt Gastbenutzer für Ihre Organisation in Teams unterstützen.</span><span class="sxs-lookup"><span data-stu-id="3c707-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="3c707-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c707-142">More information</span></span>

<span data-ttu-id="3c707-143">In den folgenden Videos erfahren Sie mehr über den Gastzugriff.</span><span class="sxs-lookup"><span data-stu-id="3c707-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="3c707-144">Hinzufügen von Gästen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3c707-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
