---
title: Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: Lesen Sie dieses Thema bietet Informationen zum Bereitstellen von Skype Raum Systemen v2 in einer hybridumgebung mit Exchange lokal.
ms.openlocfilehash: 49e0b85cc38de91ed269ca103ef995507a6d1e37
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699360"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung
 
Lesen Sie dieses Thema bietet Informationen zur Bereitstellung von Skype Raum Systemen v2 in einer hybridumgebung mit Exchange lokal und Skype für Business Online.
  
Wenn Ihre Organisation eine Kombination von Diensten, mit einigen an lokalen und online gehostet gehostet hat, wird die Konfiguration abhängen, wo jeden Dienst gehostet wird. In diesem Thema werden für Skype Raum Systemen v2 hybridbereitstellungen mit Exchange lokal gehostet. Da so viele verschiedene Variationen bei dieser Art von Bereitstellung vorhanden sind, ist nicht möglich, detaillierte Informationen für alle bereitzustellen. Der folgende Prozess wird für viele Konfigurationen verwendet werden. Wenn der Vorgang nicht für die Installation die richtige ist, wird empfohlen, dass Sie Windows PowerShell verwenden, um das gleiche Endergebnis zu erzielen, wie hier und für andere Bereitstellungsoptionen dokumentiert. 

Microsoft bietet [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), eines Skripts, das neue Benutzerkonten erstellen oder vorhandene Ressourcenkonten, mit denen Sie damit können Sie diese in kompatibel Skype Raum Systemen v2-Benutzerkonten aktivieren überprüfen helfen. Auf Wunsch können Sie die Schritte unten, um Geräts v2 Skype Raum Systemen verwendeten Konten zu konfigurieren.
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>Bereitstellen von Skype Room Systems v2 mit lokaler Exchange-Bereitstellung

Bevor Sie Skype Raum Systemen v2 mit Exchange lokal bereitstellen, achten Sie darauf, dass Sie die Anforderungen erfüllt sind. Weitere Informationen finden Sie unter [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).
  
Wenn Sie Skype Raum Systemen v2 mit Exchange lokal bereitstellen, werden Sie Active Directory-Verwaltungstools verwenden, um eine e-Mail-Adresse für Ihr Konto der lokalen Domäne hinzufügen. Dieses Konto wird mit Office 365 synchronisiert werden. Sie müssen die folgenden Schritte ausführen:
  
- Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.
    
- Aktivieren Sie das Remotepostfach, und legen Sie Eigenschaften fest.
    
- Zuweisen einer Office 365-Lizenzvertrags.
    
- Aktivieren Sie das Gerät Konto mit Skype für Business Server. Für die Aktivierung des Gerätekontos muss Ihre Umgebung die folgenden Voraussetzungen erfüllen:
    
  - Sie müssen Ihre Office 365-Plan Skype für Business Online (Plan 2) oder höher sein. Der Plan muss die Konferenzfunktion unterstützen.
    
  - Wenn Sie Enterprise-VoIP (PSTN-Telefonie) benötigen benötigen Telefoniedienstanbieter für Skype Raum Systemen v2 verwenden Sie Skype für Business Online (Plan 3).
    
  - Die Mandanten-Benutzer müssen Exchange-Postfächer haben.
    
  - Ihr Skype Raum Systemen v2 Konto erfordert einen Skype für Business Online (Plan 2) oder Skype für Business Online (Plan 3)-Lizenz, aber keine Exchange Online-Lizenz erforderlich.
    
- Ihr Skype Raum Systemen v2 Konto einen Skype für Business Server-Lizenz zuweisen.
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>Erstellen Sie ein Konto, und synchronisieren Sie es mit Active Directory.

1. Im **Active Directory-Benutzer und-Computer AD** -Tool mit der rechten Maustaste auf den Ordner oder die Organisationseinheit, dass die Skype Raum Systeme v2-Konten erstellt werden, klicken Sie auf **neu**, und klicken Sie dann auf **Benutzer**.
    
2. Geben Sie den Anzeigenamen aus dem vorherigen Cmdlet in das Feld **Vollständiger Name** und den Alias in das Feld **Benutzeranmeldename** ein. Klicken Sie auf **Weiter**.
    
3. Geben Sie das Kennwort für dieses Konto ein. Sie müssen das Kennwort zur Bestätigung erneut eingeben. Stellen Sie sicher, dass als einzige Option das Kontrollkästchen **Kennwort läuft nie ab** aktiviert ist.
    
    > [!NOTE]
    > Auswählen von **Kennwort läuft nie ab** ist eine Voraussetzung für Skype für Business Server auf Skype Raum Systemen v2. Möglicherweise verhindern Ihre Domänenregeln nicht ablaufende Kennwörter. In diesem Fall müssen Sie eine Ausnahme für jedes Skype Raum Systemen v2 Gerät Konto erstellen.
  
4. Führen Sie nach der Erstellung des Kontos eine Verzeichnissynchronisierung aus. Wenn es abgeschlossen ist, wechseln Sie zu der Benutzerseite in Ihrer Office 365 Administrationscenter, und stellen Sie sicher, dass das Konto in den vorherigen Schritten erstellten online zu zusammengeführt wurde.
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>Aktivieren des Remotepostfachs und Festlegen von Eigenschaften

1. Aktivieren Sie das Remotepostfach, indem Ihre lokale Exchange-Verwaltungsshell mit Administratorberechtigungen öffnen, und führen Sie den folgenden Befehl aus:
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. Eine remote Windows PowerShell-Sitzung starten und eine Verbindung mit Microsoft Exchange. Führen Sie von Ihrem Office 365-Mandanten die folgenden Befehle ein:
    
   ```
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess = New-PSSession -ConfigurationName Microsoft.Exchange -Credential $cred -AllowRedirection -Authentication Basic -ConnectionUri "https://<ExchangeServerFQDN>/PowerShell"
   Import-PSSession $sess
   ```

3. Um der Besprechung zu optimieren, benötigen Sie die Exchange-Eigenschaften für das Gerät-Konto wie folgt festgelegt:
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    Weitere Informationen über welche Eigenschaften Sie festlegen müssen, finden Sie unter Exchange-Eigenschaften.
    
4. Zum Anwenden einiger Kontoeinstellungen müssen Sie eine Verbindung mit Azure AD herstellen. Sie können diesen Befehl ausführen, um die Verbindung herzustellen:
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>Zuweisen einer Office 365-Lizenz

1. Das Gerät Konto muss eine gültige Office 365-Lizenz, um sicherzustellen, dass Exchange und Skype für Business Server funktioniert haben. Wenn Sie die Lizenz haben, müssen Sie einen Verwendungsspeicherort mit Ihrem Konto Gerät zuweisen – diese Einstellung bestimmt, was Lizenz-SKUs für Ihr Konto zur Verfügung stehen.
    
2. Im nächsten Schritt verwenden Sie Get-MsolAccountSku, um eine Liste der verfügbaren SKUs für Office 365-Mandanten abzurufen.
    
3. Wenn Sie die SKUs aufgelistet haben, können Sie mit dem Cmdlet „Set-MsolUserLicense“ eine Lizenz hinzufügen. In diesem Fall entspricht „$strLicense“ dem angezeigten SKU-Code (zum Beispiel „contoso:STANDARDPACK“).
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>Aktivieren des Gerätekontos in Skype for Business

1. Erstellen Sie eine Windows PowerShell-Remotesitzung von einem PC wie folgt:
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Führen Sie diesen Befehl, um Ihr Skype Raum Systemen v2-Konto für Skype für Business Server zu aktivieren:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   Wenn Sie nicht genau wissen, welcher Wert für den Parameter RegistrarPool in Ihrer Umgebung verwendet wird, können Sie den Wert aus einer vorhandenen Skype für Business Server-Benutzer, die mit diesem Befehl abrufen.
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>Zuweisen einer Skype for Business-Lizenz zu Ihrem Skype Room Systems v2-Konto

1. Melden Sie sich als mandantenadministrator an, öffnen Sie die administrativen Office 365-Portal, und klicken Sie auf die Admin-app.
    
2. Klicken Sie auf **Benutzer und Gruppen** und dann auf **Benutzer hinzufügen, Kennwörter zurücksetzen und mehr**.
    
3. Klicken Sie auf das Konto Skype Raum Systemen v2, und klicken Sie dann auf das Stiftsymbol, um die Kontoinformationen zu bearbeiten.
    
4. Klicken Sie auf **Lizenzen**.
    
5. Wählen Sie in **Lizenzen zuweisen** abhängig von Ihren Anforderungen für Lizenzen und für Enterprise-VoIP entweder Skype for Business (Plan 2) oder Skype for Business (Plan 3) aus. Sie müssen eine Lizenz planen 3 verwenden, falls Sie Enterprise-VoIP für Ihre Skype Raum Systemen v2 verwenden möchten.
    
6. Klicken Sie auf **Speichern**.
    
Für die Validierung sollten Sie alle Skype für Business-Client verwenden Sie dieses Konto anzumelden sein.
  
## <a name="see-also"></a>Siehe auch

[Konfigurieren von Konten für Skype Raum Systemen v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Bereitstellen von Skype Room Systems v2](room-systems-v2.md)
  
[Konfigurieren einer Konsole für Skype Room Systems v2](console.md)
  
[Verwalten von Skype Room Systems v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

