---
title: Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
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
f1.keywords:
- NOCSH
description: Verwenden Sie PowerShell, um den Gastzugriff auf Teams in Microsoft Teams zuzulassen oder zu blockieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e15e2e70559f75cff6be97f2996dc45666f963b8
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776960"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>Verwenden von PowerShell zum Steuern des Gastzugriffs auf ein Team
================================================

Neben der Verwendung des Microsoft 365 admin Centers und des Azure Active Directory (Azure AD)-Portals können Sie Windows PowerShell zum Steuern des Gastzugriffs verwenden. Mit PowerShell können Sie folgende Aktionen durchführen:
  
- Zulassen oder Blockieren des Gastzugriffs auf alle Teams und Microsoft 365-Gruppen

- Zulassen, dass Gäste allen Teams und Microsoft 365-Gruppen hinzugefügt werden

- Zulassen oder Blockieren von Gastbenutzern für ein bestimmtes Team oder eine bestimmte Office 365-Gruppe

Ausführliche Informationen finden Sie unter "Verwenden von PowerShell zum Steuern des Gastzugriffs" in [Verwalten des Gastzugriffs in Microsoft 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).

  
Sie können PowerShell auch zum Zulassen oder Blockieren eines Gastbenutzers basierend auf der zugehörigen Domäne verwenden. Beispiel: Ihr Unternehmen (Contoso) hat eine Partnerschaft mit einem anderen Unternehmen (Fabrikam). Sie können Fabrikam zu Ihrer Zulassungsliste hinzufügen, sodass Ihre Benutzer diese Gäste zu ihren Gruppen hinzufügen können. Weitere Informationen finden Sie unter [Zulassen/Blockieren des Gastzugriffs auf Microsoft 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=854001).
  
Wenn Sie die Gäste in Teams blockieren und Ihnen weiterhin den Zugriff auf SharePoint-Websites gestatten möchten, können Sie Azure AD PowerShell-Cmdlets verwenden, um den AllowGuestsToAccessGroups-Parameter für das Unternehmensobjekt zu deaktivieren, vorausgesetzt, die externe Freigabe ist für SharePoint-Websites aktiviert.

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>Verwenden Sie PowerShell zum Aktivieren oder Deaktivieren von Gastzugriff.

1.  Laden Sie das Skype for Business Online PowerShell-Modul unter https://www.microsoft.com/download/details.aspx?id=39366 herunter.
 
2.  Verbinden Sie eine PowerShell-Sitzung mit dem Skype for Business Online-Endpunkt.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  Überprüfen Sie Ihre Konfiguration und wenn `AllowGuestUser` ist `$False`, verwenden Sie das Cmdlet [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) zum Einstellen auf `$True`.

    ```PowerShell
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
Sie können jetzt Gastbenutzer für Ihre Organisation in Teams unterstützen.


## <a name="guest-access-vs-external-access"></a>Gastzugriff vs. externer Zugriff

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
