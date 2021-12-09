---
title: Bereitstellen Microsoft Teams-Räume mit Microsoft 365 oder Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Microsoft 365 oder Office 365, wobei Teams oder Skype for Business und Exchange online sind.
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355644"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Bereitstellen Microsoft Teams-Räume mit Microsoft 365 oder Office 365

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams-Räume mit Microsoft 365 oder Office 365, wobei Microsoft Teams und Exchange online sind.

## <a name="requirements"></a>Anforderungen

Bevor Sie Ihre Microsoft Teams-Räume mit Microsoft 365 oder Office 365 bereitstellen, vergewissern Sie sich, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams-Räume Anforderungen.](requirements.md)

### <a name="add-a-resource-account"></a>Hinzufügen eines Ressourcenkontos

1. Verbinden Sie Exchange Online PowerShell. Anweisungen finden Sie [unter Verbinden zum Exchange Online von PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Erstellen Exchange Online in PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Raumpostfächer verfügen standardmäßig nicht über zugeordnete Konten, daher müssen Sie ein Konto hinzufügen, wenn Sie ein Raumpostfach erstellen oder ändern, das es ermöglicht, sich bei anderen Benutzern zu Microsoft Teams.

   - Zum Erstellen eines neuen Raumpostfachs verwenden Sie die folgende Syntax:

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Konto: ConferenceRoom01@contoso.com
  
     - Name: ConferenceRoom01

     - Alias: ConferenceRoom01

     - Kontokennwort: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie zum Ändern eines vorhandenen Raumpostfachs die folgende Syntax:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert ConferenceRoom02 hat, und das Kennwort auf 9898P@$$W 0rd. Beachten Sie, dass das Konto aufgrund ConferenceRoom02@contoso.com vorhandenen Aliaswerts nicht mehr verwendet wird.

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)

3. Konfigurieren Exchange Online in PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - Automatisieren Der Verarbeitung: AutoAccept (Besprechungsorganisatoren erhalten die Entscheidung über die Raumreservierung direkt ohne Eingreifen des Personals.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie den Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist Microsoft Teams Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach namens ConferenceRoom01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Verbinden sie sich an MS Online PowerShell, um Active Directory-Einstellungen durch Ausführen der `Connect-MsolService` PowerShell-Cmdlet. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory wird PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt.

5. Legen Sie mithilfe der folgenden Syntax das Kennwort so ein, dass es nie abläuft:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   In diesem Beispiel wird das Kennwort für das Konto so ConferenceRoom01@contoso.onmicrosoft.com, dass es nie abläuft.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Sie können auch eine Telefonnummer für das Konto festlegen, indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > Wenn das Kennwort nicht auf Nie abläuft festgelegt ist, wird das Konto nicht mehr auf dem Gerät anmelden, wenn das Konto den Ablaufzeitraum erreicht. Das Kennwort muss dann für das Konto geändert und auch lokal auf dem Computer Teams-Räume. Benutzer können nicht an Besprechungen auf einem Teams-Räume, während das Kennwort abgelaufen ist.

6. Das Ressourcenkonto muss über eine gültige Lizenz Microsoft 365 oder Office 365 verfügen, da Exchange und Microsoft Teams nicht funktionieren. Wenn Sie über eine Lizenz verfügen, müssen Sie Ihrem Ressourcenkonto einen Verwendungsstandort zuweisen. Dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> um eine Liste der verfügbaren SKUs für Ihre Microsoft 365 oder Office 365 Organisation wie folgt abzurufen:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie die `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. In diesem Beispiel wird Besprechungsraum-Lizenz dem Konto hinzufügt:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Ausführliche Anweisungen finden Sie unter [Zuweisen von Lizenzen zu Benutzerkonten mit Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Sie können diesem Konto Telefonsystem Funktionen hinzufügen, sie müssen sie aber zuerst konfigurieren. Weitere [Informationen finden Sie Telefonsystem Unter](../what-is-phone-system-in-office-365.md) Was ist eine E-Telefonsystem?. In diesem Beispiel wird der PSTN-Anrufplan für Inlands- und Auslandsrufe hinzufügt:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem beliebigen Microsoft Teams-Client bei dem von Ihnen erstellten Konto anmelden.

## <a name="see-also"></a>Mehr dazu

[Konfigurieren von Konten für Microsoft Teams-Räume](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Microsoft Teams-Räume-Lizenzierung](rooms-licensing.md)
