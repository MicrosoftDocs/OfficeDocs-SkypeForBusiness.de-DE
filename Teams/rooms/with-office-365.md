---
title: Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365
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
description: In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams Rooms mit Microsoft 365 oder Office 365, in denen Teams oder Skype for Business und Exchange online sind.
ms.openlocfilehash: 7a25fb17e4b9fce4a51c6e2be5828ecafff59894
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569121"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>Bereitstellen von Microsoft Teams-Räumen mit Microsoft 365 oder Office 365

In diesem Thema finden Sie Informationen zum Bereitstellen von Microsoft Teams Rooms mit Microsoft 365 oder Office 365, in denen Microsoft Teams oder Skype for Business und Exchange online sind.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten besteht in der Konfiguration mithilfe von Remotekonten Windows PowerShell. Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), ein Skript, das beim Erstellen neuer Benutzerkonten hilft, oder vorhandene Ressourcenkonten zu überprüfen, über die Sie verfügen, um sie in kompatible Microsoft Teams Rooms-Benutzerkonten zu verwandeln. Wenn Es Ihnen lieber ist, können Sie die folgenden Schritte ausführen, um Konten zu konfigurieren, die Ihr Microsoft Teams Rooms-Gerät verwendet.

## <a name="requirements"></a>Anforderungen

Bevor Sie Microsoft Teams Rooms mit Microsoft 365 oder Office 365 bereitstellen, stellen Sie sicher, dass Sie die Anforderungen erfüllt haben. Weitere Informationen finden Sie unter [Microsoft Teams Rooms-Anforderungen](requirements.md).

Um Skype for Business zu aktivieren, müssen Sie über Folgendes verfügen:

- Skype for Business Online (Plan 2 oder ein unternehmensbasierter Plan) oder höher in Ihrem Microsoft 365- oder Office 365-Plan. Der Plan muss Einwahlkonferenzfunktionen zulassen.

- Wenn Sie Einwahlfunktionen aus einer Besprechung benötigen, benötigen Sie eine Lizenz für Audiokonferenzen und Telefonsystem.  Wenn Sie Auswahlfunktionen aus einer Besprechung benötigen, benötigen Sie eine Lizenz für Audiokonferenzen.

- Ihre Mandantenbenutzer müssen über Exchange-Postfächer verfügen.

- Ihr Microsoft Teams Rooms-Konto erfordert mindestens eine Skype for Business Online (Plan 2)-Lizenz, erfordert jedoch keine Exchange Online-Lizenz. Details [finden Sie unter Microsoft Teams Rooms-Lizenzen.](rooms-licensing.md)

Details zu Skype for Business Online-Plänen finden Sie in der Beschreibung des [Skype for Business Online-Diensts.](https://technet.microsoft.com/library/jj822172.aspx)

### <a name="add-a-device-account"></a>Hinzufügen eines Gerätekontos

1. Stellen Sie eine Verbindung mit Exchange Online PowerShell herzustellen. Anweisungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

2. Erstellen Sie in Exchange Online PowerShell ein neues Raumpostfach, oder ändern Sie ein vorhandenes Raumpostfach. Standardmäßig verfügen Raumpostfächer nicht über zugeordnete Konten, daher müssen Sie ein Konto hinzufügen, wenn Sie ein Raumpostfach erstellen oder ändern, das es ermöglicht, sich bei Skype Room Systems v2 zu authentifizieren.

   - Verwenden Sie zum Erstellen eines neuen Raumpostfachs die folgende Syntax:

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

   - Verwenden Sie zum Ändern eines vorhandenen Raumpostfachs die folgende Syntax:

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     In diesem Beispiel wird das Konto für das vorhandene Raumpostfach aktiviert, das den Aliaswert Rigel2 hat, und legt das Kennwort auf 9898P@ $$W 0rd fest. Beachten Sie, dass das Konto aufgrund Rigel2@contoso.onmicrosoft.com vorhandenen Aliaswerts nicht verwendet wird.

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   Ausführliche Syntax- und Parameterinformationen finden Sie unter [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) und [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).

3. Konfigurieren Sie in Exchange Online PowerShell die folgenden Einstellungen für das Raumpostfach, um die Besprechungserfahrung zu verbessern:

   - AutomatisierenVerarbeitung: AutoAccept (Besprechungsorganisatoren erhalten die Raumreservierungsentscheidung direkt ohne menschliches Eingreifen: frei = annehmen; beschäftigt = ablehnen.)

   - AddOrganizerToSubject: $false (Der Besprechungsorganisator wird dem Betreff der Besprechungsanfrage nicht hinzugefügt.)

   - DeleteComments: $false (Behalten Sie beliebigen Text im Nachrichtentext eingehender Besprechungsanfragen bei.)

   - DeleteSubject: $false (Betreff eingehender Besprechungsanfragen behalten.)

   - RemovePrivateProperty: $false (Stellt sicher, dass die private Kennzeichnung, die vom Besprechungsorganisator in der ursprünglichen Besprechungsanfrage gesendet wurde, wie angegeben bleibt.)

   - AddAdditionalResponse: $true (Der vom Parameter AdditionalResponse angegebene Text wird Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist ein Skype-Besprechungsraum!" (Der zusätzliche Text, der der Besprechungsanfrage hinzugefügt werden soll.)

   In diesem Beispiel werden diese Einstellungen für das Raumpostfach mit dem Namen Rigel-01 konfiguriert.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Ausführliche Syntax- und Parameterinformationen finden Sie unter [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

4. Stellen Sie eine Verbindung mit MS Online PowerShell sicher, um Active Directory-Einstellungen zu erstellen, indem Sie das `Connect-MsolService -Credential $cred` PowerShell-Cmdlet ausführen. Details zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0 wird](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) nicht unterstützt.

5. Wenn das Kennwort nicht ablaufen soll, verwenden Sie die folgende Syntax:

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   In diesem Beispiel wird das Kennwort für das Konto Rigel1@contoso.onmicrosoft.com nie ablaufen.

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
> Wenn das Kennwort nicht auf Nie ablaufen festgelegt ist, wird das Konto nicht mehr auf dem Gerät anmeldet, wenn das Konto den Ablaufzeitraum erreicht. Das Kennwort muss dann für das Konto geändert und auch lokal auf dem MTR-Gerät aktualisiert werden.

6. Das Gerätekonto muss über eine gültige Microsoft 365- oder Office 365-Lizenz verfügen, oder Exchange und Microsoft Teams oder Skype for Business funktionieren nicht. Wenn Sie über die Lizenz verfügen, müssen Sie Ihrem Gerätekonto einen Nutzungsspeicherort zuweisen – dies bestimmt, welche Lizenz-SKUs für Ihr Konto verfügbar sind. Sie können `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> so rufen Sie eine Liste der verfügbaren SKUs für Ihre Microsoft 365- oder Office 365-Organisation wie folgt ab:

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   Als Nächstes können Sie eine Lizenz hinzufügen, indem Sie `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. In diesem Beispiel wird dem Konto die Lizenz für den Besprechungsraum hinzufügt:

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   Ausführliche Anweisungen finden Sie unter Zuweisen von Lizenzen [zu Benutzerkonten mit Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

   Sie können diesem Konto auch Telefonsystemfunktionen hinzufügen, müssen es aber zuerst konfigurieren. Weitere Informationen finden Sie unter Was ist [Telefonsystem?](../what-is-phone-system-in-office-365.md) In diesem Beispiel wird der Nationale und internationale Anrufplan des PSTNs addiert:

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. Als Nächstes müssen Sie das Gerätekonto mit Skype for Business aktivieren. Stellen Sie sicher, dass Ihre Umgebung die anforderungen erfüllt, die in [den Microsoft Teams Rooms-Anforderungen definiert sind.](requirements.md)

   Starten Sie eine [Remotesitzung Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) wie folgt (installieren Sie [unbedingt Skype for Business Online PowerShell-Komponenten):](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
>
> Wenn Sie die neueste öffentliche Version von [Teams PowerShell verwenden,](https://www.powershellgallery.com/packages/MicrosoftTeams/)müssen Sie den Skype for Business Online Connector nicht installieren.

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto ab, das eingerichtet wird, wie in diesem Beispiel gezeigt:

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   Aktivieren Sie als Nächstes Ihr Microsoft Teams Rooms-Konto für Skype for Business Server, indem Sie das folgende Cmdlet ausführen:

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > Neue Benutzerkonten werden möglicherweise nicht im gleichen Registrierungsstellenpool wie vorhandene Benutzerkonten im Mandanten erstellt. Der oben aufgeführte Befehl verhindert aufgrund dieser Situation Fehler bei der Kontoeinrichtung.

## <a name="validate"></a>Überprüfen

Zur Überprüfung sollten Sie jeden Skype for Business-Client verwenden können, um sich bei dem konto anmelden, das Sie erstellt haben.

## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft Teams Rooms](rooms-configure-accounts.md)

[Plan für Microsoft Teams-Räume](rooms-plan.md)

[Bereitstellen von Microsoft Teams-Räume](rooms-deploy.md)

[Konfigurieren einer Konsole für Microsoft Teams-Räume](console.md)

[Microsoft Teams-Räume verwalten](rooms-manage.md)

[Lizenzierung von Microsoft Teams-Räumen](rooms-licensing.md)
