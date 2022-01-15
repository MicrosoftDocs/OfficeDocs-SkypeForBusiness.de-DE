---
title: Bereitstellen von Microsoft Teams-Räumen mit Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen Microsoft Teams-Räume mit Office 365.
ms.openlocfilehash: d4c66fb863c5c41a717808ddca43002752510fb5
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056025"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>Bereitstellen von Microsoft Teams-Räumen mit Office 365

In diesem Thema finden Sie Informationen zum Bereitstellen Microsoft Teams-Räume mit Office 365.

## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Office 365 bereitstellen, vergewissern Sie sich, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)

### <a name="add-a-resource-account"></a>Hinzufügen eines Ressourcenkontos

1. Verbinden Sie Exchange Online PowerShell. Anweisungen finden Sie [unter Verbinden zum Exchange Online von PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. Erstellen Exchange Online in PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Raumpostfächern sind standardmäßig keine Konten zugeordnet. Sie müssen ein Konto hinzufügen, wenn Sie ein Raumpostfach erstellen oder ändern, das seine Authentifizierung ermöglicht.

   - Zum Erstellen eines neuen Raumpostfachs verwenden Sie die folgende Syntax:

     ``` PowerShell
     New-Mailbox -Name '<Unique Name>' -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Name: Konferenzraum 01

     - Alias: ConferenceRoom01

     - Konto: ConferenceRoom01@contoso.com

     - Kontokennwort: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name 'Conference Room 01' -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID 'ConferenceRoom01@contoso.com' -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie zum Ändern eines vorhandenen Raumpostfachs die folgende Syntax:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert ConferenceRoom02 hat, und das Kennwort auf 9898P@$$W 0rd.

     ``` PowerShell
     Set-Mailbox -Identity 'ConferenceRoom02' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)


3. Konfigurieren Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - Automatisieren Der Verarbeitung: AutoAccept (Das Postfach macht automatisch eine Raumreservierungsentscheidung direkt ohne Eingreifen des Benutzers.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie den Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist Microsoft Teams Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach namens Project-Rigel-01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity 'ConferenceRoom01' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse 'This is a Microsoft Teams meeting room!'
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).
   
4. Verbinden MS Online PowerShell active Directory-Werte festlegen, indem Sie das PowerShell-Cmdlet "Verbinden-MsolService -Credential $cred" ausführen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt. 

5. Es wird dringend empfohlen, den Kennwortablauf für Konten zu Teams-Räume deaktivieren. Im Folgenden finden Sie ein Beispiel zum Deaktivieren des Kennwortablaufs für das Konto ConferenceRoom01:

    ``` PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```


1. Das Ressourcenkonto muss über eine gültige Lizenz Office 365 verfügen, um eine Verbindung mit Microsoft Teams. Außerdem müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Mit können `Get-MsolAccountSku` Sie eine Liste der verfügbaren SKUs für Ihren Mandanten Office 365 abrufen. Sie können eine Lizenz mit dem `Set-MsolUserLicense` Cmdlet hinzufügen.

   In diesem Beispiel wird die Besprechungsraum einem Benutzer in den USA zugewiesen.

  ``` PowerShell
   Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
  ``` 


   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)


## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem beliebigen Microsoft Teams-Client bei dem von Ihnen erstellten Konto anmelden.

## <a name="see-also"></a>Mehr dazu
[Aktualisieren von Raumpostfächern mit zusätzlichen Metadaten, um eine bessere Erfahrung mit Such- und Raumvorschlägen zu ermöglichen](/powershell/module/exchange/set-place)

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Microsoft Teams-Räume-Lizenzierung](rooms-licensing.md)
