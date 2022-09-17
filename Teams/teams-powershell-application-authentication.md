---
title: Anwendungsbasierte Authentifizierung im Teams PowerShell-Modul
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über die anwendungsbasierte Authentifizierung im Teams PowerShell-Modul, das für die Verwaltung von Microsoft Teams verwendet wird.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 479dd64d6eece46335545e79e8f618b797e85f77
ms.sourcegitcommit: 89e3681a88f06a9c6860d9eaea598e57b928b68a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2022
ms.locfileid: "67795064"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Anwendungsbasierte Authentifizierung im Teams PowerShell-Modul

Die anwendungsbasierte Authentifizierung wird jetzt im Teams PowerShell-Modul für einen begrenzten Satz von Cmdlets in der Vorschau mit der Version 4.7.1-Vorschau oder höher unterstützt. Derzeit wird dieser Authentifizierungsmodus nur in kommerziellen Umgebungen unterstützt. Es wird nicht für Kunden unterstützt, die für regional gehostete Besprechungen in Skype for Business Online aktiviert sind oder zuvor aktiviert wurden.


## <a name="cmdlets-supported"></a>Unterstützte Cmdlets

Alle Nicht-Cs-Cmdlets \*(z. B. Get-Team), Get-CsTenant Get-CsOnlineUser & Get-CsOnlineVoiceUser werden bereits unterstützt. Andere Cmdlets werden schrittweise eingeführt. 


## <a name="examples"></a>Beispiele

Die folgenden Beispiele zeigen die Verwendung des Teams PowerShell-Moduls mit der App-basierten Azure AD-Authentifizierung: 

- Verbinden mit einem Zertifikatfingerabdruck:

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  Wenn Sie den Parameter CertificateThumbprint verwenden, muss das Zertifikat auf dem Computer installiert sein, auf dem Sie den Befehl ausführen. Das Zertifikat sollte im Benutzerzertifikatspeicher installiert werden.
  
- Verbinden mithilfe von Zugriffstoken:
  
  Zugriffstoken können über den login.microsoftonline.com Endpunkt abgerufen werden. Es sind zwei Zugriffstoken erforderlich: Ressourcen "MS Graph" und "Skype- und Teams-Mandanten Admin-API".

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>Wie funktioniert es?

Das Teams PowerShell-Modul ruft das appbasierte Token mithilfe der Anwendungs-ID, Mandanten-ID und des Zertifikatfingerabdrucks ab. Dem in Azure AD bereitgestellten Anwendungsobjekt ist eine Verzeichnisrolle zugewiesen, die im Zugriffstoken zurückgegeben wird. Die rollenbasierte Zugriffssteuerung (RBAC) der Sitzung wird mithilfe der Verzeichnisrolleninformationen konfiguriert, die im Token verfügbar sind.


## <a name="setup-application-based-authentication"></a>Anwendungsbasierte Authentifizierung einrichten

Für die Authentifizierung mithilfe von Anwendungsobjekten ist ein anfängliches Onboarding erforderlich. Anwendungs- und Dienstprinzipal werden austauschbar verwendet, aber eine Anwendung ist wie ein Klassenobjekt, während ein Dienstprinzipal einer Instanz der Klasse ähnelt. Weitere Informationen zu diesen Objekten finden Sie unter [Anwendungs- und Dienstprinzipalobjekte in Azure Active Directory](/azure/active-directory/develop/app-objects-and-service-principals).

Im Folgenden werden die allgemeinen Schritte zum Erstellen von Anwendungen in Azure Ad beschrieben. Ausführliche Schritte finden Sie in diesem [Artikel](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Registrieren der Anwendung in Azure AD
2. Zuweisen von API-Berechtigungen für die Anwendung
   - Für \*-Cs-Cmdlets sind keine API-Berechtigungen erforderlich.
   - Für Nicht-Cs-Cmdlets \*: Die erforderlichen Microsoft Graph-API Berechtigungen sind `User.Read.All`, `Group.ReadWrite.All`, `AppCatalog.ReadWrite.All`, `TeamSettings.ReadWrite.All`, `Channel.Delete.All`, , `ChannelSettings.ReadWrite.All``ChannelMember.ReadWrite.All`.  
3. Generieren eines selbstsignierten Zertifikats
4. Anfügen des Zertifikats an die Azure AD-Anwendung
5. Zuweisen von Azure AD-Rollen zur Anwendung

Der Anwendung müssen die entsprechenden RBAC-Rollen zugewiesen sein. Da die Apps in Azure AD bereitgestellt werden, können Sie jede der unterstützten integrierten Rollen verwenden.
 
