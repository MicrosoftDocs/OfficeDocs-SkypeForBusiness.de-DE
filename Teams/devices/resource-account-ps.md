---
title: Erstellen Microsoft Teams Ressourcenkonten für Zusammenarbeitsleisten für Microsoft Teams mithilfe von PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Zusammenarbeitsbalken für Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 812fb4704661aa11d3388048fa044030cdb1ce00
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115603"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Erstellen eines Microsoft 365-Ressourcenkontos mithilfe der PowerShell

In diesem Thema finden Sie Informationen zum Erstellen von Ressourcenkonten für Zusammenarbeitsleisten Microsoft Teams PowerShell.

Die einfachste Möglichkeit zum Erstellen eines Ressourcenkontos ist das Microsoft 365 Admin Center. [Informationen dazu finden Sie in diesem Artikel.](resource-account-ui.md)

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Office 365 bereitstellen, vergewissern Sie sich, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Bereitstellen von Zusammenarbeitsleisten für Microsoft Teams.](collab-bar-deploy.md)

- Wenn Sie PSTN-Funktionen für die Zusammenarbeitsleiste benötigen, benötigen Sie Telefonsystem Lizenz.

- Ihre Ressourcenkonten müssen über Exchange verfügen. Da es sich um Ressourcenkonten handelt, Exchange keine Lizenz erforderlich. Wir empfehlen die Verwendung der Lizenz für Besprechungsräume für Ressourcenkonten.


### <a name="add-a-resource-account"></a>Hinzufügen eines Ressourcenkontos

1. Verbinden Sie Exchange Online PowerShell. Anweisungen finden Sie [unter Verbinden Exchange Online PowerShell.](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module)

2. Erstellen Exchange Online in PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach.

   - Zum Erstellen eines neuen Raumpostfachs verwenden Sie die folgende Syntax:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Name: Huddle-Room-01

     - Alias: HuddleRoom01

     - Konto: huddleroom01@contoso.onmicrosoft.com

     - Kontokennwort: P@$$W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Verwenden Sie zum Ändern eines vorhandenen Raumpostfachs die folgende Syntax:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert "HuddleRoom02" enthält, und das Kennwort wird auf "808P@$$W 0rd" festlegen. Beachten Sie, dass das Konto aufgrund HuddleRoom02@contoso.onmicrosoft.com vorhandenen Aliaswerts nicht mehr verwendet werden kann.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)


3. Konfigurieren Exchange Online in PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - Automatisieren der Verarbeitung: AutoAccept (Besprechungsorganisatoren erhalten die Entscheidung über die Raumreservierung direkt ohne Eingreifen eines Menschen: frei = akzeptieren; beschäftigt = ablehnen.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie den Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dieser Raum verfügt über eine Zusammenarbeitsleiste für Microsoft Teams!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Huddle-Room-01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Verbinden MS Online PowerShell, um Active Directory-Einstellungen durch Ausführen des `Connect-MsolService -Credential $cred` powershell-Cmdlets zu erstellen.   Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt. 

5. Legen Sie mithilfe der folgenden Syntax huddleroom01@contoso.onmicrosoft.com Ablauf des Kennworts für ihr Kennwort:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. Das Ressourcenkonto muss über eine gültige Office 365 verfügen, vorzugsweise die Besprechungsraum SKU. Außerdem müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Mit können `Get-MsolAccountSku` Sie eine Liste der verfügbaren SKUs für Ihren Mandanten Office 365 abrufen.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Sie können die Lizenz mithilfe von Set-MsolUserLicense zuweisen. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)




[Konfigurieren von Konten für Zusammenarbeitsleisten für Microsoft Teams mithilfe von PowerShell](resource-account-ps.md)

[Bereitstellen von Zusammenarbeitsleisten für Microsoft Teams](collab-bar-deploy.md)

[Zusammenarbeitsleisten für Microsoft Teams Lizenzierung](../rooms/rooms-licensing.md)