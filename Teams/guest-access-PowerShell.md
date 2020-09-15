---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie mithilfe von PowerShell den Gastzugriff auf alle Teams oder bestimmte Teams in Microsoft Teams zulassen oder blockieren.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c8a2e23f5c03420c4b0ce644a80e0733f9f69a5
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814334"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="9aa38-103">Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team</span><span class="sxs-lookup"><span data-stu-id="9aa38-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="9aa38-104">Neben der Verwendung des Microsoft 365 admin Centers und des Azure Active Directory (Azure AD)-Portals können Sie Windows PowerShell zum Steuern des Gastzugriffs verwenden.</span><span class="sxs-lookup"><span data-stu-id="9aa38-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="9aa38-105">Mit PowerShell können Sie folgende Aktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="9aa38-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="9aa38-106">Zulassen oder Blockieren des Gastzugriffs auf alle Teams und Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="9aa38-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="9aa38-107">Zulassen, dass Gäste allen Teams und Microsoft 365-Gruppen hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="9aa38-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="9aa38-108">Zulassen oder Blockieren von Gastbenutzern aus einem bestimmten Team oder einer Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="9aa38-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="9aa38-109">Ausführliche Informationen finden Sie unter "Verwenden von PowerShell zum Steuern des Gastzugriffs" in [Verwalten des Gastzugriffs in Microsoft 365-Gruppen](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span><span class="sxs-lookup"><span data-stu-id="9aa38-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="9aa38-110">Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden.</span><span class="sxs-lookup"><span data-stu-id="9aa38-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="9aa38-111">Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="9aa38-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="9aa38-112">Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="9aa38-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="9aa38-113">Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Microsoft 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="9aa38-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="9aa38-114">Wenn Sie die Gäste in Teams blockieren und Ihnen weiterhin den Zugriff auf SharePoint-Websites gestatten möchten, können Sie Azure AD PowerShell-Cmdlets verwenden, um den AllowGuestsToAccessGroups-Parameter für das Unternehmensobjekt zu deaktivieren, vorausgesetzt, die externe Freigabe ist für SharePoint-Websites aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9aa38-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="9aa38-115">Verwenden Sie PowerShell zum Aktivieren oder Deaktivieren von Gastzugriff.</span><span class="sxs-lookup"><span data-stu-id="9aa38-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="9aa38-116">Laden Sie das Skype for Business Online PowerShell-Modul unter https://www.microsoft.com/download/details.aspx?id=39366 herunter.</span><span class="sxs-lookup"><span data-stu-id="9aa38-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="9aa38-117">Verbinden Sie eine PowerShell-Sitzung mit dem Skype for Business Online-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="9aa38-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="9aa38-118">Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="9aa38-118">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="9aa38-119">Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="9aa38-119">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ```powershell
    Import-Module -Name MicrosoftTeams
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="9aa38-120">Überprüfen Sie Ihre Konfiguration und wenn `AllowGuestUser` ist `$False`, verwenden Sie das Cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) zum Einstellen auf `$True`.</span><span class="sxs-lookup"><span data-stu-id="9aa38-120">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```powershell
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
<span data-ttu-id="9aa38-121">Sie können jetzt Gastbenutzer für Ihre Organisation in Teams unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9aa38-121">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="9aa38-122">Gastzugriff vs. externer Zugriff</span><span class="sxs-lookup"><span data-stu-id="9aa38-122">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
