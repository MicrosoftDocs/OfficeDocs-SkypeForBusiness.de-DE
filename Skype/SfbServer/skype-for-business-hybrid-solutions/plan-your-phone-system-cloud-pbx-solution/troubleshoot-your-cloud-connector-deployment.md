---
title: Problembehandlung bei Ihrer Cloud Connector-Bereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: 7982cd153dcd9cc615201044c080479e9693550a0446b12c9a8a73c4366a9d57
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344574"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Problembehandlung bei Ihrer Cloud Connector-Bereitstellung

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.
 
Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
  
In diesem Thema werden Lösungen für häufige Probleme mit Cloud Connector Edition-Bereitstellungen beschrieben. Wenn Probleme mit Anrufen an und aus dem Telefonfestnetz auftreten, können Sie dies anhand der in diesem Thema beschriebenen Lösungen untersuchen.
  
Cloud Connector bietet integrierte Mechanismen zum automatischen Beheben einiger Probleme. Ein automatischer Erkennungsprozess sucht nach potenziellen Problemen mit den Cloud Connector-Appliances und ergreift nach Möglichkeit Korrekturmaßnahmen, um diese Probleme zu beheben, ohne dass ein Eingreifen des Administrators erforderlich ist. Der Erkennungsprozess funktioniert wie folgt:
  
- **Erkennungssequenz:** Der Cloud Connector-Verwaltungsdienst führt alle 60 Sekunden einen Prozess aus, um festzustellen, ob eine Appliance ausgefallen ist. In Cloud Connector, Version 2.0 und höher, verwendet der Erkennungsprozess den Skype for Business Corpnet-Switch zum Herstellen von PowerShell-Verbindungen mit den Cloud Connector-Computern. Für Versionen vor Version 2.0 verwendet der Erkennungsprozess den Cloud Connector-Verwaltungsschalter.
    
    > [!NOTE]
    > Damit die automatische Wiederherstellung erfolgreich ist, muss eine Netzwerkverbindung zwischen dem Host und virtuellen Computern über den Hostnetzwerk-Switch bestehen. Überprüfen Sie die Netzwerkkonnektivität, um sicherzustellen, dass die automatische Erkennung und Wiederherstellung erfolgreich ist. 
  
- **Überwachung:** Die folgenden Dienste werden in Cloud Connector, Version 2.0 und höher, überwacht:
    
  - Virtuelle Computer sind nicht mit den virtuellen Cloud Connector-Switches "Unternehmens" oder "Internet" verbunden.
    
  - Virtuelle Computer befinden sich in einem gespeicherten oder beendeten Status
    
  - Zentrale Verwaltungsserverdienste: REPLICA, MASTER
    
  - Vermittlungsserverdienste: REPLICA, RTCSRV und MEDSVC
    
  - Edgeserverdienste: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Eingehende Firewallregeln sind für CS RTCSRV auf dem Edgeserver deaktiviert, CS RTCMEDSRV auf dem Vermittlungsserver
    
    In Cloud Connector, Version 1.4.2, werden nur die folgenden Dienste überwacht:
    
  - Vermittlungsserverdienste: RTCSRV und MEDSVC
    
  - Edgeserverdienst: RTCSRV
    
- **Wiederherstellungsprozess:** Wenn überwachte Dienste ausgefallen sind, wird eine Appliance als heruntergestuft, und Dienste werden angehalten und manuell markiert, bis alle Probleme behoben werden können. Dadurch wird verhindert, dass Anrufe an eine Appliance weiterleiten, die zu Anruffehlern führen kann.
    
    Der Cloud Connector-Verwaltungsdienst versucht die automatische Wiederherstellung wie folgt:
    
  - Das anfängliche Wiederholungsintervall beträgt alle zehn Sekunden mit einem maximalen Intervall von einer Stunde.
    
  - Bei den ersten drei Wiederherstellungsversuchen beträgt die Intervalldauer 10 Sekunden. Ab dem vierten Wiederholungsversuch erhöht sich die Intervallzeit um das Doppelte der vorherigen Intervallzeit. Beispielsweise erfolgt der vierte Wiederholungsversuch in 20 Sekunden, der fünfte in 40 Sekunden usw. 
    
  - Wenn die maximale Intervalldauer von einer Stunde erreicht ist, werden wiederholungsversuche einmal pro Stunde fortgesetzt.
    
  - Wenn die Wiederherstellung erfolgreich ist, werden das Intervall und die Wiederholungsanzahl auf die ursprünglichen Werte festgelegt.
    
  - Wenn der Verwaltungsdienst neu gestartet wird, werden das Intervall und die Wiederholungsanzahl auf die ursprünglichen Werte zurückgesetzt.
    
## <a name="troubleshooting"></a>Problembehandlung

Nachfolgend finden Sie Lösungen für häufig auftretende Probleme:
  
- **Problem: Die Bereitstellung schlägt fehl oder reagiert nicht mehr, wenn die Bereitstellungsskripts ausgeführt werden. Nach der Anmeldung bei jedem virtuellen Computer fehlt oder ist die IP-Adresse für die Verwaltungs-/interne/externe NIC falsch.**
    
    **Auflösung:** Dieses Problem kann nicht automatisch behoben werden. NiCs können nicht zu virtuellen Computern hinzugefügt werden, während sie ausgeführt werden. Fahren Sie diese VMs herunter, und entfernen Sie sie im Hyper-V-Manager, und führen Sie dann die folgenden Cmdlets aus:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problem: Nachdem der Active Directory-Server und die Gesamtstruktur installiert wurden, wurde der CMS-Server und/oder Vermittlungsserver der Domäne nicht ordnungsgemäß beigetreten.**
    
    **Auflösung:** Führen Sie die folgenden Schritte aus, um dieses Problem zu beheben:
    
  - Melden Sie sich beim Active Directory-Server an, und stellen Sie sicher, dass die Domäne ordnungsgemäß erstellt wurde.
    
  - Melden Sie sich beim CMS/Vermittlungsserver an, und überprüfen Sie, ob auf der Netzwerk-NIC eine gültige IP-Adresse zugewiesen ist und ob gültige statische IP und DNS als IP-Adresse des AD-Servers konfiguriert sind.
    
  - Melden Sie sich beim CMS/Vermittlungsserver an, und öffnen Sie eine Eingabeaufforderung. Stellen Sie sicher, dass Sie den FQDN und die IP-Adresse des Active Directory-Servers pingen können. Wenn dies nicht der Fall ist, kann ein IP-Adresskonflikt auftreten. Versuchen Sie, eine neue IP für Active Directory zuzuweisen und DNS auf dem CMS/Vermittlungsserver entsprechend zu aktualisieren.
    
- **Problem: Sie erhalten die folgende Fehlermeldung: "Remove-VMSwitch: Fehler beim Entfernen des virtuellen Ethernet-Switches. Der virtuelle Switch "Cloud Connector Management Switch" kann nicht gelöscht werden, da er von virtuellen Computern verwendet oder untergeordneten Pools zugewiesen wird."**
    
    **Auflösung:** Der "Cloud Connector Management Switch" wurde nach der Bereitstellung nicht gelöscht. Wenn dieser Fehler auftritt, wechseln Sie zum Hyper-v-Manager, und stellen Sie sicher, dass noch kein virtueller Computer mit ihm verbunden ist. Wenn noch virtuelle Computer verbunden sind, trennen Sie sie, und löschen Sie den Verwaltungsschalter. Wenn der Verwaltungsschalter immer noch nicht gelöscht werden kann, starten Sie den Hostserver neu, und versuchen Sie es erneut.
    
- **Problem: Sie erhalten die folgende Fehlermeldung: "Dienst RTCMRAUTH konnte nicht gestartet werden. Stellen Sie sicher, dass der Dienst nicht deaktiviert ist."**
    
    > [!NOTE]
    > Dieses Problem gilt nur für Cloud Connector-Versionen vor 1.4.2. 
  
    Der Fehler beim Starten kann auch darauf zurückzuführen sein, dass dieser Front-End-Server zuvor fehlgeschlagen war (bei Verwendung des Computer-Failovers). Wenn dies der Fall ist, rufen Sie "Failback" auf (bei Verwendung des Computer-Failbacks).
    
    **Auflösung:** Dieses Problem tritt auf einem Edgeserver auf, wenn das Zertifikat der Stammzertifizierungsstelle oder das Zertifikat der Zwischenzertifizierungsstelle vom Edgeserver nicht als vertrauenswürdig eingestuft wird. Auch wenn das externe Zertifikat importiert werden kann, die Zertifikatkette jedoch unterbrochen ist. Unter dieser Bedingung kann der RTCMRAUTH- und/oder RTCSRV-Dienst nicht gestartet werden.
    
    Importieren Sie das Zertifikat der Stammzertifizierungsstelle und alle Zertifikate der Zwischenzertifizierungsstelle Ihres externen Zertifikats manuell in den Edgeserver, und starten Sie dann den Edgeserver neu. Nachdem die DIENSTE RTCMRAUTH und RTCSRV auf dem Edgeserver gestartet wurden, kehren Sie zu Ihrem Hostserver zurück, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problem: Der Hostserver wurde neu gestartet, als Windows Updates angewendet wurden und vom Server gewartete Aufrufe fehlschlagen.**
    
    **Auflösung:** Wenn Sie eine Hochverfügbarkeitsumgebung bereitgestellt haben, stellt Microsoft ein Cmdlet bereit, um einen Hostcomputer (Bereitstellungsinstanz) in die oder aus der aktuellen Topologie zu verschieben, wenn Sie Windows Update manuell überprüfen und installieren. Führen Sie dazu die folgenden Schritte aus:
    
1. Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie dann Folgendes aus:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Suchen Sie nach Updates, und installieren Sie alle verfügbaren Updates.
    
3. Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problem: Wenn ein Anruf von einem Skype for Business-Client mit einer PSTN-Nummer getätigt wird, kann der Anruf nicht durch Einladen einer anderen PSTN-Nummer an eine Konferenz eskaliert werden.**
    
    **Auflösung:** Informationen zum Beheben dieses Problems finden Sie unter [Konfigurieren des Onlinehybridvermittlungsservers Einstellungen.](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)
    
- **Problem: Beim Installieren des Active Directory-Servers wird eine Warnmeldung zu Windows Update angezeigt: "Windows automatische Aktualisierung ist nicht aktiviert. Um sicherzustellen, dass Ihre neu installierte Rolle oder Funktion automatisch aktualisiert wird, aktivieren Sie Windows Update."**
    
    **Auflösung:** Starten Sie eine Mandanten-Remote-PowerShell-Sitzung mit Skype for Business Mandantenadministratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die _EnableAutoUpdate-Konfiguration_ Ihrer Website zu überprüfen:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Wenn _"EnableAutoUpdate"_ auf **"True"** festgelegt ist, können Sie diese Warnmeldung ignorieren, da der CCEManagement-Dienst das Herunterladen und Installieren Windows Updates für virtuelle Computer und den Hostserver übernimmt. Wenn  _EnableAutoUpdate_ auf **False** festgelegt ist, führen Sie das folgende Cmdlet aus, um es auf **True** festzulegen.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Alternativ können Sie updates manuell suchen und installieren. Informationen dazu finden Sie im nächsten Abschnitt.
    
- **Problem: Sie erhalten eine Fehlermeldung: Appliance kann nicht registriert werden, da Ihre aktuelle Eingabe/Konfiguration oder konflikte \<SiteName\> \<ApplianceName\> mit vorhandenen \<Mediation Server FQDN\> \<Mediation Server IP Address\> Appliances auftreten. Entfernen Sie die Konfliktanwendung, oder aktualisieren Sie Ihre Eingabe-/Konfigurationsinformationen, und registrieren Sie sich erneut. ' beim Ausführen Register-CcAppliance, um die aktuelle Appliance online zu registrieren.**
    
    **Auflösung:** Werte für die \<ApplianceName\> , und müssen eindeutig sein und nur für eine \<Mediation Server FQDN\> \<Mediation Server IP Address\> Appliance-Registrierung verwendet werden. Stammt standardmäßig \<ApplianceName\> vom Hostnamen. \<Mediation Server FQDN\> und \<Mediation Server IP Address\> in der Konfigurations-Ini-Datei definiert.
    
    Beispiel: Using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10), you will have the conflict.
    
    Überprüfen Sie zunächst Ihre CloudConnector.ini-Datei im ApplianceRoot-Verzeichnisabschnitt. Sie erhalten \<SiteName\> und Werte in der \<Mediation Server FQDN\> \<Mediation Server IP Address\> Datei. \<ApplianceName\> ist der Name des Hostservers.
    
    Starten Sie zweitens Die Remote-PowerShell des Mandanten mit Ihren Skype for Business Mandantenadministratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die registrierten Appliances zu überprüfen.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Nachdem Sie Konflikte identifiziert haben, können Sie entweder die CloudConnector.ini Datei mit Informationen aktualisieren, die der registrierten Appliance entsprechen, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu beheben.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problem: Das Cmdlet Get-CcRunningVersion gibt einen leeren Wert zurück, wenn eine bereitgestellte Appliance auf dem Host ausgeführt wird.**
    
  **Auflösung:** Dies kann passieren, wenn Sie ein Upgrade von 1.3.4 oder 1.3.8 auf 1.4.1 durchführen. Nachdem Sie Version 1.4.1 mit dem .msi installiert haben, müssen Sie sie ausführen, `Register-CcAppliance` bevor Sie ein anderes Cmdlet ausführen. `Register-CcAppliance` migriert die module.ini Datei von %UserProfile%\CloudConnector zu %ProgramData%\CloudConnector. Wenn Sie es verpasst haben, wird eine neue module.ini im Ordner %ProgramData%\CloudConnector erstellt und die Informationen zur Ausführung/Sicherung der Version 1.3.4 oder 1.3.8 ersetzen.
    
  Vergleichen Sie module.ini Dateien im Ordner "%UserProfile%\CloudConnector" und "%ProgramData%\CloudConnector". Wenn Unterschiede bestehen, löschen Sie die module.ini Datei in %ProgramData%\CloudConnector, und führen Sie sie erneut  `Register-CcAppliance` aus. Sie können die Datei auch manuell auf die richtige Ausführungs- und Sicherungsversion ändern.
    
- **Problem: Nachdem Sie das Cmdlet Switch-CcVersion ausgeführt haben, um zu einer alten Version zu wechseln, die sich von der aktuellen Skriptversion unterscheidet, gibt es keine Hochverfügbarkeitsunterstützung für diese alte Version.**
    
    **Auflösung:** Sie haben beispielsweise ein Upgrade von 1.4.1 auf 1.4.2 durchgeführt. Die aktuelle Skriptversion, die durch Ausführen bestimmt werden `Get-CcVersion` kann, und die ausgeführte Version, die durch Ausführung bestimmt werden kann,  `Get-CcRunningVersion` sind 1.4.2. Wenn Sie jetzt ausführen, `Switch-CcVersion` um die ausgeführte Version wieder auf 1.4.1 umzustellen, gibt es keine Hochverfügbarkeitsunterstützung für diese alte Version.
    
    Um die vollständige Unterstützung für hohe Verfügbarkeit zu erhalten, wechseln Sie zurück zu 1.4.2, damit die ausgeführte Version und die Skriptversion identisch sind. Wenn Sie Probleme mit Ihrer 1.4.2-Bereitstellung haben, deinstallieren Sie sie, und installieren Sie sie so schnell wie möglich neu.
    
- **Problem: Zertifizierungsstellenzertifikate oder interne Zertifikate, die für die zentrale Verwaltung ausgestellt wurden, Store, vermittlungsserver und Edgeserver in Kürze ablaufen oder kompromittiert sind.**
    
    **Auflösung:** Skype for Business Zertifizierungsstellenzertifikate sind fünf Jahre lang gültig. Interne Zertifikate, die für die zentrale Store, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind zwei Jahre gültig.
    
    > [!NOTE]
    > In Cloud Connector, Version 2.0 und höher, wurde das Cmdlet Renew-CcServerCertificate in Update-CcServerCertificate geändert, und das Cmdlet Renew-CcCACertificate in Update-CcCACertificate geändert. 
  
    Wenn interne Zertifikate, die für die zentrale Store, den Vermittlungsserver und den Edgeserver ausgestellt wurden, in Kürze ablaufen oder kompromittiert sind, führen Sie das Cmdlet Renew-CcServerCertificate oder Update-CcServerCertificate aus, um Ihre Zertifikate zu erneuern.
    
    Wenn Zertifizierungsstellenzertifikate bald ablaufen, führen Sie das cmdlet Renew-CcCACertificate oder Update-CcCACertificate aus, um Ihre Zertifikate zu erneuern.
    
    **Wenn Zertifizierungsstellenzertifikate kompromittiert sind und nur eine Appliance am Standort vorhanden ist,** führen Sie die folgenden Schritte aus:
    
1. Führen Sie das Cmdlet Enter-CcUpdate aus, um Dienste auszugleichen und die Appliance in den Wartungsmodus zu versetzen.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Führen Sie die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:
    
    Für Cloud Connector-Versionen vor Version 2.0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Oder für Cloud Connector Version 2.0 und höher:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das cmdlet Export-CcRootCertificate aus der Appliance aus, und installieren Sie dann das exportierte Zertifikat auf Ihren PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway ausstellen.

   ```powershell
   Export-CcRootCertificate
   ```

4. Führen Sie das Cmdlet Exit-CcUpdate aus, um Dienste zu starten und den Wartungsmodus zu beenden.

   ```powershell
   Exit-CcUpdate
   ```


    **Wenn Zertifizierungsstellenzertifikate kompromittiert sind und mehrere Appliances am Standort** vorhanden sind, führen Sie die folgenden sequenziellen Schritte für jede Appliance am Standort aus.
    
    Microsoft empfiehlt, dass Sie diese Schritte in Zeiten ausführen, die nicht zu Spitzenzeiten verwendet werden.
    
1. Führen Sie in der ersten Appliance das Cmdlet Remove-CcCertificationAuthorityFile aus, um die Ca-Sicherungsdateien im Verzeichnis zu \<SiteRoot\> bereinigen.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Führen Sie das Cmdlet Enter-CcUpdate aus, um Dienste auszugleichen und jede Appliance in den Wartungsmodus zu versetzen.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Führen Sie in der ersten Appliance die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:
    
     Für Cloud Connector-Versionen vor Version 2.0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Oder für Cloud Connector Version 2.0 und höher:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Führen Sie in der ersten Appliance das folgende Cmdlet aus, um die Ca-Dateien im Ordner zu \<SiteRoot\> sichern.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Führen Sie auf allen anderen Appliances am selben Standort die folgenden Befehle aus, um die Ca-Sicherungsdateien zu nutzen, damit alle Appliances dasselbe Stammzertifikat verwenden und dann neue Zertifikate anfordern. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das cmdlet Export-CcRootCertificate von einer beliebigen Appliance am Standort aus, und installieren Sie dann das exportierte Zertifikat auf Ihren PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway ausstellen.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Führen Sie das Cmdlet Exit-CcUpdate aus, um Dienste zu starten und den Wartungsmodus zu beenden. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problem: Im Cloud Connector-Verwaltungsdienstprotokoll wird die folgende Fehlermeldung angezeigt: "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unerwartete Ausnahme beim Melden des Status an online: System.Management.Automation.CmdletInvocationException: Anmeldung für den Benutzer \<Global Tenant Admin\> fehlgeschlagen. Erstellen Sie ein neues Anmeldeinformationsobjekt, und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben. ---\>**
    
    **Auflösung:** Die Anmeldeinformationen des globalen Mandantenadministrators Microsoft 365 oder Office 365 wurden geändert, seit die Cloud Connector-Appliance registriert wurde. Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, führen Sie Folgendes über Administrator-PowerShell in der Host-Appliance aus:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problem: Nachdem Sie das Kennwort für das Hostserverkonto geändert haben, das Sie für die Bereitstellung verwendet haben, wird die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString : Schlüssel ist nicht gültig für die Verwendung im angegebenen Zustand." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log oder beim Ausführen des Cmdlets Get-CcCredential.**
    
    **Auflösung:** Alle Cloud Connector-Anmeldeinformationen werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml". Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
    
    **Wenn Sie Cloud Connector Version 1.4.2 ausführen,** generieren Sie alle Cloud Connector-Kennwörter neu, indem Sie die folgenden Schritte ausführen:
    
  1. Starten Sie den Hostserver neu.
    
  2. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials". \<CurrentUser\>.xml".
    
  3. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance -Local" aus, um die Kennwörter nach der Beschreibung erneut einzugeben. Geben Sie dieselben Kennwörter ein, die Sie vor der Cloud Connector-Bereitstellung eingegeben haben.
    
     **Wenn Sie Cloud Connector Version 2.0 oder höher ausführen,** generieren Sie alle Cloud Connector-Kennwörter neu, indem Sie die folgenden Schritte ausführen:
    
  4. Starten Sie den Hostserver neu.
    
  5. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials". \<CurrentUser\>.xml" .
    
  6. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance -Local" aus, um die Kennwörter nach der Beschreibung erneut einzugeben. 
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector Version 1.4.2 generiert wurde, verwenden Sie bei Aufforderung das VMAdmin-Kennwort für das CceService-Kennwort. Geben Sie das gleiche Kennwort ein, das Sie vor der Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde und die Kennwörter "DomainAdmin" und "VMAdmin" unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:
    
  7. Führen Sie Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
  8. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
  9. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das zuvor verwendete DomainAdmin-Kennwort ein.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 2.0 oder höher, generiert wurde, verwenden VmAdmin und DomainAdmin standardmäßig dasselbe Kennwort wie CceService. Wenn Sie die Kennwörter "DomainAdmin" und "VMAdmin" geändert haben, müssen Sie die folgenden Schritte ausführen:
    
  10. Führen Sie Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das zuvor verwendete DomainAdmin-Kennwort ein.
    
  11. Führen Sie Set-CcCredential -AccountType VmAdmin wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das zuvor verwendete VmAdmin-Kennwort ein. 
    
- **Problem: Bei Cloud Connector, Version 2.1 und höher, erhalten Sie beim Ausführen von Register-CcAppliance oder anderen Cmdlets in der Appliance eine Fehlermeldung wie z. B.: "Für Each-Object: Die Eigenschaft 'Common' kann in diesem Objekt nicht gefunden werden. Stellen Sie sicher, dass die Eigenschaft vorhanden ist. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Auflösung:** Cloud Connector 2.1 und höher erfordert .NET Framework 4.6.1 oder höher. Aktualisieren Sie .NET Framework für die Appliance auf Version 4.6.1 oder höher, und führen Sie die Cmdlets erneut aus.

- **Problem: Bei Cloud Connector Edition 2.1 wird beim Ausführen von Install-CcAppliance eine Fehlermeldung angezeigt, z. B.: "Fehler beim Installieren einer neuen Instanz mit Fehler: "Status" kann nicht festgelegt werden, da nur Zeichenfolgen als Werte zum Festlegen von XmlNode-Eigenschaften verwendet werden können"**

   **Auflösung:** Fügen Sie in Cloudconnector.ini im Abschnitt [Common] die Konfiguration "State" wie folgt hinzu: CountryCode=US State=WA City=Redmond

   Es ist nicht zwingend erforderlich, dass die Zeile "State" einen Wert aufweist, die Zeile "State" kann jedoch nicht aus der Cloudconnector.ini-Datei entfernt werden.

- **Problem: Sie erhalten die folgende Fehlermeldung "Dismount-WindowsImage: Dismount-WindowsImage fehlgeschlagen. Fehlercode = 0xc1550115" beim Installieren oder Aktualisieren von Cloud Connector Edition.**
    
    **Auflösung:** Starten Sie eine PowerShell-Konsole als Administrator, führen Sie "DISM -Cleanup-Wim'" aus. Dadurch werden alle problematischen Bilder bereinigt. Führen Sie Install-CcAppliance erneut aus, oder warten Sie, bis die Bits automatisch aktualisiert werden.
    
- **Problem: Bereitstellung der ersten Cloud Connector-Appliance in einer HA-Umgebung schlägt fehl**
    
    **Auflösung:** Welche Schritte Sie ausführen, hängt davon ab, warum die Bereitstellung fehlgeschlagen ist:
    
  - Wenn die erste Cloud Connector-Appliance fehlschlägt und Sie den Grund für den Fehler nicht ermitteln können, müssen Sie die Appliance erneut installieren, bis die Bereitstellung erfolgreich war, und dann die anderen Appliances installieren.
    
  - Wenn die erste Cloud Connector-Appliance mit einem kleineren Problem fehlschlägt, z. B. einem externen Zertifikatproblem, können Sie das Problem möglicherweise beheben, ohne die Appliance erneut zu installieren. Anschließend können Sie die Bereitstellung mithilfe von Mandanten-Remote-PowerShell wie folgt als erfolgreich markieren. (Sie können auch die folgenden Schritte ausführen, wenn die erste Bereitstellung erfolgreich war. Aus irgendeinem Grund meldet Cloud Connector die Bereitstellung jedoch nicht als erfolgreich.)
    
  - Führen Sie das Cmdlet Get-CsHybridPSTNAppliance aus, um die Identität (GUID) der ersten Cloud Connector-Appliance abzurufen.
    
  - Führen Sie die Set-CsCceApplianceDeploymentStatus wie folgt aus, um die Appliance als erfolgreich bereitgestellt zu kennzeichnen:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problem: Sie müssen Windows Updates manuell auf dem Hostserver oder auf virtuellen Computern suchen und installieren.**
    
   **Auflösung:** Es wird empfohlen, automatisierte Betriebssystemupdates zu nutzen, die von Skype for Business Cloud Connector Edition bereitgestellt werden. Nachdem eine Appliance für die Onlineverwaltung registriert und das automatische Betriebssystemupdate aktiviert wurde, überprüfen und installieren der Hostserver und die virtuellen Computer Windows Updates automatisch gemäß den Einstellungen des Fensters für die BS-Updatezeit.
    
   Wenn Sie Windows Updates manuell suchen und installieren müssen, führen Sie die Schritte in diesem Abschnitt aus, die für Ihren Bereitstellungstyp gelten. Sie sollten planen, sowohl den Hostserver als auch die darauf ausgeführten virtuellen Computer gleichzeitig zu aktualisieren, um die für die Updates erforderliche Ausfallzeiten zu minimieren.
    
   Wenn Sie möchten, können Sie einen Windows Server Update Services (WSUS)-Server verwenden, um Updates für Cloud Connector-Server bereitzustellen. Achten Sie darauf, das Windows Update so zu konfigurieren, dass **es nicht** automatisch installiert wird.
    
   Informationen zum manuellen Aktualisieren Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.
    
- **Problem: Wenn Cloud Connector auf einen neuen Build aktualisiert wird, werden Cloud Connector-Cmdlets nicht aktualisiert.** Dies geschieht manchmal, wenn ein PowerShell-Fenster geöffnet bleibt, wenn eine automatische Aktualisierung erfolgt.
    
  **Auflösung:** Zum Laden der aktualisierten Cmdlets können Sie einen der folgenden Schritte ausführen:
    
   - Schließen Sie PowerShell in der Cloud Connector-Appliance, und öffnen Sie PowerShell erneut.
    
     - Sie können auch Import-Module CloudConnector -Force ausführen. 
 
-   **Problem: "Der Begriff "Stop-CsWindowsService" wird nicht als Name eines Cmdlets, einer Funktion, einer Skriptdatei oder eines funktionsfähigen Programms erkannt." Fehler beim Versuch, Enter-CcUpdate Cmdlet auszuführen.**

    **Auflösung:** Löschen Sie die Datei $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell erstellt diese Datei als Cache von Cmdlets aus gefundenen Modulen, sodass nicht jedes Mal alle Module erneut analysiert werden müssen, da dies die Dinge sehr langsam machen würde. Höchstwahrscheinlich ist eine Dateibeschädigung aufgetreten, die beim Zurücklesen aus diesem Cache zu irreführenden Ergebnissen für PowerShell geführt hat.

-   **Problem: "Import-Module CloudConnector" generiert den Fehler "Import-Module: Das angegebene Modul "CloudConnector" wurde nicht geladen, da keine gültige Moduldatei in einem Modulverzeichnis gefunden wurde"**

    **Lösung:**
    - Überprüfen Sie, ob das CloudConnector-Modul unter "c:\Program Files\WindowsPowerShell\Modules" vorhanden ist.
    
    - Nach dem Überprüfen, dass das CloudConnector-Modul unter diesem Speicherort vorhanden ist, kann die PSModulePath-Umgebungsvariable, die den Pfad zu den Speicherorten der Module speichert, geändert werden:
    
     a. Temporäre Änderung: Starten Sie PowerShell als Administrator, und führen Sie den folgenden Befehl aus: $env:PSModulePath = $env:PSModulePath + "; C:\Programme\WindowsPowerShell\Module\"
        
     b. Starten Sie PowerShell für beständige Änderungen als Administrator, und führen Sie die folgenden Befehle nacheinander aus: $CurrentValue = [Umgebung]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Manuelles Installieren Windows Updates

Wenn Sie keine automatischen Updates in Ihrer Umgebung verwenden möchten, führen Sie die folgenden Schritte aus, um Windows Updates manuell zu suchen und anzuwenden. Für die Überprüfung und Installation Windows Updates ist möglicherweise ein Serverneustart erforderlich. Wenn ein Hostserver neu gestartet wird, können Benutzer Cloud Connector nicht verwenden, um Anrufe zu tätigen oder zu empfangen. Sie können Updates manuell suchen und installieren, um zu steuern, wann die Updates stattfinden, und dann die Computer bei Bedarf neu starten, wenn Sie sich entscheiden, Dienstunterbrechungen zu vermeiden.
  
Um manuell nach Updates zu suchen, stellen Sie eine Verbindung mit jedem Hostserver her, und öffnen Sie die **Systemsteuerung.** Wählen Sie **"System and Security \> Windows Update"** aus, und verwalten Sie dann die Updates und Serverneustarts entsprechend Ihrer Umgebung.
  
- Wenn nur eine Appliance am Standort vorhanden ist, stellen Sie eine Verbindung zu jedem virtuellen Computer her, und öffnen Sie die **Systemsteuerung.** Wählen Sie **"System and Security \> Windows Update"** aus, und konfigurieren Sie dann die Updates und Serverneustarts nach Bedarf.
    
- Wenn sich mehrere Appliances am Standort befinden, können Benutzer während der Updates nicht auf die Instanz zugreifen, die aktualisiert und neu gestartet wird. Benutzer stellen eine Verbindung mit anderen Instanzen in der Bereitstellung her, bis alle virtuellen Computer und alle Skype for Business Dienste auf den virtuellen Computern gestartet werden, nachdem die Updates abgeschlossen sind. Um mögliche Dienstunterbrechungen zu vermeiden, können Sie die Instanz aus HA entfernen, während Sie die Updates anwenden, und sie nach Abschluss wiederherstellen. Gehen Sie hierzu folgendermaßen vor:
    
1. Öffnen Sie auf jedem Hostserver eine PowerShell-Konsole als Administrator.
    
2. Entfernen Sie die Instanz aus HA mit dem folgenden Cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und den virtuellen Computer neu zu starten.
    
4. Legen Sie die Instanz mit dem folgenden Cmdlet wieder auf HA fest:
    
   ```powershell
   Exit-CcUpdate
   ```

Führen Sie für Bereitstellungen mit mehreren Standorten die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, und wenden Sie Updates auf jeweils einen Standort an.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Tipps beim Installieren von Antivirensoftware auf dem Cloud Connector-Hostcomputer

Wenn Sie Antivirensoftware auf dem Cloud Connector-Hostcomputer installieren müssen, müssen Sie die folgenden Ausschlüsse hinzufügen:
  
- Lokales Appliance-Verzeichnis auf jedem Computer.
    
- Remotestandortverzeichnis auf jedem Computer.
    
- Das lokale Standortverzeichnis auf dem Computer hostet den freigegebenen Websitestammordner.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Der Prozess Microsoft.Rtc.CCE.ManagementService.exe.