---
title: Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 03/06/2019
ms.topic: article
ms.service: msteams
MS.collection:
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
ms.openlocfilehash: 6a4b0013e3e3ca31baea21e4e733a9606f3765c6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885283"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="feb4f-103">Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="feb4f-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="feb4f-104">Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="feb4f-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="feb4f-105">Die Gasteinstellungen werden in Azure Active Directory festgelegt.</span><span class="sxs-lookup"><span data-stu-id="feb4f-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="feb4f-106">Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="feb4f-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="feb4f-107">Wenn ein Benutzer die Meldung erhält "Wenden Sie sich an Ihren Administrator", wenn sie versuchen, ihr Team Gastsystem hinzuzufügen, ist es wahrscheinlich, dass das Feature Gast noch nicht aktiviert wurde, oder die Einstellungen für eine effektive sind noch nicht.</span><span class="sxs-lookup"><span data-stu-id="feb4f-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings aren't effective yet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="feb4f-108">Um die Nutzung der Gastzugriffsfunktion in vollem Umfang zu ermöglichen, müssen Sie die gegenseitige Abhängigkeit bezüglich der Kernautorisierung von Microsoft Teams, Azure Active Directory und Office 365 verstehen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="feb4f-109">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="feb4f-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="feb4f-110">Gastzugriff im Vergleich zum externen Zugriff (Verbund)</span><span class="sxs-lookup"><span data-stu-id="feb4f-110">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="configure-guest-access-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="feb4f-111">Konfigurieren des Zugriffs von Gast in der Verwaltungskonsole von Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="feb4f-111">Configure guest access in the Microsoft Teams admin center</span></span>

1.  <span data-ttu-id="feb4f-112">Melden Sie sich bei der Microsoft-Teams-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="feb4f-112">Sign in to the Microsoft Teams admin center.</span></span>

2.  <span data-ttu-id="feb4f-113">Wählen Sie **gesamte Org Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="feb4f-113">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="feb4f-114">Legen Sie die Umschaltfläche **Gast Zugriffsberechtigung in Microsoft-Teams** auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="feb4f-114">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="feb4f-115">Legen Sie Gast Access Switch auf auf zulassen</span><span class="sxs-lookup"><span data-stu-id="feb4f-115">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="feb4f-116">Legen Sie die schaltet unter **aufrufen**, **Besprechung**und **Messaging** auf **ein-** oder **Ausschalten**, je nach den Möglichkeiten, den, die Sie für Gastbenutzer zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="feb4f-116">Set the toggles under **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the capabilities you want to allow for guest users.</span></span>

    - <span data-ttu-id="feb4f-117">**Private tätigen** – aktivieren Sie diese Einstellung **auf** um Gäste Peer-zu-Peer-Anrufe tätigen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-117">**Make private calls** – Turn this setting **On** to allow guests to make peer-to-peer calls.</span></span>
    - <span data-ttu-id="feb4f-118">**Zulassen von IP-video** - aktivieren diese Einstellung **auf** Gäste Video in ihre Anrufe und Besprechungen verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-118">**Allow IP video** - Turn this setting **On** to allow guests to use video in their calls and meetings.</span></span>
    - <span data-ttu-id="feb4f-119">**Bildschirmfreigabe Modus** – diese Einstellung steuert die Verfügbarkeit der Bildschirmfreigabe für Gastbenutzer.</span><span class="sxs-lookup"><span data-stu-id="feb4f-119">**Screen sharing mode** – This setting controls the availability of screen sharing for guest users.</span></span> 
       - <span data-ttu-id="feb4f-120">Aktivieren Sie diese Einstellung, um **deaktiviert** die Möglichkeit für ihre Bildschirme in Teams freigeben Gäste entfernen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-120">Turn this setting to **Disabled** to remove the ability for guests to share their screens in Teams.</span></span> 
       - <span data-ttu-id="feb4f-121">Aktivieren Sie diese Einstellung, um **einzelne Anwendung** um Freigabe von einzelnen Anwendungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-121">Turn this setting to **Single application** to allow sharing of individual applications.</span></span> 
       - <span data-ttu-id="feb4f-122">Aktivieren Sie diese Einstellung, um den **gesamten Bildschirm** aus, um die vollständige Bildschirmfreigabe zulassen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-122">Turn this setting to **Entire screen** to allow complete screen sharing.</span></span>
    - <span data-ttu-id="feb4f-123">**Zulassen "Jetzt besprechen"** – aktivieren Sie diese Einstellung **auf** um Gäste mit der Funktion "Jetzt besprechen" in Microsoft-Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-123">**Allow Meet Now** – Turn this setting **On** to allow guests to use the Meet Now feature in Microsoft Teams.</span></span>
    - <span data-ttu-id="feb4f-124">**Bearbeiten gesendete Nachrichten** - aktivieren diese Einstellung **auf** Gäste bearbeiten zu Nachrichten sie zuvor gesendet.</span><span class="sxs-lookup"><span data-stu-id="feb4f-124">**Edit sent messages** - Turn this setting **On** to allow guests to edit messages they previously sent.</span></span>
    - <span data-ttu-id="feb4f-125">**Gäste können gesendete Nachrichten löschen** – aktivieren Sie diese Einstellung **auf** Gäste löschen zu Nachrichten sie zuvor gesendet.</span><span class="sxs-lookup"><span data-stu-id="feb4f-125">**Guests can delete sent messages** – Turn this setting **On** to allow guests to delete messages they previously sent.</span></span>
    - <span data-ttu-id="feb4f-126">**Gruppenchat** – aktivieren Sie diese Einstellung **auf** so übergeben Sie die Gäste der Möglichkeit, Chat in Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="feb4f-126">**Chat** – Turn this setting **On** to give guests the ability to use chat in Teams.</span></span>
    - <span data-ttu-id="feb4f-127">**Verwenden Sie Giphys Unterhaltungen** – aktivieren diese Einstellung **auf** um Gäste mit Giphys in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-127">**Use Giphys in conversations** – Turn this setting **On** to allow guests to use Giphys in conversations.</span></span> <span data-ttu-id="feb4f-128">Giphy ist ein online-Datenbank und die Suchmaschine, mit dem Benutzer suchen und Freigeben von animierte GIF-Dateien.</span><span class="sxs-lookup"><span data-stu-id="feb4f-128">Giphy is an online database and search engine that allows users to search for and share animated GIF files.</span></span> <span data-ttu-id="feb4f-129">Jede Giphy wird eine Content Bewertung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-129">Each Giphy is assigned a content rating.</span></span>
    - <span data-ttu-id="feb4f-130">**Giphy zum Bewerten** – wählen Sie eine Bewertung aus der Dropdown-Liste aus:</span><span class="sxs-lookup"><span data-stu-id="feb4f-130">**Giphy content rating** –  Select a rating from the drop-down list:</span></span>
       - <span data-ttu-id="feb4f-131">**Alle Inhalte zulassen** - Gäste können sehen, fügen alle Giphys in Chats, unabhängig von der zum bewerten.</span><span class="sxs-lookup"><span data-stu-id="feb4f-131">**Allow all content** - Guests will be able to insert all Giphys in chats, regardless of the content rating.</span></span>
       - <span data-ttu-id="feb4f-132">**Moderater** - Gäste können Giphys in Chats einfügen, aber einigermaßen aus Versender nicht jugendfreier Inhalte eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="feb4f-132">**Moderate** - Guests will be able to insert Giphys in chats, but will be moderately restricted from adult content.</span></span>
       - <span data-ttu-id="feb4f-133">**Strict** – Gäste können Giphys in Chats einfügen, aber unbedingt Versender nicht jugendfreier Inhalte einfügen eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="feb4f-133">**Strict** – Guests will be able to insert Giphys in chats, but will be strictly restricted from inserting adult content.</span></span>
    - <span data-ttu-id="feb4f-134">**Verwenden Sie Memes Unterhaltungen** - aktivieren diese Einstellung **auf** um Gäste mit Memes in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-134">**Use Memes in conversations** - Turn this setting **On** to allow guests to use Memes in conversations.</span></span>
    - <span data-ttu-id="feb4f-135">**Verwenden Sie Aufkleber Unterhaltungen** – aktivieren diese Einstellung **auf** um Gäste mit Aufkleber in Unterhaltungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="feb4f-135">**Use Stickers in conversations** – Turn this setting **On** to allow guests to use stickers in conversations.</span></span> 


5.  <span data-ttu-id="feb4f-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="feb4f-136">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="feb4f-137">Verwenden von PowerShell, aktivieren oder deaktivieren Sie Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="feb4f-137">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="feb4f-138">Laden Sie die Skype für Business Online-PowerShell-Modul aushttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="feb4f-138">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="feb4f-139">Verbinden Sie eine PowerShell-Sitzung mit der Skype für Business Online Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="feb4f-139">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="feb4f-140">Überprüfen Sie die Konfiguration und wenn `AllowGuestUser` ist `$False`, verwenden Sie das Cmdlet " [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) ", um diese Liste festgelegt, `$True`.</span><span class="sxs-lookup"><span data-stu-id="feb4f-140">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
<span data-ttu-id="feb4f-141">Sie können jetzt Gastbenutzer in Teams für Ihre Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="feb4f-141">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="feb4f-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="feb4f-142">More information</span></span>

<span data-ttu-id="feb4f-143">Das folgende Video ausführliche Informationen zum Gastzugriff.</span><span class="sxs-lookup"><span data-stu-id="feb4f-143">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="feb4f-144">Hinzufügen von Gästen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="feb4f-144">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
