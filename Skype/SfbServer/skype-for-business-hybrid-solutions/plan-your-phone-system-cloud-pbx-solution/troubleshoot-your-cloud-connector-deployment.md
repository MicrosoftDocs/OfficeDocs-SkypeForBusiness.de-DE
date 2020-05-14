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
ms.openlocfilehash: 97ece0ee1bcc11c22fd55709d025169ed95b16ff
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220225"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a>Problembehandlung bei Ihrer Cloud Connector-Bereitstellung
 
Problembehandlung bei der Cloud Connector Edition-Bereitstellung.
  
In diesem Thema werden Lösungen für häufige Probleme mit Cloud Connector Edition-Bereitstellungen beschrieben. Wenn Probleme mit Anrufen von und über das Telefon Festnetz (Public Switched Telephone Network, PSTN) auftreten, können Sie anhand der in diesem Thema beschriebenen Lösungen nachforschen.
  
Cloud Connector bietet integrierte Mechanismen zum automatischen Beheben von Problemen. Ein automatischer Erkennungsprozess sucht nach potenziellen Problemen mit den Cloud Connector-Appliances und führt, wenn möglich, Korrekturmaßnahmen durch, um diese Probleme zu beheben, ohne dass ein Administratoreingriff erforderlich ist. Der Erkennungsprozess funktioniert wie folgt:
  
- **Erkennungssequenz:** Der Cloud Connector-Verwaltungsdienst führt einen Prozess alle 60 Sekunden aus, um festzustellen, ob eine Appliance nicht aktiv ist. In Cloud Connector Version 2,0 und höher verwendet der Erkennungsprozess den Skype for Business Corpnet-Switch, um PowerShell-Verbindungen mit den Cloud Connector-Computern herzustellen. für frühere Versionen von 2,0 wird im Erkennungsprozess der Cloud Connector-Verwaltungs Switch verwendet.
    
    > [!NOTE]
    > Damit die automatische Wiederherstellung erfolgreich ausgeführt werden kann, muss die Netzwerkverbindung zwischen dem Host und den virtuellen Computern über den Host Netzwerk Switch erfolgen. Stellen Sie sicher, dass Sie die Netzwerkkonnektivität überprüfen, um sicherzustellen, dass die automatische Erkennung und Wiederherstellung erfolgreich ist. 
  
- **Überwachung:** Die folgenden Dienste werden in Cloud Connector, Version 2,0 und höher, überwacht:
    
  - Virtuelle Computer sind nicht mit den Cloud Connector-Unternehmens-oder Internet-Switches verbunden
    
  - Virtuelle Computer befinden sich in einem gespeicherten oder gestoppten Status
    
  - Dienste für den zentralen Verwaltungs Server: Replikat, Master
    
  - Vermittlungsserver Dienste: Replica, RTCSRV und MEDSVC
    
  - Edgeserver Dienste: Replica, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY
    
  - Eingehende Firewallregeln sind für CS RTCSRV auf dem Edgeserver, CS RTCMEDSRV auf dem Vermittlungsserver, deaktiviert.
    
    In Cloud Connector, Version 1.4.2, werden nur die folgenden Dienste überwacht:
    
  - Vermittlungsserver Dienste: RTCSRV und MEDSVC
    
  - Edgeserver Dienst: RTCSRV
    
- **Wiederherstellungsprozess:** Wenn überwachte Dienste nicht verfügbar sind, wird eine Appliance markiert, und die Dienste werden angehalten und manuell markiert, bis alle Probleme gelöst werden können. Dadurch wird verhindert, dass Anrufe an eine Appliance weitergeleitet werden, die zu Anruf Fehlern führen können.
    
    Der Cloud Connector-Verwaltungsdienst führt die automatische Wiederherstellung wie folgt erneut aus.
    
  - Das anfängliche Wiederholungsintervall beträgt alle zehn Sekunden mit einer maximalen Intervallzeit von einer Stunde.
    
  - Für die ersten drei Wiederherstellungsversuche beträgt die Intervallzeit 10 Sekunden. Ab dem vierten Wiederholungsversuch nimmt die Intervallzeit um das Zweifache der vorherigen Intervallzeit zu. Beispielsweise wird der vierte Wiederholungsversuch in 20 Sekunden, dem fünften in 40 Sekunden usw. ausgeführt. 
    
  - Wenn die maximale Intervallzeit von einer Stunde erreicht wird, werden Wiederholungsversuche einmal pro Stunde fortgesetzt.
    
  - Wenn die Wiederherstellung erfolgreich ist, werden die Intervall-und Wiederholungszähler auf Ihre anfänglichen Werte festgelegt.
    
  - Wenn der Verwaltungsdienst neu gestartet wird, werden das Intervall und die Wiederholungsanzahl auf die ursprünglichen Werte zurückgesetzt.
    
## <a name="troubleshooting"></a>Problembehandlung

Im folgenden finden Sie Lösungen zu häufig auftretenden Problemen:
  
- **Problem: die Bereitstellung schlägt fehl oder reagiert nicht mehr, wenn die Bereitstellungsskripts ausgeführt werden. Nach der Anmeldung bei den einzelnen VM-Daten ist die IP-Adresse für die Verwaltungs-/interne/externe NIC nicht vorhanden oder falsch.**
    
    **Lösung:** Dieses Problem kann nicht automatisch aufgelöst werden. NICs können während der Ausführung nicht zu VMS hinzugefügt werden. Beenden Sie diese VMs in Hyper-v Manager, und führen Sie dann die folgenden Cmdlets aus:
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    **Problem: Nachdem der Active Directory Server und die Gesamtstruktur installiert wurden, wurde der CMS-Server und/oder Vermittlungsserver der Domäne nicht ordnungsgemäß hinzugefügt.**
    
    **Lösung:** Führen Sie die folgenden Schritte aus, um dieses Problem zu beheben:
    
  - Melden Sie sich am Active Directory Server an, und überprüfen Sie, ob die Domäne ordnungsgemäß erstellt wurde.
    
  - Melden Sie sich beim CMS/Vermittlungsserver an, und stellen Sie sicher, dass auf der Corpnet-NIC eine gültige IP-Adresse zugewiesen ist und dass gültige statische IP-Adressen und DNS als IP-Adresse des Ad-Servers konfiguriert ist.
    
  - Melden Sie sich beim CMS/Vermittlungsserver an, und öffnen Sie eine Eingabeaufforderung. Stellen Sie sicher, dass Sie den FQDN und die IP-Adresse des Active Directory Servers pingen können. Wenn dies nicht der Fall ist, liegt möglicherweise ein IP-Adresskonflikt vor. Versuchen Sie, eine neue IP für Active Directory zuzuweisen und DNS auf dem CMS/Vermittlungsserver entsprechend zu aktualisieren.
    
- **Problem: Sie erhalten die folgende Fehlermeldung "Remove-VMSwitch: failed beim Entfernen des virtuellen Ethernet-Switches". Der virtuelle Switch ' Cloud Connector Management Switch ' kann nicht gelöscht werden, da er von virtuellen Computern verwendet oder untergeordneten Pools zugewiesen wird. "**
    
    **Lösung:** Der "Cloud Connector-Verwaltungs Switch" wurde nach der Bereitstellung nicht gelöscht. Wenn Sie diesen Fehler getroffen haben, wechseln Sie zu Hyper-v-Manager, und stellen Sie sicher, dass noch kein virtueller Computer verbunden ist. Wenn noch virtuelle Computer angeschlossen sind, trennen Sie Sie, und löschen Sie den Verwaltungs Switch. Wenn der Verwaltungs Switch immer noch nicht gelöscht werden kann, starten Sie den Hostserver neu, und versuchen Sie es erneut.
    
- **Problem: Sie erhalten die folgende Fehlermeldung "Dienst RTCMRAUTH konnte nicht gestartet werden. Stellen Sie sicher, dass der Dienst nicht deaktiviert ist. "**
    
    > [!NOTE]
    > Dieses Problem bezieht sich nur auf Cloud Connector-Versionen früher als 1.4.2. 
  
    Der Fehler beim starten könnte auch daran liegen, dass dieser Front-End-Server zuvor einen Failover durchführen konnte (bei einem Computer Failover). Wenn dies der Fall ist, rufen Sie Fail Back (using Computer Fail Back) auf.
    
    **Lösung:** Dieses Problem tritt auf einem Edgeserver auf, wenn das Zertifikat der Stammzertifizierungsstelle oder das Zertifikat der Zwischenzertifizierungsstelle nicht vom Edgeserver als vertrauenswürdig eingestuft wird. Selbst wenn das externe Zertifikat importiert werden kann, die Zertifikatkette jedoch beschädigt ist. Unter dieser Bedingung kann der RTCMRAUTH-und/oder der RTCSRV-Dienst nicht gestartet werden.
    
    Importieren Sie das Zertifikat der Stammzertifizierungsstelle und alle Zertifikate der Zwischenzertifizierungsstelle Ihres externen Zertifikats manuell in das Edgeserver, und starten Sie dann den Edgeserver neu. Nachdem Sie die RTCMRAUTH-und RTCSRV-Dienste im Edgeserver gestartet haben, kehren Sie zu Ihrem Host Server zurück, starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um zur neuen Bereitstellung zu wechseln:
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    **Problem: der Hostserver wurde neu gestartet, als Windows-Updates angewendet wurden, und Anrufe, die vom Server gewartet werden, schlagen fehl.**
    
    **Lösung:** Wenn Sie eine Umgebung mit hoher Verfügbarkeit bereitgestellt haben, stellt Microsoft ein Cmdlet zur Verfügung, mit dem ein Hostcomputer (Bereitstellungs Instanz) bei der manuellen Überprüfung und Installation von Windows Update in die oder aus der aktuellen Topologie gebracht werden kann. Führen Sie die folgenden Schritte aus, um dies zu erreichen:
    
1. Starten Sie auf dem Hostserver eine PowerShell-Konsole als Administrator, und führen Sie dann Folgendes aus:
    
   ```powershell
   Enter-CcUpdate
   ```

2. Suchen Sie nach Updates, und installieren Sie alle verfügbaren.
    
3. Führen Sie in der PowerShell-Konsole das folgende Cmdlet aus:
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    **Problem: Wenn ein Anruf von einem Skype for Business-Client mit einer PSTN-Nummer getätigt wird, kann der Anruf nicht durch einladen einer anderen PSTN-Nummer zu einer Konferenz eskaliert werden.**
    
    **Lösung:** Informationen zum Beheben dieses Problems finden Sie unter [configure Online Hybrid Vermittlungsserver Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).
    
- **Problem: bei der Installation von Active Directory Server wird eine Warnmeldung zu Windows Update angezeigt – "automatische Windows-Updates sind nicht aktiviert. Aktivieren Sie Windows Update, um sicherzustellen, dass die neu installierte Rolle oder das Feature automatisch aktualisiert wird. "**
    
    **Lösung:** Starten Sie eine Remote PowerShell-Mandanten Sitzung mit Skype for Business Mandanten-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die _EnableAutoUpdate_ -Konfiguration Ihrer Website zu überprüfen:
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    Wenn _EnableAutoUpdate_ auf **true**festgelegt ist, können Sie diese Warnmeldung gefahrlos ignorieren, da der CCEManagement-Dienst das herunterladen und Installieren von Windows-Updates für virtuelle Computer und den Hostserver übernimmt. Wenn _EnableAutoUpdate_ auf **false**festgelegt ist, führen Sie das folgende Cmdlet aus, um es auf **true**festzulegen.
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    Alternativ können Sie auch manuell nach Updates suchen und diese installieren. Informationen dazu finden Sie im nächsten Abschnitt.
    
- **Problem: Sie erhalten eine Fehlermeldung: die Appliance kann nicht registriert werden, da Ihre aktuelle Eingabe/Konfiguration \< Sitename \> oder \< Appliancename \> oder \< Vermittlungsserver FQDN \> oder \< Vermittlungsserver IP-Adresse \> mit vorhandenen Appliances in Konflikt steht. Entfernen Sie die Konflikt-Appliance oder aktualisieren Sie Ihre Eingabe/Konfigurationsinformationen, und registrieren Sie sich dann erneut. ' beim Ausführen von Register-ccappliance ", um die aktuelle Appliance online zu registrieren.**
    
    **Lösung:** Werte für den \< Appliancename \> , \< Vermittlungsserver FQDN \> und \< Vermittlungsserver IP-Adresse \> müssen eindeutig sein und nur für eine Appliance-Registrierung verwendet werden. Standardmäßig \< kommt Appliancename \> aus dem Hostnamen. \<Vermittlungsserver FQDN \> und \< Vermittlungsserver IP-Adresse, die \> in der Konfigurations-ini-Datei definiert ist.
    
    Verwenden Sie beispielsweise (Appliancename = MyserverNew, Vermittlungsserver FQDN = ms. contoso. com, Vermittlungsserver IP Address = 10.10.10.10), um sich auf Sitename = mysite zu registrieren, aber wenn es eine registrierte Appliance gibt (Appliancename = MyServer, Vermittlungsserver FQDN = ms. contoso. com, Vermittlungsserver IP Address = 10.10.10.10), haben Sie den Konflikt.
    
    Überprüfen Sie zuerst die Datei "cloudconnector. ini im Abschnitt ApplianceRoot Directory. Sie erhalten \< Sitename \> , \< Vermittlungsserver FQDN \> und \< Vermittlungsserver IP-Adress \> Werte in der Datei. \<Appliancename \> ist der Name des Hostservers.
    
    Starten Sie als zweites die mandantenfähige Remote-PowerShell mit Ihren Skype for Business Mandanten-Administratoranmeldeinformationen, und führen Sie dann das folgende Cmdlet aus, um die registrierten Appliances zu überprüfen.
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    Nachdem Sie Konflikte identifiziert haben, können Sie entweder Ihre "cloudconnector. ini-Datei mit Informationen aktualisieren, die mit der registrierten Appliance übereinstimmen, oder die Registrierung der vorhandenen Appliance aufheben, um die Konflikte zu lösen.
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- **Problem: das Get-CcRunningVersion-Cmdlet gibt einen leeren Wert zurück, wenn auf dem Host eine bereitgestellte Appliance installiert ist.**
    
  **Lösung:** Dies kann passieren, wenn Sie ein Upgrade von 1.3.4 oder 1.3.8 auf 1.4.1 durchführen. Nachdem Sie die Version 1.4.1 mit der MSI-Installation installiert haben, müssen Sie ausgeführt werden, `Register-CcAppliance` bevor Sie ein anderes Cmdlet ausführen. `Register-CcAppliance`die Datei "Module. ini" wird von%USERPROFILE%\CloudConnector zu%ProgramData%\CloudConnector. migriert. Wenn Sie es verpasst haben, wird im Ordner%ProgramData%\CloudConnector eine neue Modul. ini erstellt, und die Informationen zur laufenden/Sicherungsversion für 1.3.4 oder 1.3.8 werden ersetzt.
    
  Vergleichen Sie die Modul. ini-Dateien im Ordner%UserProfile%\CloudConnector und%ProgramData%\CloudConnector. Wenn es Unterschiede gibt, löschen Sie die Datei Module. ini in%ProgramData%\CloudConnector, und führen Sie eine erneute Ausführung aus `Register-CcAppliance` . Sie können die Datei auch manuell in die richtige Ausführungs-und Sicherungsversion ändern.
    
- **Problem: Nachdem Sie das Switch-CcVersion-Cmdlet ausgeführt haben, um zu einer älteren Version zu wechseln, die sich von der aktuellen Skriptversion unterscheidet, gibt es keine Unterstützung für hohe Verfügbarkeit für diese alte Version.**
    
    **Lösung:** Sie haben beispielsweise ein Upgrade von 1.4.1 auf 1.4.2 durchgeführt. Ihre aktuelle Skriptversion, die durch Ausführen bestimmt werden kann `Get-CcVersion` , und die laufende Version, die durch Ausführen bestimmt werden kann, `Get-CcRunningVersion` sind beide 1.4.2. Wenn Sie zu diesem Zeitpunkt ausführen, `Switch-CcVersion` um die ausgeführte Version wieder auf 1.4.1 umzuschalten, wird keine Unterstützung für hohe Verfügbarkeit für diese alte Version verfügbar sein.
    
    Um eine vollständige Unterstützung für hohe Verfügbarkeit zu erhalten, wechseln Sie zurück zu 1.4.2, sodass die laufende Version und die Skriptversion identisch sind. Wenn Probleme mit ihrer 1.4.2-Bereitstellung auftreten, deinstallieren Sie Sie, und installieren Sie Sie so bald wie möglich neu.
    
- **Problem: Zertifikat Zertifizierungsstellenzertifikate oder interne Zertifikate, die für zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver ausgestellt wurden, sind nahezu abgelaufen oder werden kompromittiert.**
    
    **Lösung:** Skype for Business Zertifizierungsstellenzertifikate sind fünf Jahre gültig. Interne Zertifikate, die für die zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver ausgestellt wurden, gelten für zwei Jahre.
    
    > [!NOTE]
    > In Cloud Connector Version 2,0 und höher wurde das Cmdlet Renew-ccservercertificate "in Update-ccservercertificate" geändert, und das Cmdlet Renew-cccacertificate "wurde in Update-cccacertificate" geändert. 
  
    Wenn die für zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver ausgestellten internen Zertifikate nahezu abgelaufen sind oder kompromittiert sind, führen Sie das Cmdlet Renew-ccservercertificate "oder Update-ccservercertificate" aus, um Ihre Zertifikate zu erneuern.
    
    Wenn Zertifizierungsstellenzertifikate kurz vor dem Ablauf sind, führen Sie das Cmdlet Renew-cccacertificate "oder Update-cccacertificate" aus, um Ihre Zertifikate zu erneuern.
    
    **Wenn Zertifizierungsstellenzertifikate kompromittiert sind und nur eine Appliance am Standort vorhanden ist,** führen Sie die folgenden Schritte aus:
    
1. Führen Sie das Cmdlet Enter-CCUpdate "aus, um die Dienste zu entladen und die Appliance in den Wartungsmodus zu versetzen.
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. Führen Sie die folgenden Cmdlets aus, um neue Zertifizierungsstellenzertifikate und alle internen Serverzertifikate zurückzusetzen und zu erstellen:
    
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
    
3. Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate aus der Appliance aus, und installieren Sie dann das exportierte Zertifikat in ihren PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf dem Gateway ausgeben.

   ```powershell
   Export-CcRootCertificate
   ```

4. Führen Sie das Cmdlet Exit-CCUpdate "aus, um die Dienste zu starten und den Wartungsmodus zu beenden.

   ```powershell
   Exit-CcUpdate
   ```


    **Wenn Zertifizierungsstellenzertifikate kompromittiert sind und sich an dem Standort mehrere Appliances befinden,** führen Sie die folgenden Schritte auf jeder Appliance am Standort aus.
    
    Microsoft empfiehlt, dass Sie diese Schritte während nicht-Spitzennutzungszeiten durchführen.
    
1. Führen Sie auf der ersten Appliance das Cmdlet Remove-CcCertificationAuthorityFile aus, um die Sicherungsdateien der Zertifizierungsstelle im SiteRoot-Verzeichnis zu bereinigen \< \> .

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. Führen Sie das Cmdlet Enter-CCUpdate "aus, um die Dienste zu entladen und die einzelnen Appliances in den Wartungsmodus zu versetzen.

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

4. Führen Sie auf der ersten Appliance das folgende Cmdlet aus, um die Zertifizierungsstellen Dateien im \< Ordner SiteRoot zu sichern \> .
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. Führen Sie auf allen anderen Appliances am selben Standort die folgenden Befehle aus, um die Sicherungsdateien der Zertifizierungsstelle zu nutzen, damit die Appliances alle dasselbe Stammzertifikat verwenden und dann neue Zertifikate anfordern. 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. Wenn TLS zwischen dem Gateway und dem Vermittlungsserver verwendet wird, führen Sie das Cmdlet Export-CcRootCertificate von einer beliebigen Appliance am Standort aus, und installieren Sie dann das exportierte Zertifikat in ihren PSTN-Gateways. Möglicherweise müssen Sie das Zertifikat auch erneut auf dem Gateway ausgeben.
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. Führen Sie das Cmdlet Exit-CCUpdate "aus, um die Dienste zu starten und den Wartungsmodus zu beenden. 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- **Problem: Sie erhalten die folgende Fehlermeldung im Cloud Connector-Verwaltungsdienst Protokoll "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": "cceservice"-Fehler: 0: unerwartete Ausnahme beim Melden von Status an Online: System. Management. Automation. CmdletInvocationException: Anmeldung für den Benutzer \< "globaler mandantenadministrator" fehlgeschlagen \> . Erstellen Sie ein neues Credential-Objekt, um sicherzustellen, dass Sie den richtigen Benutzernamen und das richtige Kennwort verwendet haben. ---\>**
    
    **Lösung:** Die Anmeldeinformationen des globalen Mandanten Administrators von Microsoft 365 oder Office 365 wurden seit der Registrierung der Cloud Connector-Appliance geändert. Um die lokal gespeicherten Anmeldeinformationen in der Cloud Connector-Appliance zu aktualisieren, führen Sie die folgenden von Administrator-PowerShell auf der Host-Appliance aus:
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- **Problem: nach dem Ändern des Kennworts für das Hostserver Konto, das Sie für die Bereitstellung verwendet haben, wird die folgende Fehlermeldung angezeigt: "ConvertTo-SecureString: Key ungültig für die Verwendung in angegebenem Zustand." in%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log oder beim Ausführen des Cmdlets Get-CcCredential.**
    
    **Lösung:** Alle Cloud Connector-Anmeldeinformationen werden in der folgenden Datei gespeichert: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ". Wenn das Kennwort auf dem Hostserver geändert wird, müssen Sie die lokal gespeicherten Anmeldeinformationen aktualisieren.
    
    **Wenn Sie Cloud Connector, Version 1.4.2, ausführen, generieren Sie** alle Cloud Connector-Kennwörter mit den folgenden Schritten neu:
    
  1. Starten Sie den Hostserver neu.
    
  2. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".
    
  3. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-ccappliance"-local "aus, um die Kennwörter nach der Beschreibung erneut einzugeben. Geben Sie dieselben Kennwörter ein, die Sie zuvor für die Cloud Connector-Bereitstellung eingegeben haben.
    
     **Wenn Sie Cloud Connector, Version 2,0 oder höher, ausführen, generieren Sie** alle Cloud Connector-Kennwörter mit den folgenden Schritten neu:
    
  4. Starten Sie den Hostserver neu.
    
  5. Löschen Sie die folgende Datei: "%SystemDrive%\Programdata\Cloudconnector\credentials. \< CurrentUser \> . xml ".
    
  6. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie dann "Register-ccappliance"-local "aus, um die Kennwörter nach der Beschreibung erneut einzugeben. 
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector Version 1.4.2 generiert wurde, verwenden Sie das "vmadmin"-Kennwort für das "cceservice"-Kennwort, wenn Sie dazu aufgefordert werden. Geben Sie das gleiche Kennwort ein, das Sie zuvor für die Cloud Connector-Bereitstellung für alle anderen Konten eingegeben haben.
    
     Wenn die zwischengespeicherte Kennwortdatei mit dem Cloud Connector Version 1.4.2 generiert wurde und die DomainAdmin-und "vmadmin"-Kennwörter unterschiedlich sind, müssen Sie die folgenden Schritte ausführen:
    
  7. Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:
    
  8. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das "cceservice"-Kennwort verwendet haben.
    
  9. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das DomainAdmin-Kennwort ein, das Sie zuvor verwendet haben.
    
     Wenn die zwischengespeicherte Kennwortdatei mit Cloud Connector Version 2,0 oder höher generiert wurde, verwenden "vmadmin" und DomainAdmin standardmäßig dasselbe Kennwort wie "cceservice". Wenn Sie die DomainAdmin-und "vmadmin"-Kennwörter geändert haben, müssen Sie die folgenden Schritte ausführen:
    
  10. Führen Sie wie folgt "Sets-CcCredential-AccountType DomainAdmin" aus:
    
       1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das Kennwort "cceservice" verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das DomainAdmin-Kennwort ein, das Sie zuvor verwendet haben.
    
  11. Führen Sie wie folgt "Sets-CcCredential-AccountType" vmadmin "" aus:
    
       1. Wenn Sie zur Eingabe der alten Kontoanmeldeinformationen aufgefordert werden, geben Sie die Anmeldeinformationen ein, die Sie für das Kennwort "cceservice" verwendet haben.
    
       2. Wenn Sie zur Eingabe der neuen Kontoanmeldeinformationen aufgefordert werden, geben Sie das Kennwort für das "vmadmin"-Kennwort ein, das Sie zuvor verwendet haben. 
    
- **Problem: bei der Cloud Connector-Version 2,1 und höher wird beim Ausführen von Register-ccappliance "oder anderen Cmdlets für die Appliance eine Fehlermeldung wie:" für jedes-Objekt: die Eigenschaft "Common" kann für dieses Objekt nicht gefunden werden angezeigt. Stellen Sie sicher, dass die Eigenschaft vorhanden ist. Unter C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 Char: 14 "**
    
    **Lösung:** Für Cloud Connector 2,1 und höher ist .NET Framework 4.6.1 oder höher erforderlich. Aktualisieren Sie .NET Framework auf der Appliance auf Version 4.6.1 oder höher, und führen Sie das Cmdlet (s) erneut aus.

- **Problem: bei der Cloud Connector Edition 2,1 wird bei der Ausführung von install-ccappliance "eine Fehlermeldung wie die folgende angezeigt:" Fehler beim Installieren der neuen Instanz mit Fehler: "State kann nicht festgelegt werden", da nur Zeichenfolgen als Werte zum Festlegen von XmlNode-Eigenschaften verwendet werden können "**

   **Lösung:** Fügen Sie in "cloudconnector. ini im Abschnitt [common] die Konfigurationsdatei" State "wie unten hinzu: CountryCode = US State = WA City = Redmond

   Es ist nicht erforderlich, dass die "State"-Reihe einen Wert aufweist, die "State"-Reihe kann jedoch nicht aus der Datei "" cloudconnector. ini "entfernt werden.

- **Problem: Sie erhalten die folgende Fehlermeldung "Dismount-WindowsImage: Dismount-WindowsImage failed. Fehlercode = 0xc1550115 "beim Installieren oder Aktualisieren von Cloud Connector Edition.**
    
    **Lösung:** Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie "DISM-Cleanup-WIM" aus. Dadurch werden alle unruhigen Bilder bereinigt. Führen Sie Install-ccappliance "erneut aus, oder warten Sie, bis die Bits automatisch aktualisiert werden.
    
- **Problem: die Bereitstellung der ersten Cloud Connector-Appliance in einer ha-Umgebung schlägt fehl**
    
    **Lösung:** Die Schritte, die Sie ausführen, hängen davon ab, warum die Bereitstellung fehlgeschlagen ist:
    
  - Wenn die erste Cloud Connector-Appliance fehlschlägt und Sie den Grund für den Fehler nicht ermitteln können, müssen Sie die Appliance erst dann erneut installieren, wenn die Bereitstellung erfolgreich war, und dann die anderen Appliances installieren.
    
  - Wenn bei der ersten Cloud Connector-Appliance ein kleineres Problem auftritt, beispielsweise ein externes Zertifikat, können Sie das Problem möglicherweise beheben, ohne die Appliance erneut zu installieren. Anschließend können Sie die Remote-PowerShell von Mandanten verwenden, um die Bereitstellung wie folgt als erfolgreich zu kennzeichnen. (Wenn die erste Bereitstellung erfolgreich war, können Sie auch die folgenden Schritte verwenden, aber aus irgendeinem Grund kann Cloud Connector die Bereitstellung nicht als Erfolg melden.)
    
  - Um die Identität (GUID) der ersten Cloud Connector-Appliance abzurufen, führen Sie das Cmdlet Get-CsHybridPSTNAppliance aus.
    
  - Um die Appliance als erfolgreich bereitgestellt zu markieren, führen Sie das-CsCceApplianceDeploymentStatus wie folgt aus:
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- **Problem: Sie müssen Windows-Updates manuell auf dem Hostserver oder auf virtuellen Computern überprüfen und installieren.**
    
   **Lösung:** Es wird empfohlen, dass Sie die von Skype for Business Cloud Connector Edition bereitgestellten automatisierten Betriebssystemupdates nutzen. Nachdem eine Appliance für die Online Verwaltung registriert wurde und das automatische Betriebssystemupdate aktiviert ist, werden der Hostserver und die virtuellen Computer Windows-Updates automatisch entsprechend den Einstellungen des Zeitfensters für das Betriebssystemupdate überprüfen und installieren.
    
   Wenn Sie Windows-Updates manuell überprüfen und installieren müssen, befolgen Sie die Schritte in diesem Abschnitt, die für Ihre Art der Bereitstellung gelten. Sie sollten sowohl den Hostserver als auch die virtuellen Computer, auf denen er ausgeführt wird, gleichzeitig aktualisieren, um die für die Aktualisierungen erforderliche Ausfallzeit zu minimieren.
    
   Wenn Sie dies bevorzugen, können Sie einen WSUS-Server (Windows Server Update Services) verwenden, um Updates für Cloud Connector-Server bereitzustellen. Achten Sie darauf, dass Sie das Windows-Update so konfigurieren, dass es **nicht** automatisch installiert wird.
    
   Informationen zum manuellen Aktualisieren Ihrer Cloud Connector-Bereitstellung finden Sie im folgenden Abschnitt.
    
- **Problem: Wenn Cloud Connector für einen neuen Build aktualisiert wird, werden die Cloud Connector-Cmdlets nicht aktualisiert.** Dies geschieht manchmal, wenn ein PowerShell-Fenster geöffnet bleibt, wenn die automatische Aktualisierung erfolgt.
    
  **Lösung:** Um die aktualisierten Cmdlets zu laden, können Sie einen der folgenden Schritte ausführen:
    
   - Schließen Sie PowerShell in der Cloud Connector-Appliance, und öffnen Sie dann PowerShell erneut.
    
     - Sie können auch Import-Module "cloudconnector-Force ausführen. 
 
-   **Problem: "der Ausdruck" Stop-CsWindowsService "wird nicht als Name eines Cmdlets, einer Funktion, einer Skriptdatei oder eines benutzbaren Programms erkannt." Fehler beim Versuch, das Enter-CCUpdate "-Cmdlet auszuführen.**

    **Lösung:** Löschen Sie die $Home \appdata\local\microsoft\windows\powershell\moduleanalysiscache-Datei.
Diese Datei wird von PowerShell als Cache von Cmdlets aus Modulen erstellt, die Sie findet, sodass Sie nicht jedes Mal alle Module erneut analysieren müssen, da dies die Dinge wirklich langsam machen würde. Höchstwahrscheinlich gab es einige Dateibeschädigungen, die beim Lesen aus diesem Cache irreführende Ergebnisse für PowerShell bereitgestellt haben.

-   **Problem: "Import-Module" cloudconnector "generiert Fehler" Import-Module: das angegebene Modul "" cloudconnector "wurde nicht geladen, da in keinem Modulverzeichnis eine gültige Moduldatei gefunden wurde."**

    **Lösung:**
    - Überprüfen, ob das "cloudconnector-Modul tatsächlich unter c:\Program Files\WindowsPowerShell\Modules vorhanden ist
    
    - Nachdem Sie überprüft haben, dass das "cloudconnector-Modul unter diesem Speicherort vorhanden ist, kann die PSModulePath-Umgebungsvariable, die den Pfad zu den Speicherorten der Module speichert, geändert werden:
    
     a. Temporäre Änderung: Starten Sie PowerShell als Administrator, und führen Sie den folgenden Befehl aus: $env:P smodulepath = $ENV:P smodulepath + "; C:\Program Files\WindowsPowerShell\Modules\"
        
     b. Für eine beständige Änderung starten Sie PowerShell als Administrator, und führen Sie die folgenden Befehle nacheinander aus: $CurrentValue = [Environment]:: GetEnvironmentVariable ("PSModulePath", "Machine") SetEnvironmentVariable ("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules "," Machine ")

    
## <a name="install-windows-updates-manually"></a>Manuelles Installieren von Windows-Updates

Wenn Sie keine automatischen Updates in Ihrer Umgebung verwenden möchten, führen Sie die folgenden Schritte aus, um Windows-Updates manuell zu überprüfen und anzuwenden. Für die Überprüfung und Installation von Windows-Updates ist möglicherweise ein Serverneustart erforderlich. Wenn ein Hostserver neu gestartet wird, können Benutzer keine Cloud Connector verwenden, um Anrufe zu tätigen oder zu empfangen. Sie können manuell nach Updates suchen und diese installieren, um zu steuern, wann die Updates ausgeführt werden, und dann die Computer bei Bedarf während der Zeit neu starten, die Sie zur Vermeidung von Unterbrechungen der Dienste auswählen.
  
Wenn Sie manuell nach Updates suchen möchten, stellen Sie eine Verbindung zu jedem Hostserver her, und öffnen Sie die **System**Steuerung. Wählen Sie **System and Security \> Windows Update**aus, und verwalten Sie dann die Updates und Serverneustarts entsprechend Ihrer Umgebung.
  
- Wenn sich nur eine Appliance am Standort befindet, stellen Sie eine Verbindung zu jedem virtuellen Computer her, und öffnen Sie die **System**Steuerung. Wählen Sie **System and Security \> Windows Update**aus, und konfigurieren Sie dann die Updates und Serverneustarts je nach Bedarf.
    
- Wenn sich mehr als eine Appliance am Standort befindet, kann der Zugriff auf die Instanz, die aktualisiert und neu gestartet wird, während der Updates nicht von Benutzern erreicht werden. Benutzer stellen eine Verbindung mit anderen Instanzen in der Bereitstellung her, bis alle virtuellen Computer und alle Skype for Business Dienste auf den virtuellen Computern gestartet werden, nachdem die Updates abgeschlossen wurden. Um mögliche Dienstunterbrechungen zu vermeiden, können Sie die Instanz aus dem ha-Objekt entfernen, während Sie die Updates anwenden, und diese dann nach Abschluss wiederherstellen. Gehen Sie hierzu folgendermaßen vor:
    
1. Öffnen Sie auf jedem Hostserver eine PowerShell-Konsole als Administrator.
    
2. Entfernen Sie die Instanz mit dem folgenden Cmdlet aus ha:
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    Führen Sie die Schritte für eine einzelne Instanz aus, um die Updates manuell anzuwenden und den virtuellen Computer neu zu starten.
    
4. Legen Sie die Instanz mit dem folgenden Cmdlet wieder auf ha fest:
    
   ```powershell
   Exit-CcUpdate
   ```

Für Bereitstellungen mit mehreren Standorten führen Sie die Schritte für einen einzelnen Standort für jeden Standort in der Bereitstellung aus, und wenden Sie gleichzeitig Aktualisierungen auf eine Website an.
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a>Tipps für die Installation der Antiviren-Software auf dem Cloud Connector-Hostcomputer

Wenn Sie Antivirensoftware auf dem Cloud Connector-Hostcomputer installieren müssen, müssen Sie die folgenden Ausnahmen hinzufügen:
  
- Lokales Appliance-Verzeichnis auf jedem Computer.
    
- Remote Websiteverzeichnis auf jedem Computer.
    
- Das lokale Websiteverzeichnis auf dem Computer hostet den Stammordner der freigegebenen Website.
    
- %ProgramFiles%\Skype for Business Cloud Connector Edition
    
- %ALLUSERSPROFILE%\CloudConnector
    
- %ProgramFiles%\WindowsPowerShell\Modules\CloudConnector
    
- Der Prozess Microsoft. RTC. CCE. anwendungsverwaltungdienstanwendungendienstanwendungen. exe.
