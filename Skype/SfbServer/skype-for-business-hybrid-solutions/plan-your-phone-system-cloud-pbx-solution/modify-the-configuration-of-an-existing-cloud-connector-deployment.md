---
title: Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1-oder höher-Bereitstellung zu ändern.
ms.openlocfilehash: 32a231ed85b94c09591adfcc6299cba704be267f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799435"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung
 
Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1-oder höher-Bereitstellung zu ändern. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Ändern der Konfiguration einer einzelnen Site
<a name="BKMK_SIngleSite"> </a>

Wenn die Site nur eine Appliance enthält und Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten, können Sie die Datei „CloudConnector.ini“ ändern und die Bereitstellung erneut starten.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Maschinen auf dem Hostserver zu deinstallieren:  
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie die Datei „CloudConnector.ini“ im Verzeichnis der Appliance.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für vorherige Versionen fahren Sie mit dem nächsten Schritt fort.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Führen Sie das folgende Cmdlet aus, um die Appliance wieder zu registrieren:
    
   ```powershell
   Register-CcAppliance
   ```

6. Führen Sie das folgende Cmdlet aus, um Skype for Business Cloud Connector Edition zu installieren:
    
   ```powershell
   Install-CcAppliance
   ```

Wenn am Standort mehrere Appliances vorhanden sind, müssen Sie diese Schritte ausführen, die Datei „CloudConnector.ini“ ändern und die Appliances nacheinander erneut bereitstellen.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf der aktuellen Appliance zu deinstallieren: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie die Datei „CloudConnector.ini“ im Verzeichnis der Appliance.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für vorherige Versionen fahren Sie mit dem nächsten Schritt fort.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Führen Sie das folgende Cmdlet aus, um die Appliance wieder zu registrieren:
    
   ```powershell
   Register-CcAppliance
   ```

6. Führen Sie das folgende Cmdlet in allen anderen Appliances am Standort aus, um die aktuelle Konfiguration zu übernehmen:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Führen Sie das folgende Cmdlet aus, um den Cloud Connector für die aktuelle Appliance erneut bereitzustellen:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Ändern der Konfiguration mehrerer Sites
<a name="BKMK_MultipleSites"> </a>

Wenn Sie die Konfiguration für mehrere Websites in einer Bereitstellung ändern möchten, führen Sie die Schritte für eine einzelne Website aus, und aktualisieren Sie jeweils eine Website.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Ändern der Konfiguration Ihres Office 365-Mandanten, um automatische Updates zu aktivieren
<a name="BKMK_MultipleSites"> </a>

Wenn Sie automatische Updates für das Betriebssystem und automatische Bits-Updates aktivieren möchten, müssen Sie das Skype for Business-mandantenadministrator Konto für die Online Verwaltung verwenden und die Mandanten-Remote-PowerShell wie folgt verwenden.
  
Wenn Sie automatische Updates für das Betriebssystem oder automatische Updates für Bits deaktiviert haben, verpassen Ihr Host und Ihr virtueller Computer möglicherweise wichtige Windows-Updates, und Cloud Connector wird nicht automatisch auf die neue Version aktualisiert. Es wird dringend empfohlen, automatische Updates zu aktivieren.
  
1. Die EnableAutoUpdate-Eigenschaft der Website muss auf "true" (der Standardwert) festgelegt werden. Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass „EnableAutoUpdate“ auf „true“ festgelegt ist:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Erstellen Sie ein Zeitfenster für automatische Updates für den Mandanten.
    
    Dabei kann es sich um ein tägliches, wöchentliches oder monatliches Zeitfenster handeln. Für alle Zeitfenster ist eine Startzeit und eine Dauer erforderlich.
    
   - Für tägliche Zeitfenster müssen Sie nur die Startzeit und die Dauer angeben.  
    
   - Für wöchentliche Zeitfenster werden die Wochentage benötigt, das heißt ein einzelner Tag oder mehrere Tage.
    
   - Bei einem monatlichen Zeitfenster sind zwei Typen möglich. Zunächst können Sie einen Tag im Monat angeben, also einen einzigen Tag. Beim zweiten Typ können Sie Wochen im Monat sowie Wochentage angeben (ein Element oder mehrere Elemente).
    
   - Für jeden Mandanten können 20 Zeitfenster definiert sein. Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für Betriebssystemupdates und Updates der Bits erstellt. Führen Sie die folgenden Cmdlets aus, um tägliche, wöchentliche oder monatliche Zeitfenster festzulegen:
    
   ```powershell
   New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
   ```

   ```powershell
   New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
   ```

   - Weisen Sie der Website Aktualisierungszeit Fenster zu. 
    
     Die Zeitfenster für BITS-Updates und Betriebssystemupdates werden getrennt konfiguriert. Beiden Updatearten können Sie ein oder mehrere Zeitfenstern zuweisen. Jedes Zeitfenster kann verschiedenen Sites und Zwecken zugewiesen sein (BITS-Update und Betriebssystemupdate). Führen Sie das folgende Cmdlet aus, um das Zeitfenster für die Website einzurichten: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aktualisieren der Anmeldeinformationen für den dedizierten Mandantenadministrator 
<a name="BKMK_MultipleSites"> </a>

Administrative Änderungen im Office 365-Mandanten für Cloud Connector erfolgen über ein Konto mit den erforderlichen Berechtigungen. In Cloud Connector-Versionen vor 2,0 ist dieses Konto ein dediziertes globales mandantenadministrator Konto. In Cloud Connector-Versionen 2,0 und höher kann dieses Konto ein Office 365-Konto mit Skype for Business-Administrator Rechten sein.
  
Wenn sich die Anmeldeinformationen für Ihr Administratorkonto in Office 365 ändern, müssen Sie auch die lokal zwischengespeicherten Anmeldeinformationen in Cloud Connector aktualisieren, indem Sie den folgenden Administrator PowerShell-Befehl auf jeder von Ihnen bereitgestellten Cloud Connector-Appliance ausführen:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aktualisieren des Kennworts für den Hostserver 
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector Version 2,0 und höher. 
  
Alle Anmeldeinformationen für den Cloud Connector werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
  
Wenn Sie die lokal gespeicherten Anmeldeinformationen auf der Cloud Connector-Appliance aktualisieren möchten, verwenden Sie die Cmdlets [Get-CcCredential](get-cccredential.md) und [CcCredential](set-cccredential.md) , und führen Sie die folgenden Schritte aus:
  
1. Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen:  
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType VMAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType CceService-DisplayPassword
    
2. Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.
    
3. Starten Sie den Hostserver neu.
    
4. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance-local" aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben. Achten Sie darauf, das gleiche Kennwort einzugeben, das Sie vor der Cloud Connector-Bereitstellung eingegeben haben.
    
Für „VmAdmin“ und „DomainAdmin“ wird standardmäßig das gleiche Kennwort wie für „CceService“ verwendet. Wenn in Schritt 1 andere Kennwörter für „DomainAdmin“, „VMAdmin“ und „CceService“ zurückgegeben wurden, müssen Sie die folgenden Schritte ausführen:
  
1. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „DomainAdmin“ ein.
    
2. Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „VmAdmin“ ein.  
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aktualisieren des Kennworts für das CceService-Konto
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector Version 2.0.1 und höher. 
  
Der Cloud Connector-Dienst führt den Cloud Connector-Verwaltungsdienst aus. Das CceService-Konto wird während der Cloud Connector Edition-Bereitstellung erstellt und in den folgenden Dateien gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "und"%SystemDrive%\Programdata\Cloudconnector\credentials.. CceService. xml ".
  
Um sicherzustellen, dass alle Appliances auf die Websiteverzeichnis Freigabe zugreifen können, muss das Kennwort für das CceService-Konto auf allen innerhalb der Website bereitgestellten Appliances identisch sein. Berücksichtigen Sie dabei Folgendes:
  
- Standardmäßig ist das CceService-Konto als "Kennwort läuft nie ab" konfiguriert. Wenn Sie das Kennwort aktualisieren, empfiehlt Microsoft, diese Konfiguration beizubehalten.
    
- Sie sollten das Kennwort während der Verwendung außerhalb der Spitzenzeiten und außerhalb der Zeitfenster für automatische Updates für Bits oder Windows-Updates aktualisieren. Wenn Sie das Kennwort aktualisieren, muss die Appliance entleert und neu gestartet werden, was einige Zeit in Anspruch nimmt. Beim Neustart der Appliance werden die automatischen Aktualisierungsvorgänge unterbrechen. 
    
- Wenn Sie das Kennwort für das CceService-Konto ändern, müssen Sie alle Anmeldeinformationen angeben und in der lokal gespeicherten Datei aktualisieren. 
    
Für jede Appliance, die zur gleichen PSTN-Website gehört, müssen Sie Folgendes angeben: 
  
1. Führen Sie die folgenden Befehle aus, um die Kontonamen und Kennwörter abzurufen, die Sie später verwenden werden:
    
   ```powershell
   Get-CcCredential -AccountType TenantAdmin -DisplayPassword
   Get-CcCredential -AccountType TenantAdmin
   Get-CcCredential -AccountType OMSWorkspace -DisplayPassword
   Get-CcCredential -AccountType OMSWorkspace 
   Get-CcCredential -AccountType ExternalCert -DisplayPassword
   Get-CcCredential -AccountType CABackupFile -DisplayPassword
   Get-CcCredential -AccountType CceService -DisplayPassword
   Get-CcCredential -AccountType VMAdmin -DisplayPassword
   Get-CcCredential -AccountType DomainAdmin -DisplayPassword
   ```

2. Führen Sie das Cmdlet "Enter-CcUpdate" aus, um die Appliance zu entladen und in den manuellen Wartungsmodus zu verschieben.
    
3. Aktualisieren Sie das Kennwort des CceService-Kontos auf dem Hostserver.
    
4. Starten Sie den Hostserver neu.
    
5. Führen Sie das Cmdlet Restore-CcCredentials aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben. 
    
    Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben, mit Ausnahme des CceService-Kontos. Geben Sie für das CceService-Konto Ihr neues Kennwort ein. Stellen Sie sicher, dass das neue Kennwort für das CceService-Konto für alle Appliances auf der PSTN-Website identisch ist.
    
6. Für „VmAdmin“ und „DomainAdmin“ wird standardmäßig das gleiche Kennwort wie für „CceService“ verwendet. Wenn in Schritt 1 andere Kennwörter für „DomainAdmin“, „VMAdmin“ und „CceService“ zurückgegeben wurden, müssen Sie die folgenden Schritte ausführen:
    
7. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
   - Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „DomainAdmin“ ein.
    
8. Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:
    
   - Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „VmAdmin“ ein.  
    
9. Führen Sie das Cmdlet Exit-CcUpdate aus, um die Appliance aus dem manuellen Wartungsmodus zu verschieben.
    
10. Nachdem Sie diese Schritte für alle Appliances auf derselben PSTN-Website ausgeführt haben, löschen Sie die folgenden Dateien im Stammverzeichnis der Website:
    
    - CcLockFile
    
    - FQDN\<des externen SIP-Pools Site_ Edge\>
    
    - FQDN\<des externen SIP-Pools Tenant_ Edge\>
    
    - FQDN\<des externen SIP-Pools TenantConfigLock_ Edge\>
    
## <a name="add-a-new-sip-domain"></a>Hinzufügen einer neuen SIP-Domäne 
<a name="BKMK_UpdatePassword"> </a>

Gehen Sie wie folgt vor, um Ihrer vorhandenen Cloud Connector-Bereitstellung eine neue SIP-Domäne (oder mehrere SIP-Domänen) hinzuzufügen:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen und die Möglichkeit haben, DNS-Datensätze hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne oder den neuen Domänen.
    
3. Fordern Sie ein neues Edge-externes Zertifikat mit zusätzlichen San-Namen für SIP. Domain für jede SIP-Domäne an, die in ihrer Cloud Connector-Konfiguration definiert ist. 
    
4. Legen Sie den Pfad für das neue externe Zertifikat des Edges wie folgt fest:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Befolgen Sie die Anweisungen zum [Ändern der Konfiguration einer einzelnen Site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder [Ändern der Konfiguration mehrerer Sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Ändern der primären SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie die primäre SIP-Domäne in ihrer Cloud Connector-Bereitstellung ändern müssen, gehen Sie folgendermaßen vor:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen und die Möglichkeit haben, DNS-Datensätze hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne.
    
3. Fordern Sie ein neues Edge-externes Zertifikat mit zusätzlichen San-Namen für SIP. Domain für jede SIP-Domäne an, die in ihrer Cloud Connector-Konfiguration definiert ist. 
    
4. Legen Sie den Pfad für das neue externe Zertifikat des Edges wie folgt fest:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Entfernen Sie die mandantenregistrierung für jede Appliance auf einer Website, indem Sie das folgende Cmdlet in Administrator-PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Entfernen Sie die Siteregistrierung für jede Site, indem Sie das folgende Cmdlet in Skype for Business Online-PowerShell ausführen:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Deinstallieren Sie jede Appliance, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registrieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installieren Sie jede Appliance einzeln, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Ersetzen des Zertifikats für externe Edge durch ein neues Zertifikat
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie das Zertifikat für externe Edge auf Ihren Cloud Connector-Appliances ersetzen müssen, müssen Sie ein neues Edge-Zertifikat anfordern, die PFX-Datei vorbereiten, die den privaten Schlüssel und die vollständige Zertifikatkette enthält, und dann auf jeder Appliance die folgenden Aktionen ausführen:
  
1. Setzen Sie die Appliance mithilfe des Cmdlets Enter-CcUpdate in den Wartungsmodus.
    
2. Führen Sie den folgenden Befehl aus: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Wenn das Kennwort des neuen Zertifikats mit dem alten übereinstimmt, wird der Import erfolgreich ausgeführt. Wenn das Kennwort anders ist, erhalten Sie eine Fehlermeldung, dass das Kennwort falsch ist, und Sie müssen das Kennwort zurücksetzen, indem Sie das Cmdlet "Register-CcAppliance" mit dem Parameter "-local" ausführen und dann Schritt 2 wiederholen. 
    
4. Verwenden Sie das Cmdlet Exit-CcUpdate, um die Appliance aus dem Wartungsmodus zu nehmen.
    

