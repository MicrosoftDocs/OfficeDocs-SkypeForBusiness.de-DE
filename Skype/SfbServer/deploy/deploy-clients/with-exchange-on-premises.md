---
title: Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung (Hybrid)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: In diesem Thema erfahren Sie, wie Sie  in einer Hybridumgebung mit einer lokalen -Bereitstellung bereitstellen.
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a>Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung (Hybrid)
 
In diesem Thema erfahren Sie, wie Sie  in einer Hybridumgebung mit einer lokalen -Bereitstellung bereitstellen.
  
If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted. This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises. Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them. The following process will work for many configurations. If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options. You should then use the provided Windows PowerShell script to verify your Skype Room Systems v2 setup. (See Account Verification Script.)
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung

Vergewissern Sie sich vor der Bereitstellung von  mit lokaler -Bereitstellung, dass die Anforderungen erfüllt sind. For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Wenn Sie  mit lokaler -Bereitstellung bereitstellen, fügen Sie mit den Active Directory-Verwaltungstools eine E-Mail-Adresse für Ihr lokales Domänenkonto hinzu. Dieses Konto wird mit  synchronisiert. Sie müssen die folgenden Schritte ausführen:
  
- Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.
    
- Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.
    
- Zuweisen einer Office 365-Lizenz
    
- Aktivieren des Gerätekontos in Skype for Business Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:
    
  - You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan. Der Plan muss die Konferenzfunktion unterstützen.
    
  - If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).
    
  - Ihre Mandantenbenutzer müssen über -Postfächer verfügen.
    
  - Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.
    
- Zuweisen einer Skype for Business Server 2015-Lizenz zu Ihrem Skype Room Systems v2-Konto
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

1. Klicken Sie im Tool Active Directory-Benutzer und -Computer mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, in der Ihre -Konten erstellt werden sollen. Klicken Sie auf Neu und dann auf Benutzer.
    
2. Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.
    
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.
    
    > [!NOTE]
    > Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Fall müssen Sie für jedes einzelne -Gerätekonto eine Ausnahme erstellen.
  
4. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wechseln Sie nach Abschluss der Synchronisierung zur Benutzerseite im  Admin Center, und vergewissern Sie sich, dass das in den vorherigen Schritten erstellte Konto mit der Onlineversion zusammengeführt wurde.
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. Aktivieren Sie das Remotepostfach, indem Sie Ihre lokale -Verwaltungsshell mit Administratorberechtigungen öffnen und folgenden Befehl ausführen:
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. Start a remote Windows PowerShell session and connect to Microsoft Exchange. Führen Sie auf Ihrem -Mandanten die folgenden Befehle aus:
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. Um die Besprechungsumgebung zu verbessern, müssen Sie die -Eigenschaften für das Gerätekonto wie folgt festlegen:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    Weitere Informationen zu den Eigenschaften, die Sie festlegen müssen, finden Sie unter „-Eigenschaften“.
    
4. Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure AD herstellen. Sie können diesen Befehl ausführen, um die Verbindung herzustellen:
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>Zuweisen einer Office 365-Lizenz

1. The device account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work. Das Gerätekonto muss über eine gültige -Lizenz verfügen, damit  und  funktionieren. Wenn Sie die Lizenz haben, müssen Sie dem Gerätekonto einen Verwendungsstandort zuweisen. Von diesem hängt ab, welche Lizenz-SKUs für Ihr Konto verfügbar sind.
    
2. Rufen Sie als Nächstes mit „Get-MsolAccountSku“ eine Liste der verfügbaren SKUs für Ihren -Mandanten ab.
    
3. Wenn Sie die SKUs aufgelistet haben, können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>Aktivieren des Gerätekontos in Skype for Business

1. Erstellen Sie wie folgt auf einem PC eine -Remotesitzung:
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Wenn Sie nicht sicher sind, welchen Wert Sie für den Parameter „RegistrarPool“ in Ihrer Umgebung verwenden sollen, können Sie mit dem folgenden Befehl den Wert eines vorhandenen -Benutzers abrufen:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Zuweisen einer Skype for Business-Lizenz zu Ihrem Skype Room Systems v2-Konto

1. Melden Sie sich als Mandantenadministrator an, öffnen Sie das -Verwaltungsportal, und klicken Sie auf die Verwaltungs-App.
    
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
    
3. Klicken Sie auf das -Konto und dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
    
4. Klicken Sie auf **Lizenzen**.
    
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Wenn Sie Enterprise-VoIP mit  verwenden möchten, müssen Sie eine Plan 3-Lizenz verwenden.
    
6. Klicken Sie auf **Speichern**.
    
Zur Überprüfung können Sie sich mit einem beliebigen -Client bei diesem Konto anmelden.
  
## <a name="see-also"></a>Siehe auch

#### 

[Planung für Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Bereitstellen von Skype Room Systems v2](room-systems-v2.md)
  
[Konfigurieren einer Konsole für Skype Room Systems v2](console.md)
  
[Verwalten von Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

