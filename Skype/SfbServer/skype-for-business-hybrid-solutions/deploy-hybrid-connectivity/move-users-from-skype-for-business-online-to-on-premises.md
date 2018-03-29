---
title: Verschieben von Benutzern von Skype für Business Online auf lokal
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/19/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 55733bb5-6742-4daf-8db5-1c5df86f4cea
description: 'Zusammenfassung: Erfahren Sie, wie Benutzerkonten für Business Server lokal in Skype von online zu verschieben.'
ms.openlocfilehash: e429aebc6847146ad5bef2b34d6ccfa7d2997ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="move-users-from-skype-for-business-online-to-on-premises"></a>Verschieben von Benutzern von Skype für Business Online auf lokal
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Benutzerkonten für Business Server lokal in Skype von online zu verschieben.
  
Sie müssen möglicherweise Verschieben von Benutzerkonten von online zu lokal, um sicherzustellen, dass Benutzer online verwaltet und lokal untereinander sichtbar sind. Um untereinander erkannt werden, müssen alle Benutzer im lokalen Active Directory Anwesenheitsstatus haben. Weitere Informationen finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md). Sie sollten online Benutzer lokal, beispielsweise verschieben wenn: 
  
- Sie müssen neue Benutzer, die lokal erstellt und dann in der Cloud verschoben werden müssen.
    
- Ihrer Organisation bereitgestellt Skype für Business Online, bevor es Skype für Business Server bereitgestellt. Aus diesem Grund haben Benutzer, die zuerst in der Cloud erstellt wurden und an dieser Stelle müssen lokal in verschoben werden soll, bevor sie ans Skype für Business Online sind. 
    
In diesem Thema werden zwei Szenarien beschrieben:
  
- [Verschieben Sie Benutzer online – wurden, die ursprünglich online – zu lokale](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonline)
    
- [Verschieben Sie online Benutzer (die ursprünglich lokal wurden) in lokal](move-users-from-skype-for-business-online-to-on-premises.md#BKMK_originallyonprem)
    
## <a name="move-online-userswho-were-originally-onlineto-on-premises"></a>Verschieben Sie Benutzer online – wurden, die ursprünglich online – zu lokale
<a name="BKMK_originallyonline"> </a>

Dieser Abschnitt gilt nur für Benutzer, die erstellt und online aktiviert wurden, aber wer verfügen nicht über ein Konto in die lokale Active Directory. 
  
Bevor Sie beginnen, Online-Benutzer zu Ihrer lokalen Umgebung zu verschieben, überprüfen Sie, ob alle folgenden Punkte zutreffen:
  
- Ihre lokale Umgebung muss vollständig bereitgestellt und validiert. Weitere Informationen finden Sie unter [Bereitstellen von Lync Server 2013](http://technet.microsoft.com/library/b76795a4-4e71-4c70-a5c0-d1197fa8028c.aspx) oder [Bereitstellen von Skype für Business Server 2015](../../deploy/deploy.md), abhängig davon, welche Version Sie lokal verwenden. 
    
- Online-Mandanten muss für den Remotezugriff PowerShell konfiguriert werden.
    
    Dazu installieren Sie zunächst die Skype für Business Online Connector-Modul für Windows PowerShell, erhalten Sie hier: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
    
    Nachdem Sie das Modul installieren, können Sie eine Remotesitzung herstellen, indem Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell eingeben:
    
  ```
  Import-Module SkypeOnlineConnector
  ```

  ```
  $cred = Get-Credential
  ```

  ```
  $CSSession = New-CsOnlineSession -Credential $cred
  ```

  ```
  Import-PSSession $CSSession -AllowClobber
  ```

    Weitere Informationen dazu, wie Sie eine remote-PowerShell-Sitzung mit Skype für Business Online herstellen finden Sie unter [Connecting to Lync Online durch Verwenden von Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).
    
    Weitere Informationen zur Verwendung der Skype für Business Online Connector PowerShell-Modul finden Sie unter [Using Windows PowerShell zum Verwalten von Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
    
- Online-Mandanten muss für einen freigegebenen SIP-Adressraum konfiguriert werden. Zu diesem Zweck, starten Sie zuerst eine remote-Powershell-Sitzung mit Skype für Business Online. Führen Sie dann das folgende Cmdlet aus:
    
  ```
  Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
  ```

    > [!NOTE]
    > Das SharedSipAddressSpace-Attribut muss "True", bis verschieben in online abgeschlossen ist und keine Benutzer bleiben weiterhin lokal. 
  
Nachdem Sie diese Schritte abgeschlossen haben, können Sie Benutzerkonten migrieren, wie im folgenden Verfahren beschrieben:
  
### <a name="move-user-accounts-originally-enabled-online-to-an-on-premises-deployment"></a>Verschieben von Benutzerkonten, die ursprünglich online mit einer lokalen Bereitstellung aktiviert

1. Stellen Sie zuerst sicher, dass Ihre Organisation für die Hybridbereitstellung konfiguriert ist, einschließlich für Azure Active Directory-Verbindungs- und Synchronisierungstools. Weitere Informationen finden Sie unter [Planen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
  - Geben Sie in der lokalen Bereitstellung der Skype für Business Server-Verwaltungsshell die folgenden Cmdlets zum Erstellen der Hostinganbieter für Skype für Business Online. Für die Parameter Identität und Name können Sie jeden beliebigen Wert wählen.
    
  ```
  Set-CsAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $true
  ```

  ```
  New-CsHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
  ```

2. Vergewissern Sie sich, dass auf Ihrem lokalen Edge-Servern Sie die Zertifikatkette, die Verbindung mit Skype für Online Business ermöglicht haben wie in der folgenden Tabelle dargestellt. Sie können diese Kette hier herunterladen: [https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip](https://corp.sts.microsoft.com/Onboard/ADFS_Onboarding_Pack/corp_sts_certs.zip).
    
|**Zertifikat**|**Zertifikatspeicher**|
|:-----|:-----|
|Baltimore CyberTrust Root  <br/> |Vertrauenswürdige Stammzertifizierungsstelle  <br/> |
|Microsoft Internet Authority (Zertifikat einer neuen Zertifizierungsstelle)  <br/> |Zwischenzertifizierungsstelle  <br/> |
|MSIT Machine Auth CA2 (neue ausstellende CA2)  <br/> |Zwischenzertifizierungsstelle  <br/> |
   
3. Aktivieren Sie im lokalen Active Directory die betroffenen Benutzerkonten für Skype für Business Server 2015 lokal. Geben Sie dafür für einen einzelnen Benutzer das folgende Cmdlet ein: 
    
  ```
  Enable-CsUser
-Identity "username " 
-SipAddress "sip: username @contoso.com"
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

    Oder erstellen Sie ein Skript, das Benutzernamen aus einer Datei liest und sie als Eingabe für das Cmdlet „Enable-CsUser“ bereitstellt:
    
  ```
  Enable-CsUser
-Identity $Identity 
-SipAddress $SipAddress 
-HostingProviderProxyFqdn "sipfed.online.lync.com"
  ```

4. Synchronisieren Sie die online-Benutzer mit den aktualisierten lokalen Benutzern. Weitere Informationen finden Sie unter [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?LinkId=530320).
    
5. Aktualisieren Sie die folgenden DNS-Einträge, um alle SIP-Datenverkehr an Ihre lokale Bereitstellung leiten:
    
  - Aktualisieren Sie den Eintrag **lyncdiscover.contoso.com** so, dass er auf den FQDN des lokalen Reverseproxyservers verweist.
    
  - Update der ** *_sip* . _tls.contoso.com** SRV aufzeichnen, um die öffentliche IP-Adresse oder die VIP-Adresse des Zugriffs-edgedienst der lokalen Lync zu beheben.
    
  - Update der ** *_sipfederationtls* . _tcp.contoso.com** SRV aufzeichnen, um die öffentliche IP-Adresse oder die VIP-Adresse des Zugriffs-edgedienst von Skype zu beheben für Business Server 2015 lokale-.
    
  - Wenn Ihre Organisation verwendet DNS (manchmal als "Split-Brain-DNS" bezeichnet) geteilt, stellen Sie sicher, dass Benutzer, die zum Auflösen von Namen durch die internen DNS-Zone auf den Front-End-Pool weitergeleitet werden.
    
6. Typ der `Get-CsUser` Cmdlet einige Eigenschaften über die Benutzer überprüfen, die verschoben werden können. Sie sollten sicherstellen, dass HostingProviderProxyFQDN auf `"sipfed.online.lync.com"` festgelegt ist und die SIP-Adressen ordnungsgemäß eingerichtet sind.
    
7. Verschieben Sie Benutzer online lokal.
    
    Geben Sie Folgendes ein, um einen einzelnen Benutzer zu verschieben:
    
  ```
  $cred = Get-Credential
  ```

  ```
  Move-CsUser -Identity <username>@contoso.com  -Target "<fe-pool>.contoso.com " -Credential $cred -HostedMigrationOverrideURL <URL>
  ```

    Verschieben mehrerer Benutzer können mit dem Cmdlet **Get-CsUSer** mit dem Parameter Filter, um die Benutzer mit einer bestimmten Eigenschaft auszuwählen. Beispielsweise können Sie alle Online-Benutzer auswählen, durch das Filtern nach {Hostinganbieter - Eq "sipfed.online.lync.om"}. Sie können dann die zurückgegebenen Benutzer an das Cmdlet **Move-CsUSer** leiten, wie unten dargestellt.
    
  ```
  Get-CsUser -Filter {Hosting Provider -eq "sipfed.online.lync.com"} | Move-CsUser -Target "<fe-pool>.contoso.com " -Credential $creds -HostedMigrationOverrideURL <URL>
  ```

    Das Format der URL für der **HostedMigrationOverrideUrl** -Parameter die URL auf den Pool sein muss, auf dem der Migration gehosteten Dienst wird, im folgenden Format ausgeführt, angegeben: _Https://\<Pool-FQDN\>/HostedMigration/ hostedmigrationService.svc_.
    
    Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.
    
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten

1. Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.
    
2. Öffnen Sie das **Skype for Business Admin Center**.
    
3. Wenn das **Skype for Business Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten: 
    
     `https://admin0a.online.lync.com`
    
5. Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
    
    Ergebnis-URL, die den Wert der **HostedMigrationOverrideUrl**ist, sollte wie folgt aussehen:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    
    > [!NOTE]
    > Standardmäßig beträgt die maximale Größe für Transaktionsprotokolldateien der rtcxds-Datenbank 16 GB. Dies ist möglicherweise nicht groß genug ist, wenn Sie eine große Anzahl von Benutzern auf einmal verschieben, insbesondere dann, wenn Sie die Spiegelung aktiviert haben. Sie können dieses Problem umgehen, indem Sie die Dateigröße erhöhen oder die Protokolldateien regelmäßig sichern. Weitere Informationen finden Sie unter [https://support.microsoft.com/kb/2756725](https://support.microsoft.com/kb/2756725). 
  
8. Dies ist ein optionaler Schritt. Wenn Sie eine Integration in Exchange 2013 Online benötigen, müssen Sie einen zusätzlichen Hostinganbieter verwenden. Weitere Informationen hierzu finden Sie unter [Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md).
    
9. Die Benutzer sind jetzt verschoben. Geben Sie das folgende Cmdlet ein, um zu überprüfen, ob ein Benutzer korrekte Werte für die in der folgenden Tabelle gezeigten Attribute hat: 
    
  ```
  Get-CsUser | fl DisplayName,HostingProvider,SipAddress,Enabled
  ```

|**Active Directory-Attribut**|**Name des Attributs**|**Richtigen Wert für Online-Benutzer**|**Richtigen Wert für lokale Benutzer**|
|:-----|:-----|:-----|:-----|
|MsRTCSIP-DeploymentLocator  <br/> |HostingProvider  <br/> |sipfed.Online.Lync.com  <br/> |SRV:  <br/> |
|MsRTCSIP-PrimaryUserAddress  <br/> |SIPAddress  <br/> |SIP:UserName@contoso.com  <br/> |SIP:UserName@contoso.com  <br/> |
|sRTCSIP UserEnabled  <br/> |Aktiviert  <br/> |True  <br/> |True  <br/> |
   
10. Jeder verschobene Benutzer muss sich ab- und dann erneut anmelden. Nach der Anmeldung sollte jeder Benutzer seine Kontaktlisten überprüfen und ggf. Kontakte hinzufügen.
    
    Beachten Sie, dass geplante Besprechungen nicht von der Online- zur lokalen Bereitstellung migriert werden. Benutzer müssen diese Besprechungen erneut planen, nachdem sie verschoben wurden.
    
    Nachdem die DNS-Einträge aktualisiert werden und alle Benutzer werden auf lokalen geleitet, leitet das Attribut HostingProvider den Benutzer zum SRV-Einträge verwenden, oder weisen sie dem Onlineanbieter "sipfed.online.lync.com."
    
## <a name="move-online-users-who-were-originally-on-premises-to-on-premises"></a>Verschieben Sie online Benutzer (die ursprünglich lokal wurden) in lokal
<a name="BKMK_originallyonprem"> </a>

Dieser Abschnitt gilt nur für Benutzer, die erstellt und aktiviert für eine lokale Bereitstellung und klicken Sie dann auf online aus einer lokalen Bereitstellung verschoben wurden. 
  
- Führen Sie die folgenden Cmdlets zum Verschieben eines Benutzers von Skype für Business Online wieder auf lokal, ersetzen den Wert für die **Identität** und **Ziel** -Parameter an den richtigen Werten für Ihre Umgebung:
    
  ```
  $cred=Get-Credential
  ```

  ```
  Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
  ```

Das Format der URL für den **HostedMigrationOverrideUrl** -Parameter angegebene muss die URL auf den Pool, in dem der Migration gehosteten Dienst, im folgenden Format ausgeführt wird:
  
 _Https://\<Pool-FQDN\>/HostedMigration/hostedmigrationService.svc_. Sie können die URL des gehosteten Migrationsdiensts anhand der URL der Lync Online-Systemsteuerung für Ihr Office 365-Mandantenkonto ermitteln.
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a>So ermitteln Sie die URL des gehosteten Migrationsdiensts für Ihren Office 365-Mandanten

1. Melden Sie sich als Administrator bei Ihrem Office 365-Mandanten an.
    
2. Öffnen Sie das **Skype for Business Admin Center**.
    
3. Wenn das **Skype for Business Admin Center** angezeigt wird, wählen Sie die URL in der Adressliste bis zu **lync.com** aus und kopieren Sie sie. Eine Beispiel-URL sieht ähnlich wie die folgende aus:
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. Ersetzen Sie **webdir** in der URL durch **admin**, womit Sie folgendes Ergebnis erhalten: 
    
     `https://admin0a.online.lync.com`
    
5. Fügen Sie dann folgende Zeichenfolge an die URL an: **/HostedMigration/hostedmigrationservice.svc**.
    
    Ergebnis-URL, die den Wert der **HostedMigrationOverrideUrl**ist, sollte wie folgt aussehen:
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`
    

