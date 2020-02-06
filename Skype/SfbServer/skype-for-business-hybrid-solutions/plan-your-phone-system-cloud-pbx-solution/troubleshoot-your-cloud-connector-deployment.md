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
ms.openlocfilehash: 3a6fd80cc0c4125303021746cdb626d8c5b49a5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814223"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Problembehandlung bei Ihrer Cloud Connector-Bereitstellung
 
Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
  
In diesem Thema werden Lösungen für allgemeine Probleme bei Cloud Connector Edition-Bereitstellungen beschrieben. Wenn Probleme mit Anrufen an das und aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) auftreten, können Sie diese anhand der in diesem Thema beschriebenen Lösungen untersuchen.
  
Cloud Connector bietet integrierte Mechanismen zum automatischen beheben einiger Probleme. Ein automatischer Erkennungsprozess sucht nach potenziellen Problemen mit den Cloud Connector-Appliances und führt, wenn möglich, Korrekturmaßnahmen zur Behebung dieser Probleme durch, ohne dass ein Administratoreingriff erforderlich ist. So funktioniert der Erkennungsprozess:
  
- **Erkennungsreihenfolge:** Der Cloud Connector-Verwaltungsdienst führt einen Prozess alle 60 Sekunden durch, um festzustellen, ob eine Appliance ausgefallen ist. In der Cloud Connector-Version 2,0 und höher verwendet der Erkennungsprozess den Skype for Business-Corpnet-Schalter zum Herstellen von PowerShell-Verbindungen mit den Cloud Connector-Computern. bei früheren Versionen von 2,0 verwendet der Erkennungsprozess den Cloud Connector-Verwaltungs Schalter.
    
    > [!NOTE]
    > Damit die automatische Wiederherstellung erfolgreich ausgeführt werden kann, muss die Netzwerkverbindung zwischen dem Host und den virtuellen Computern über den Host Netzwerkschalter erfolgen. Überprüfen Sie die Netzwerkkonnektivität, um sicherzustellen, dass die automatische Erkennung und Wiederherstellung erfolgreich ausgeführt werden kann. 
  
- **Überwachung:** Die folgenden Dienste werden in Cloud Connector, Version 2,0 und höher, überwacht:
    
  - Virtuelle Computer sind nicht mit dem Cloud Connector verbunden. virtuelle Switches für Unternehmen oder Internet
    
  - Virtuelle Computer befinden sich in einem gespeicherten oder gestoppten Status
    
  - Zentrale Verwaltungs Server Dienste: Replikat, Master
    
  - Vermittlungs Server Dienste: Replikat, RTCSRV und MEDSVC
    
  - Edge-Server Dienste: Replikat, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Eingehende Firewallregeln sind für CS RTCSRV on Edge Server, CS RTCMEDSRV auf dem Vermittlungsserver deaktiviert
    
    In der Cloud Connector-Version 1.4.2 werden nur die folgenden Dienste überwacht:
    
  - Vermittlungs Server Dienste: RTCSRV und MEDSVC
    
  - Edge-Server Dienst: RTCSRV
    
- **Wiederherstellungsprozess:** Wenn überwachte Dienste ausgefallen sind, wird eine Appliance markiert, und Dienste werden angehalten und manuell markiert, bis alle Probleme behoben werden können. Dadurch wird verhindert, dass Anrufe an eine Appliance weitergeleitet werden, die zu Anruf Fehlern führen kann.
    
    Der Cloud Connector-Verwaltungsdienst führt die automatische Wiederherstellung wie folgt aus:
    
  - Das anfängliche Wiederholungsintervall beträgt alle zehn Sekunden mit einer maximalen Intervallzeit von einer Stunde.
    
  - Bei den ersten drei Wiederherstellungsversuchen beträgt die Intervallzeit 10 Sekunden. Ab der vierten Wiederholung nimmt die Intervallzeit um das Zweifache der vorherigen Intervallzeit zu. Der vierte Versuch wird beispielsweise in 20 Sekunden, der fünfte in 40 Sekunden usw. erfolgen. 
    
  - Wenn die maximale Intervallzeit von einer Stunde erreicht ist, werden die Wiederholungsversuche einmal pro Stunde fortgesetzt.
    
  - Wenn die Wiederherstellung erfolgreich ist, werden das Intervall und die Wiederholungsanzahl auf die Anfangswerte festgesetzt.
    
  - Wenn der Verwaltungsdienst neu gestartet wird, werden das Intervall und die Wiederholungsanzahl auf die anfänglichen Werte zurückgesetzt.
    
## <a name="troubleshooting"></a>Problembehandlung

Im folgenden finden Sie Lösungen für häufig auftretende Probleme:
  
- **Problem: Die Bereitstellung schlägt fehl oder reagiert nicht mehr bei Ausführung von Bereitstellungsskripten. Nach der Anmeldung bei den einzelnen VMs fehlt die IP-Adresse oder passt nicht zur Verwaltungs-, internen bzw. externen NIC.**
    
    **Auflösung:** Dieses Problem kann nicht automatisch aufgelöst werden. Während der Ausführung der VMs können diesen keine NICs hinzugefügt werden. Fahren Sie diese VMs im Hyper-V-Manager herunter und entfernen Sie sie, und führen Sie anschließend die folgenden Cmdlets aus:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problem: Nach der Installation von Active Directory (AD) und der Gesamtstruktur wurde der CMS-Server bzw. der Vermittlungsserver nicht ordnungsgemäß zur Domäne hinzugefügt.**
    
    **Lösung:** Um dieses Problem zu beheben, führen Sie die folgenden Schritte durch:
    
  - Melden Sie sich beim Active Directory-Server an, und überprüfen Sie, ob die Domäne ordnungsgemäß erstellt wurde.
    
  - Melden Sie sich beim CMS bzw. beim Vermittlungsserver an, und überprüfen Sie, ob der Netzwerkkarte des Unternehmensnetzwerks eine gültige IP-Adresse zugewiesen wurde und ob eine gültige statische IP und ein DNS als IP-Adresse des AD-Servers konfiguriert wurden.
    
  - Melden Sie sich beim CMS/Mediation-Server an, und öffnen Sie eine Eingabeaufforderung. Stellen Sie sicher, dass Sie den FQDN und die IP-Adresse des Active Directory-Servers anpingen können. Wenn dies nicht möglich ist, kann es zu einem IP-Adressenkonflikt kommen. Versuchen Sie, eine neue IP für Active Directory zuzuweisen und DNS auf dem CMS/Mediation-Server entsprechend zu aktualisieren.
    
- **Problem: Es wird die folgende Fehlermeldung angezeigt: "Remove-VMSwitch: Fehler beim Entfernen des virtuellen Ethernet-Switches. Der virtuelle Schalter "Cloud Connector-Verwaltungs Schalter" kann nicht gelöscht werden, da er von virtuellen Computern oder untergeordneten Pools verwendet wird. "**
    
    **Auflösung:** Der "Cloud Connector-Verwaltungs Schalter" wurde nach der Bereitstellung nicht gelöscht. Wenn dieser Fehler auftritt, navigieren Sie zum Hyper-V-Manager, und stellen Sie sicher, dass keine andere virtuelle Maschine verbunden ist. Wenn nach wie vor virtuelle Maschinen verbunden sind, trennen Sie sie, und löschen Sie den Management-Switch. Wenn der Management-Switch nicht gelöscht werden kann, starten Sie den Hostserver neu, und versuchen Sie es erneut.
    
- **Problem: Es wird die folgende Fehlermeldung angezeigt: "Dienst RTCMRAUTH konnte nicht gestartet werden. Vergewissern Sie sich, dass der Dienst nicht deaktiviert ist. "**
    
    > [!NOTE]
    > Dieses Problem gilt nur für Cloud Connector-Versionen, die älter als 1.4.2 sind. 
  
    Der Startfehler kann auch darauf zurückzuführen sein, dass für diesen Front End-Server zuvor ein Failover (Computer-Failover) durchgeführt wurde. In diesem Fall sollten Sie ein Failback (Computer-Failback) starten.
    
    **Lösung:** Dieser Fehler tritt auf einem Edgeserver auf, wenn der Edgeserver dem Zertifikat der Stammzertifizierungsstelle oder dem Zertifikat der Zwischenzertifizierungsstelle nicht vertraut. Selbst wenn ein externes Zertifikat importiert werden kann, ist die Zertifizierungskette unterbrochen. Unter dieser Bedingung kann der RTCMRAUTH- bzw. der RTCSRV-Dienst nicht gestartet werden.
    
    Importieren Sie das Zertifikat der Stammzertifizierungsstelle und alle Zertifikate der Zwischenzertifizierungsstelle Ihres externen Zertifikats manuell auf den Edgeserver, und starten Sie den Edgeserver anschließend neu. Wenn die Dienste RTCMRAUTH und RTCSRV auf dem Edgeserver gestartet werden, navigieren Sie zu Ihrem Hostserver, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problem: Der Hostserver wurde nach dem Anwenden von Windows-Updates neu gestartet, und vom Server verarbeitete Anrufe sind fehlgeschlagen.**
    
    **Lösung:** Wenn Sie eine Umgebung mit hoher Verfügbarkeit bereitgestellt haben und ein Windows-Update manuell überprüfen und installieren, können Sie mit einem von Microsoft angebotenen Cmdlet einen Hostcomputer (Bereitstellungsinstanz) in die aktuelle Topologie oder aus der aktuellen Topologie verschieben. Führen Sie hierzu die folgenden Schritte aus:
    
1. Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie Folgendes aus:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Suchen und installieren Sie alle verfügbaren Updates.
    
3. Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problem: Wenn ein Anruf über einen Skype for Business-Client mit einer PSTN-Nummer getätigt wird, kann der Anruf nicht durch Einladen einer anderen PSTN-Nummer zu einer Konferenz eskaliert werden.**
    
    **Auflösung:** Informationen zum Beheben dieses Problems finden Sie unter Konfigurieren von Einstellungen für den [Hybriden Online-Vermittlungs Server](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problem: Eine Warnmeldung zum Windows-Update wird angezeigt, wenn Sie Active Directory-Server installieren: „Die automatische Aktualisierung von Windows ist nicht aktiviert. Aktivieren Sie "Windows Update", um sicherzustellen, dass die neu installierte Rolle oder das neu installierte Feature automatisch aktualisiert wird.“**
    
    **Auflösung:** Starten Sie eine Mandanten-Remote-PowerShell-Sitzung unter Verwendung von Skype for Business-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die _EnableAutoUpdate_ -Konfiguration Ihrer Website zu überprüfen:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Wenn _EnableAutoUpdate_ auf " **true**" festgelegt ist, können Sie diese Warnmeldung bedenkenlos ignorieren, da der CCEManagement-Dienst das herunterladen und Installieren von Windows-Updates für virtuelle Computer und den Hostserver übernimmt. Wenn _EnableAutoUpdate_ auf **false**festgelegt ist, führen Sie das folgende Cmdlet aus, um es auf **true**festzulegen.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Alternativ dazu können Sie Updates manuell suchen und installieren. Informationen hierzu finden Sie im nächsten Abschnitt.
    
- **Problem: Es wird eine Fehlermeldung angezeigt: die Appliance kann nicht registriert werden, da \<Ihre\> aktuelle \<Eingabe/\> Konfiguration \<Sitename oder\> Appliancename oder Mediation Server-FQDN oder \<die IP-Adresse\> des Vermittlungsservers Konflikte mit der vorhandenen Appliance (n) verursacht. Entfernen Sie die Konflikt Appliance, oder aktualisieren Sie Ihre Eingabe/Konfigurationsinformationen, und registrieren Sie sich dann erneut. "Wenn Sie Register-CcAppliance ausführen, um die aktuelle Appliance online zu registrieren.**
    
    **Auflösung:** Werte für die \<IP-\>Adresse \<\> Appliancename,\> Vermittlungsserver-FQDN und \<Vermittlungsserver müssen eindeutig sein und nur für eine Appliance-Registrierung verwendet werden. Standardmäßig\> stammt \<Appliancename aus dem Host-Namen. \<Der in der\> Konfigurations \<-ini-Datei\> definierte IP-Adresse des Mediation Server-FQDN und des Vermittlungsservers.
    
    Wenn Sie beispielsweise (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) zum Registrieren von SiteName=MySite verwenden, aber eine registrierte Appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) vorhanden ist, tritt ein Konflikt auf.
    
    Überprüfen Sie zunächst die Datei „CloudConnector.ini“ im ApplianceRoot-Verzeichnisabschnitt. Sie \<erhalten in der\>Datei \<Sitename-\> , \<Vermittlungsserver-\> FQDN und Vermittlungsserver-IP-Adresswerte. \<Appliancename\> ist der Name Ihres Hostservers.
    
    Starten Sie anschließend Mandanten-Remote-PowerShell mit Ihren Skype for Business-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die registrierten Appliances zu überprüfen.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Nach der Überprüfung aller Konflikte können Sie die Datei „CloudConnector.ini“ mit den Informationen aktualisieren, die mit der registrierten Appliance übereinstimmen, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu beheben.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problem: das Cmdlet "Get-CcRunningVersion" gibt einen leeren Wert zurück, wenn eine bereitgestellte Appliance auf dem Host ausgeführt wird.**
    
  **Auflösung:** Dies kann passieren, wenn Sie ein Upgrade von 1.3.4 oder 1.3.8 auf 1.4.1 durchführen. Nachdem Sie Version 1.4.1 mit der MSI-Version installiert haben, müssen `Register-CcAppliance` Sie vor dem Ausführen eines anderen Cmdlets ausgeführt werden. `Register-CcAppliance`migriert die Datei "Module. ini" von%USERPROFILE%\CloudConnector zu%ProgramData%\CloudConnector. Wenn Sie Sie verpasst haben, wird im Ordner%ProgramData%\CloudConnector eine neue Modul. ini erstellt, und die Informationen zum Ausführen/Sichern der Version für 1.3.4 oder 1.3.8 werden ersetzt.
    
  Vergleichen Sie Modul. ini-Dateien in%USERPROFILE%\CloudConnector und%ProgramData%\CloudConnector-Ordner. Wenn es Unterschiede gibt, löschen Sie die Datei Modul. ini in `Register-CcAppliance`%ProgramData%\CloudConnector, und führen Sie eine erneute Ausführung aus. Sie können die Datei auch manuell auf die richtige Ausführungs-und Sicherungsversion ändern.
    
- **Problem: Nachdem Sie das Cmdlet Switch-CcVersion ausgeführt haben, um zu einer älteren Version zu wechseln, die sich von der aktuellen Skriptversion unterscheidet, gibt es keine Unterstützung für hohe Verfügbarkeit für diese alte Version.**
    
    **Auflösung:** Sie haben beispielsweise ein Upgrade von 1.4.1 auf 1.4.2 durchgeführt. Ihre aktuelle Skriptversion, die durch ausgeführt werden kann `Get-CcVersion`, und die ausgeführte Version, die durch Ausführen `Get-CcRunningVersion` bestimmt werden kann, sind beide 1.4.2. Wenn Sie `Switch-CcVersion` die ausgeführte Version zu diesem Zeitpunkt wieder auf 1.4.1 umschalten, gibt es keine Unterstützung für hohe Verfügbarkeit für diese alte Version.
    
    Um die vollständige Unterstützung von hoher Verfügbarkeit zu erhalten, müssen Sie zurück zu Version 1.4.2 wechseln, damit die zurzeit ausgeführte Version mit der Skriptversion übereinstimmt. Wenn bei Ihrer 1.4.2-Bereitstellung Probleme auftreten, deinstallieren Sie die Version, und installieren Sie sie umgehend neu.
    
- **Problem: Zertifizierungsstellenzertifikate oder interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, laufen in Kürze ab oder sind kompromittiert.**
    
    **Lösung:** Zertifizierungsstellenzertifikate für Skype for Business sind fünf Jahre lang gültig. Für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte interne Zertifikate sind zwei Jahre lang gültig.
    
    > [!NOTE]
    > In der Cloud Connector-Version 2,0 und höher wurde das Cmdlet Renew-CcServerCertificate in Update-CcServerCertificate geändert, und das Cmdlet Renew-CcCACertificate wurde in Update-CcCACertificate geändert. 
  
    Wenn interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, nahezu abgelaufen sind oder gefährdet sind, führen Sie das Cmdlet Renew-CcServerCertificate oder Update-CcServerCertificate aus, um Ihre Zertifikate zu erneuern.
    
    Wenn Zertifikate der Zertifizierungsstelle nahezu abgelaufen sind, führen Sie das Cmdlet Renew-CcCACertificate oder Update-CcCACertificate aus, um Ihre Zertifikate zu erneuern.
    
    Führen Sie die folgenden Schritte aus **, wenn Zertifikate der Zertifizierungsstelle kompromittiert werden und nur eine Appliance auf der Website vorhanden ist** :
    
1. Führen Sie das Cmdlet „Enter-CcUpdate“ aus, um Dienste auszugleichen und die Appliance in den Wartungsmodus zu versetzen.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Führen Sie die folgenden Cmdlets aus, um die Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und neu zu erstellen:
    
    Für Cloud Connector-Versionen vor 2,0:
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Oder für Cloud Connector Release 2,0 und höher:
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. Wenn TLS zwischen dem Gateway und dem Vermittlungs Server verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate von der Appliance aus, und installieren Sie dann das exportierte Zertifikat für Ihre PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway ausgeben.

   ```powershell
   Export-CcRootCertificate
   ```

4. Führen Sie das Cmdlet Exit-CcUpdate aus, um Dienste zu starten und den Wartungsmodus zu beenden.

   ```powershell
   Exit-CcUpdate
   ```


    **Wenn Zertifikate der Zertifizierungsstelle kompromittiert werden und mehrere Appliances auf der Website vorhanden sind,** führen Sie die folgenden Schritte auf jeder Appliance auf der Website aus.
    
    Microsoft empfiehlt, dass Sie diese Schritte während der Verwendung außerhalb der Spitzenzeiten durchführen.
    
1. Führen Sie auf der ersten Appliance das Cmdlet Remove-CcCertificationAuthorityFile aus, um die Sicherungsdateien der Zertifizierungs \<Stelle\> im Verzeichnis SiteRoot zu bereinigen.

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Führen Sie das Cmdlet "Enter-CcUpdate" aus, um Dienste zu entladen und jede Appliance in den Wartungsmodus zu versetzen.

     ```powershell
     Enter-CcUpdate
     ```
    
3. Führen Sie auf der ersten Appliance die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:
    
     Für Cloud Connector-Versionen vor 2,0:
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Oder für Cloud Connector Release 2,0 und höher:
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. Führen Sie auf der ersten Appliance das folgende Cmdlet aus, um die ca-Dateien im \<SiteRoot\> -Ordner zu sichern.
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Führen Sie auf allen anderen Appliances am gleichen Standort die folgenden Befehle aus, um die Sicherungsdateien der ca zu nutzen, damit die Appliances alle dasselbe Stammzertifikat verwenden und dann neue Zertifikate anfordern. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Wenn TLS zwischen dem Gateway und dem Vermittlungs Server verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate von einer beliebigen Appliance auf der Website aus, und installieren Sie dann das exportierte Zertifikat für Ihre PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf Ihrem Gateway ausgeben.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Führen Sie das Cmdlet Exit-CcUpdate aus, um Dienste zu starten und den Wartungsmodus zu beenden. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problem: die folgende Fehlermeldung wird im Cloud Connector-Verwaltungsdienst Protokoll "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log" angezeigt: CceService-Fehler: 0: unerwartete Ausnahme beim Melden des Status Online: System. Management. Automation. CmdletInvocationException: Anmeldung für den globalen mandantenadministrator \<\>des Benutzers fehlgeschlagen. Erstellen Sie ein neues Anmeldeinformationsobjekt, indem Sie sicherstellen, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben. ---\>**
    
    **Auflösung:** Die Office 365-Administratoranmeldeinformationen für globale Mandanten wurden geändert, seit die Cloud Connector-Appliance registriert wurde. Wenn Sie die lokal gespeicherten Anmeldeinformationen auf der Cloud Connector-Appliance aktualisieren möchten, führen Sie die folgenden Schritte über die Administrator-PowerShell auf der Host-Appliance aus:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problem: Nachdem Sie das Kennwort für das Hostserver Konto geändert haben, das Sie für die Bereitstellung verwendet haben, wird die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString: Key ist nicht gültig für die Verwendung im angegebenen Zustand." in%ProgramFiles%\Skype for Business-Cloud-Connector Edition\ManagementService\CceManagementService.log oder während der Ausführung des Cmdlets Get-CcCredential.**
    
    **Auflösung:** Alle Anmeldeinformationen für den Cloud Connector werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ". Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
    
    **Wenn Sie Cloud Connector, Version 1.4.2, ausführen**, generieren Sie mit den folgenden Schritten alle Cloud Connector-Kennwörter neu:
    
  1. Starten Sie den Hostserver neu.
    
  2. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  3. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance-local" aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben. Geben Sie die gleichen Kennwörter ein, die Sie vor der Cloud Connector-Bereitstellung eingegeben haben.
    
     **Wenn Sie Cloud Connector, Version 2,0 oder höher, ausführen, müssen Sie** alle Cloud Connector-Kennwörter erneut erstellen, indem Sie die folgenden Schritte ausführen:
    
  4. Starten Sie den Hostserver neu.
    
  5. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>. xml ".
    
  6. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-CcAppliance-local" aus, um die Kennwörter, die der Beschreibung folgen, erneut einzugeben. 
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde, verwenden Sie das „VMAdmin“-Kennwort als „CceService“-Kennwort, wenn Sie danach gefragt werden. Geben Sie das gleiche Kennwort ein, das Sie vor der Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde und die Kennwörter von „DomainAdmin“ und „VMAdmin“ nicht übereinstimmen, müssen Sie die folgenden Schritte ausführen:
    
  7. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
  8. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
  9. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 2,0 oder höher, generiert wurde, verwenden VmAdmin und DomainAdmin standardmäßig dasselbe Kennwort wie CceService. Wenn Sie die Kennwörter für „DomainAdmin“ und „VMAdmin“ geändert haben, müssen Sie die folgenden Schritte ausführen:
    
  10. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.
    
  11. Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „VmAdmin“ ein.  
    
- **Problem: beim Ausführen von Register-CcAppliance-oder anderen Cmdlets auf der Appliance mit Cloud Connector Version 2,1 und höher erhalten Sie eine Fehlermeldung wie "für jedes-Objekt: die Eigenschaft" Common "kann für dieses Objekt nicht gefunden werden. Überprüfen Sie, ob die Eigenschaft vorhanden ist. Unter C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**
    
    **Auflösung:** Für Cloud Connector 2,1 und höher ist .NET Framework 4.6.1 oder höher erforderlich. Aktualisieren Sie .NET Framework auf der Appliance auf Version 4.6.1 oder höher, und führen Sie das Cmdlet (s) erneut aus.

- **Problem: bei der Cloud Connector Edition 2,1 wird beim Ausführen von CcAppliance eine Fehlermeldung wie die folgende angezeigt: "Fehler beim Installieren einer neuen Instanz mit Fehler:" Status "kann nicht festgesetzt werden, da nur Zeichenfolgen als Werte zum Einrichten von XmlNode-Eigenschaften verwendet werden können"**

   **Auflösung:** Fügen Sie in Cloudconnector. ini unter dem Abschnitt [common] die Konfiguration "State" wie folgt hinzu: CountryCode = US-Bundesland = WA City = Redmond

   Es ist nicht zwingend erforderlich, dass die Zeile "Zustand" über einen Wert verfügt, aber die Zeile "Zustand" kann nicht aus der Datei "Cloudconnector. ini" entfernt werden.

- **Problem: Es wird die folgende Fehlermeldung "Dismount-WindowsImage: Dismount-WindowsImage Fehler" angezeigt. Fehlercode = 0xc1550115 "beim Installieren oder Aktualisieren von Cloud Connector Edition.**
    
    **Auflösung:** Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "DISM-Cleanup-WIM" aus. Damit werden alle von dem Problem betroffenen Images bereinigt. Führen Sie „Install-CcAppliance“ erneut aus, oder warten Sie, bis die Bits automatisch aktualisiert werden.
    
- **Problem: die Bereitstellung der ersten Cloud Connector-Appliance in einer ha-Umgebung schlägt fehl**
    
    **Auflösung:** Welche Schritte Sie ausführen, hängt von dem Grund ab, warum die Bereitstellung fehlgeschlagen ist:
    
  - Wenn die erste Cloud Connector-Appliance fehlschlägt und Sie den Grund für den Fehler nicht ermitteln können, müssen Sie die Appliance erneut installieren, bis die Bereitstellung erfolgreich ist, und dann die anderen Appliances installieren.
    
  - Wenn die erste Cloud Connector-Appliance mit einem kleineren Problem wie einem externen Zertifikat Fehler fehlschlägt, können Sie das Problem möglicherweise beheben, ohne die Appliance erneut installieren zu müssen. Sie können dann mithilfe der Mandanten-Remote-PowerShell die Bereitstellung wie folgt als erfolgreich kennzeichnen. (Sie können auch die folgenden Schritte ausführen, wenn die erste Bereitstellung erfolgreich war, aber aus irgendeinem Grund kann Cloud Connector die Bereitstellung nicht als Erfolg melden.)
    
  - Führen Sie das Cmdlet "Get-CsHybridPSTNAppliance" aus, um die Identität (GUID) der ersten Cloud Connector-Appliance abzurufen.
    
  - Wenn Sie die Appliance als erfolgreich bereitgestellt markieren möchten, führen Sie die CsCceApplianceDeploymentStatus wie folgt aus:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problem: Auf dem Hostserver oder den virtuellen Maschinen müssen Sie manuell nach Windows-Updates suchen bzw. diese installieren.**
    
   **Lösung:** Wir empfehlen Ihnen, dass Sie die Vorteile der automatisierten Betriebssystem-Updates der Skype for Business Cloud Connector Edition nutzen. Nachdem eine Appliance für die Online-Verwaltung registriert und das automatische Update des Betriebssystems aktiviert wurde, werden Windows-Updates vom Hostserver von den virtuellen Maschinen automatisch in Übereinstimmung mit den Windows-Einstellungen der Aktualisierungszeit für das Betriebssystem gesucht und installiert.
    
   Wenn Sie manuell nach Windows-Updates suchen und diese installieren müssen, führen Sie die zu Ihrem Bereitstellungstyp passenden Schritte in diesem Abschnitt durch. Sie sollten das gleichzeitige Update des Hostservers und der darauf ausgeführten virtuellen Maschinen planen, um die bei Updates entstehenden Ausfallzeiten zu minimieren.
    
   Sie können auch einen WSUS (Windows Server Update Services)-Server für die Bereitstellung von Updates für Cloud Connector-Server verwenden. Stellen Sie hierfür nur sicher, dass Sie **nicht** die automatische Installation von Windows-Update konfigurieren.
    
   Weitere Informationen zum manuellen Update Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.
    
- **Problem: beim Aktualisieren des Cloud Connectors für einen neuen Build werden die Cmdlets für den Cloud Connector nicht aktualisiert.** Dies geschieht manchmal, wenn ein PowerShell-Fenster geöffnet bleibt, wenn die automatische Aktualisierung erfolgt.
    
  **Auflösung:** Zum Laden der aktualisierten Cmdlets können Sie einen der folgenden Schritte ausführen:
    
   - Schließen Sie PowerShell auf der Cloud Connector-Appliance, und öffnen Sie PowerShell erneut.
    
     - Sie können auch Import-Module CloudConnector-Force ausführen. 
 
-   **Problem: "der Begriff" Stop-CsWindowsService "wird nicht als Name eines Cmdlets, einer Funktion, einer Skriptdatei oder eines bedienbaren Programms erkannt." Fehler beim Versuch, das Cmdlet "Enter-CcUpdate" auszuführen.**

    **Auflösung:** Löschen Sie die $Home \appdata\local\microsoft\windows\powershell\moduleanalysiscache-Datei.
PowerShell erstellt diese Datei als einen Cache von Cmdlets von Modulen, die Sie findet, damit Sie nicht jedes Mal alle Module neu analysieren muss, da sich die Dinge wirklich verlangsamen würden. Höchstwahrscheinlich gab es einige Dateibeschädigungen, die bei der Wiedergabe aus diesem Cache irreführende Ergebnisse für PowerShell bereitgestellt haben.

-   **Problem: "Import-Module CloudConnector" generiert Fehler "Import-Module: das angegebene Modul" CloudConnector "wurde nicht geladen, da in einem Modulverzeichnis keine gültige Moduldatei gefunden wurde."**

    **Lösung:**
    - Überprüfen Sie, ob das CloudConnector-Modul in der Tat unter c:\Program Files\WindowsPowerShell\Modules vorhanden ist.
    
    - Nach dem überprüfen, ob das CloudConnector-Modul unter diesem Speicherort vorhanden ist, kann die PSModulePath-Umgebungsvariable, die den Pfad zu den Speicherorten der Module speichert, geändert werden:
    
     a. Temporäre Änderung: Starten Sie PowerShell als Administrator, und führen Sie den folgenden Befehl aus: $env:P smodulepath = $ENV:P smodulepath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Starten Sie für eine dauerhafte Änderung PowerShell als Administrator, und führen Sie die folgenden Befehle einzeln aus: $CurrentValue = [Umgebung]:: GetEnvironmentVariable ("PSModulePath"; "Machine") SetEnvironmentVariable ("PSModulePath"; $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," Machine ")

    
## <a name="install-windows-updates-manually"></a>Manuelles Installieren von Windows-Updates

Wenn Sie keine automatischen Updates in Ihrer Umgebung verwenden möchten, führen Sie die folgenden Schritte aus, um Windows-Updates manuell zu überprüfen und anzuwenden. Für das überprüfen und Installieren von Windows-Updates ist möglicherweise ein Serverneustart erforderlich. Wenn ein Hostserver neu gestartet wird, können Benutzer keinen Cloud Connector verwenden, um Anrufe zu tätigen oder zu empfangen. Sie können Aktualisierungen manuell suchen und installieren, um zu steuern, wann die Aktualisierungen erfolgen, und dann die Computer nach Bedarf zu von Ihnen gewählten Zeiten neu starten, um Dienstunterbrechungen zu vermeiden.
  
Stellen Sie für die manuelle Suche nach Updates eine Verbindung zu jedem Hostserver her, und öffnen Sie die **Systemsteuerung**. Wählen Sie **System- \>und Sicherheitseinstellungen für Windows Update**aus, und verwalten Sie die Updates und Serverneustarts entsprechend Ihrer Umgebung.
  
- Wenn Ihr Standort nur über eine Appliance verfügt, stellen Sie eine Verbindung zu jeder virtuellen Maschine her, und öffnen Sie die **Systemsteuerung**. Wählen Sie **System und \>Sicherheit Windows Update**aus, und konfigurieren Sie dann die Updates und Serverneustarts entsprechend.
    
- Wenn Ihr Standort über mehrere Appliances verfügt, können Benutzer während des Updates nicht auf die Instanz zugreifen, die gerade aktualisiert und neu gestartet wird. Benutzer stellen eine Verbindung zu anderen Instanzen in der Bereitstellung her, bis alle virtuellen Maschinen und alle Skype for Business-Dienste auf den virtuellen Maschinen nach Abschluss der Updates gestartet werden. Um mögliche Ausfallzeiten zu vermeiden, können Sie beim Anwenden der Updates die Instanz aus HA entfernen und sie nach Abschluss des Vorgangs wiederherstellen. Gehen Sie hierfür wie folgt vor:
    
1. Öffnen Sie auf allen Hostservern eine PowerShell-Konsole als Administrator.
    
2. Entfernen Sie die Instanz mit dem folgenden Cmdlet aus HA:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und die virtuelle Maschine neu zu starten.
    
4. Legen Sie die Instanz mit dem folgenden Cmdlet erneut auf HA fest:
    
   ```powershell
   Exit-CcUpdate
   ```

Führen Sie für die Bereitstellungen mit mehreren Standorten die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, wobei die Updates jeweils auf einen Standort angewendet werden.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Tipps für die Installation von Antivirus-Software auf dem Cloud Connector-Hostcomputer

Wenn Sie Antivirus-Software auf dem Cloud Connector-Hostcomputer installieren müssen, müssen Sie die folgenden Ausnahmen hinzufügen:
  
- Lokales Appliance-Verzeichnis auf jedem Computer.
    
- Remote-Websiteverzeichnis auf jedem Computer.
    
- Lokales Websiteverzeichnis auf dem Computer hostet den Stammordner der freigegebenen Website.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Der Prozess Microsoft. RTC. CCE. Managementservice. exe.
