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
ms.openlocfilehash: 7fdfdd5ac5a76ebbc3ac58e12a69e2e3af1330cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109171"
---
# <a name="modify-the-configuration-of-an-existing-cloud-connector-deployment"></a>Ändern der Konfiguration einer vorhandenen Cloud Connector-Bereitstellung

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

Führen Sie die Schritte in diesem Thema aus, um die Konfiguration einer vorhandenen Skype for Business Cloud Connector Edition 1.4.1 oder höher zu ändern. 
  
## <a name="modify-the-configuration-of-a-single-site"></a>Ändern der Konfiguration eines einzelnen Standorts
<a name="BKMK_SIngleSite"> </a>

Wenn sich am Standort nur eine Appliance befindet, können Sie die CloudConnector.ini ändern und die Bereitstellung erneut starten, wenn Sie die Konfigurationseinstellungen nach der Bereitstellung der Appliance ändern möchten.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf dem Hostserver zu deinstallieren: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance zu aufheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie CloudConnector.ini datei im Appliance Directory.
    
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

Wenn sich mehrere Appliances am Standort befindet, müssen Sie die folgenden Schritte ausführen, die datei CloudConnector.ini ändern und die Appliances nach und nach erneut bereitstellen.
  
1. Führen Sie das folgende Cmdlet aus, um alle vorhandenen virtuellen Computer auf der aktuellen Appliance zu deinstallieren: 
    
   ```powershell
   Uninstall-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet aus, um die Registrierung der Appliance zu aufheben:
    
   ```powershell
   Unregister-CcAppliance
   ```

3. Aktualisieren Sie CloudConnector.ini datei im Appliance Directory.
    
4. Führen Sie das folgende Cmdlet aus, um die Konfiguration zu aktualisieren: (Dieser Schritt gilt nur für Version 2; für frühere Versionen fahren Sie mit dem nächsten Schritt fort.)
    
   ```powershell
   Import-CcConfiguration 
   ```

5. Führen Sie das folgende Cmdlet aus, um die Appliance erneut zu registrieren:
    
   ```powershell
   Register-CcAppliance
   ```

6. Führen Sie das folgende Cmdlet auf allen anderen Appliances am Standort aus, um die neueste Konfiguration zu finden:
    
   ```powershell
   Publish-CcAppliance
   ```

7. Führen Sie das folgende Cmdlet aus, um Cloud Connector auf der aktuellen Appliance erneut zu bereitstellen:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="modify-the-configuration-of-multiple-sites"></a>Ändern der Konfiguration mehrerer Websites
<a name="BKMK_MultipleSites"> </a>

Um die Konfiguration für mehrere Standorte in einer Bereitstellung zu ändern, führen Sie die Schritte für einen einzelnen Standort aus, indem Sie einen Standort gleichzeitig aktualisieren.
  
## <a name="modify-the-configuration-of-your-microsoft-365-or-office-365-organization-to-enable-automatic-updates"></a>Ändern der Konfiguration Ihrer Microsoft 365- oder Office 365-Organisation, um automatische Updates zu aktivieren
<a name="BKMK_MultipleSites"> </a>

Um automatische Updates des Betriebssystems und automatische Bits-Updates zu aktivieren, müssen Sie das Skype for Business-Mandantenadministratorkonto für die Onlineverwaltung verwenden und die Mandanten-Remote-PowerShell wie folgt verwenden.
  
Wenn Sie automatische Updates des Betriebssystems oder automatische Bits-Updates deaktiviert haben, fehlen ihrem Host und dem virtuellen Computer möglicherweise wichtige Windows-Updates, und Cloud Connector aktualisiert nicht automatisch auf die neue Version. Es wird dringend empfohlen, automatische Updates zu aktivieren.
  
1. Die EnableAutoUpdate-Eigenschaft der Website muss auf true (Standardwert) festgelegt werden. Führen Sie das folgende Cmdlet aus, um sicherzustellen, dass EnableAutoUpdate auf true festgelegt ist:
    
   ```powershell
   Get-CsHybridPSTNSite -Identity <SiteName>
   ```

2. Erstellen Sie das Zeitfenster für automatische Updates für den Mandanten.
    
    Das Zeitfenster kann täglich, wöchentlich und monatlich sein. Alle Zeitfenster benötigen eine Startzeit und eine Dauer.
    
   - Für ein tägliches Zeitfenster sind nur Startzeit und Dauer erforderlich. 
    
   - Für ein wöchentliches Zeitfenster werden Wochentage benötigt, die einen einzelnen Tag oder mehrere Tage sein können.
    
   - Für ein monatliches Zeitfenster können zwei Typen verwendet werden. Der erste Typ ist, den Tag des Monats anzugeben, der ein einzelner Tag sein kann. Der zweite Typ besteht in der Angabe der Wochen des Monats sowie der Wochentage, bei denen es sich bei beiden um ein einzelnes Element oder mehrere Elemente handelt.
    
   - Für jeden Mandanten können 20 Zeitfenster definiert sein. Das Standardzeitfenster wird für einen neuen Mandanten als Standardzeitfenster für Betriebssystemupdates und Bits-Updates erstellt. Führen Sie die folgenden Cmdlets aus, um das tägliche, wöchentliche oder monatliche Zeitfenster zu festlegen:
    
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

   - Weisen Sie der Website Aktualisierungszeitfenster zu. 
    
     Die Zeitfenster für Bits- und Betriebssystemaktualisierungszeit werden separat konfiguriert. Beiden fenstern kann ein- oder mehrere Zeitfenster zugewiesen werden. Jedes Zeitfenster kann verschiedenen Websites und einem anderen Zweck zugewiesen werden (Bits-Update und Betriebssystemupdate). Führen Sie das folgende Cmdlet aus, um das Zeitfenster für die Website festlegen: 
    
   ```powershell
   Set-CsHybridPSTNSite -Identity <SiteName> -BitsUpdateTimeWindow @{add="MidDayOfMonth","WeekdayNight"} -OsUpdateTimeWindow @{replace="Night"}
   ```

## <a name="update-the-dedicated-tenant-admin-credentials"></a>Aktualisieren der dedizierten Mandantenadministratoranmeldeinformationen
<a name="BKMK_MultipleSites"> </a>

Administrative Änderungen in der Microsoft 365- oder Office 365-Organisation für Cloud Connector werden über ein Konto mit den erforderlichen Berechtigungen vorgenommen. In Cloud Connector-Versionen vor 2.0 ist dieses Konto ein dediziertes globales Mandantenadministratorkonto. In Cloud Connector, Version 2.0 und höher, kann es sich bei diesem Konto um ein Microsoft 365- oder Office 365-Konto mit Skype for Business-Administratorrechten sein.
  
Wenn sich die Anmeldeinformationen Ihres Administratorkontos in Microsoft 365 oder Office 365 ändern, müssen Sie auch die lokal zwischengespeicherten Anmeldeinformationen in Cloud Connector aktualisieren, indem Sie den folgenden Administrator-PowerShell-Befehl für jede cloudconnector-Appliance ausführen, die Sie bereitgestellt haben:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="update-the-password-for-the-host-server"></a>Aktualisieren des Kennworts für den Hostserver
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector, Version 2.0 und höher. 
  
Alle Cloud #A0 werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml". Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
  
Verwenden Sie die [Cmdlets Get-CcCredential](get-cccredential.md) und [Set-CcCredential,](set-cccredential.md) um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, und führen Sie die folgenden Schritte aus:
  
1. Führen Sie die folgenden Befehle aus, um die Kennwörter abzurufen, die Sie später benötigen: 
    
   - Get-CcCredential -AccountType DomainAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType VMAdmin -DisplayPassword
    
   - Get-CcCredential -AccountType CceService -DisplayPassword
    
2. Ändern Sie das Kennwort Ihres Kontos auf dem Hostserver.
    
3. Starten Sie den Hostserver neu.
    
4. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".
    
5. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance -Local" aus, um die Kennwörter nach der Beschreibung erneut ein eingeben zu können. Stellen Sie sicher, dass Sie dasselbe Kennwort eingeben, das Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben.
    
Standardmäßig verwenden VmAdmin und DomainAdmin dasselbe Kennwort wie CceService. Wenn sich die in Schritt 1 zurückgegebenen Domänenadmin-, VMAdmin- und CceService-Kennwörter unterscheiden, müssen Sie die folgenden Schritte ausführen:
  
1. Führen Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der Anmeldeinformationen für das neue Konto aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene Domänenadmin-Kennwort ein.
    
2. Führen Set-CcCredential -AccountType VmAdmin wie folgt aus:
    
1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
2. Wenn Sie zur Eingabe der Anmeldeinformationen für das neue Konto aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene VmAdmin-Kennwort ein. 
    
## <a name="update-the-password-for-the-cceservice-account"></a>Aktualisieren des Kennworts für das CceService-Konto
<a name="BKMK_UpdatePassword"> </a>

> [!NOTE]
> Dieser Abschnitt gilt für Cloud Connector, Version 2.0.1 und höher. 
  
Der Cloud Connector-Dienst führt den Cloud Connector-Verwaltungsdienst aus. Das CceService-Konto wird während der Cloud Connector \Programdata\Cloudconnector\credentials..CceService.xml erstellt und in den folgenden Dateien gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" und "%SystemDrive%\Programdata\Cloudconnector\credentials..CceService.xml".
  
Damit alle Appliances auf die Websiteverzeichnisfreigabe zugreifen können, muss das Kennwort für das CceService-Konto für alle appliances identisch sein, die innerhalb des Standorts bereitgestellt werden. Denken Sie dabei an Folgendes:
  
- Standardmäßig ist das CceService-Konto als "Kennwort läuft nie ab" konfiguriert. Wenn Sie das Kennwort aktualisieren, empfiehlt Microsoft, diese Konfiguration zu behalten.
    
- Sie sollten das Kennwort zu Zeiten ohne Spitzenauslastung und außerhalb der Zeitfenster für automatische Updates für Bits oder Windows-Updates aktualisieren. Wenn Sie das Kennwort aktualisieren, muss die Appliance entleert und neu gestartet werden. Dies dauert einige Zeit. Durch den Neustart der Appliance werden automatische Aktualisierungsvorgänge unterbrochen. 
    
- Wenn Sie das Kennwort für das CceService-Konto ändern, müssen Sie alle Anmeldeinformationen angeben und in der lokal gespeicherten Datei aktualisieren. 
    
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

2. Führen Sie Enter-CcUpdate cmdlet aus, um die Appliance zu entleeren und in den manuellen Wartungsmodus zu verschieben.
    
3. Aktualisieren Sie das Kennwort des CceService-Kontos auf dem Hostserver.
    
4. Starten Sie den Hostserver neu.
    
5. Führen Sie Restore-CcCredentials cmdlet aus, um die Kennwörter nach der Beschreibung erneut ein eingeben. 
    
    Stellen Sie sicher, dass Sie dasselbe Kennwort eingeben, das Sie zuvor für die Cloud Connector-Bereitstellung mit Ausnahme des CceService-Kontos eingegeben haben. Geben Sie für das CceService-Konto Ihr neues Kennwort ein. Stellen Sie sicher, dass das neue Kennwort für das CceService-Konto für alle Appliances am PSTN-Standort identisch ist.
    
6. Standardmäßig verwenden VmAdmin und DomainAdmin dasselbe Kennwort wie CceService. Wenn sich die in Schritt 1 zurückgegebenen Domänenadmin-, VMAdmin- und CceService-Kennwörter unterscheiden, müssen Sie die folgenden Schritte ausführen:
    
7. Führen Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
   - Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der Anmeldeinformationen für das neue Konto aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene Domänenadmin-Kennwort ein.
    
8. Führen Set-CcCredential -AccountType VmAdmin wie folgt aus:
    
   - Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
   - Wenn Sie zur Eingabe der Anmeldeinformationen für das neue Konto aufgefordert werden, geben Sie das Kennwort für das in Schritt 1 zurückgegebene VmAdmin-Kennwort ein. 
    
9. Führen Sie Exit-CcUpdate cmdlet aus, um die Appliance aus dem manuellen Wartungsmodus zu verschieben.
    
10. Nachdem Sie diese Schritte für alle Appliances am gleichen PSTN-Standort abgeschlossen haben, löschen Sie die folgenden Dateien im Stammverzeichnis des Standorts:
    
    - CcLockFile
    
    - Site_\<Edge External Sip Pool fqdn\>
    
    - Tenant_\<Edge External Sip Pool fqdn\>
    
    - TenantConfigLock_\<Edge External Sip Pool fqdn\>
    
## <a name="add-a-new-sip-domain"></a>Hinzufügen einer neuen SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Gehen Sie wie folgt vor, um ihrer vorhandenen Cloud Connector-Bereitstellung eine neue SIP-Domäne (oder mehrere SIP-Domänen) hinzuzufügen:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 ausgeführt haben und die Möglichkeit haben, DNS-Einträge hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter Hinzufügen einer Domäne zu [Microsoft 365 oder Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne oder -Domänen.
    
3. Fordern Sie ein neues externes Edgezertifikat mit zusätzlichen SAN-Namen für sip.domain für jede IN Ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an. 
    
4. Legen Sie den Pfad für das neue externe Edgezertifikat wie folgt dar:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Befolgen Sie die [Anweisungen, um die Konfiguration eines einzelnen Standorts zu ändern](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_SIngleSite) oder [die Konfiguration mehrerer Websites zu ändern.](modify-the-configuration-of-an-existing-cloud-connector-deployment.md#BKMK_MultipleSites)
    
## <a name="modify-the-primary-sip-domain"></a>Ändern der primären SIP-Domäne
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie die primäre SIP-Domäne in Ihrer Cloud Connector-Bereitstellung ändern müssen, gehen Sie wie folgt vor:
  
1. Stellen Sie sicher, dass Sie die Schritte zum Aktualisieren Ihrer Domäne in Microsoft 365 oder Office 365 ausgeführt haben und die Möglichkeit haben, DNS-Einträge hinzuzufügen. Weitere Informationen zum Einrichten Ihrer Domäne in Microsoft 365 oder Office 365 finden Sie unter Hinzufügen einer Domäne zu [Microsoft 365 oder Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
    
2. Aktualisieren Sie die Cloud Connector-Konfigurationsdatei mit der neuen SIP-Domäne.
    
3. Fordern Sie ein neues externes Edgezertifikat mit zusätzlichen SAN-Namen für sip.domain für jede IN Ihrer Cloud Connector-Konfiguration definierte SIP-Domäne an. 
    
4. Legen Sie den Pfad für das neue externe Edgezertifikat wie folgt dar:
    
   ```powershell
   Set-CcExternalCertificateFilePath -Path <Full path to External certificate>
   ```

5. 
    
    Entfernen Sie die Mandantenregistrierung für jede Appliance an einem Standort, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Unregister-CcAppliance
   ```

6. 
    
    Entfernen Sie die Websiteregistrierung für jede Website, indem Sie das folgende Cmdlet in Skype for Business Online PowerShell ausführen:
    
   ```powershell
   Remove-CsHybridPSTNSite
   ```

7. 
    
    Deinstallieren Sie jede Appliance, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Uninstall-CcAppliance
   ```

8. 
    
     Registrieren Sie jede Appliance, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Register-ccAppliance
   ```

9. 
    
     Installieren Sie jede Appliance nach dem anderen, indem Sie das folgende Cmdlet in Administrator PowerShell auf Cloud Connector ausführen:
    
   ```powershell
   Install-CcAppliance
   ```

## <a name="replace-the-external-edge-certificate-with-a-new-certificate"></a>Ersetzen des externen Edgezertifikats durch ein neues Zertifikat
<a name="BKMK_UpdatePassword"> </a>

Wenn Sie das externe Edgezertifikat in Ihren Cloud Connector-Appliances ersetzen müssen, müssen Sie ein neues Edgezertifikat abrufen, die PFX-Datei mit dem privaten Schlüssel und der vollständigen Zertifikatkette vorbereiten und dann für jede Appliance die folgenden Schritte tun:
  
1. Setzen Sie die Appliance mithilfe des cmdlets Enter-CcUpdate Wartungsmodus ein.
    
2. Führen Sie den folgenden Befehl aus: 
    
   ```powershell
   Set-CcExternalCertificateFilePath -Target EdgeServer -Path <Full file path of new certificate including filename> -Import
   ```

3. 
    
    Wenn das Kennwort des neuen Zertifikats mit dem alten identisch ist, ist der Import erfolgreich. Wenn das Kennwort anders ist, wird eine Fehlermeldung angezeigt, dass das Kennwort falsch ist, und Sie müssen das Kennwort zurücksetzen, indem Sie das cmdlet Register-CcAppliance mit dem Parameter -Local ausführen und dann Schritt 2 wiederholen. 
    
4. Entfernen Sie die Appliance mithilfe des Exit -CcUpdate-Cmdlets aus dem Wartungsmodus.
