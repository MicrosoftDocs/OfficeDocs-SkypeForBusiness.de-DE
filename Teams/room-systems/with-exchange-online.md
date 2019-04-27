---
title: Bereitstellen von Microsoft-Teams, Räume mit Exchange Online
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms mit Exchange Online.
ms.openlocfilehash: 1dc4e73fea7376033d8914cd1814e1edeb68e7d5
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362843"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>Bereitstellen von Microsoft-Teams, Räume mit Exchange Online

Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms mit Exchange Online und Skype für Business Server lokal.
  
Wenn Ihre Organisation eine Kombination von Diensten, mit einigen an lokalen und online gehostet gehostet hat, wird die Konfiguration abhängen, wo jeden Dienst gehostet wird. In diesem Thema werden die hybridbereitstellungen für Microsoft-Teams Chatrooms mit Exchange online gehostet. Da so viele verschiedene Variationen bei dieser Art von Bereitstellung vorhanden sind, ist nicht möglich, detaillierte Informationen für alle bereitzustellen. Der folgende Prozess wird für viele Konfigurationen verwendet werden. Wenn der Vorgang nicht für die Installation die richtige ist, wird empfohlen, dass Sie Windows PowerShell verwenden, um das gleiche Endergebnis zu erzielen, wie hier und für andere Bereitstellungsoptionen dokumentiert.

Die einfachste Möglichkeit zum Einrichten von Benutzerkonten ist von remote Windows PowerShell konfigurieren. Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Microsoft Teams Räume-Benutzerkonten aktivieren überprüfen helfen. Auf Wunsch können Sie die Schritte unten, um das Konfigurieren von Konten, mit Ihrem Microsoft-Teams Chatrooms Gerät.

## <a name="requirements"></a>Voraussetzungen

Vor der Bereitstellung von Microsoft-Teams Chatrooms mit Exchange Online, achten Sie darauf, dass Sie die Anforderungen erfüllt sind. Weitere Informationen finden Sie unter [Microsoft Teams Chatrooms Requirements](requirements.md).
  
Führen Sie die folgenden Schritte aus, für die Bereitstellung von Microsoft-Teams Chatrooms mit Exchange Online. Vergewissern Sie sich, dass Sie über die erforderlichen Berechtigungen zum Ausführen der zugehörigen Cmdlets verfügen.
  
### <a name="create-an-account-and-set-exchange-properties"></a>Erstellen eines Kontos und Festlegen der Exchange-Eigenschaften

1. Starten Sie eine remote Windows PowerShell-Sitzung auf einem PC und eine Verbindung mit Exchange Online wie folgt:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach. Dadurch wird das Konto in Microsoft Teams Räume zu authentifizieren.

   Wenn Sie ein vorhandenes Ressourcenpostfach ändern:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    Wenn Sie eine neue Ressourcenpostfach erstellen:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Um der Besprechung zu optimieren, benötigen Sie die Exchange-Eigenschaften für das Benutzerkonto wie folgt festgelegt:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>Hinzufügen einer E-Mail-Adresse für Ihr lokales Domänenkonto

1. In **Active Directory-Benutzer und-Computer AD** -Tool mit der rechten Maustaste auf den Container oder Organisationseinheit, dass Ihre Microsoft Teams Räume-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.
2. Geben Sie den Anzeigenamen (-Identity) aus dem vorherigen Cmdlet (Set-Mailbox oder New-Mailbox) in das Feld **Vollständiger Name** und der Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Auswählen von **Kennwort läuft nie ab** ist eine Voraussetzung für Skype für Business Server auf Microsoft Teams Chatrooms. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Fall müssen Sie eine Ausnahme für jedes Benutzerkonto Microsoft Teams Chatrooms zu erstellen.
  
4. Klicken Sie auf **Fertig stellen**, um das Konto zu erstellen.
5. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wechseln Sie nach Abschluss der Synchronisierung zur Benutzerseite, und vergewissern Sie sich, dass die beiden in den vorherigen Schritten erstellten Konten zusammengeführt wurden.

### <a name="assign-an-office-365-license"></a>Zuweisen einer Office 365-Lizenz

1. Schließen Sie zuerst Azure AD einige kontoeinstellungen anwenden. Sie können dieses Cmdlet ausführen, um die Verbindung herzustellen.

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. Das Benutzerkonto muss eine gültige Office 365-Lizenz, um sicherzustellen, dass Exchange und Skype für Business Server funktioniert haben. Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort Ihres Benutzerkontos zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen. Die Zuordnung stellen Sie in einem der folgenden Schritt.
3. Im nächsten Schritt verwenden.`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> zum Abrufen einer Liste der verfügbaren SKUs für Office 365-Mandanten.
4. Nachdem Sie sich die SKUs anbieten, können Sie hinzufügen, eine Lizenz mit der`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> Cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“). 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>Aktivieren des Benutzerkontos mit Skype für Business Server

1. Erstellen Sie eine Windows PowerShell-Remotesitzung von einem PC wie folgt:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. Führen Sie diesen Befehl, um Ihr Konto Microsoft Teams Chatrooms für Skype für Business Server zu aktivieren:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    Wenn Sie nicht genau wissen, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet wird, können Sie den Wert aus einer vorhandenen Skype für Business Server-Benutzer, die mit diesem Befehl abrufen.

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>Weisen Sie Ihr Konto Microsoft Teams Chatrooms einen Skype für Business Server-Lizenz

1. Melden Sie sich als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie auf der Microsoft-Teams Räume-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Lizenz planen 3 verwenden, falls Sie Enterprise-VoIP auf Microsoft Teams Chatrooms verwenden möchten.
6. Klicken Sie auf **Speichern**.

Für die Validierung sollten Sie alle Skype für Business-Client verwenden Sie dieses Konto anzumelden sein.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft-Teams Räume](room-systems-v2-configure-accounts.md)

[Planen der Microsoft-Teams, Räume](skype-room-systems-v2-0.md)
  
[Bereitstellen von Microsoft-Teams, Räume](room-systems-v2.md)
  
[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
