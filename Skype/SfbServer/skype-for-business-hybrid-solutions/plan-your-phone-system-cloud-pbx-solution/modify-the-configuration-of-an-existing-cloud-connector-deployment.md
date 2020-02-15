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
description: Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher-Bereitstellung zu ändern.
ms.openlocfilehash: 4c2c0b8ad5340cd4ae4275f1ac009bf3d9d3ec0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018006"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung
 
Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher-Bereitstellung zu ändern. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Ändern der Konfiguration eines einzelnen Standorts
<a name="BKMK_SIngleSite"> </a>

Wenn der Standort nur eine Appliance enthält und Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten, können Sie die Datei "cloudconnector. ini ändern und die Bereitstellung erneut starten.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf dem Hostserver zu deinstallieren: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie die Datei "cloudconnector. ini im Appliance-Verzeichnis.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Führen Sie das folgende Cmdlet aus, um die Appliance erneut zu registrieren:
    
   ```powershell
   Register-CcAppliance
   ```

6. Führen Sie das folgende Cmdlet aus, um Skype for Business Cloud Connector Edition zu installieren:
    
   ```powershell
   Install-CcAppliance
   ```

Wenn sich mehr als eine Appliance am Standort befindet, müssen Sie die folgenden Schritte ausführen, die Datei "cloudconnector. ini ändern und die Appliances nacheinander bereitstellen.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer in der aktuellen Appliance zu deinstallieren: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie die Datei "cloudconnector. ini im Appliance-Verzeichnis.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Führen Sie das folgende Cmdlet aus, um die Appliance erneut zu registrieren:
    
   ```powershell
   Register-CcAppliance
   ```

6. Führen Sie das folgende Cmdlet für alle anderen Appliances am Standort aus, um die neueste Konfiguration zu übernehmen:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Führen Sie das folgende Cmdlet aus, um Cloud Connector in der aktuellen Appliance erneut bereitzustellen:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Ändern der Konfiguration mehrerer Standorte
<a name="BKMK_MultipleSites"> </a>

Wenn Sie die Konfiguration für mehrere Websites in einer Bereitstellung ändern möchten, führen Sie die Schritte für einen einzelnen Standort aus, und aktualisieren Sie gleichzeitig einen Standort.
  
## <a name="modify-the-configuration-of-your-office-365-tenant-to-enable-automatic-updates"></a>Ändern der Konfiguration des Office 365 Mandanten, um automatische Updates zu aktivieren
<a name="BKMK_MultipleSites"> </a>

Zum Aktivieren von automatischen Updates für das Betriebssystem und für automatische Bits-Aktualisierungen müssen Sie das Skype for Business mandantenadministrator Konto für die Online Verwaltung verwenden und die Remote-Mandanten-PowerShell wie folgt verwenden.
  
Wenn Sie automatische Updates für das Betriebssystem oder automatische Bits-Updates deaktiviert haben, verpassen Ihr Host und Ihr virtueller Computer möglicherweise wichtige Windows-Updates und Cloud Connector wird nicht automatisch auf die neue Version aktualisiert. Es wird dringend empfohlen, dass Sie automatische Updates aktivieren.
  
1. Die EnableAutoUpdate-Eigenschaft der Website muss auf true (der Standardwert) festgelegt werden. Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass EnableAutoUpdate auf true festgelegt ist:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Erstellen des Zeitfensters für die automatische Aktualisierung für den Mandanten.
    
    Das Zeitfenster kann täglich, wöchentlich und monatlich sein. Alle Zeitfenster benötigen eine Startzeit und eine Dauer.
    
   - Für ein tägliches Zeitfenster werden nur Anfangszeit und Dauer benötigt. 
    
   - Für ein wöchentliches Zeitfenster werden Tage der Woche benötigt, wobei es sich um einen einzelnen Tag oder mehrere Tage handeln kann.
    
   - Für ein monatliches Zeitfenster können zwei Typen vorhanden sein. Der erste Typ besteht darin, den Tag des Monats anzugeben, bei dem es sich um einen einzelnen Tag handeln kann. Der zweite Typ besteht darin, die Wochen des Monats zusammen mit den Wochentagen anzugeben, bei denen es sich sowohl um ein einzelnes Element als auch um mehrere Elemente handeln kann.
    
   - Für jeden Mandanten kann 20 Zeitfenster definiert werden. Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für das Betriebssystemupdate und das Bits-Update erstellt. Führen Sie die folgenden Cmdlets aus, um das Tages-, Wochen-oder Monats Zeitfenster festzulegen:
    
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

   - Zuweisen von Aktualisierungszeit Fenstern zur Website 
    
     Die Zeitfenster für Bits-Aktualisierung und Betriebssystemupdates werden separat konfiguriert. Beide können einem oder mehreren Zeitfenstern zugewiesen werden. Jedes Zeitfenster kann unterschiedlichen Standorten und unterschiedlichen Zwecken zugewiesen werden (Bits-Update und Betriebssystemupdate). Führen Sie das folgende Cmdlet aus, um das Zeitfenster für die Website festzulegen: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aktualisieren der dedizierten Administratoranmeldeinformationen für Mandanten
<a name="BKMK_MultipleSites"> </a>

Administrative Änderungen im Office 365 Mandanten für Cloud Connector werden von einem Konto mit den erforderlichen Berechtigungen vorgenommen. In Cloud Connector-Versionen vor 2,0 ist dieses Konto ein dediziertes globales mandantenadministrator Konto. In Cloud Connector-Versionen 2,0 und höher kann dieses Konto ein Office 365 Konto mit Skype for Business Administrator Rechten sein.
  
Wenn sich die Anmeldeinformationen Ihres Administratorkontos in Office 365 ändern, müssen Sie auch die lokal zwischengespeicherten Anmeldeinformationen in Cloud Connector aktualisieren, indem Sie den folgenden Administrator-PowerShell-Befehl auf jeder von Ihnen bereitgestellten Cloud Connector-Appliance ausführen:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aktualisieren des Kennworts für den Hostserver
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector, Version 2,0 und höher. 
  
Alle Cloud Connector-Anmeldeinformationen werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Wenn das Kennwort auf dem Hostserver geändert wird, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
  
Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, verwenden Sie die Cmdlets [Get-CcCredential](get-cccredential.md) und [Sets-CcCredential](set-cccredential.md) , und führen Sie die folgenden Schritte aus:
  
1. Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen: 
    
   - Get-CcCredential-AccountType DomainAdmin-DisplayPassword
    
   - Get-CcCredential-AccountType "vmadmin"-DisplayPassword
    
   - Get-CcCredential-AccountType "cceservice"-DisplayPassword
    
2. Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.
    
3. Starten Sie den Hostserver neu.
    
4. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
5. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-ccappliance"-local "aus, um die Kennwörter nach der Beschreibung erneut einzugeben. Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben.
    
Standardmäßig verwenden "vmadmin" und DomainAdmin dasselbe Kennwort wie "cceservice". Wenn die in Schritt 1 zurückgegebenen DomainAdmin-, "vmadmin"-und "cceservice"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:
  
1. Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:
    
1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.
    
2. Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:
    
1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene "vmadmin"-Kennwort ein. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aktualisieren des Kennworts für das "cceservice"-Konto
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector, Version 2.0.1 und höher. 
  
Der Cloud Connector-Dienst führt den Cloud Connector-Verwaltungsdienst aus. Das "cceservice"-Konto wird während der Cloud Connector Edition-Bereitstellung erstellt und in den folgenden Dateien gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml "und"%SystemDrive%\Programdata\Cloudconnector\credentials.. "Cceservice". xml ".
  
Um sicherzustellen, dass alle Appliances auf die Websiteverzeichnis Freigabe zugreifen können, muss das Kennwort für das "cceservice"-Konto auf allen innerhalb des Standorts bereitgestellten Appliances identisch sein. Denken Sie dabei an Folgendes:
  
- Standardmäßig wird das "cceservice"-Konto als "Kennwort läuft nie ablaufen" konfiguriert. Wenn Sie das Kennwort aktualisieren, empfiehlt Microsoft, diese Konfiguration beizubehalten.
    
- Sie sollten das Kennwort während nicht-Spitzennutzungszeiten und außerhalb der Zeitfenster für die automatische Aktualisierung für Bits oder Windows-Updates aktualisieren. Wenn Sie das Kennwort aktualisieren, muss die Appliance entladen und neu gestartet werden, was einige Zeit in Anspruch nimmt. Durch einen Neustart der Appliance werden automatische Updatevorgänge unterbrechen. 
    
- Wenn Sie das Kennwort für das "cceservice"-Konto ändern, müssen Sie alle Anmeldeinformationen angeben und diese in der lokal gespeicherten Datei aktualisieren. 
    
Für jede Appliance, die zum gleichen PSTN-Standort gehört, müssen Sie Folgendes angeben: 
  
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

2. Führen Sie das Cmdlet Enter-CCUpdate "aus, um die Appliance zu entleeren und in den manuellen Wartungsmodus zu versetzen.
    
3. Aktualisieren Sie das Kennwort des "cceservice"-Kontos auf dem Hostserver.
    
4. Starten Sie den Hostserver neu.
    
5. Führen Sie das Cmdlet Restore-CcCredentials aus, um die Kennwörter nach der Beschreibung erneut einzugeben. 
    
    Stellen Sie sicher, dass Sie das Kennwort eingeben, das Sie vor der Cloud Connector-Bereitstellung mit Ausnahme des "cceservice"-Kontos eingegeben haben. Geben Sie für das "cceservice"-Konto Ihr neues Kennwort ein. Stellen Sie sicher, dass das neue Kennwort für das "cceservice"-Konto für alle Appliances am PSTN-Standort identisch ist.
    
6. Standardmäßig verwenden "vmadmin" und DomainAdmin dasselbe Kennwort wie "cceservice". Wenn die in Schritt 1 zurückgegebenen DomainAdmin-, "vmadmin"-und "cceservice"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:
    
7. Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:
    
   - Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.
    
8. Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:
    
   - Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene "vmadmin"-Kennwort ein. 
    
9. Führen Sie das Cmdlet Exit-CCUpdate "aus, um die Appliance aus dem manuellen Wartungsmodus zu entfernen.
    
10. Nachdem Sie diese Schritte für alle Appliances am gleichen PSTN-Standort ausgeführt haben, löschen Sie die folgenden Dateien im Websitestamm Verzeichnis:
    
    - CcLockFile
    
    - FQDN\<des externen SIP-Pools Site_ Edge\>
    
    - FQDN\<des externen SIP-Pools Tenant_ Edge\>
    
    - FQDN\<des externen SIP-Pools TenantConfigLock_ Edge\>
    
## <a name="add-a-new-sip-domain"></a>Hinzufügen einer neuen SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Gehen Sie folgendermaßen vor, um der vorhandenen Cloud Connector-Bereitstellung eine neue SIP-Domäne (oder mehrere SIP-Domänen) hinzuzufügen:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben. Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne oder den neuen Domänen.
    
3. Fordern Sie ein neues externes Edge-Zertifikat mit zusätzlichen San-Namen für "SIP. Domain" für jede in ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an. 
    
4. Legen Sie den Pfad für das neue externe Edge-Zertifikat wie folgt fest:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Befolgen Sie die Anweisungen zum [Ändern der Konfiguration eines einzelnen Standorts](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder zum [Ändern der Konfiguration mehrerer Standorte](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites).
    
## <a name="modify-the-primary-sip-domain"></a>Ändern der primären SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie die primäre SIP-Domäne in ihrer Cloud Connector-Bereitstellung ändern müssen, gehen Sie wie folgt vor:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Office 365 abgeschlossen haben und die Möglichkeit zum Hinzufügen von DNS-Einträgen haben. Weitere Informationen zum Einrichten Ihrer Domäne in Office 365 finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne.
    
3. Fordern Sie ein neues externes Edge-Zertifikat mit zusätzlichen San-Namen für "SIP. Domain" für jede in ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an. 
    
4. Legen Sie den Pfad für das neue externe Edge-Zertifikat wie folgt fest:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Entfernen Sie die mandantenregistrierung für jede Appliance an einem Standort, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Entfernen Sie die Website Registrierung für jede Website, indem Sie das folgende Cmdlet in Skype for Business Online PowerShell ausführen:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Deinstallieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registrieren Sie die einzelnen Appliances, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installieren Sie jede Appliance nacheinander, indem Sie das folgende Cmdlet in der Administrator-PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Ersetzen des externen Edge-Zertifikats durch ein neues Zertifikat
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie das externe Edge-Zertifikat auf Ihren Cloud Connector-Appliances ersetzen müssen, müssen Sie ein neues Edge-Zertifikat erhalten, die PFX-Datei vorbereiten, die den privaten Schlüssel und die vollständige Zertifikatkette enthält, und dann auf jeder Appliance die folgenden Aktionen ausführen:
  
1. Stellen Sie die Appliance mithilfe des Enter-CCUpdate "-Cmdlets in den Wartungsmodus ein.
    
2. Führen Sie den folgenden Befehl aus: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Wenn das Kennwort des neuen Zertifikats mit dem des alten identisch ist, wird der Import erfolgreich ausgeführt. Wenn das Kennwort unterschiedlich ist, wird eine Fehlermeldung angezeigt, dass das Kennwort falsch ist, und Sie müssen das Kennwort zurücksetzen, indem Sie das Cmdlet "Register-ccappliance" "mit dem Parameter"-local "ausführen und dann Schritt 2 wiederholen. 
    
4. Verwenden Sie das Cmdlet Exit-CCUpdate ", um die Appliance aus dem Wartungsmodus zu entfernen.
    

