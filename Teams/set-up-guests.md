---
title: Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams
author: LaithAlShamri
ms.author: lolaj
manager: serdars
ms.date: 10/11/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Aktivieren oder Deaktivieren der Funktion für den Gastzugriff in Microsoft Teams
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ab67b3fa9ad58c1aa3e8fdd254e3b3515743b4c
ms.sourcegitcommit: 9dd5d8fe6888f0c7d2df1e40fdd8b4c80512f8f9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "25498121"
---
<a name="turn-on-or-off-guest-access-to-microsoft-teams"></a><span data-ttu-id="90f50-103">Aktivieren oder deaktivieren des Gastzugriffs auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90f50-103">Turn on or off guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="90f50-104">Als Office 365-Administrator müssen Sie die Gastfunktion aktivieren, bevor Sie oder die Benutzer Ihrer Organisation (vor allem Teambesitzer) Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="90f50-104">As the Office 365 admin, you must enable the guest feature before you or your organization's users (specifically, team owners) can add guests.</span></span> 

<span data-ttu-id="90f50-105">Die Gasteinstellungen werden in Azure Active Directory festgelegt.</span><span class="sxs-lookup"><span data-stu-id="90f50-105">The guest settings are set in Azure Active Directory.</span></span> <span data-ttu-id="90f50-106">Es dauert ca. 2 bis 24 Stunden, bis die Änderungen in der gesamten Office 365-Organisation wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="90f50-106">It takes 2 hours to 24 hours for the changes to be effective across your Office 365 organization.</span></span> <span data-ttu-id="90f50-107">Wenn Benutzer versuchen, einen Gast zu ihrem Team hinzuzufügen, und dabei die Meldung „Wenden Sie sich an Ihren Administrator“ sehen, ist wahrscheinlich die Gastfunktion nicht aktiviert, oder die Einstellungen sind noch nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="90f50-107">If a user sees the message "Contact your administrator" when they try to add a guest to their team, it's likely that either the guest feature hasn't been enabled or the settings haven’t become effective yet.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="90f50-108">Um die Nutzung der Gastzugriffsfunktion in vollem Umfang zu ermöglichen, müssen Sie die gegenseitige Abhängigkeit bezüglich der Kernautorisierung von Microsoft Teams, Azure Active Directory und Office 365 verstehen.</span><span class="sxs-lookup"><span data-stu-id="90f50-108">To enable the full experience of the guest access feature, it's important to understand the core authorization dependency between Microsoft Teams, Azure Active Directory, and Office 365.</span></span> <span data-ttu-id="90f50-109">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="90f50-109">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>

## <a name="configure-guest-access-in-the-teams--skype-for-business-admin-center"></a><span data-ttu-id="90f50-110">Konfigurieren von Gastzugriff in der Teams & Skype für Business-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="90f50-110">Configure guest access in the Teams & Skype for Business admin center</span></span>

1.  <span data-ttu-id="90f50-111">Melden Sie sich bei der Teams & Skype für Business Administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="90f50-111">Sign in to the Teams & Skype for Business admin center.</span></span>

2.  <span data-ttu-id="90f50-112">Wählen Sie **gesamte Org Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="90f50-112">Select **Org-wide settings** > **Guest access**.</span></span>

3. <span data-ttu-id="90f50-113">Legen Sie die Umschaltfläche **Gast Zugriffsberechtigung in Microsoft-Teams** auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="90f50-113">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![<span data-ttu-id="90f50-114">Legen Sie Gast Access Switch auf auf zulassen</span><span class="sxs-lookup"><span data-stu-id="90f50-114">Allow guest access switch set to On</span></span> ](media/set-up-guests-image1.png)

4.  <span data-ttu-id="90f50-115">Legen Sie die Schaltet für **aufrufen**, **Besprechung**und **Messaging** zum **ein-** oder **Ausschalten**, je nach dem Zugriff, den Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="90f50-115">Set the toggles for **Calling**, **Meeting**, and **Messaging** to **On** or **Off**, depending on the access you want to allow.</span></span>

5.  <span data-ttu-id="90f50-116">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="90f50-116">Click **Save**.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="90f50-117">Verwenden von PowerShell, aktivieren oder deaktivieren Sie Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="90f50-117">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="90f50-118">Laden Sie die Skype für Business Online-PowerShell-Modul aushttps://www.microsoft.com/en-us/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="90f50-118">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/en-us/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="90f50-119">Verbinden Sie eine PowerShell-Sitzung mit der Skype für Business Online Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="90f50-119">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  <span data-ttu-id="90f50-120">Überprüfen Sie die Konfiguration und wenn `AllowGuestUser` ist `$False`, verwenden Sie das Cmdlet " [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) ", um diese Liste festgelegt, `$True`.</span><span class="sxs-lookup"><span data-stu-id="90f50-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

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
    AllowTBotProactiveMessaging      : False
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="90f50-121">Sie können jetzt Gastbenutzer in Teams für Ihre Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="90f50-121">You can now have guest users in Teams for your organization.</span></span>

## <a name="more-information"></a><span data-ttu-id="90f50-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90f50-122">More information</span></span>

<span data-ttu-id="90f50-123">Das folgende Video ausführliche Informationen zum Gastzugriff.</span><span class="sxs-lookup"><span data-stu-id="90f50-123">Watch the following video for more details about guest access.</span></span>

|  |  |
|---------|---------|
| <span data-ttu-id="90f50-124">Hinzufügen von Gästen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90f50-124">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
