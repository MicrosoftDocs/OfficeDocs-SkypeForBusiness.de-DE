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
description: Behandeln Sie Die Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094823"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Problembehandlung bei Ihrer Cloud Connector-Bereitstellung

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)
 
Behandeln Sie Die Cloud Connector Edition-Bereitstellung.
  
In diesem Thema werden Lösungen für häufige Probleme mit Cloud Connector Edition-Bereitstellungen beschrieben. Wenn Probleme mit Anrufen an und über das Festnetz (Public Switched Telephone Network, PSTN) auftreten, können Sie die in diesem Thema beschriebenen Lösungen untersuchen.
  
Cloud Connector bietet integrierte Mechanismen zum automatischen Beheben einiger Probleme. Ein automatischer Erkennungsprozess sucht nach potenziellen Problemen mit den Cloud Connector-Appliances und führt nach Möglichkeit Korrekturmaßnahmen aus, um diese Probleme ohne Administratoreingriff zu beheben. Der Erkennungsprozess funktioniert wie folgt:
  
- **Erkennungssequenz:** Der Cloud Connector-Verwaltungsdienst führt alle 60 Sekunden einen Prozess aus, um zu ermitteln, ob eine Appliance aus ist. In Cloud Connector, Version 2.0 und höher, verwendet der Erkennungsprozess den Switch Skype for Business Corpnet zum Herstellen von #A0 mit den Cloud Connector-Computern. Für Versionen vor 2.0 verwendet der Erkennungsprozess den Cloud Connector-Verwaltungsschalter.
    
    > [!NOTE]
    > Damit die automatische Wiederherstellung erfolgreich ausgeführt werden kann, muss eine Netzwerkverbindung zwischen dem Host und virtuellen Computern über den Hostnetzwerkschalter besteht. Überprüfen Sie unbedingt die Netzwerkkonnektivität, um sicherzustellen, dass die automatische Erkennung und Wiederherstellung erfolgreich ist. 
  
- **Überwachung:** Die folgenden Dienste werden in Cloud Connector, Version 2.0 und höher, überwacht:
    
  - Virtuelle Computer sind nicht mit den virtuellen Switches des Cloud Connector Corporate oder Internet verbunden
    
  - Virtuelle Computer befinden sich in einem gespeicherten oder beendeten Status
    
  - Zentrale Verwaltungsserverdienste: REPLICA, MASTER
    
  - Vermittlungsserverdienste: REPLICA, RTCSRV und MEDSVC
    
  - Edgeserverdienste: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Eingehende Firewallregeln sind für CS RTCSRV auf dem Edgeserver, CS RTCMEDSRV auf dem Vermittlungsserver deaktiviert.
    
    In Cloud Connector, Version 1.4.2, werden nur die folgenden Dienste überwacht:
    
  - Vermittlungsserverdienste: RTCSRV und MEDSVC
    
  - Edgeserverdienst: RTCSRV
    
- **Wiederherstellungsprozess:** Wenn überwachte Dienste nicht mehr verwendet werden, wird eine Appliance nach unten markiert, und Dienste werden angehalten und manuell markiert, bis alle Probleme behoben werden können. Dadurch wird verhindert, dass Anrufe an eine Appliance geroutet werden, die Anruffehler verursachen kann.
    
    Der Cloud Connector-Verwaltungsdienst wird die automatische Wiederherstellung wie folgt wiederholen:
    
  - Das anfängliche Wiederholungsintervall ist alle zehn Sekunden mit einer maximalen Intervallzeit von einer Stunde.
    
  - Bei den ersten drei Wiederherstellungsversuchen beträgt die Intervallzeit 10 Sekunden. Ab dem vierten Wiederholungsversuch erhöht sich die Intervallzeit um das Zweifache der vorherigen Intervallzeit. Der vierte Wiederholungsversuch erfolgt beispielsweise in 20 Sekunden, der fünfte in 40 Sekunden und so weiter. 
    
  - Wenn die maximale Intervallzeit von einer Stunde erreicht ist, werden wiederholungsversuche einmal pro Stunde fortgesetzt.
    
  - Wenn die Wiederherstellung erfolgreich ist, werden die Intervall- und Wiederholungsanzahlen auf ihre Anfangswerte festgelegt.
    
  - Wenn der Verwaltungsdienst neu gestartet wird, werden die Intervall- und Wiederholungsanzahl auf ihre Anfangswerte zurückgesetzt.
    
## <a name="troubleshooting"></a>Problembehandlung

Nachfolgend finden Sie Lösungen für häufig aufgetretene Probleme:
  
- **Problem: Die Bereitstellung schlägt fehl oder reagiert nicht mehr, wenn die Bereitstellungsskripts ausgeführt werden. Nach der Anmeldung bei jedem virtuellen Computer fehlt oder ist die IP-Adresse für die Verwaltungs-/Interne/Externe NIC nicht vorhanden oder falsch.**
    
    **Lösung:** Dieses Problem kann nicht automatisch behoben werden. NiCs können VMs während der Ausführung nicht hinzugefügt werden. Fahren Sie diese virtuellen Computer im Hyper-V-Manager herunter, und entfernen Sie sie, und führen Sie dann die folgenden Cmdlets aus:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problem: Nachdem der Active Directory Server und die Gesamtstruktur installiert wurden, haben der CMS Server und/oder Vermittlungsserver der Domäne nicht ordnungsgemäß bei treten.**
    
    **Lösung:** Gehen Sie wie folgt vor, um dieses Problem zu beheben:
    
  - Melden Sie sich beim Active Directory Server an, und vergewissern Sie sich, dass die Domäne ordnungsgemäß erstellt wurde.
    
  - Melden Sie sich beim CMS/Mediation Server an, und vergewissern Sie sich, dass auf der Corpnet-NIC eine gültige IP-Adresse zugewiesen ist und dass gültige statische IP- und DNS-Adressen als DIE IP-Adresse des AD-Servers konfiguriert sind.
    
  - Melden Sie sich beim CMS/Mediation Server an, und öffnen Sie eine Eingabeaufforderung. Stellen Sie sicher, dass Sie den FQDN und die IP-Adresse des Active Directory Servers pingen können. Wenn dies nicht möglich ist, kann es zu einem Konflikt mit der IP-Adresse führen. Versuchen Sie, active Directory eine neue IP zuzuordnen und DNS auf dem CMS/Vermittlungsserver entsprechend zu aktualisieren.
    
- **Problem: Sie erhalten die folgende Fehlermeldung: "Remove-VMSwitch : Failed while removing virtual Ethernet switch. Der virtuelle Switch "Cloud Connector Management Switch" kann nicht gelöscht werden, da er von virtuellen Computern ausgeführt oder untergeordneten Pools zugewiesen wird."**
    
    **Lösung:** Der "Cloud Connector Management Switch" wurde nach der Bereitstellung nicht gelöscht. Wenn dieser Fehler auftritt, wechseln Sie bitte zu Hyper-v-Manager, und vergewissern Sie sich, dass noch kein virtueller Computer mit diesem verbunden ist. Wenn noch virtuelle Computer verbunden sind, trennen Sie sie, und löschen Sie den Verwaltungsschalter. Wenn der Verwaltungsschalter weiterhin nicht gelöscht werden kann, starten Sie den Hostserver neu, und versuchen Sie es erneut.
    
- **Problem: Sie erhalten die folgende Fehlermeldung: "Dienst RTCMRAUTH konnte nicht gestartet werden. Stellen Sie sicher, dass der Dienst nicht deaktiviert ist."**
    
    > [!NOTE]
    > Dieses Problem gilt nur für Cloud Connector-Versionen vor 1.4.2. 
  
    Der Fehler beim Starten kann auch daran liegt, dass dieser Front-End-Server zuvor nicht ausgeführt wurde (bei Verwendung eines Computerfehlers). Wenn dies der Fall ist, rufen Sie bitte ein Fail back auf (mit computer fail back).
    
    **Lösung:** Dieses Problem tritt auf einem Edgeserver auf, wenn das Stammzertifizierungsstellenzertifikat oder das Zwischenzertifizierungsstellenzertifikat vom Edgeserver nicht als vertrauenswürdig eingestuft wird. Auch wenn das externe Zertifikat importiert werden kann, aber die Zertifikatkette unterbrochen ist. Unter dieser Bedingung kann der RTCMRAUTH- und/oder RTCSRV-Dienst nicht gestartet werden.
    
    Importieren Sie das Stammzertifizierungsstellenzertifikat und alle Zwischenzertifizierungsstellenzertifikate Ihres externen Zertifikats manuell in den Edgeserver, und starten Sie den Edgeserver neu. Nachdem die DIENSTE RTCMRAUTH und RTCSRV auf dem Edgeserver gestartet wurden, wechseln Sie zurück zu Ihrem Hostserver, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problem: Der Hostserver wurde neu gestartet, als Windows-Updates angewendet wurden, und vom Server ausgeführte Anrufe werden nicht ausgeführt.**
    
    **Lösung:** Wenn Sie eine Hochverfügbarkeitsumgebung bereitgestellt haben, stellt Microsoft ein Cmdlet zur Verfügung, mit dem Sie einen Hostcomputer (Bereitstellungsinstanz) in die aktuelle Topologie oder aus der aktuellen Topologie verschieben können, wenn Sie Windows Update manuell überprüfen und installieren. Verwenden Sie dazu die folgenden Schritte:
    
1. Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie dann aus:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Suchen Sie nach Updates, und installieren Sie alle verfügbaren.
    
3. Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problem: Wenn ein Anruf von einem Skype for Business-Client über eine PSTN-Nummer erfolgt, kann der Anruf nicht zu einer Konferenz eskaliert werden, indem eine andere PSTN-Nummer eingeladen wird.**
    
    **Lösung:** Informationen zum Beheben dieses Problems finden Sie unter [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problem: Beim Installieren des Active Directory-Servers wird eine Warnmeldung zu Windows Update angezeigt: "Die automatische Aktualisierung von Windows ist nicht aktiviert. Um sicherzustellen, dass Ihre neu installierte Rolle oder Ihr neu installiertes Feature automatisch aktualisiert wird, aktivieren Sie Windows Update."**
    
    **Lösung:** Starten Sie eine Client-Remote-PowerShell-Sitzung mit Skype for Business-Mandantenadministratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die _EnableAutoUpdate-Konfiguration_ Ihrer Website zu überprüfen:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Wenn  _EnableAutoUpdate_ auf **True** festgelegt ist, können Sie diese Warnmeldung ignorieren, da der CCEManagement-Dienst das Herunterladen und Installieren von Windows-Updates für virtuelle Computer und den Hostserver verarbeiten wird. Wenn _EnableAutoUpdate_ auf **False** festgelegt ist, führen Sie das folgende Cmdlet aus, um es auf True **zu setzen.**
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Alternativ können Sie manuell nach Updates suchen und diese installieren. Informationen dazu finden Sie im nächsten Abschnitt.
    
- **Problem: Sie erhalten eine Fehlermeldung: Appliance kann nicht registriert werden, da Ihre aktuelle Eingabe/Konfiguration oder oder Konflikte mit vorhandenen \<SiteName\> \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> Appliances auftreten. Entfernen Sie die Konflikt appliance, oder aktualisieren Sie Ihre Eingabe-/Konfigurationsinformationen, und registrieren Sie sich dann erneut. ' beim Ausführen Register-CcAppliance, um die aktuelle Appliance online zu registrieren.**
    
    **Lösung:** Werte für \<ApplianceName\> den und müssen eindeutig sein und nur für eine \<Mediation Server FQDN\> \<Mediation Server IP Address\> Appliance-Registrierung verwendet werden. Stammt standardmäßig \<ApplianceName\> aus dem Hostnamen. \<Mediation Server FQDN\> und \<Mediation Server IP Address\> in der Konfigurations-ini-Datei definiert.
    
    Beispiel: verwenden (ApplianceName= MyserverNeu, Vermittlungsserver FQDN=ms.contoso.com, Vermittlungsserver-IP-Adresse=10.10.10.10), um sich bei SiteName=MySite zu registrieren, aber wenn eine registrierte Appliance (ApplianceName= Myserver, Vermittlungsserver FQDN=ms.contoso.com, Vermittlungsserver-IP-Adresse=10.10.10.10) vorhanden ist, liegt der Konflikt vor.
    
    Überprüfen Sie zunächst ihre CloudConnector.ini im Abschnitt ApplianceRoot-Verzeichnis. Sie erhalten \<SiteName\> , und Werte in der \<Mediation Server FQDN\> \<Mediation Server IP Address\> Datei. \<ApplianceName\> ist ihr Hostservername.
    
    Zweitens starten Sie Mandanten-Remote-PowerShell mit Ihren Skype for Business-Mandantenadministratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die registrierten Appliances zu überprüfen.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Nachdem Sie Konflikte identifiziert haben, können Sie ihre CloudConnector.ini entweder mit Informationen aktualisieren, die der registrierten Appliance entspricht, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu beheben.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problem: Das cmdlet Get-CcRunningVersion gibt einen leeren Wert zurück, wenn auf dem Host eine bereitgestellte Appliance ausgeführt wird.**
    
  **Lösung:** Dies kann beim Upgrade von 1.3.4 oder 1.3.8 auf 1.4.1 geschehen. Nachdem Sie Version 1.4.1 mit dem MSI installiert haben, müssen Sie ausführen, bevor Sie ein `Register-CcAppliance` anderes Cmdlet ausführen. `Register-CcAppliance` migriert die module.ini datei von %UserProfile%\CloudConnector zu %ProgramData%\CloudConnector. Wenn Sie es verpasst haben, wird module.ini im Ordner "%ProgramData%\CloudConnector" erstellt und die Informationen zur Ausführungs-/Sicherungsversion für 1.3.4 oder 1.3.8 ersetzt.
    
  Vergleichen module.ini Dateien im Ordner "%UserProfile%\CloudConnector" und "%ProgramData%\CloudConnector". Wenn Unterschiede bestehen, löschen Sie die module.ini in %ProgramData%\CloudConnector, und führen Sie erneut  `Register-CcAppliance` aus. Sie können die Datei auch manuell in die richtige Ausführungs- und Sicherungsversion ändern.
    
- **Problem: Nachdem Sie das cmdlet Switch-CcVersion, um zu einer alten Version zu wechseln, die sich von der aktuellen Skriptversion abwechselt, gibt es keine Unterstützung für hohe Verfügbarkeit für diese alte Version.**
    
    **Lösung:** Beispielsweise haben Sie ein Upgrade von 1.4.1 auf 1.4.2 durchgeführt. Ihre aktuelle Skriptversion, die durch Ausführen bestimmt werden kann, und Ihre ausgeführte Version, die durch Ausführen bestimmt werden kann, sind `Get-CcVersion`  `Get-CcRunningVersion` beide 1.4.2. Wenn Sie derzeit ausführen, um die ausgeführte Version wieder auf 1.4.1 umschalten, gibt es für diese alte Version keine `Switch-CcVersion` Hochverfügbarkeitsunterstützung.
    
    Um den vollständigen Support für hohe Verfügbarkeit zu erhalten, wechseln Sie zurück zu 1.4.2, damit die Ausführungsversion und die Skriptversion identisch sind. Wenn Probleme mit Ihrer 1.4.2-Bereitstellung auftreten, deinstallieren Sie sie, und installieren Sie sie so bald wie möglich erneut.
    
- **Problem: Zertifikate der Zertifizierungsstelle oder interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, sind kurz vor dem Ablauf oder sind gefährdet.**
    
    **Lösung:** Skype for Business-Zertifizierungsstellenzertifikate sind fünf Jahre gültig. Interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt werden, sind zwei Jahre gültig.
    
    > [!NOTE]
    > In Cloud Connector, Version 2.0 und höher, wurde das cmdlet Renew-CcServerCertificate in Update-CcServerCertificate geändert, und das cmdlet Renew-CcCACertificate wurde in Update-CcCACertificate geändert. 
  
    Wenn interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, kurz vor ablaufen oder gefährdet sind, führen Sie das cmdlet Renew-CcServerCertificate oder Update-CcServerCertificate aus, um Ihre Zertifikate zu erneuern.
    
    Wenn Zertifizierungsstellenzertifikate kurz vor dem Ablauf stehen, führen Sie das cmdlet Renew-CcCACertificate oder Update-CcCACertificate aus, um Ihre Zertifikate zu erneuern.
    
    **Wenn Zertifizierungsstellenzertifikate gefährdet sind** und nur eine Appliance am Standort vorhanden ist, führen Sie die folgenden Schritte aus:
    
1. Führen Sie Enter-CcUpdate cmdlet aus, um Dienste zu entleeren und die Appliance in den Wartungsmodus zu setzen.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Führen Sie die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:
    
    Für Cloud Connector-Versionen vor 2.0:
    
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
    
3. Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das cmdlet Export-CcRootCertificate aus der Appliance aus, und installieren Sie dann das exportierte Zertifikat in Ihre PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway aus ausgestellt haben.

   ```powershell
   Export-CcRootCertificate
   ```

4. Führen Sie Exit-CcUpdate cmdlet aus, um Dienste zu starten und den Wartungsmodus zu beenden.

   ```powershell
   Exit-CcUpdate
   ```


    **Wenn Zertifizierungsstellenzertifikate gefährdet** sind und mehrere Appliances am Standort vorhanden sind, führen Sie die folgenden sequenziellen Schritte für jede Appliance am Standort aus.
    
    Microsoft empfiehlt, diese Schritte zu Zeiten außerhalb der Spitzenauslastung durchzuführen.
    
1. Führen Sie auf der ersten Appliance das cmdlet Remove-CcCertificationAuthorityFile aus, um die Sicherungsdateien der Zertifizierungsstelle im Verzeichnis zu \<SiteRoot\> bereinigen.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Führen Sie Enter-CcUpdate cmdlet aus, um Dienste zu entleeren und jede Appliance in den Wartungsmodus zu setzen.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Führen Sie auf der ersten Appliance die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:
    
     Für Cloud Connector-Versionen vor 2.0:
    
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

4. Führen Sie auf der ersten Appliance das folgende Cmdlet aus, um die Ca-Dateien im Ordner zu \<SiteRoot\> sichern.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Führen Sie auf allen anderen Appliances am gleichen Standort die folgenden Befehle aus, um die Sicherungsdateien der Zertifizierungsstelle zu nutzen, sodass alle Appliances dasselbe Stammzertifikat verwenden und dann neue Zertifikate anfordern. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das cmdlet Export-CcRootCertificate von einer beliebigen Appliance am Standort aus, und installieren Sie dann das exportierte Zertifikat in Ihre PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway aus ausgestellt haben.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Führen Sie Exit-CcUpdate cmdlet aus, um Dienste zu starten und den Wartungsmodus zu beenden. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problem: Sie erhalten die folgende Fehlermeldung im Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unerwartete Ausnahme beim Melden des Status online: System.Management.Automation.CmdletInvocationException: Fehler bei der Anmeldung für den Benutzer \<Global Tenant Admin\> . Erstellen Sie ein neues Anmeldeinformationsobjekt, und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben. ---\>**
    
    **Lösung:** Die Anmeldeinformationen des globalen Mandantenadministrators für Microsoft 365 oder Office 365 wurden seit der Registrierung der Cloud Connector-Appliance geändert. Führen Sie zum Aktualisieren der lokal gespeicherten Anmeldeinformationen auf der Cloud Connector-Appliance in Administrator PowerShell die folgenden Schritte auf der Host-Appliance aus:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problem: Nachdem Sie das Kennwort für das Hostserverkonto geändert haben, das Sie für die Bereitstellung verwendet haben, wird die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString : Der Schlüssel ist nicht gültig für die Verwendung im angegebenen Zustand." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log oder beim Ausführen des cmdlets Get-CcCredential.**
    
    **Lösung:** Alle Cloud #A0 werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml". Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
    
    **Wenn Sie Cloud Connector Version 1.4.2 ausführen,** regenerieren Sie alle Cloud Connector-Kennwörter neu, indem Sie die folgenden Schritte ausführen:
    
  1. Starten Sie den Hostserver neu.
    
  2. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml".
    
  3. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance -Local" aus, um die Kennwörter nach der Beschreibung erneut ein eingeben zu können. Geben Sie dieselben Kennwörter ein, die Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben.
    
     **Wenn Sie Cloud Connector Version 2.0** oder höher ausführen, generieren Sie alle Cloud Connector-Kennwörter neu, indem Sie die folgenden Schritte ausführen:
    
  4. Starten Sie den Hostserver neu.
    
  5. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\> xml" .
    
  6. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance -Local" aus, um die Kennwörter nach der Beschreibung erneut ein eingeben zu können. 
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde, verwenden Sie das VMAdmin-Kennwort für das CceService-Kennwort, wenn Sie dazu aufgefordert werden. Geben Sie dasselbe Kennwort ein, das Sie zuvor für die Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde und die Kennwörter DomainAdmin und VMAdmin unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:
    
  7. Führen Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
  8. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
  9. Wenn Sie zur Eingabe der anmeldeinformationen für das neue Konto aufgefordert werden, geben Sie das Kennwort für das zuvor verwendete Domänenadmin-Kennwort ein.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 2.0 oder höher, generiert wurde, verwenden VmAdmin und DomainAdmin standardmäßig dasselbe Kennwort wie CceService. Wenn Sie die Kennwörter DomainAdmin und VMAdmin geändert haben, müssen Sie die folgenden Schritte ausführen:
    
  10. Führen Set-CcCredential -AccountType DomainAdmin wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der anmeldeinformationen für das neue Konto aufgefordert werden, geben Sie das Kennwort für das zuvor verwendete Domänenadmin-Kennwort ein.
    
  11. Führen Set-CcCredential -AccountType VmAdmin wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das CceService-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der anmeldeinformationen für das neue Konto aufgefordert werden, geben Sie das Kennwort für das vmAdmin-Kennwort ein, das Sie zuvor verwendet haben. 
    
- **Problem: Bei Cloud Connector, Version 2.1 und höher, erhalten Sie beim Ausführen von Register-CcAppliance oder anderen Cmdlets auf der Appliance eine Fehlermeldung wie: "For Each-Object : The property 'Common' cannot be found on this object. Stellen Sie sicher, dass die Eigenschaft vorhanden ist. Unter C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**
    
    **Lösung:** Cloud Connector 2.1 und höher erfordert .NET Framework 4.6.1 oder höher. Aktualisieren Sie .NET Framework der Appliance auf Version 4.6.1 oder höher, und führen Sie die Cmdlets erneut aus.

- **Problem: Bei Cloud Connector Edition 2.1 wird beim Ausführen von Install-CcAppliance eine Fehlermeldung angezeigt, z. B.: "Fehler beim Installieren einer neuen Instanz mit Fehler: "Status kann nicht festgelegt werden, da nur Zeichenfolgen als Werte zum Festlegen von XmlNode-Eigenschaften verwendet werden können"**

   **Lösung:** Fügen Cloudconnector.ini unter dem Abschnitt [Common] die Konfiguration "State" wie folgt hinzu: CountryCode=US State=WA City=Redmond

   Es ist nicht zwingend erforderlich, dass die Zeile "Status" einen Wert hat, die Zeile "Status" kann jedoch nicht aus der Cloudconnector.ini werden.

- **Problem: Sie erhalten die folgende Fehlermeldung "Dismount-WindowsImage : Dismount-WindowsImage fehlgeschlagen. Fehlercode = 0xc1550115" beim Installieren oder Aktualisieren von Cloud Connector Edition.**
    
    **Lösung:** Starten Sie eine PowerShell-Konsole als Administrator, führen Sie "DISM -Cleanup-Wim'" aus. Dadurch werden alle problemebelästigten Bilder bereinigt. Führen Install-CcAppliance erneut aus, oder warten Sie, bis die Bits automatisch aktualisiert werden.
    
- **Problem: Fehler bei der Bereitstellung der ersten Cloud Connector-Appliance in einer HA-Umgebung**
    
    **Lösung:** Die schritte, die Sie ausführen, hängen vom Grund ab, warum die Bereitstellung fehlgeschlagen ist:
    
  - Wenn die erste Cloud Connector-Appliance ausfällt und Sie den Grund für den Fehler nicht ermitteln können, müssen Sie die Appliance erneut installieren, bis die Bereitstellung erfolgreich war, und dann die anderen Appliances installieren.
    
  - Wenn bei der ersten Cloud Connector-Appliance ein kleineres Problem auftritt, z. B. ein externes Zertifikatproblem, können Sie das Problem möglicherweise beheben, ohne die Appliance erneut zu installieren. Anschließend können Sie die Bereitstellung mithilfe der Mandanten-Remote-PowerShell wie folgt als erfolgreich kennzeichnen. (Sie können auch die folgenden Schritte ausführen, wenn die erste Bereitstellung erfolgreich war, aber aus einem bestimmten Grund kann Cloud Connector die Bereitstellung nicht als erfolgreich melden.)
    
  - Um die Identität (GUID) der ersten Cloud Connector-Appliance zu erhalten, führen Sie das cmdlet Get-CsHybridPSTNAppliance aus.
    
  - Um die Appliance als erfolgreich bereitgestellt zu markieren, führen Sie die Set-CsCceApplianceDeploymentStatus wie folgt aus:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problem: Sie müssen windows-Updates manuell auf dem Hostserver oder auf virtuellen Computern überprüfen und installieren.**
    
   **Lösung:** Es wird empfohlen, von automatisierten Betriebssystemupdates zu profitieren, die von Skype for Business Cloud Connector Edition bereitgestellt werden. Nachdem eine Appliance für die Onlineverwaltung registriert wurde und das automatische Betriebssystemupdate aktiviert ist, überprüfen und installieren der Hostserver und virtuelle Computer Windows Updates automatisch gemäß den Einstellungen für das Betriebssystemupdatezeitfenster.
    
   Wenn Sie Windows Updates manuell suchen und installieren müssen, führen Sie die Schritte in diesem Abschnitt aus, die für Ihren Bereitstellungstyp gelten. Sie sollten planen, sowohl den Hostserver als auch die darauf ausgeführten virtuellen Computer gleichzeitig zu aktualisieren, um die für die Updates erforderliche Ausfallzeiten zu minimieren.
    
   Wenn es Ihnen lieber ist, können Sie einen Windows Server Update Services (WSUS)-Server verwenden, um Updates für Cloud Connector-Server zur Verfügung zu stellen. Stellen Sie sicher, dass Windows Update nicht **automatisch** installiert wird.
    
   Informationen zum manuellen Aktualisieren Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.
    
- **Problem: Wenn Cloud Connector auf einen neuen Build aktualisiert wird, werden Cloud Connector-Cmdlets nicht aktualisiert.** Dies geschieht manchmal, wenn ein PowerShell-Fenster geöffnet bleibt, wenn die automatische Aktualisierung erfolgt.
    
  **Lösung:** Zum Laden der aktualisierten Cmdlets können Sie einen der folgenden Schritte ausführen:
    
   - Schließen Sie PowerShell auf der Cloud Connector-Appliance, und öffnen Sie PowerShell erneut.
    
     - Sie können auch cloudConnector -Force Import-Module ausführen. 
 
-   **Problem: "Der Begriff 'Stop-CsWindowsService' wird nicht als Name eines Cmdlets, einer Funktion, einer Skriptdatei oder eines funktionsfähigen Programms erkannt." Fehler beim Ausführen Enter-CcUpdate Cmdlets.**

    **Lösung:** Löschen Sie $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell erstellt diese Datei als Cache von Cmdlets aus Modulen, die sie findet, sodass sie nicht jedes Mal alle Module neu analysieren muss, da dies die Dinge wirklich verlangsamen würde. Wahrscheinlich gab es einige Dateibeschädigungen, die PowerShell beim Lesen aus diesem Cache irreführende Ergebnisse lieferten.

-   **Problem: "Import-Module CloudConnector" generiert fehler "Import-Module: Das angegebene Modul "CloudConnector" wurde nicht geladen, da keine gültige Moduldatei in einem Modulverzeichnis gefunden wurde"**

    **Lösung:**
    - Überprüfen, ob das CloudConnector-Modul tatsächlich unter c:\Program Files\WindowsPowerShell\Modules vorhanden ist
    
    - Nach der Validierung, ob das CloudConnector-Modul unter diesem Speicherort vorhanden ist, kann die PSModulePath-Umgebungsvariable, die den Pfad zu den Speicherorten der Module speichert, geändert werden:
    
     a. Temporäre Änderung: Starten Sie Powershell als Administrator, und führen Sie den folgenden Befehl aus: $env:PSModulePath = $env:PSModulePath + "; C:\Programme\WindowsPowerShell\Modules\"
        
     b. Starten Sie PowerShell für dauerhafte Änderungen als Administrator, und führen Sie die folgenden Befehle eins nach dem anderen aus: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")

    
## <a name="install-windows-updates-manually"></a>Manuelles Installieren von Windows-Updates

Wenn Sie keine automatischen Updates in Ihrer Umgebung verwenden möchten, führen Sie die folgenden Schritte aus, um windows-Updates manuell zu überprüfen und anzuwenden. Für die Überprüfung und Installation von Windows-Updates ist möglicherweise ein Serverneustart erforderlich. Wenn ein Hostserver neu gestartet wird, können Benutzer Cloud Connector nicht zum Senden oder Empfangen von Anrufen verwenden. Sie können manuell nach Updates suchen und diese installieren, um zu steuern, wann die Updates stattfinden, und die Computer dann bei Bedarf neu starten, während Sie eine Unterbrechung der Dienste vermeiden möchten.
  
Um manuell nach Updates zu suchen, stellen Sie eine Verbindung mit jedem Hostserver herzustellen und die **Systemsteuerung zu öffnen.** Wählen **Sie System- und \> Sicherheits-Windows Update** aus, und verwalten Sie dann die Updates und Serverneustarts entsprechend Ihrer Umgebung.
  
- Wenn sich nur eine Appliance am Standort befindet, stellen Sie eine Verbindung mit jedem virtuellen Computer herzustellen und die **Systemsteuerung zu öffnen.** Wählen **Sie System- und \> Sicherheits-Windows Update** aus, und konfigurieren Sie dann die Updates und Serverneustarts entsprechend.
    
- Wenn sich mehrere Appliances am Standort befinden, können Benutzer während der Updates nicht auf die Instanz zugreifen, die aktualisiert und neu gestartet wird. Benutzer stellen eine Verbindung mit anderen Instanzen in der Bereitstellung ein, bis alle virtuellen Computer und alle Skype for Business-Dienste nach Abschluss der Updates auf den virtuellen Computern gestartet werden. Um mögliche Dienstunterbrechungen zu vermeiden, können Sie die Instanz aus ha entfernen, während Sie die Updates anwenden, und sie dann wiederherstellen, wenn sie abgeschlossen ist. Gehen Sie hierzu folgendermaßen vor:
    
1. Öffnen Sie auf jedem Hostserver eine PowerShell-Konsole als Administrator.
    
2. Entfernen Sie die Instanz aus HA mit dem folgenden Cmdlet:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und den virtuellen Computer neu zu starten.
    
4. Legen Sie die Instanz mit dem folgenden Cmdlet auf HA zurück:
    
   ```powershell
   Exit-CcUpdate
   ```

Führen Sie für Bereitstellungen mit mehreren Standort die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, und führen Sie jeweils Updates auf einen Standort aus.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Tipps beim Installieren von Antivirensoftware auf dem Cloud Connector-Hostcomputer

Wenn Sie Antivirensoftware auf dem Cloud Connector-Hostcomputer installieren müssen, müssen Sie die folgenden Ausschlüsse hinzufügen:
  
- Lokales Appliance-Verzeichnis auf jedem Computer.
    
- Remotestandortverzeichnis auf jedem Computer.
    
- Das lokale Standortverzeichnis auf dem Computer hostet den freigegebenen Stammordner der Website.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Der Prozess Microsoft.Rtc.CCE.ManagementService.exe.