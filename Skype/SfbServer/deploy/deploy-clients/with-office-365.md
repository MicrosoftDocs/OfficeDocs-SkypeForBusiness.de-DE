---
title: Bereitstellen von Skype Room Systems v2 mit Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lesen Sie dieses Thema bietet Informationen zum Skype Raum Systemen v2 mit Office 365 bereitstellen.
ms.openlocfilehash: ac6cbd53f16fb9fe07e24ef288eddbc5acca1b00
ms.sourcegitcommit: 5e094591704e27d9d802ff86c1ada6d775ab783a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>Bereitstellen von Skype Room Systems v2 mit Office 365 
 
Lesen Sie dieses Thema bietet Informationen zum Skype Raum Systemen v2 mit Office 365 bereitstellen.
  
In diesem Thema wird beschrieben, wie ein Gerät Konto für Skype Raum Systemen v2 hinzufügen, wenn Sie eine Office 365-online-Bereitstellung verfügen.
  
## <a name="deploy-skype-room-systems-v2-with-office-365"></a>Bereitstellen von Skype Room Systems v2 mit Office 365 

Bevor Sie Skype Raum Systemen v2 mit Office 365 bereitstellen, müssen Sie unbedingt, dass Sie die Anforderungen erfüllt sind. Weitere Informationen finden Sie unter [Skype Raum Systemen v2 Requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Um Skype für Unternehmen zu aktivieren, müssen Sie über Folgendes verfügen:
  
- Skype für Business Online (Plan 2) oder höher in Ihrem Office 365-Plan. Der Plan muss die Konferenzfunktion unterstützen.
    
- Wenn Sie Enterprise-VoIP (PSTN-Telefonie) benötigen benötigen Telefoniedienstanbieter für Skype Raum Systemen v2 verwenden Sie Skype für Business Online (Plan 3).
    
- Die Mandanten-Benutzer müssen Exchange-Postfächer haben.
    
- Ihr Skype Raum Systemen v2 Konto erfordert einen Skype für Business Online (Plan 2) oder Skype für Business Online (Plan 3)-Lizenz, aber keine Exchange Online-Lizenz erforderlich.
    
### <a name="add-a-device-account"></a>Hinzufügen eines Gerätekontos

1. Starten Sie eine remote Windows PowerShell-Sitzung auf einem PC und eine Verbindung mit Exchange herstellen. Vergewissern Sie sich, dass die richtigen Berechtigungen zum Ausführen der zugehörigen Cmdlets festgelegt sind. Es folgen einige Beispiele für Cmdlets, die in Ihrer Umgebung verwendet und geändert werden können.
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential 
   $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. Nach dem Einrichten einer Sitzung, werden Sie entweder ein neues Postfach erstellen und als eine RoomMailboxAccount zu aktivieren oder Ändern der Einstellungen für ein vorhandenes Raumpostfach. Dadurch wird das Konto zum Skype Raum Systemen v2 authentifizieren.
    
  Wenn Sie ein vorhandenes Ressourcenpostfach ändern:
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

  Wenn Sie eine neue Ressourcenpostfach erstellen:
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 
-Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. Sie müssen verschiedene Exchange-Eigenschaften für das Gerätekonto festlegen, um die Besprechungsumgebung zu verbessern. Im Abschnitt zu den Exchange-Eigenschaften sehen Sie, welche Eigenschaften Sie festlegen müssen.
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
   -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

   ```

4. Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure Active Directory herstellen. Führen Sie das folgende Cmdlet aus, um die Verbindung mit Azure AD herzustellen:
    
   ```
   Connect-MsolService -Credential $cred
   ```

5. 	Wenn das Kennwort nicht ablaufen soll, führen Sie das Cmdlet „Set-MsolUser“ mit der Option „PasswordNeverExpires“ wie folgt aus:   
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
   ```

   Sie können auch wie folgt eine Telefonnummer für den Raum festlegen:
    
   ```
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

6. Das Gerät Konto muss eine gültige Office 365-Lizenz verfügen, oder Exchange und Skype für Unternehmen funktionieren nicht. Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen. Get-MsolAccountSku können Sie wie folgt eine Liste der verfügbaren SKUs für Ihre Office 365-Mandanten abzurufen:
    
   ```
   Get-MsolAccountSku
   ```

   Als Nächstes können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).
    
   ```
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

7. Als Nächstes müssen Sie das Gerät Konto mit Skype für Unternehmen zu aktivieren. Stellen Sie sicher, dass Ihre Umgebung die definierten in [Skype Raum Systemen v2 Anforderungen](../../plan-your-deployment/clients-and-devices/requirements.md)erfüllt.
    
   Starten Sie wie folgt eine remote Windows PowerShell-Sitzung (unbedingt Skype für Business Online-PowerShell-Komponenten zu installieren):
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   Aktivieren Sie im nächsten Schritt Ihr Skype Raum Systemen v2-Konto für Skype für Business Server durch Ausführen des folgenden Cmdlets:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   Rufen Sie die RegistrarPool-Informationen aus dem neuen Benutzerkonto-Setup wird, wie im folgenden Beispiel dargestellt:
    
    ```
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > Neue Benutzerkonten möglicherweise nicht im gleichen Registrar-Pool als vorhandenen Benutzerkonten in den Mandanten erstellt werden. Der vorangehenden Befehl wird verhindert, dass Fehler in kontoeinrichtung aufgrund dieser Situation. 
  
Nachdem Sie die vorhergehenden Schritte zum Aktivieren der Erstellung Ihres Kontos Skype Raum Systemen v2 im Skype für Business Online abgeschlossen haben, müssen Sie Skype Raum Systemen v2 Gerät eine Lizenz zuweisen. Verwenden das administrative Office 365-Portal, weisen Sie entweder einen Skype für Business Online (Plan 2) oder eine Skype für Business Online (Plan 3)-Lizenz auf das Gerät.
  
### <a name="assign-a-license-to-your-account"></a>Zuweisen einer Lizenz zu Ihrem Konto

1. Anmeldung als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.
    
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
    
3. Wählen Sie das Konto Skype Raum Systemen v2, und klicken Sie auf, oder tippen Sie auf das Stiftsymbol, das Möglichkeit zu bearbeiten.
    
4. Klicken Sie auf die Option **Lizenzen**.
    
5. Klicken Sie im Abschnitt **Lizenzen zuweisen** müssen Sie Skype für Business Online (Plan 2) oder Skype auswählen, für Business Online (Plan 3), je nach Ihrer Lizenzierung und was Sie entschieden haben, im Hinblick auf Enterprise-VoIP benötigen. Sie müssen eine Lizenz planen 3 verwenden, wenn Sie auf Skype Raum Systemen v2 Cloud Nebenstellenanlage verwenden möchten. Minimal benötigen Sie CloudPBX für VoIP-Konnektivität. Konfigurieren Sie anschließend Hybrid-VoIP oder PSTN-Basis für die PSTN-Konnektivität-Methode aufrufen.
    
6. Klicken Sie auf **Speichern**, um die Aufgabe abzuschließen.
    
## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>Beispiel: Raum setup im Exchange Online und Skype für Business Online

```
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com
 -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true
 -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
 
Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept 
-AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
$false -DeleteSubject $false -RemovePrivateProperty $false
 
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true 
-AdditionalResponse "This is a Rigel room!"
 
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
 
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
 
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress

```

> [!NOTE]
> Dadurch werden CloudPBX und PSTNCallingDomesticAndInternational hinzugefügt. Zudem müssen Sie mit der Verwaltungsschnittstelle eine Telefonnummer zuweisen. 
  
## <a name="see-also"></a>Siehe auch

#### 

[Planen von Skype Raum Systemen v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Bereitstellen von Skype Raum Systemen v2](room-systems-v2.md)
  
[Konfigurieren einer Skype Raum Systemen v2-Konsole](console.md)
  
[Verwalten von Skype Raum Systemen v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

