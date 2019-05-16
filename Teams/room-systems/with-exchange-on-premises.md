---
title: Bereitstellen von Microsoft Teams-Raum mit Exchange vor Ort
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms in einer hybridumgebung mit Exchange lokal.
ms.openlocfilehash: 7ab9a582e26db15159677343d9edddd6bd9c45f9
ms.sourcegitcommit: 751035e1d35fc79a6b74955d7c6c46ecea0645e5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2019
ms.locfileid: "34082722"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Bereitstellen von Microsoft Teams-Raum mit Exchange vor Ort

Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Microsoft-Teams Chatrooms in einer hybridumgebung mit Exchange auf lokale und Microsoft-Teams oder Skype für Business Online.
  
Wenn Ihre Organisation eine Kombination von Diensten, mit einigen an lokalen und online gehostet gehostet hat, wird die Konfiguration abhängen, wo jeden Dienst gehostet wird. In diesem Thema werden die hybridbereitstellungen für Microsoft-Teams Chatrooms mit Exchange lokal gehostet. Da so viele verschiedene Variationen bei dieser Art von Bereitstellung vorhanden sind, ist nicht möglich, detaillierte Informationen für alle bereitzustellen. Der folgende Prozess wird für viele Konfigurationen verwendet werden. Wenn der Vorgang nicht für die Installation die richtige ist, wird empfohlen, dass Sie Windows PowerShell verwenden, um das gleiche Endergebnis zu erzielen, wie hier und für andere Bereitstellungsoptionen dokumentiert.

Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Microsoft Teams Räume-Benutzerkonten aktivieren überprüfen helfen. Auf Wunsch können Sie die Schritte unten, um das Konfigurieren von Konten, mit Ihrem Microsoft-Teams Chatrooms Gerät.
  
## <a name="requirements"></a>Voraussetzungen

Vor der Bereitstellung von Microsoft-Teams Chatrooms mit Exchange lokal, achten Sie darauf, dass Sie die Anforderungen erfüllt sind. Weitere Informationen finden Sie unter [Microsoft Teams Chatrooms Requirements](requirements.md).
  
Wenn Sie Microsoft-Teams Chatrooms mit Exchange lokal bereitgestellt werden, werden Sie Active Directory-Verwaltungstools verwenden, um eine e-Mail-Adresse für Ihr Konto der lokalen Domäne hinzufügen. Dieses Konto wird mit Office 365 synchronisiert werden. Sie müssen die folgenden Schritte ausführen:
  
- Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

- Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.

- Zuweisen einer Office 365-Lizenzvertrags.

- Aktivieren Sie das Gerät Konto mit Skype für Business Server. Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:

  - Sie müssen Ihre Office 365-Plan Skype für Business Online (Plan 2) oder höher sein. Der Plan muss die Konferenzfunktion unterstützen.
  
  - - Wenn Sie Enterprise-VoIP (PSTN-Telefonie) benötigen benötigen Telefoniedienstanbieter für Microsoft-Teams Chatrooms verwenden Sie Skype für Business Online (Plan 3).
  
  - - Die Mandanten-Benutzer müssen Exchange-Postfächer haben.
  
  - - Ihr Microsoft-Teams Chatrooms Konto erfordert einen Skype für Business Online (Plan 2) oder Skype für Business Online (Plan 3)-Lizenz, aber keine Exchange Online-Lizenz erforderlich.

- Weisen Sie Ihr Konto Microsoft Teams Chatrooms einen Skype für Business Server-Lizenz.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

1. Klicken Sie im Tool **Active Directory-Benutzer und-Computer** mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, dass Ihre Microsoft Teams Räume-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.

2. Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.

3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.

    > [!NOTE]
    > Auswählen von **Kennwort läuft nie ab** ist eine Voraussetzung für Skype für Business Server auf Microsoft Teams Chatrooms. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Fall müssen Sie eine Ausnahme für jedes Microsoft Teams Chatrooms Gerät Konto erstellen.
  
4. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wenn es abgeschlossen ist, wechseln Sie zu der Benutzerseite in Ihrer Microsoft 365 Administrationscenter, und stellen Sie sicher, dass das Konto in den vorherigen Schritten erstellten online zu zusammengeführt wurde.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. [Öffnen Sie die Exchange-Verwaltungsshell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) oder [eine Verbindung mit Exchange-Server mit remote-PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

2. Erstellen Sie ein Postfach für das Konto (postfachaktivierung das Konto) in Exchange PowerShell mithilfe des folgenden Befehls:

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   Informationen zur Syntax und Parametern finden Sie unter [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).

3. Konfigurieren Sie die folgenden Einstellungen in der Exchange PowerShell klicken Sie auf das Raumpostfach, um die Besprechung zu verbessern:

   - AutomateProcessing: AutoAccept (Besprechungsorganisatoren empfangen die Raum Reservierung Entscheidung direkt und ohne Eingreifen: freien = akzeptieren; gebucht = ablehnen.)

   - AddOrganizerToSubject: $false (Organisator der Besprechung wird nicht auf den Betreff der Besprechungsanfrage hinzugefügt.)

   - DeleteComments: $false (beibehalten im Textkörper Nachricht eingehender Besprechungsanfragen.)

   - DeleteSubject: $false (Keep den Betreff der eingehenden Besprechungsanfragen).

   - RemovePrivateProperty: $false (stellt sicher das Flag ' Privat ', die vom Organisator Besprechung in der ursprünglichen Besprechung gesendet wurde anfordern bleibt wie angegeben).

   - AddAdditionalResponse: $true (der Text, durch den Parameter AdditionalResponse angegeben wird auf Besprechungsanfragen hinzugefügt.)

   - AdditionalResponse: "Dies ist eine Skype Besprechungsraum!" (Der zusätzliche Text, der auf die Besprechungsanfrage hinzugefügt.)

   In diesem Beispiel wird konfiguriert diese Einstellungen für das Raumpostfach mit dem Namen Project-Rigel-01.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   Informationen zur Syntax und Parametern finden Sie unter [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).

### <a name="assign-an-office-365-license"></a>Zuweisen einer Office 365-Lizenz

1. Verbinden Sie mit Azure Active Directory. Ausführliche Informationen zu Active Directory finden Sie unter [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0). 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) wird nicht unterstützt. 

2. Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Microsoft-Teams, funktionieren nicht. Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen. Sie können`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> Um eine Liste der verfügbaren SKUs abzurufen.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. Sie können im nächsten Schritt fügen Sie eine Lizenz using der`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> Cmdlet. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   Weitere Informationen finden Sie unter [Zuweisen von Lizenzen, um die Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="enable-the-device-account"></a>Aktivieren Sie das Gerät-Konto

Skype für Business Online PowerShell wird verwendet, um die Dienste für Microsoft-Teams und Skype für Business Online zu verwalten.

1. Erstellen Sie eine Windows PowerShell-Remotesitzung von einem PC wie folgt:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Um Ihr Konto Microsoft Teams Räume zu aktivieren, führen Sie diesen Befehl aus:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Wenn Sie nicht genau wissen, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet wird, können Sie den Wert aus einen vorhandenen Benutzer mit diesem Befehl abrufen:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Weisen Sie eine Lizenz mit Ihrem Microsoft-Teams Räume-Konto

1. Melden Sie sich als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
3. Klicken Sie auf der Microsoft-Teams Räume-Konto, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
4. Klicken Sie auf **Lizenzen**.
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Lizenz planen 3 verwenden, falls Sie Enterprise-VoIP auf Ihrem Microsoft-Teams Chatrooms verwenden möchten.
6. Klicken Sie auf **Speichern**.

Für die Validierung sollten Sie alle Clients verwenden Sie dieses Konto anzumelden sein.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Microsoft-Teams Räume](room-systems-v2-configure-accounts.md)

[Planen der Microsoft-Teams, Räume](skype-room-systems-v2-0.md)
  
[Bereitstellen von Microsoft-Teams, Räume](room-systems-v2.md)
  
[Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md)
  
[Microsoft Teams Rooms verwalten](skype-room-systems-v2.md)
