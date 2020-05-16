---
title: Erstellen von Microsoft Teams-Ressourcenkonten für Zusammenarbeits leisten für Microsoft Teams mithilfe von PowerShell
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
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Zusammenarbeits leisten für Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268052"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a>Erstellen eines Microsoft 365-Ressourcenkontos mithilfe der PowerShell

In diesem Thema finden Sie Informationen zum Erstellen von Ressourcenkonten für Zusammenarbeits Balken für Microsoft Teams mithilfe von PowerShell.

Die einfachste Möglichkeit zum Erstellen eines Ressourcenkontos ist die Verwendung des Microsoft 365 admin Centers. [Weitere Informationen hierzu finden Sie in diesem Artikel](resource-account-ui.md).

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a>Voraussetzungen

Stellen Sie sicher, dass Sie die Anforderungen erfüllt haben, bevor Sie Microsoft Teams-Räume mit Office 365 bereitstellen. Weitere Informationen finden Sie unter [Bereitstellen von Zusammenarbeits leisten für Microsoft Teams](collab-bar-deploy.md).

- Wenn Sie für die Zusammenarbeits Leiste PSTN-Funktionen benötigen, benötigen Sie eine Telefon System Lizenz.

- Ihre Ressourcenkonten müssen Exchange-Postfächer aufweisen. Da es sich hierbei um Ressourcenkonten handelt, ist keine Exchange-Lizenz erforderlich. Wir empfehlen die Verwendung der Lizenz für Besprechungsräume für Ressourcenkonten.


### <a name="add-a-resource-account"></a>Hinzufügen eines Ressourcenkontos

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell her. Anweisungen hierzu finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).

2. Erstellen Sie in Exchange Online PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach.

   - Verwenden Sie die folgende Syntax, um ein neues Raumpostfach zu erstellen:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Name: drängen-Room-01

     - Alias: HuddleRoom01

     - Konto: huddleroom01@contoso.onmicrosoft.com

     - Kontokennwort: P@ $ $W 0rd242

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach mit dem Alias Wert HuddleRoom02 aktiviert, und das Kennwort wird auf 808P@ $ $W 0rd festgelegt. Beachten Sie, dass das Konto aufgrund des vorhandenen Alias Werts HuddleRoom02@contoso.onmicrosoft.com wird.

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und [festgelegtes Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).


3. Konfigurieren Sie in Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungs Erfahrung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Raum Reservierungs Entscheidung direkt ohne menschliche Intervention: kostenlos = akzeptieren; busy = ablehnen.)

   - AddOrganizerToSubject: $false (der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Text im Nachrichtentext der eingehenden Besprechungsanfragen behalten.)

   - Dem DeleteSubject können: $false (Betreff der eingehenden Besprechungsanfragen beibehalten.)

   - RemovePrivateProperty: $false (stellt sicher, dass das private Flag, das vom Organisator der Besprechung in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (der durch den AdditionalResponse-Parameter angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "dieser Raum verfügt über eine Kollaborations Leiste für Microsoft Teams!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Room-Postfach mit dem Namen "Zusammendrängen-Raum-01" konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Satz-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Stellen Sie eine Verbindung mit MS Online PowerShell her, um Active Directory-Einstellungen durch Ausführen des `Connect-MsolService -Credential $cred` PowerShell-Cmdlets zu erstellen.   Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt. 

5. Verwenden Sie die folgende Syntax, um das Kennwort für huddleroom01@contoso.onmicrosoft.com so zu ändern, dass es nicht abläuft:

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. Das Ressourcenkonto muss über eine gültige Office 365-Lizenz verfügen, vorzugsweise über die SKU des Besprechungsraums. Sie müssen Ihrem Geräte Konto auch einen Verwendungsstandort zuweisen, der bestimmt, welche Lizenz SKUs für Ihr Konto zur Verfügung stehen. Sie können verwenden `Get-MsolAccountSku` , um eine Liste der verfügbaren SKUs für Ihren Office 365-Mandanten abzurufen.

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    Sie können die Lizenz mithilfe von "Satz-MsolUserLicense" zuweisen. 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).




[Konfigurieren von Konten für Zusammenarbeits leisten für Microsoft Teams mithilfe von PowerShell](resource-account-ps.md)

[Bereitstellen von Zusammenarbeits leisten für Microsoft Teams](collab-bar-deploy.md)

[Kollaborations leisten für Microsoft Teams-Lizenzierung](../rooms/rooms-licensing.md)


