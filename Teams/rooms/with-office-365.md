---
title: Bereitstellen von Microsoft Teams Rooms mit Microsoft 365 oder Office 365
ms.author: v-cichur
author: cichur
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams Rooms mit Microsoft 365 oder Office 365, wo Teams oder Skype for Business und Exchange online sind.
ms.openlocfilehash: 4ec54763379e4a13a69eb3e08019924708873faf
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196209"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Bereitstellen von Microsoft Teams Rooms mit Microsoft 365 oder Office 365

Lesen Sie dieses Thema, um Informationen zur Bereitstellung von Microsoft Teams Rooms mit Microsoft 365 oder Office 365 zu erhalten, wo Microsoft Teams oder Skype for Business und Exchange online sind.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht in der Konfiguration mithilfe von Remotecomputern Windows PowerShell. Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, das beim Erstellen neuer Benutzerkonten oder beim Überprüfen vorhandener Ressourcenkonten hilft, um sie in kompatible Microsoft Teams -Räume-Benutzerkonten zu verwandeln. Wenn Sie es vorziehen, können Sie die folgenden Schritte ausführen, um Konten zu konfigurieren, die von Ihrem Gerät in Microsoft Teams Rooms verwendet werden.

## <a name="requirements"></a>Anforderungen

Bevor Sie Microsoft Teams Rooms mit Microsoft 365 oder Office 365 bereitstellen, stellen Sie sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter ["Anforderungen für Microsoft Teams-Räume".](requirements.md)

Um Skype for Business zu aktivieren, müssen Sie über Folgendes verfügen:

- Skype for Business Online (Plan 2 oder ein enterprise-basierter Plan) oder höher in Ihrem Microsoft 365- oder Office 365-Plan. Der Plan muss Einwahlkonferenzfunktionen zulassen.

- Wenn Sie Einwahlfunktionen aus einer Besprechung benötigen, benötigen Sie eine Lizenz für Audiokonferenzen und Telefonsystem.  Wenn Sie Auswahlfunktionen aus einer Besprechung benötigen, benötigen Sie eine Lizenz für Audiokonferenzen.

- Ihre Mandantenbenutzer müssen über Ein-/Aus-Postfächer verfügen.

- Ihr Microsoft Teams Rooms-Konto erfordert mindestens eine Skype for Business Online (Plan 2)-Lizenz, aber keine Exchange Online-Lizenz. Details [finden Sie unter "Microsoft Teams-Räume"-Lizenzen.](rooms-licensing.md)

Details zu Skype for Business Online-Plänen finden Sie in der [Dienstbeschreibung für Skype for Business Online.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Hinzufügen eines Gerätekontos

1. Herstellen einer Verbindung mit Exchange Online PowerShell Anweisungen finden Sie unter ["Herstellen einer Verbindung mit Exchange Online PowerShell".](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. Erstellen Sie in Exchange Online PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Raumpostfächern sind standardmäßig keine Konten zugeordnet, daher müssen Sie beim Erstellen oder Ändern eines Raumpostfachs, das es ermöglicht, sich bei Skype Room Systems v2 zu authentifizieren, ein Konto hinzufügen.

   - Verwenden Sie die folgende Syntax, um ein neues Raumpostfach zu erstellen:

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird ein neues Raumpostfach mit den folgenden Einstellungen erstellt:

     - Name: Rigel-01

     - Alias: Rigel1

     - Konto: Rigel1@contoso.onmicrosoft.com

     - Kontokennwort: P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - Verwenden Sie die folgende Syntax, um ein vorhandenes Raumpostfach zu ändern:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach mit dem Aliaswert "Rigel2" aktiviert und das Kennwort auf 9898P@ $$W 0rd. Beachten Sie, dass das Konto aufgrund Rigel2@contoso.onmicrosoft.com Vorhandenen Aliaswerts nicht mehr verwendet werden kann.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Neues Postfach"](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und ["Set-Mailbox".](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)

3. Konfigurieren Sie in Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren erhalten die Raumreservierungsentscheidung direkt und ohne Eingreifen von Menschen: free = accept; busy = decline.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der durch den Parameter "AdditionalResponse" angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist ein Skype-Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach namens "Rigel-01" konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Informationen zur Syntax und zu Parametern finden Sie unter ["Set-CalendarProcessing".](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. Stellen Sie eine Verbindung mit MS Online PowerShell sicher, um Active Directory-Einstellungen zu erstellen, indem Sie das `Connect-MsolService -Credential $cred` PowerShell-Cmdlet ausführen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt.

5. Wenn das Kennwort nicht ablaufen soll, verwenden Sie die folgende Syntax:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   In diesem Beispiel wird das Kennwort für das Konto so Rigel1@contoso.onmicrosoft.com, dass es nie abläuft.

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   Sie können auch eine Telefonnummer für das Konto festlegen, indem Sie den folgenden Befehl ausführen:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

> [!NOTE]
> Wenn das Kennwort nicht auf "Nie ablaufen" festgelegt ist, kann sich das Konto nicht mehr auf dem Gerät anmelden, wenn das Konto den Ablaufzeitraum erreicht. Das Kennwort muss dann für das Konto geändert und auch lokal auf dem MTR-Gerät aktualisiert werden.

6. Das Gerätekonto muss über eine gültige Microsoft 365- oder Office 365-Lizenz verfügen, da Exchange und Microsoft Teams oder Skype for Business nicht funktionieren. Wenn Sie über eine Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Verwendungsstandort zuweisen – dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> um eine Liste der verfügbaren SKUs für Ihre Microsoft 365- oder Office 365-Organisation wie folgt abzurufen:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. In diesem Beispiel wird dem Konto die Besprechungsraumlizenz hinzufügt:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Ausführliche Anweisungen finden Sie unter "Zuweisen von Lizenzen zu [Benutzerkonten mit Office 365 PowerShell".](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Sie können diesem Konto auch Telefonsystemfunktionen hinzufügen, müssen es aber zuerst konfigurieren. Weitere [Informationen finden Sie unter "Was ist ein Telefonsystem?".](../what-is-phone-system-in-office-365.md) In diesem Beispiel wird der PstN-Anrufplan für Inlands- und Auslandsrufe hinzufügt:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Als Nächstes müssen Sie das Gerätekonto bei Skype for Business aktivieren. Stellen Sie sicher, dass Ihre Umgebung die in den Anforderungen von [Microsoft Teams Rooms definierten Anforderungen erfüllt.](requirements.md)

   Starten Sie eine [remote Windows PowerShell wie](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) folgt (installieren Sie unbedingt Skype for Business Online [PowerShell-Komponenten):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie Skype for Business Online Connector nicht installieren.

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto ab, das eingerichtet wird, wie im folgenden Beispiel gezeigt:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Aktivieren Sie als Nächstes Ihr Microsoft Teams Rooms-Konto für Skype for Business Server, indem Sie das folgende Cmdlet ausführen:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Neue Benutzerkonten werden möglicherweise nicht im gleichen Registrierungsstellenpool wie die vorhandenen Benutzerkonten im Mandanten erstellt. Der befehl oben verhindert aufgrund dieser Situation Fehler bei der Kontoeinrichtung.

## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie in der Lage sein, sich mit einem beliebigen Skype for Business-Client bei dem von Ihnen erstellten Konto anmelden zu können.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft Teams Rooms](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Lizenzierung von Microsoft Teams-Räumen](rooms-licensing.md)
