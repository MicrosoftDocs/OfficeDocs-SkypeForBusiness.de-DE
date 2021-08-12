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
description: Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher zu ändern.
ms.openlocfilehash: 151408d48f7623d72d5af4f8fef605d9dcc7d690a915cc7e8454a91f051dd0f1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324184"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher zu ändern. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Ändern der Konfiguration eines einzelnen Standorts
<a name="BKMK_SIngleSite"> </a>

Wenn nur eine Appliance am Standort vorhanden ist, können Sie, wenn Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten, die datei CloudConnector.ini ändern und die Bereitstellung erneut starten.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf dem Hostserver zu deinstallieren: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie die CloudConnector.ini-Datei im Appliance-Verzeichnis.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (Dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)
    
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

Wenn sich mehrere Appliances am Standort befinden, müssen Sie die folgenden Schritte ausführen, die CloudConnector.ini-Datei ändern und die Appliances nacheinander erneut bereitstellen.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer in der aktuellen Appliance zu deinstallieren: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance aufzuheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie die CloudConnector.ini-Datei im Appliance-Verzeichnis.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (Dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)
    
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

Um die Konfiguration für mehrere Standorte in einer Bereitstellung zu ändern, führen Sie die Schritte für einen einzelnen Standort aus, indem Sie jeweils einen Standort aktualisieren.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Ändern der Konfiguration Ihrer Microsoft 365 oder Office 365 Organisation, um automatische Updates zu aktivieren
<a name="BKMK_MultipleSites"> </a>

Um automatische Updates des Betriebssystems und bits automatische Updates zu aktivieren, müssen Sie das Skype for Business Mandantenadministratorkonto für die Onlineverwaltung verwenden und Mandanten-Remote-PowerShell wie folgt verwenden.
  
Wenn Sie automatische Updates des Betriebssystems oder bits automatische Updates deaktiviert haben, fehlen Ihrem Host und virtuellen Computer möglicherweise wichtige Windows Updates, und Cloud Connector wird nicht automatisch auf die neue Version aktualisiert. Es wird dringend empfohlen, automatische Updates zu aktivieren.
  
1. Die EnableAutoUpdate-Eigenschaft der Website muss auf "true" festgelegt werden (Standardwert). Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass EnableAutoUpdate auf "true" festgelegt ist:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Erstellen Sie das Zeitfenster für die automatische Aktualisierung für den Mandanten.
    
    Das Zeitfenster kann täglich, wöchentlich und monatlich sein. Alle Zeitfenster benötigen eine Startzeit und eine Dauer.
    
   - Für ein tägliches Zeitfenster sind nur Startzeit und Dauer erforderlich. 
    
   - Für ein wöchentliches Zeitfenster sind Wochentage erforderlich, bei denen es sich um einen einzelnen Tag oder mehrere Tage handelt.
    
   - Für ein monatliches Zeitfenster können zwei Typen vorhanden sein. Der erste Typ ist die Angabe des Monatstags, bei dem es sich um einen einzelnen Tag handelt. Der zweite Typ besteht darin, die Wochen des Monats zusammen mit den Wochentagen anzugeben, die beide ein einzelnes Element oder mehrere Elemente sein können.
    
   - Für jeden Mandanten können 20 Zeitfenster definiert sein. Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für Betriebssystemupdates und Bits-Updates erstellt. Führen Sie die folgenden Cmdlets aus, um das tägliche, wöchentliche oder monatliche Zeitfenster festzulegen:
    
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

   - Weisen Sie der Website Updatezeitfenster zu. 
    
     Die Zeitfenster für Bitupdates und BS-Updates werden separat konfiguriert. Beide können einzel- oder mehrfache Fenster zugewiesen werden. Jedes Zeitfenster kann verschiedenen Websites und unterschiedlichen Zwecken zugewiesen werden (Bits-Update und Betriebssystemupdate). Führen Sie das folgende Cmdlet aus, um das Zeitfenster für die Website festzulegen: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aktualisieren der Anmeldeinformationen des dedizierten Mandantenadministrators
<a name="BKMK_MultipleSites"> </a>

Administrative Änderungen an der Microsoft 365 oder Office 365 Organisation für Cloud Connector werden von einem Konto mit den erforderlichen Berechtigungen vorgenommen. In Cloud Connector-Versionen vor Version 2.0 ist dieses Konto ein dediziertes globales Mandantenadministratorkonto. In Cloud Connector, Version 2.0 und höher, kann es sich bei diesem Konto um ein Microsoft 365 oder Office 365 Konto mit Skype for Business Administratorrechten handeln.
  
Wenn sich die Anmeldeinformationen Ihres Administratorkontos in Microsoft 365 oder Office 365 ändern, müssen Sie auch die lokal zwischengespeicherten Anmeldeinformationen in Cloud Connector aktualisieren, indem Sie den folgenden Administrator-PowerShell-Befehl in jeder Cloud Connector-Appliance ausführen, die Sie bereitgestellt haben:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aktualisieren des Kennworts für den Hostserver
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector, Version 2.0 und höher. 
  
Alle Cloud Connector-Anmeldeinformationen werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml". Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
  
Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, verwenden Sie die Cmdlets ["Get-CcCredential"](get-cccredential.md) und ["Set-CcCredential",](set-cccredential.md) und führen Sie die folgenden Schritte aus:
  
1. Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen: 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.
    
3. Starten Sie den Hostserver neu.
    
4. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials". \<CurrentUser\>.xml".
    
5. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance -Local" aus, um die Kennwörter nach der Beschreibung erneut einzugeben. Achten Sie darauf, dass Sie dasselbe Kennwort eingeben, das Sie vor der Cloud Connector-Bereitstellung eingegeben haben.
    
Standardmäßig verwenden VmAdmin und DomainAdmin dasselbe Kennwort wie CceService. Wenn sich die in Schritt 1 zurückgegebenen Kennwörter "DomainAdmin", "VMAdmin" und "CceService" unterscheiden, müssen Sie die folgenden Schritte ausführen:
  
1. Führen Sie Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.
    
2. Führen Sie Set-CcCredential -AccountType VmAdmin wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene VmAdmin-Kennwort ein. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aktualisieren des Kennworts für das CceService-Konto
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector, Version 2.0.1 und höher. 
  
Der Cloud Connector-Dienst führt den Cloud Connector-Verwaltungsdienst aus. Das CceService-Konto wird während der Cloud Connector Edition-Bereitstellung erstellt und in den folgenden Dateien gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml" und "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Um sicherzustellen, dass alle Appliances auf die Standortverzeichnisfreigabe zugreifen können, muss das Kennwort für das CceService-Konto für alle appliances, die innerhalb des Standorts bereitgestellt werden, identisch sein. Denken Sie dabei an Folgendes:
  
- Standardmäßig ist das CceService-Konto als "Kennwort läuft nie ab". Wenn Sie das Kennwort aktualisieren, empfiehlt Microsoft, diese Konfiguration zu behalten.
    
- Sie sollten das Kennwort während nicht spitzen Nutzungszeiträumen und außerhalb der Zeitfenster für automatische Updates für Bits oder Windows Updates aktualisieren. Wenn Sie das Kennwort aktualisieren, muss die Appliance geleert und neu gestartet werden, was einige Zeit in Anspruch nimmt. Durch den Neustart der Appliance werden die automatischen Updatevorgänge unterbrochen. 
    
- Wenn Sie das Kennwort für das CceService-Konto ändern, müssen Sie alle Anmeldeinformationen angeben und in der lokal gespeicherten Datei aktualisieren. 
    
Für jede Appliance, die zum selben PSTN-Standort gehört, müssen Sie Folgendes angeben: 
  
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

2. Führen Sie das Cmdlet Enter-CcUpdate aus, um die Appliance auszugleichen und in den manuellen Wartungsmodus zu verschieben.
    
3. Aktualisieren Sie das Kennwort des CceService-Kontos auf dem Hostserver.
    
4. Starten Sie den Hostserver neu.
    
5. Führen Sie das Cmdlet Restore-CcCredentials aus, um die Kennwörter nach der Beschreibung erneut einzugeben. 
    
    Geben Sie mit Ausnahme des CceService-Kontos unbedingt dasselbe Kennwort ein, das Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben. Geben Sie für das CceService-Konto Ihr neues Kennwort ein. Stellen Sie sicher, dass das neue Kennwort für das CceService-Konto für alle Appliances am PSTN-Standort identisch ist.
    
6. Standardmäßig verwenden VmAdmin und DomainAdmin dasselbe Kennwort wie CceService. Wenn sich die in Schritt 1 zurückgegebenen Kennwörter "DomainAdmin", "VMAdmin" und "CceService" unterscheiden, müssen Sie die folgenden Schritte ausführen:
    
7. Führen Sie Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
   - Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene DomainAdmin-Kennwort ein.
    
8. Führen Sie Set-CcCredential -AccountType VmAdmin wie folgt aus:
    
   - Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene VmAdmin-Kennwort ein. 
    
9. Führen Sie das Cmdlet Exit-CcUpdate aus, um die Appliance aus dem manuellen Wartungsmodus zu verschieben.
    
10. Nachdem Sie diese Schritte für alle Appliances am selben PSTN-Standort ausgeführt haben, löschen Sie die folgenden Dateien im Stammverzeichnis des Standorts:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Hinzufügen einer neuen SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Gehen Sie folgendermaßen vor, um Ihrer vorhandenen Cloud Connector-Bereitstellung eine neue SIP-Domäne (oder mehrere SIP-Domänen) hinzuzufügen:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 abgeschlossen haben und die Möglichkeit haben, DNS-Einträge hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365 oder Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne oder -Domänen.
    
3. Fordern Sie ein neues externes Edgezertifikat mit zusätzlichen SAN-Namen für "sip.domain" für jede SIP-Domäne an, die in Ihrer Cloud Connector-Konfiguration definiert ist. 
    
4. Legen Sie den Pfad für das neue externe Edgezertifikat wie folgt fest:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Folgen Sie den Anweisungen zum [Ändern der Konfiguration eines einzelnen Standorts](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder zum Ändern der Konfiguration mehrerer [Standorte.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Ändern der primären SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie die primäre SIP-Domäne in Ihrer Cloud Connector-Bereitstellung ändern müssen, gehen Sie wie folgt vor:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 abgeschlossen haben und die Möglichkeit haben, DNS-Einträge hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365 oder Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne.
    
3. Fordern Sie ein neues externes Edgezertifikat mit zusätzlichen SAN-Namen für "sip.domain" für jede SIP-Domäne an, die in Ihrer Cloud Connector-Konfiguration definiert ist. 
    
4. Legen Sie den Pfad für das neue externe Edgezertifikat wie folgt fest:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Entfernen Sie die Mandantenregistrierung für jede Appliance an einem Standort, indem Sie das folgende Cmdlet in Administrator-PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Entfernen Sie die Websiteregistrierung für jede Website, indem Sie das folgende Cmdlet in Skype for Business Online PowerShell ausführen:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Deinstallieren Sie jede Appliance, indem Sie das folgende Cmdlet in PowerShell-Administrator auf Cloud Connector ausführen:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registrieren Sie jede Appliance, indem Sie das folgende Cmdlet in PowerShell-Administrator auf Cloud Connector ausführen:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installieren Sie jede Appliance nacheinander, indem Sie das folgende Cmdlet in PowerShell-Administrator auf Cloud Connector ausführen:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Ersetzen des externen Edgezertifikats durch ein neues Zertifikat
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie das externe Edgezertifikat in Ihren Cloud Connector-Appliances ersetzen müssen, müssen Sie ein neues Edgezertifikat abrufen, die PFX-Datei mit dem privaten Schlüssel und der vollständigen Zertifikatkette vorbereiten und dann in jeder Appliance Folgendes ausführen:
  
1. Versetzen Sie die Appliance mithilfe des Cmdlets Enter-CcUpdate in den Wartungsmodus.
    
2. Führen Sie den folgenden Befehl aus: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Wenn das Kennwort des neuen Zertifikats mit dem alten identisch ist, ist der Import erfolgreich. Wenn das Kennwort anders ist, erhalten Sie eine Fehlermeldung, dass das Kennwort falsch ist, und Sie müssen das Kennwort zurücksetzen, indem Sie das Cmdlet Register-CcAppliance mit dem Parameter "-Local" ausführen und dann Schritt 2 wiederholen. 
    
4. Beenden Sie den Wartungsmodus der Appliance mithilfe des Cmdlets "Exit -CcUpdate".
