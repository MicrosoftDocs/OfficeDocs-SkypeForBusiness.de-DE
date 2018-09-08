---
title: Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 90490c65-0e40-4e85-96e1-751f27897e25
description: Führen Sie die Schritte in diesem Thema, um die Konfiguration von einer vorhandenen Skype für Business Cloud Connector Edition 1.4.1 oder höher Bereitstellung zu ändern.
ms.openlocfilehash: fe226e67f6f492e0fae7473156908cd4a5147ea2
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885803"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung
 
Führen Sie die Schritte in diesem Thema, um die Konfiguration von einer vorhandenen Skype für Business Cloud Connector Edition 1.4.1 oder höher Bereitstellung zu ändern. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Ändern der Konfiguration einer einzelnen Site
<a name="BKMK_SIngleSite"> </a>

Wenn die Site nur eine Appliance enthält und Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten, können Sie die Datei „CloudConnector.ini“ ändern und die Bereitstellung erneut starten.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Maschinen auf dem Hostserver zu deinstallieren:  
    
  ```
  Uninstall-CcAppliance
  ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
  ```
  Unregister-CcAppliance
  ```

3. Aktualisieren Sie die Datei „CloudConnector.ini“ im Verzeichnis der Appliance.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen, fahren Sie mit dem nächsten Schritt fort.)
    
  ```
   Import-CcConfiguration 
  ```

5. Führen Sie das folgende Cmdlet aus, um die Appliance wieder zu registrieren:
    
  ```
  Register-CcAppliance
  ```

6. Führen Sie das folgende Cmdlet aus, um Skype for Business Cloud Connector Edition zu installieren:
    
  ```
  Install-CcAppliance
  ```

Wenn am Standort mehrere Appliances vorhanden sind, müssen Sie diese Schritte ausführen, die Datei „CloudConnector.ini“ ändern und die Appliances nacheinander erneut bereitstellen.
  
1. Führen Sie das folgende Cmdlet, um alle vorhandenen virtuellen Computern in der aktuellen Anwendung zu deinstallieren: 
    
  ```
  Uninstall-CcAppliance
  ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
  ```
  Unregister-CcAppliance
  ```

3. Aktualisieren Sie die Datei „CloudConnector.ini“ im Verzeichnis der Appliance.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen, fahren Sie mit dem nächsten Schritt fort.)
    
  ```
   Import-CcConfiguration 
  ```

5. Führen Sie das folgende Cmdlet aus, um die Appliance wieder zu registrieren:
    
  ```
  Register-CcAppliance
  ```

6. Führen Sie das folgende Cmdlet in allen anderen Appliances am Standort aus, um die aktuelle Konfiguration zu übernehmen:
    
  ```
  Publish-CcAppliance
  ```

7. Führen Sie auf der aktuellen Anwendung Cloud Connector erneut bereitstellen, um das folgende Cmdlet aus:
    
  ```
  Install-CcAppliance
  ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Ändern der Konfiguration mehrerer Sites
<a name="BKMK_MultipleSites"> </a>

Um die Konfiguration für mehrere Standorte in einer Bereitstellung zu ändern, führen Sie die Schritte für eine einzelne Website, eine Website zu einem Zeitpunkt aktualisieren.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Ändern der Konfiguration Ihres Office 365-Mandanten zum Aktivieren der automatischen updates
<a name="BKMK_MultipleSites"> </a>

Um automatische Updates Betriebssystem und Bits automatische Updates zu aktivieren, müssen Sie die Skype für Business Mandanten Administratorkonto für die online-Verwaltung verwenden und remote-PowerShell wie folgt Mandanten verwenden.
  
Wenn Sie automatische Updates Betriebssystem oder Bits automatische Updates deaktiviert, Ihre Host und dem virtuellen Computer verpassen möglicherweise wichtige Windows-Updates und Cloud-Connector wird nicht automatisch auf die neue Version aktualisiert. Es wird dringend empfohlen, automatische Updates zu aktivieren.
  
1. Die EnableAutoUpdate-Eigenschaft der Website muss auf "true" (Standardwert) festgelegt werden. Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass „EnableAutoUpdate“ auf „true“ festgelegt ist:
    
  ```
  Get-CsHybridPSTNSite -Identity <SiteName>
  ```

2. Erstellen Sie ein Zeitfenster für automatische Updates für den Mandanten.
    
    Dabei kann es sich um ein tägliches, wöchentliches oder monatliches Zeitfenster handeln. Für alle Zeitfenster ist eine Startzeit und eine Dauer erforderlich.
    
  - Für tägliche Zeitfenster müssen Sie nur die Startzeit und die Dauer angeben.  
    
  - Für wöchentliche Zeitfenster werden die Wochentage benötigt, das heißt ein einzelner Tag oder mehrere Tage.
    
  - Bei einem monatlichen Zeitfenster sind zwei Typen möglich. Zunächst können Sie einen Tag im Monat angeben, also einen einzigen Tag. Beim zweiten Typ können Sie Wochen im Monat sowie Wochentage angeben (ein Element oder mehrere Elemente).
    
  - Für jeden Mandanten können 20 Zeitfenster definiert sein. Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für Betriebssystemupdates und Updates der Bits erstellt. Führen Sie die folgenden Cmdlets aus, um tägliche, wöchentliche oder monatliche Zeitfenster festzulegen:
    
  ```
  New-CsTenantUpdateTimeWindow -Identity Night -Daily -StartTime 22:00 -Duration 6:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity WeekdayNight -Weekly -DaysOfWeek Monday,Tuesday,Wednesday,Thursday,Friday -StartTime 22:00 -Duration 4:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity FirstAndLastWeekend -Monthly -WeeksOfMonth First,Last -DaysOfWeek Sunday,Saturday -StartTime 0:00 -Duration 10:00
  ```

  ```
  New-CsTenantUpdateTimeWindow -Identity MidDayOfMonth -Monthly -DayOfMonth 15 -StartTime 0:00 -Duration 1.00:00
  ```

  - Weisen Sie der Website Start von Windows Update. 
    
    Die Zeitfenster für BITS-Updates und Betriebssystemupdates werden getrennt konfiguriert. Beiden Updatearten können Sie ein oder mehrere Zeitfenstern zuweisen. Jedes Zeitfenster kann verschiedenen Sites und Zwecken zugewiesen sein (BITS-Update und Betriebssystemupdate). Führen Sie das folgende Cmdlet, um das Zeitfenster für die Website festzulegen: 
    
  ```
  Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
  ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aktualisieren der Anmeldeinformationen für den dedizierten Mandantenadministrator 
<a name="BKMK_MultipleSites"> </a>

Administrative werden in Office 365-Mandanten für Cloud-Connector von einem Konto mit den erforderlichen Berechtigungen geändert. In Versionen vor 2.0 Cloud Connector ist dieses Konto ein Administratorkonto dedizierten globalen Mandanten. In der Cloud Connector, Version 2.0 und höher kann dieses Konto ein Office 365-Konto mit Skype für Business Administratorrechte sein.
  
Wenn die Anmeldeinformationen Ihres Admin-Kontos in Office 365 ändern, müssen Sie auch so aktualisieren Sie die lokal zwischengespeicherten Anmeldeinformationen in der Cloud Connector mithilfe des folgenden Befehls Administrator PowerShell auf jede Cloud Connector Einheit, die Sie bereitgestellt haben:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aktualisieren des Kennworts für den Hostserver 
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt ist für Cloud-Connector-Version 2.0 und höher. 
  
Alle Cloud Connector Anmeldeinformationen werden in der folgenden Datei gespeichert: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ". Wenn das Kennwort für den Hostserver geändert wird, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
  
Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Anwendung zu aktualisieren, verwenden Sie die Cmdlets [Get-CcCredential](get-cccredential.md) und [Set-CcCredential](set-cccredential.md) , und gehen Sie folgendermaßen vor:
  
1. Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen:  
    
  - Get-CcCredential - AccountType DomainAdmin "- DisplayPassword
    
  - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
  - Get-CcCredential AccountType - CceService - DisplayPassword
    
2. Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.
    
3. Starten Sie den Hostserver neu.
    
4. Löschen Sie die folgende Datei: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".
    
5. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance-lokale" die Kennwörter die Beschreibung nach erneut eingeben. Stellen Sie sicher, dass Sie das gleiche Kennwort eingeben eingegebene vor dem für die Bereitstellung von Cloud-Connector.
    
Für „VmAdmin“ und „DomainAdmin“ wird standardmäßig das gleiche Kennwort wie für „CceService“ verwendet. Wenn in Schritt 1 andere Kennwörter für „DomainAdmin“, „VMAdmin“ und „CceService“ zurückgegeben wurden, müssen Sie die folgenden Schritte ausführen:
  
1. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „DomainAdmin“ ein.
    
2. Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „VmAdmin“ ein.  
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aktualisieren Sie das Kennwort für das Konto CceService
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> In diesem Abschnitt wird für Cloud-Connector-Version 2.0.1 oder höher. 
  
Der Connector Cloud-Dienst ausgeführt wird, den Cloud Connector-Verwaltungsdienst. Das Konto CceService während der Bereitstellung Cloud Connector Edition erstellt und in den folgenden Dateien gespeichert: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml "und"% SystemDrive%\Programdata\Cloudconnector\credentials... CceService.xml".
  
Um sicherzustellen, dass alle Einheiten auf die Website Directory Freigabe zugreifen können, muss das Kennwort für das Konto CceService dieselbe auf allen Einheiten, die innerhalb der Website bereitgestellt. Berücksichtigen Sie dabei Folgendes:
  
- Standardmäßig wird das Konto CceService wie "Kennwort läuft nie ab" konfiguriert. Wenn Sie das Kennwort aktualisieren, empfiehlt es sich diese Konfiguration zu aktualisieren.
    
- Sie sollten das Kennwort nicht spitzenauslastung Zeiträumen und außerhalb von Automatische Updates Zeitfenster für Bits oder Windows-Updates aktualisieren. Wenn Sie das Kennwort aktualisieren, muss das Gerät ein Ausgleich vorgenommen und neu gestartet, die einige Zeit. Neustarten der Appliance werden die Vorgänge für automatische Updates ist unterbrochen. 
    
- Wenn Sie das Kontokennwort CceService ändern, müssen Sie alle Anmeldeinformationen angeben und diese in der lokal gespeicherten Datei zu aktualisieren. 
    
Für jede Anwendung, die am gleichen Standort PSTN angehört, benötigen Sie Folgendes angeben: 
  
1. Führen Sie die folgenden Befehle zum Abrufen der Kontonamen und Kennwörter, die Sie später verwenden:
    
  ```
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

2. Führen Sie das Cmdlet EINGABETASTE CcUpdate die Appliance abzuleiten und verschieben sie in den Wartungsmodus manuelle aus.
    
3. Aktualisieren Sie das Kennwort des Kontos CceService auf dem Hostserver.
    
4. Starten Sie den Hostserver neu.
    
5. Führen Sie das Cmdlet Restore-CcCredentials, um die Kennwörter die Beschreibung nach erneut eingeben. 
    
    Stellen Sie sicher, dass Sie das gleiche Kennwort eingeben, das Sie vor dem für die Cloud Connector-Bereitstellung mit Ausnahme der CceService-Konto eingegeben haben. Geben Sie Ihr neue Kennwort für das Konto CceService. Stellen Sie sicher, dass das neue Kennwort für das Konto CceService für alle Einheiten in der PSTN-Website identisch ist.
    
6. Für „VmAdmin“ und „DomainAdmin“ wird standardmäßig das gleiche Kennwort wie für „CceService“ verwendet. Wenn in Schritt 1 andere Kennwörter für „DomainAdmin“, „VMAdmin“ und „CceService“ zurückgegeben wurden, müssen Sie die folgenden Schritte ausführen:
    
1. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
  - Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
  - Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „DomainAdmin“ ein.
    
2. Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:
    
  - Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
  - Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das in Schritt 1 zurückgegebene Kennwort für „VmAdmin“ ein.  
    
7. Führen Sie das Exit-CcUpdate-Cmdlet, um die Einheit nicht mehr im Wartungsmodus manuelle verschieben.
    
8. Nachdem Sie diese Schritte auf allen Einheiten auf der gleichen PSTN-Website abgeschlossen haben, löschen Sie die folgenden Dateien in das Stammverzeichnis der Website:
    
  - CcLockFile
    
  - Site_\<externen Sip-Edge-Pool-Fqdn\>
    
  - Tenant_\<externen Sip-Edge-Pool-Fqdn\>
    
  - TenantConfigLock_\<externen Sip-Edge-Pool-Fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Hinzufügen einer neuen SIP-Domäne 
<a name="BKMK_UpdatePassword"> </a>

Um eine neue SIP-Domäne (oder mehrere SIP-Domänen) Ihre vorhandene Bereitstellung Cloud Connector hinzuzufügen, führen Sie folgende Schritte aus:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihre Domäne in Office 365 und haben die Möglichkeit zum Hinzufügen von DNS-Einträgen abgeschlossen haben. Weitere Informationen dazu, wie Sie Ihre Domäne in Office 365 einrichten finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren der Konfigurationsdatei Cloud Connector mit den neuen SIP-Domäne oder Domänen.
    
3. Anfordern eines neuen externen Edge-Zertifikats mit zusätzlichen SAN-Namen für angegeben für jede SIP-Domäne in der Cloud Connectorkonfiguration definiert. 
    
4. Legen Sie den Pfad für das neue externe Zertifikat des Edges wie folgt fest:
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    Befolgen Sie die Anweisungen zum [Ändern der Konfiguration einer einzelnen Site](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder [Ändern der Konfiguration mehrerer Sites](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Ändern der primären SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie die primäre SIP-Domäne in der Cloud Connector Bereitstellung ändern müssen, führen Sie folgende Schritte aus:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihre Domäne in Office 365 und haben die Möglichkeit zum Hinzufügen von DNS-Einträgen abgeschlossen haben. Weitere Informationen dazu, wie Sie Ihre Domäne in Office 365 einrichten finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/en-us/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren Sie die Konfigurationsdatei Cloud Connector mit der neuen SIP-Domäne.
    
3. Anfordern eines neuen externen Edge-Zertifikats mit zusätzlichen SAN-Namen für angegeben für jede SIP-Domäne in der Cloud Connectorkonfiguration definiert. 
    
4. Legen Sie den Pfad für das neue externe Zertifikat des Edges wie folgt fest:
    
  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
  ```

5. 
    
    Entfernen Sie die Mandanten-Registrierung für jede Anwendung in einer Website, indem Sie das folgende Cmdlet in Administrator PowerShell Cloud Connector ausführen:
    
  ```
  Unregister-CcAppliance
  ```

6. 
    
    Entfernen Sie die Siteregistrierung für jede Site, indem Sie das folgende Cmdlet in Skype for Business Online-PowerShell ausführen:


    
  ```
  Remove-CsHybridPSTNSite
  ```

7. 
    
    Deinstallieren Sie jede Appliance, indem Sie das folgende Cmdlet in PowerShell Administrator auf Cloud Connector ausgeführt wird:
    
  ```
  Uninstall-CcAppliance
  ```

8. 
    
     Registrieren Sie jede Appliance, indem Sie das folgende Cmdlet in Administrator PowerShell Cloud Connector ausführen:
    
  ```
  Register-ccAppliance
  ```

9. 
    
     Installieren Sie jede Anwendung einzeln, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
  ```
  Install-CcAppliance
  ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Ersetzen Sie das externe edgezertifikat durch ein neues Zertifikat
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie das externe edgezertifikat auf Ihre Cloud-Connector Appliances ersetzen müssen, müssen Sie ein neues edgezertifikat zu erhalten, die PFX-Datei mit dem privaten Schlüssel und die vollständige Zertifikatkette vorbereiten und führen Sie dann auf jede Appliance die folgenden:
  
1. Tragen Sie mithilfe des Cmdlets EINGABETASTE CcUpdate der Appliance im Wartungsmodus befindet.
    
2. Führen Sie den folgenden Befehl aus: 
    
  ```
  Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
  ```

3. 
    
    Wenn das Kennwort für das neue Zertifikat die alte identisch ist, wird der Import erfolgreich durchgeführt. Wenn das Kennwort unterscheidet, wird eine Fehlermeldung, dass das Kennwort falsch ist, und Sie das Kennwort zurücksetzen, indem Sie das Register-CcAppliance-Cmdlet ausführen müssen, mit dem lokalen Parameter, und wiederholen Sie Schritt 2. 
    
4. Nutzen Sie die Einheit nicht mehr im Wartungsmodus mithilfe des Exit - CcUpdate-Cmdlets.
    

