---
title: Problembehandlung bei Ihrer Cloud Connector-Bereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: a80d6977ff565d5d06f2487e5fb3ab8293b5e000
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240750"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Problembehandlung bei Ihrer Cloud Connector-Bereitstellung
 
Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
  
In diesem Thema werden Lösungen für allgemeine Probleme bei Cloud Connector Edition-Bereitstellungen beschrieben. Wenn Probleme mit Anrufen an das und aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) auftreten, können Sie diese anhand der in diesem Thema beschriebenen Lösungen untersuchen.
  
Cloud-Connector bietet integrierte Mechanismen zur Problembehebung einige automatisch. Ein Prozess, der automatischen Erkennung sucht nach potenziellen Problemen mit der Cloud Connector Appliances und, falls möglich, dauert Maßnahme zum Beheben dieser Probleme ohne Eingriffe Administrator. So funktioniert der Erkennungsprozess:
  
- **Erkennung Sequenz:** Der Verwaltung des Connector-Cloud-Dienst ausgeführt wird einen Prozess alle 60 Sekunden, um festzustellen, ob eine Einheit ausgefallen ist. In der Cloud Connector, Version 2.0 und höher verwendet der Erkennungsprozess die Skype für Business Corpnet Schalter zum Beschleunigen des PowerShell-Verbindungen mit der Cloud Connector-Computern. für Versionen vor 2.0 verwendet der Erkennungsprozess Schalters Management Cloud-Connector.
    
    > [!NOTE]
    > Für die automatische Wiederherstellung erfolgreich ausgeführt werden kann muss Netzwerkkonnektivität zwischen dem Host und dem virtuellen Computer über die Host-Netzwerkswitch vorhanden sein. Netzwerkkonnektivität, um sicherzustellen, automatische Erkennung überprüfen und die Wiederherstellung erfolgreich ausgeführt werden kann. 
  
- **Überwachung:** Die folgenden Dienste werden in der Cloud Connector, Version 2.0 und höher überwacht:
    
  - Virtuelle Computer sind nicht auf die Cloud-Connector im Unternehmen oder virtuelle Switches Internet verbunden
    
  - Virtuelle Computer werden im Status gespeichert oder beendet
    
  - Zentralen Verwaltungsserver Diensten: REPLIKAT, Master-Shape
    
  - Mediation Server-Dienste: REPLIKAT, RTCSRV und MEDSVC
    
  - Edge-Server-Dienste: REPLIKAT, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Firewall, die Regeln für CS RTCSRV, klicken Sie auf Edgeserver CS RTCMEDSRV auf Vermittlungsserver deaktiviert sind, eingehend
    
    In der Cloud Connector Version 1.4.2 werden nur die folgenden Dienste überwacht:
    
  - Mediation Server-Dienste: RTCSRV und MEDSVC
    
  - Edge-Server-Dienst: RTCSRV
    
- **Wiederherstellungsprozess:** Wenn alle überwachten Dienste nach unten sind, eine Einheit nach unten markiert ist, und Dienste beendet und manuelle gekennzeichnet, bis alle Probleme aufgelöst werden können. Dadurch wird verhindert, dass Anrufe vom routing an ein Gerät, das anruffehlern führen kann.
    
    Der Cloud Connector-Verwaltungsdienst wird automatische Wiederherstellung wie folgt wiederholen.
    
  - Das ursprüngliche Wiederholungsintervall wird alle zehn Sekunden mit einer maximalen Intervall von einer Stunde.
    
  - Für die ersten drei Wiederherstellungsversuche ist das Intervall 10 Sekunden. Die vierte wiederholen beginnend, erhöht zweimal der vorherigen Intervall Interval Time. Beispielsweise wird der vierte Wiederholungsversuch treten in 20 Sekunden, das fünfte in 40 Sekunden usw. 
    
  - Wenn die maximale Intervall von einer Stunde erreicht ist, werden einmal pro Stunde Wiederholungsversuche fortgesetzt.
    
  - Wenn die Wiederherstellung erfolgreich ist, werden die Zähler Intervall und "Wiederholen" auf die Anfangswerte festgelegt.
    
  - Wenn der Verwaltungsdienst gestartet wird, werden die Zähler Intervall und "Wiederholen" auf die Anfangswerte zurückgesetzt.
    
## <a name="troubleshooting"></a>Problembehandlung

Es folgen Lösungen zu häufig auftretenden Problemen:
  
- **Problem: Die Bereitstellung schlägt fehl oder reagiert nicht mehr bei Ausführung von Bereitstellungsskripten. Nach der Anmeldung bei den einzelnen VMs fehlt die IP-Adresse oder passt nicht zur Verwaltungs-, internen bzw. externen NIC.**
    
    **Lösung:** Dieses Problem kann nicht automatisch aufgelöst werden. Während der Ausführung der VMs können diesen keine NICs hinzugefügt werden. Fahren Sie diese VMs im Hyper-V-Manager herunter und entfernen Sie sie, und führen Sie anschließend die folgenden Cmdlets aus:
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    **Problem: Nach der Installation von Active Directory (AD) und der Gesamtstruktur wurde der CMS-Server bzw. der Vermittlungsserver nicht ordnungsgemäß zur Domäne hinzugefügt.**
    
    **Lösung:** Um dieses Problem zu beheben, führen Sie die folgenden Schritte durch:
    
  - Melden Sie sich beim Active Directory-Server an, und überprüfen Sie, ob die Domäne ordnungsgemäß erstellt wurde.
    
  - Melden Sie sich beim CMS bzw. beim Vermittlungsserver an, und überprüfen Sie, ob der Netzwerkkarte des Unternehmensnetzwerks eine gültige IP-Adresse zugewiesen wurde und ob eine gültige statische IP und ein DNS als IP-Adresse des AD-Servers konfiguriert wurden.
    
  - Melden Sie sich an den CMS/Vermittlungsserver, und öffnen Sie ein Eingabeaufforderungsfenster. Stellen Sie sicher, dass Sie den FQDN und IP-Adresse des Active Directory-Servers Ping ausführen können. Wenn dies nicht möglich ist, kann ein Konflikt der IP-Adresse vorhanden sein. Versuchen Sie, weisen Sie eine neue IP-Adresse für Active Directory und DNS entsprechend auf dem CMS/Vermittlungsserver zu aktualisieren.
    
- **Problem: Sie erhalten die folgende Fehlermeldung "Remove-VMSwitch: Fehler beim virtuellen Ethernet-Switch zu entfernen. Für der virtuelle Switch 'Cloud Connector Management Schalter' kann nicht gelöscht, da sie durch Ausführen von virtuellen Computern verwendet wird, oder in untergeordneten Pools zugewiesen."**
    
    **Lösung:** "Cloud Connector Management Switch" wurde nach der Bereitstellung nicht gelöscht. Wenn dieser Fehler auftritt, navigieren Sie zum Hyper-V-Manager, und stellen Sie sicher, dass keine andere virtuelle Maschine verbunden ist. Wenn nach wie vor virtuelle Maschinen verbunden sind, trennen Sie sie, und löschen Sie den Management-Switch. Wenn der Management-Switch nicht gelöscht werden kann, starten Sie den Hostserver neu, und versuchen Sie es erneut.
    
- **Problem: Sie erhalten die folgende Fehlermeldung angezeigt, "Dienst RTCMRAUTH konnte nicht gestartet. Stellen Sie sicher, dass der Dienst nicht deaktiviert ist."**
    
    > [!NOTE]
    > Dieses Problem betrifft nur Cloud Connector-Versionen vor 1.4.2. 
  
    Der Startfehler kann auch darauf zurückzuführen sein, dass für diesen Front End-Server zuvor ein Failover (Computer-Failover) durchgeführt wurde. In diesem Fall sollten Sie ein Failback (Computer-Failback) starten.
    
    **Lösung:** Dieser Fehler tritt auf einem Edgeserver auf, wenn der Edgeserver dem Zertifikat der Stammzertifizierungsstelle oder dem Zertifikat der Zwischenzertifizierungsstelle nicht vertraut. Selbst wenn ein externes Zertifikat importiert werden kann, ist die Zertifizierungskette unterbrochen. Unter dieser Bedingung kann der RTCMRAUTH- bzw. der RTCSRV-Dienst nicht gestartet werden.
    
    Importieren Sie das Zertifikat der Stammzertifizierungsstelle und alle Zertifikate der Zwischenzertifizierungsstelle Ihres externen Zertifikats manuell auf den Edgeserver, und starten Sie den Edgeserver anschließend neu. Wenn die Dienste RTCMRAUTH und RTCSRV auf dem Edgeserver gestartet werden, navigieren Sie zu Ihrem Hostserver, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:
    
  ```
  Switch-CcVersion
  ```

- 
    
    **Problem: Der Hostserver wurde nach dem Anwenden von Windows-Updates neu gestartet, und vom Server verarbeitete Anrufe sind fehlgeschlagen.**
    
    **Lösung:** Wenn Sie eine Umgebung mit hoher Verfügbarkeit bereitgestellt haben und ein Windows-Update manuell überprüfen und installieren, können Sie mit einem von Microsoft angebotenen Cmdlet einen Hostcomputer (Bereitstellungsinstanz) in die aktuelle Topologie oder aus der aktuellen Topologie verschieben. Führen Sie hierzu die folgenden Schritte aus:
    
1. Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie Folgendes aus:
    
   ```
   Enter-CcUpdate
   ```

2. Suchen und installieren Sie alle verfügbaren Updates.
    
3. Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:
    
   ```
   Exit-CcUpdate
   ```

- 
    
    **Problem: Wenn ein Anruf über einen Skype for Business-Client mit einer PSTN-Nummer getätigt wird, kann der Anruf nicht durch Einladen einer anderen PSTN-Nummer zu einer Konferenz eskaliert werden.**
    
    **Lösung:** Zum Beheben dieses Problems finden Sie unter [Konfigurieren von hybridem online Mediation Server-Einstellungen](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problem: Eine Warnmeldung zum Windows-Update wird angezeigt, wenn Sie Active Directory-Server installieren: „Die automatische Aktualisierung von Windows ist nicht aktiviert. Aktivieren Sie "Windows Update", um sicherzustellen, dass die neu installierte Rolle oder das neu installierte Feature automatisch aktualisiert wird.“**
    
    **Lösung:** Starten einer Mandanten Remote-PowerShell-Sitzung mithilfe der Skype für Business Mandanten-Admin-Anmeldeinformationen, und führen Sie das folgende Cmdlet aus, um die _EnableAutoUpdate_ -Konfiguration Ihrer Website zu überprüfen:
    
  ```
  Get-CsHybridPSTNSite
  ```

    Wenn _EnableAutoUpdate_ auf **True**festgelegt ist, können Sie diese Warnung ignorieren, da der Dienst CCEManagement herunterladen und Installieren von Windows-Updates für virtuelle Computer und den Hostserver behandelt werden sollen. Wenn _EnableAutoUpdate_ auf **False**festgelegt ist, führen Sie folgende Cmdlet auf **True**festlegen.
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Alternativ dazu können Sie Updates manuell suchen und installieren. Informationen hierzu finden Sie im nächsten Abschnitt.
    
- **Problem: Sie erhalten eine Fehlermeldung angezeigt: Appliance kann nicht registriert werden, da der aktuellen Input-Konfiguration \<SiteName\> oder \<ApplianceName\> oder \<Mediation Server-FQDN\> oder \<Mediation Server-IP-Adresse \> steht in Konflikt mit vorhandenen Einheiten. Entfernen Sie Konflikt Appliance oder aktualisieren Sie Ihre Informationen Input-Konfiguration, und klicken Sie dann erneut zu registrieren. "beim Ausführen von Register-CcAppliance, um aktuelle Appliance online zu registrieren.**
    
    **Lösung:** Werte für die \<ApplianceName\>, \<Mediation Server-FQDN\> und \<Mediation Server-IP-Adresse\> muss eindeutig und nur für die Registrierung einer Appliance verwendet. In der Standardeinstellung \<ApplianceName\> stammen aus den Hostnamen. \<Mediation Server-FQDN\> und \<Mediation Server-IP-Adresse\> Konfiguration Ini-Datei definiert.
    
    Wenn Sie beispielsweise (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) zum Registrieren von SiteName=MySite verwenden, aber eine registrierte Appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) vorhanden ist, tritt ein Konflikt auf.
    
    Überprüfen Sie zunächst die Datei „CloudConnector.ini“ im ApplianceRoot-Verzeichnisabschnitt. Sie erhalten \<SiteName\>, \<Mediation Server-FQDN\> und \<Mediation Server-IP-Adresse\> Werte in der Datei. \<ApplianceName\> ist der Hostname der Server.
    
    Zweitens führen starten Mandanten Remote-PowerShell mit Ihrer Skype für Business Mandanten Administratoranmeldeinformationen, Sie das folgende Cmdlet aus, um die registrierten Einheiten zu überprüfen.
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    Nach der Überprüfung aller Konflikte können Sie die Datei „CloudConnector.ini“ mit den Informationen aktualisieren, die mit der registrierten Appliance übereinstimmen, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu beheben.
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problem: Das Cmdlet Get-CcRunningVersion gibt einen leeren Wert zurück, wenn eine auf dem Host bereitgestellten Appliance vorhanden ist.**
    
  **Lösung:** Dies kann bei der Aktualisierung von 1.3.4 oder 1.3.8 zu 1.4.1 auftreten. Wenn Sie Version 1.4.1 mit MSI-Datei installieren, müssen Sie ausführen `Register-CcAppliance` vor dem Ausführen von einem beliebigen anderen Cmdlet. `Register-CcAppliance`die Datei module.ini wird von %UserProfile%\CloudConnector nach % ProgramData%\CloudConnector migriert werden. Wenn Sie die verpasst haben, eine neue module.ini im Ordner %ProgramData%\CloudConnector erstellt werden und die Ausführung-Sicherung Versionsinformationen für 1.3.4 oder 1.3.8 ersetzen.
    
  Vergleichen Sie die Dateien im Ordner %UserProfile%\CloudConnector und %ProgramData%\CloudConnector module.ini. Wenn Unterschiede vorhanden sind, löschen Sie die Datei module.ini in %ProgramData%\CloudConnector und erneut ausführen `Register-CcAppliance`. Sie können auch die Datei manuell fest, um die korrekte Ausführung und Sicherungsversion ändern.
    
- **Problem: Nach der Ausführung des Switch-CcVersion-Cmdlets, um eine ältere Version wechseln, der aktuelle Version des Skripts unterscheidet, wird keine hohe Verfügbarkeit unterstützt für die alte Version.**
    
    **Lösung:** Sie haben beispielsweise von 1.4.1 auf 1.4.2 aktualisiert. Die aktuelle Skriptversion, die durch Ausführen von ermittelt werden kann `Get-CcVersion`, und Ihre ausgeführt wird, die durch Ausführen von ermittelt werden kann `Get-CcRunningVersion` sind beide 1.4.2. Zu diesem Zeitpunkt, wenn Sie ausführen `Switch-CcVersion` die ausgeführte Version zum 1.4.1 wechseln möchten, klicken Sie dann fallen keine Unterstützung hoher Verfügbarkeit für die alte Version.
    
    Um die vollständige Unterstützung von hoher Verfügbarkeit zu erhalten, müssen Sie zurück zu Version 1.4.2 wechseln, damit die zurzeit ausgeführte Version mit der Skriptversion übereinstimmt. Wenn bei Ihrer 1.4.2-Bereitstellung Probleme auftreten, deinstallieren Sie die Version, und installieren Sie sie umgehend neu.
    
- **Problem: Zertifizierungsstellenzertifikate oder interne Zertifikate, die für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellt wurden, laufen in Kürze ab oder sind kompromittiert.**
    
    **Lösung:** Zertifizierungsstellenzertifikate für Skype for Business sind fünf Jahre lang gültig. Für den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver ausgestellte interne Zertifikate sind zwei Jahre lang gültig.
    
    > [!NOTE]
    > In der Cloud Connector, Version 2.0 und höher das Erneuern CcServerCertificate-Cmdlet Update-CcServerCertificate geändert hat, und das Erneuern CcCACertificate-Cmdlet Update-CcCACertificate geändert hat. 
  
    Wenn interne Zertifikaten für den zentralen Verwaltungsspeicher, Vermittlungsserver und Edge-Server in der Nähe Ablauf sind oder gefährdet ist, führen Sie die erneuern CcServerCertificate oder Update-CcServerCertificate-Cmdlet, um Ihre Zertifikate zu erneuern.
    
    Wenn Zertifikate von Zertifizierungsstellen in Ihrer Nähe Ablauf sind, führen Sie das Erneuern CcCACertificate oder Update-CcCACertificate-Cmdlet, um Ihre Zertifikate erneuern.
    
    **Wenn Zertifikate von Zertifizierungsstellen sind beschädigt, und es nur ein einziges Gerät in der Website ist** ausführen die folgenden Schritte:
    
1. Führen Sie das Cmdlet „Enter-CcUpdate“ aus, um Dienste auszugleichen und die Appliance in den Wartungsmodus zu versetzen.
    
2. Führen Sie die folgenden Cmdlets aus, um die Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und neu zu erstellen:
    
    Cloud-Connector-Versionen vor 2.0:
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    Oder Cloud Connector, Version 2.0 und höher:
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. Führen Sie das Exit-CcUpdate-Cmdlet, um Dienste starten und Beenden im Wartungsmodus befindet.
    
4. Führen Sie das Cmdlet „Export-CcRootCertificate“ für die lokale Datei in der Appliance aus. Kopieren Sie dann das exportierte Zertifikat, und installieren Sie es in Ihren PSTN-Gateways. 
    
    Führen Sie folgende Schritte für jede Anwendung in der Website, **Wenn Zertifikate von Zertifizierungsstellen sind beschädigt, und es mehrere Einheiten auf der Website gibt** .
    
    Microsoft empfiehlt, dass Sie diese Schritte nicht spitzenauslastung Zeiten ausführen.
    
   - Führen Sie auf der ersten Appliance das Cmdlet Remove-CcCertificationAuthorityFile zum Bereinigen von der Zertifizierungsstelle Sichern von Dateien in die \<SiteRoot\> Directory.
    
   - Führen Sie das Cmdlet EINGABETASTE CcUpdate abzuleiten Dienste, und platzieren Sie jede Anwendung im Wartungsmodus aus.
    
   - Führen Sie die folgenden Cmdlets aus, um die Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und neu zu erstellen:
    
     Cloud-Connector-Versionen vor 2.0:
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     Oder Cloud Connector, Version 2.0 und höher:
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

   - Führen Sie auf der ersten Appliance So sichern Sie die Zertifizierungsstellen-Dateien in das folgende Cmdlet der \<SiteRoot\> Ordner. Auf allen anderen Einheiten am gleichen Standort später mit dem Cmdlet Reset-CcCACertificate nutzen die Sicherungsdateien der Zertifizierungsstelle automatisch und Appliances verwendet das-Stammzertifikat.
    
     ```
     Backup-CcCertificationAuthority
     ```

   - Führen Sie das Exit-CcUpdate-Cmdlet, um Dienste starten und Beenden im Wartungsmodus befindet. 
    
   - Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate aus jeder Anwendung auf der Website, und installieren Sie das exportierte Zertifikat auf PSTN-Gateways. 
    
- **Problem: Erhalten Sie die folgende Fehlermeldung angezeigt, in der Cloud Connector Management Service-Protokoll, "C:\Programme\Microsoft Files\Skype für Business Cloud Connector Edition\ManagementService\CceManagementService.log": Fehler CceService: 0: Unerwartete Ausnahme beim Statusberichte zu online: System.Management.Automation.CmdletInvocationException: Fehler bei der Anmeldung für den Benutzer \<globaler Administrator\>. Erstellen Sie ein neues Credential-Objekt, und stellen Sie sicher, dass Sie den richtigen Benutzernamen und das Kennwort verwendet haben. ---\>**
    
    **Lösung:** Die Office 365-Mandanten globale Administratorinformationen wurden geändert, seit die Cloud Connector Appliance registriert wurde. Führen Sie zum Aktualisieren der lokal gespeicherten Anmeldeinformationen für die Cloud Connector Appliance Folgendes über Administrator PowerShell in der Host-Anwendung:
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problem: Nachdem Sie das Kennwort für das Host-Server-Konto Sie für die Bereitstellung verwendet ändern, Sie erhalten Sie die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString: Schlüssel ist nicht gültig für die Verwendung in angegebenen Zustand." in %ProgramFiles%\Skype für Business Cloud-Connector Edition\ManagementService\CceManagementService.log oder beim Ausführen des Cmdlets Get-CcCredential.**
    
    **Lösung:** Alle Cloud Connector Anmeldeinformationen werden in der folgenden Datei gespeichert: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ". Wenn sich das Kennwort auf dem Hostserver ändert, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
    
    **Wenn Sie Cloud Connector, Version 1.4.2, ausführen**, generieren Sie mit den folgenden Schritten alle Cloud Connector-Kennwörter neu:
    
  1. Starten Sie den Hostserver neu.
    
  2. Löschen Sie die folgende Datei: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".
    
  3. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance-lokale" die Kennwörter die Beschreibung nach erneut eingeben. Geben Sie die gleichen Kennwörter ein, die Sie vor der Cloud Connector-Bereitstellung eingegeben haben.
    
     **Wenn Sie Cloud Connector, Version 2.0 oder höher, ausführen** neu zu generieren aller Cloud Connector Kennwörter folgende Schritte:
    
  4. Starten Sie den Hostserver neu.
    
  5. Löschen Sie die folgende Datei: "% SystemDrive%\Programdata\Cloudconnector\credentials. \<CurrentUser\>.xml ".
    
  6. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "Register-CcAppliance-lokale" die Kennwörter die Beschreibung nach erneut eingeben. 
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde, verwenden Sie das „VMAdmin“-Kennwort als „CceService“-Kennwort, wenn Sie danach gefragt werden. Geben Sie das gleiche Kennwort ein, das Sie vor der Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector, Version 1.4.2, generiert wurde und die Kennwörter von „DomainAdmin“ und „VMAdmin“ nicht übereinstimmen, müssen Sie die folgenden Schritte ausführen:
    
  7. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
  8. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
  9. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.
    
     Die zwischengespeicherten Kennwortdatei mit Cloud-Connector, Version 2.0 oder höher, standardmäßig generiert wurde, verwenden VmAdmin und DomainAdmin "als CceService dasselbe Kennwort. Wenn Sie die Kennwörter für „DomainAdmin“ und „VMAdmin“ geändert haben, müssen Sie die folgenden Schritte ausführen:
    
  10. Führen Sie „Set-CcCredential -AccountType DomainAdmin“ wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „DomainAdmin“ ein.
    
  11. Führen Sie „Set-CcCredential -AccountType VmAdmin“ wie folgt aus:
    
       1. Wenn Sie zur Eingabe der alten Anmeldeinformationen für das Konto aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das „CceService“-Kennwort verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Anmeldeinformationen für das Konto aufgefordert werden, geben Sie das zuvor verwendete Kennwort für „VmAdmin“ ein.  
    
- **Problem: Mit Cloud-Connector Version 2.1 oder höher, bei der Ausführung von Register-CcAppliance oder anderen Cmdlets auf der Appliance Sie erhalten eine Fehlermeldung wie etwa: "für jedes Objekt: die Eigenschaft"Common"nicht werden für dieses Objekt gefunden kann. Stellen Sie sicher, dass die Eigenschaft vorhanden ist. Unter C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**
    
    **Lösung:** Cloud-Connector 2.1 und höher erfordert .NET Framework 4.6.1 oder höher. Aktualisieren Sie .NET Framework auf die Appliance 4.6.1 Version oder höher, und führen Sie die Cmdlet(s) erneut aus.

- **Problem: Mit Cloud Connector Edition 2.1, wenn Install CcAppliance ausgeführt, Sie erhalten eine Fehlermeldung wie: "Fehler beim Installieren von neuen Instanz mit Fehler:"Status"kann nicht festgelegt werden, da nur Zeichenfolgen als Werte verwendet werden können, XmlNode-Eigenschaften festlegen"**

   **Lösung:** In Cloudconnector.ini, klicken Sie im Abschnitt [Common] Fügen Sie hinzu Config "Status" wie folgt: CountryCode = US Zustand = WA Ort = "Redmond"

   Es ist nicht notwendig für die Zeile "Status"-Wert aufweisen, jedoch die Zeile "State" aus der Datei Cloudconnector.ini nicht entfernt werden kann.

- **Problem: Sie erhalten die folgende Fehlermeldung "Dismount-WindowsImage: Dismount-WindowsImage ist fehlgeschlagen. Fehlercode = 0xc1550115 "beim Installieren oder Aktualisieren von Cloud-Connector Edition.**
    
    **Lösung:** Starten Sie eine PowerShell-Konsole als Administrator ausführen "DISM-Cleanup-Wim'". Damit werden alle von dem Problem betroffenen Images bereinigt. Führen Sie „Install-CcAppliance“ erneut aus, oder warten Sie, bis die Bits automatisch aktualisiert werden.
    
- **Problem: Die Bereitstellung der ersten Cloud Connector Appliance in einer Umgebung HA fehlschlägt**
    
    **Lösung:** Die erforderlichen Schritte hängen von den Grund Fehler bei der Bereitstellung:
    
  - Wenn die erste Cloud Connector Appliance fehlschlägt, und Sie nicht die Ursache des Fehlers bestimmen, müssen Sie installieren Sie das Gerät erneut, bis die Bereitstellung erfolgreich ist, und installieren Sie dann den anderen Appliances.
    
  - Schlägt die erste Cloud Connector Appliance eine kleinere Problem, wie ein Problem externes Zertifikat können Sie das Problem zu beheben, ohne das Gerät erneut installieren sein. Sie können dann mit Mandanten für remote-PowerShell wie folgt die Bereitstellung als erfolgreich markieren. (Sie können auch die folgenden Schritte aus, wenn die erste Bereitstellung erfolgreich war, aber aus irgendeinem Grund Cloud-Connector ein Fehler auftritt, die Bereitstellung als einen Erfolg gemeldet.)
    
  - Wenn die Identität (GUID) der ersten Cloud Connector Appliance erhalten möchten, führen Sie das Cmdlet Get-CsHybridPSTNAppliance.
    
  - Um die Appliance als erfolgreich bereitgestellt zu markieren, führen Sie das Set-CsCceApplianceDeploymentStatus wie folgt aus:
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problem: Auf dem Hostserver oder den virtuellen Maschinen müssen Sie manuell nach Windows-Updates suchen bzw. diese installieren.**
    
   **Lösung:** Wir empfehlen Ihnen, dass Sie die Vorteile der automatisierten Betriebssystem-Updates der Skype for Business Cloud Connector Edition nutzen. Nachdem eine Appliance für die Online-Verwaltung registriert und das automatische Update des Betriebssystems aktiviert wurde, werden Windows-Updates vom Hostserver von den virtuellen Maschinen automatisch in Übereinstimmung mit den Windows-Einstellungen der Aktualisierungszeit für das Betriebssystem gesucht und installiert.
    
   Wenn Sie manuell nach Windows-Updates suchen und diese installieren müssen, führen Sie die zu Ihrem Bereitstellungstyp passenden Schritte in diesem Abschnitt durch. Sie sollten das gleichzeitige Update des Hostservers und der darauf ausgeführten virtuellen Maschinen planen, um die bei Updates entstehenden Ausfallzeiten zu minimieren.
    
   Sie können auch einen WSUS (Windows Server Update Services)-Server für die Bereitstellung von Updates für Cloud Connector-Server verwenden. Stellen Sie hierfür nur sicher, dass Sie **nicht** die automatische Installation von Windows-Update konfigurieren.
    
   Weitere Informationen zum manuellen Update Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.
    
- **Problem: Wenn Cloud Connector auf einen neuen Build aktualisiert werden, werden die Cloud Connector-Cmdlets nicht aktualisiert.** In diesem Fall manchmal auf, wenn ein PowerShell-Fenster geöffnet gelassen wird bei der automatischen Aktualisierung.
    
  **Lösung:** Um die aktualisierten Cmdlets zu laden, können Sie entweder die folgenden Schritte ausführen:
    
   - Schließen Sie PowerShell in der Cloud Connector-Anwendung, und klicken Sie dann öffnen Sie PowerShell.
    
     - Oder führen Sie Import-Module CloudConnector-Force. 
 
-   **Problem: "der Begriff 'Stop-CsWindowsService' ist nicht als den Namen eines-Cmdlet, Funktion, Skriptdatei oder betriebsbereiten Programm. erkannt" Fehler beim Versuch, EINGABETASTE CcUpdate-Cmdlet ausführen.**

    **Lösung:** Löschen Sie die Datei $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache.
PowerShell erstellt diese Datei als Cache des Cmdlets von Modulen, die es findet, sodass es nicht alle Module jedes Mal als erneut analysieren, die langsam Dinge machen. In den meisten Fällen gab es einige eine Beschädigung der Datei, die irreführende Ergebnisse PowerShell bereitgestellt werden, wenn es wieder aus diesem Cache gelesen wurde.

-   **Problem: "Import-Module CloudConnector" generiert Fehler "Import-Module: das angegebene Modul"CloudConnector"wurde nicht geladen werden, da kein gültiges Modul-Datei in einem beliebigen Modulverzeichnis gefunden wurde"**

    **Lösung:**
    - Überprüfen Sie, dass tatsächlich das Modul CloudConnector unter c:\Program Files\WindowsPowerShell\Modules vorhanden ist
    
    - Nachdem das Modul CloudConnector validieren unter diesem Speicherort vorhanden ist, kann die PSModulePath-Umgebungsvariable speichern den Pfad zu der Speicherorte der Module geändert werden:
    
     a. Temporäre ändern: Start Powershell als Administrator an, und führen Sie folgenden Befehl: $env: PSModulePath = $env: PSModulePath + "; C:\Programme\Microsoft Files\WindowsPowerShell\Modules\"
        
     b. Für persistent ändern, starten Sie PowerShell als Administrator an, und führen die folgenden Befehle, die jeweils: $CurrentValue = [Umgebung]:: GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Programme\Microsoft Files\WindowsPowerShell\Modules","Computer")

    
## <a name="install-windows-updates-manually"></a>Manuelles Installieren von Windows-updates

Gehen folgendermaßen Sie vor, um zu prüfen, ob und Anwenden von Updates für Windows, wenn Sie nicht automatische Updates in Ihrer Umgebung verwenden möchten. Suchen nach und Installieren von Windows-Updates erfordern möglicherweise einen Neustart des Servers. Wenn Sie ein Hostserver neu gestartet wird, werden Benutzer müssen nicht Cloud Connector zu tätigen oder Entgegennehmen von Anrufen verwendet. Sie können Aktualisierungen manuell suchen und installieren, um zu steuern, wann die Aktualisierungen erfolgen, und dann die Computer nach Bedarf zu von Ihnen gewählten Zeiten neu starten, um Dienstunterbrechungen zu vermeiden.
  
Stellen Sie für die manuelle Suche nach Updates eine Verbindung zu jedem Hostserver her, und öffnen Sie die **Systemsteuerung**. Wählen Sie **System und Sicherheit \>Windows Update**, und klicken Sie dann die Updates verwalten und Neustart des Servers als Antwort für Ihre Umgebung.
  
- Wenn Ihr Standort nur über eine Appliance verfügt, stellen Sie eine Verbindung zu jeder virtuellen Maschine her, und öffnen Sie die **Systemsteuerung**. Wählen Sie **System und Sicherheit \>Windows Update**, und konfigurieren Sie anschließend die Updates und Neustart des Servers als Antwort.
    
- Wenn Ihr Standort über mehrere Appliances verfügt, können Benutzer während des Updates nicht auf die Instanz zugreifen, die gerade aktualisiert und neu gestartet wird. Benutzer stellen eine Verbindung zu anderen Instanzen in der Bereitstellung her, bis alle virtuellen Maschinen und alle Skype for Business-Dienste auf den virtuellen Maschinen nach Abschluss der Updates gestartet werden. Um mögliche Ausfallzeiten zu vermeiden, können Sie beim Anwenden der Updates die Instanz aus HA entfernen und sie nach Abschluss des Vorgangs wiederherstellen. Gehen Sie hierfür wie folgt vor:
    
1. Öffnen Sie auf allen Hostservern eine PowerShell-Konsole als Administrator.
    
2. Entfernen Sie die Instanz mit dem folgenden Cmdlet aus HA:
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und die virtuelle Maschine neu zu starten.
    
4. Legen Sie die Instanz mit dem folgenden Cmdlet erneut auf HA fest:
    
   ```
   Exit-CcUpdate
   ```

Führen Sie für die Bereitstellungen mit mehreren Standorten die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, wobei die Updates jeweils auf einen Standort angewendet werden.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Tipps bei der Installation von Antivirussoftware auf dem Hostcomputer Cloud-Connector

Wenn Sie Antivirensoftware auf dem Hostcomputer Cloud Connector installieren möchten, müssen Sie die folgenden Ausnahmen hinzufügen:
  
- Lokale Appliance-Verzeichnis auf jedem Computer.
    
- Remote Websiteverzeichnis auf jedem Computer.
    
- Lokale Websiteverzeichnis auf dem Computer dient als Host den Stammordner für freigegebene Websites.
    
- %ProgramFiles%\Skype für Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Der Vorgang Microsoft.Rtc.CCE.ManagementService.exe.
