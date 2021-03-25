---
title: Erstellen von Microsoft Teams-Ressourcenkonten für Zusammenarbeitsbalken für Microsoft Teams mit PowerShell
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

In diesem Thema finden Sie Informationen zum Erstellen von Ressourcenkonten für Zusammenarbeitsbalken für Microsoft Teams mit PowerShell.

Die einfachste Möglichkeit zum Erstellen eines Ressourcenkontos ist das Microsoft 365 Admin Center. [In diesem Artikel erfahren Sie, wie Sie dies tun.](resource-account-ui.md)

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Anforderungen

Bevor Sie Microsoft Teams Rooms mit Office 365 bereitstellen, stellen Sie sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Bereitstellen von Zusammenarbeitsbalken für Microsoft Teams](collab-bar-deploy.md).

- Wenn Sie PSTN-Funktionen für die Zusammenarbeitsleiste benötigen, benötigen Sie eine Telefonsystemlizenz.

- Ihre Ressourcenkonten müssen über Exchange-Postfächer verfügen. Da es sich um Ressourcenkonten handelt, ist keine Exchange-Lizenz erforderlich. Wir empfehlen die Verwendung der Lizenz für Besprechungsräume für Ressourcenkonten.


### <a name="add-a-resource-account"></a>Hinzufügen eines Ressourcenkontos

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell herzustellen. Anweisungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. Erstellen Sie in Exchange Online PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach.

   - Verwenden Sie zum Erstellen eines neuen Raumpostfachs die folgende Syntax:

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

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert HuddleRoom02 hat, und legt das Kennwort auf 808P@ $$W 0rd fest. Beachten Sie, dass das Konto aufgrund HuddleRoom02@contoso.onmicrosoft.com vorhandenen Aliaswerts nicht verwendet wird.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Syntax- und Parameterinformationen finden Sie unter [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).


3. Konfigurieren Sie in Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - AutomatisierenVerarbeitung: AutoAccept (Besprechungsorganisatoren erhalten die Raumreservierungsentscheidung direkt ohne menschliches Eingreifen: frei = annehmen; beschäftigt = ablehnen.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie beliebigen Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dieser Raum verfügt über eine Zusammenarbeitsleiste für Microsoft Teams!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach namens Huddle-Room-01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Ausführliche Syntax- und Parameterinformationen finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Stellen Sie eine Verbindung mit MS Online PowerShell sicher, um Active Directory-Einstellungen zu erstellen, indem Sie das `Connect-MsolService -Credential $cred` Powershell-Cmdlet ausführen.   Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 wird](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt. 

5. Legen Sie das Kennwort für huddleroom01@contoso.onmicrosoft.com die folgende Syntax nicht ab:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. Das Ressourcenkonto muss über eine gültige Office 365-Lizenz verfügen, vorzugsweise über die Besprechungsraum-SKU. Außerdem müssen Sie Ihrem Gerätekonto einen Nutzungsspeicherort zuweisen – dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können eine Liste der verfügbaren SKUs für `Get-MsolAccountSku` Ihren Office 365-Mandanten abrufen.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Sie können die Lizenz mithilfe von Set-MsolUserLicense zuweisen. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Ausführliche Anweisungen finden Sie unter Zuweisen von Lizenzen [zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)




[Konfigurieren von Konten für Zusammenarbeitsbalken für Microsoft Teams mit PowerShell](resource-account-ps.md)

[Bereitstellen von Zusammenarbeitsbalken für Microsoft Teams](collab-bar-deploy.md)

[Zusammenarbeitsbalken für Microsoft Teams-Lizenzierung](../rooms/rooms-licensing.md)