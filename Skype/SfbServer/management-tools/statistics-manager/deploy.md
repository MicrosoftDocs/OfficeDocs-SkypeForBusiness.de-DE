---
title: Bereitstellen von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server bereitstellen.'
ms.openlocfilehash: 79e07c29a5df4a5da239687708a9bb52e995d191
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814815"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Bereitstellen von Statistics Manager für Skype for Business Server
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server bereitstellen.
  
 Statistics Manager für Skype for Business Server ist ein leistungsstarkes Tool, mit dem Sie Integritäts- und Leistungsdaten von Skype for Business Server in Echtzeit anzeigen können. Sie können alle paar Sekunden Leistungsdaten auf Hunderten von Servern abfragen und die Ergebnisse sofort auf der Statistics Manager-Website anzeigen.
  
Bevor Sie versuchen, Statistics Manager zu installieren, sollten Sie mit den Software-, Netzwerk- und Hardwareanforderungen vertraut sein. Weitere Informationen finden Sie unter [Plan for Statistics Manager for Skype for Business Server](plan.md).
  
> [!NOTE]
> Wenn Sie ein Upgrade von einer früheren Version von Statistics Manager durchführen, lesen Sie [upgrade Statistics Manager for Skype for Business Server](upgrade.md). 
  
> [!NOTE]
> Die Statistics -Manager-Website wurde getestet und funktioniert ordnungsgemäß in Internet Explorer 11+, Edge 20.10240+ und Chrome 46+ (aktuelle immergrüne Version). 
  
Den Statistics Manager können Sie unter [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload) herunterladen. 
  
Dieses Thema enthält die folgenden Abschnitte:
  
- [Bereitstellen von Statistics Manager](deploy.md#BKMK_Deploy)
    
- [Problembehandlung für Ihre Bereitstellung](deploy.md#BKMK_Troubleshoot)
    
- [Erstellen eines selbst signierten Zertifikats](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Bereitstellen von Statistics Manager
<a name="BKMK_Deploy"> </a>

Führen Sie zum Bereitstellen von Statistics Manager die folgenden Schritte aus:
  
1. Bereiten Sie den Listenerhostcomputer vor, indem Sie das Zwischenspeicherungssystem "Redis" im Arbeitsspeicher installieren und sicherstellen, dass Sie die entsprechenden Zertifikate installiert haben.
    
2. Installieren Sie den Listenerdienst auf dem Hostcomputer. 
    
3. Installieren Sie die Website auf dem Hostcomputer.
    
4. Installieren Sie einen Agent auf jedem Skype for Business Server-Computer, den Sie überwachen möchten.
    
5. Importieren Sie die Topologie für die Überwachten Server.
    
> [!NOTE]
> Redis, der Listenerdienst und die Website müssen alle auf demselben Hostcomputer installiert sein. Stellen Sie sicher, dass auf dem Hostcomputer Skype for Business Server nicht installiert ist. 
  
### <a name="prepare-the-listener-host-machine"></a>Vorbereiten des Listenerhostcomputers

Zum Vorbereiten des Hostcomputers müssen Sie das Im-Memory-Cache-System von Redis installieren und sicherstellen, dass ein gültiges Zertifikat auf dem Computer vorhanden ist. Microsoft empfiehlt, den neuesten stabilen Build von Redis 3.0 zu installieren. Statistics Manager, Version 2.0, wurde mit Redis 3.2.100 getestet. 
  
1. Laden Sie Redis von der folgenden Website herunter: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis) . 
    
    Nicht signierte Installationsprogramme können heruntergeladen werden von [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Wenn erforderlich, stehen signierte Binärdateien über beliebte Paketmanager zur Verfügung: [Nuget](https://www.nuget.org/packages/Redis-64/) und [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Führen Sie die bereitgestellte msi aus, und folgen Sie den Eingabeaufforderungen.
    
   - Aktivieren Sie das Kontrollkästchen nicht, um eine Firewallregel hinzuzufügen.
    
2. Der Listenerdienst erfordert ein Zertifikat. Microsoft empfiehlt dringend, dass Sie über ein Zertifikat verfügen, das von einer vertrauenswürdigen Zertifizierungsstelle signiert ist. 
    
    Wenn Sie ein selbst signiertes Zertifikat verwenden möchten , z. B. zu Testzwecken in einer Übungseinheit, lesen Sie "Erstellen eines selbst signierten [Zertifikats".](deploy.md#BKMK_SelfCert)
    
    Beachten Sie, dass der Agent die Überprüfung des Zertifikatfingerabdrucks (anstelle der Verkettungsüberprüfung) verwendet. Die vollständige Zertifikatüberprüfung wird nicht abgeschlossen, da selbst signierte Zertifikate verwendet werden können.
    
### <a name="install-the-listener-service"></a>Installieren des Listenerdiensts

Installieren Sie den Listenerdienst auf dem Hostcomputer, indem Sie StatsManPerfAgentListener.msi ausführen und Folgendes angeben:
  
1. Überprüfen Sie den Lizenzvertrag, und wenn Sie zustimmen, wählen Sie "Ich stimme den **Bedingungen des** Lizenzvertrags zu, und klicken Sie dann auf **"Weiter".** 
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen an:
    
   - **Dienstkennwort:** Dies ist das Kennwort, das die Remoteagenten für die Authentifizierung beim Listenerdienst verwenden.
    
   - **Dienstport:** Dies ist die HTTPS-Portnummer, die der Listener für die Kommunikation mit den Agents verwendet. Während der Installation wird dieser Port über die lokale Firewall zugelassen, eine URL-ACL wird erstellt, und ein #A0 wird an diesen Port gebunden. Der Standardwert ist 8443.
    
   - **Zertifikatfingerabdruck:** Dies ist der Zertifikatfingerabdruck, den der Listener zum Verschlüsseln des HTTPS-Protokolls verwendet. Der Netzwerkdienst muss über Lesezugriff auf den privaten Schlüssel verfügen.
    
     Klicken Sie auf die **Schaltfläche "Auswählen...",** um den Fingerabdruck auszuwählen.
    
     Sie finden den Zertifikatfingerabdruck mithilfe des Zertifikat-Managers oder mithilfe des folgenden PowerShell-Befehls:
    
       ```PowerShell
       Get-ChildItem -path cert:\LocalMachine\My
       ```

   - **Installieren Sie Dir:** Dies ist das Verzeichnis, in dem die Binärdateien installiert werden. Sie können die Standardeinstellung ändern, indem Sie die Schaltfläche **"Durchsuchen..."** verwenden.
    
   - **AppData Dir:** Dies ist das Verzeichnis, in dem der Ordner "Logs" und andere Daten gespeichert werden. Sie können die Standardeinstellung ändern. Sie wird bei der Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Führen Sie die folgenden Schritte aus, um die Installation zu überprüfen:
  
1. Öffnen Sie einen Browser, und navigieren Sie zu https://localhost: \<service-port\> /healthcheck/
    
    Standardmäßig ist der Dienstport 8443 (es sei denn, Sie haben einen anderen Port angegeben).
    
2. Um sicherzustellen, dass der Listener ordnungsgemäß installiert wurde, suchen Sie nach folgendem Beispiel:
    
   - Wenn die Seite mit der Integritätsprüfung angezeigt wird, war die Installation des Listeners erfolgreich.
    
   - Wenn knownServerCount 1 oder höher ist, wird die Verbindung mit Redis hergestellt.
    
   - Nachdem Sie einige Minuten gewartet haben und mindestens ein Agent installiert wurde, überprüfen Sie, ob der Wert des Werts "ValuesWritten" erhöht wird.
    
### <a name="install-the-website"></a>Installieren der Website

Installieren Sie die Website auf dem Hostcomputer, indem Sie StatsManWebSite.msi (im Lieferumfang von [Skype for Business Server, Real-Time Statistics Manager (64-Bit) enthalten)](https://www.microsoft.com/en-in/download/details.aspx?id=57518)ausführen und Folgendes angeben:
  
1. Überprüfen Sie den Lizenzvertrag, und wenn Sie zustimmen, wählen Sie "Ich stimme den **Bedingungen des** Lizenzvertrags zu, und klicken Sie dann auf **"Weiter".** 
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen an:
    
   - **Dienstport:** Dies ist die Portnummer, auf die die Website lauscht. Sie können sie später mithilfe der IIS-Manager-Bindung ändern. Während der Installation wird dieser Port über die lokale Firewall zugelassen.
    
   - **Installieren Sie Dir:** Dies ist das Verzeichnis, in dem die Binärdateien installiert werden. Sie können die Standardeinstellung ändern, indem Sie die Schaltfläche **"Durchsuchen..."** verwenden.
    
   - **AppData Dir:** Dies ist das Verzeichnis, in dem der Ordner "Logs" und andere Daten gespeichert werden. Sie können die Standardeinstellung ändern. Sie wird bei der Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Öffnen Sie zum Anzeigen der Website einen Browser, und navigieren Sie zu: http://localhost ,webport \> /.
  
Um nur Integritätsinformationen anzuzeigen, öffnen Sie einen Browser, und navigieren Sie zu: http://localhost: \<webport\> /healthcheck/.
  
Standardmäßig ist die Webportnummer 8080. Sie können die Portbindung der Website mithilfe des IIS-Managers ändern.
  
Das Webinstallationsprogramm fügt eine lokale Sicherheitsgruppe namens StatsManWebSiteUsers hinzu. Sie können dieser Sicherheitsgruppe Konten hinzufügen, um Zugriff auf die Website zu gewähren. 
  
### <a name="install-the-agents"></a>Installieren der Agents

Installieren Sie einen Agent auf jedem Skype for Business Server, den Sie überwachen möchten, indem Sie StatsManPerfAgent.msi ausführen und Folgendes angeben:
  
1. Überprüfen Sie den Lizenzvertrag, und wenn Sie zustimmen, wählen Sie "Ich stimme den **Bedingungen des** Lizenzvertrags zu, und klicken Sie dann auf **"Weiter".** 
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen an:
    
   - **Dienstkennwort:** Dies ist das Kennwort, das der Remoteagent für die Authentifizierung beim Listenerdienst verwendet.
    
   - **Dienst-URI:** Dies ist der URI, in dem sich der Listener befindet. Es sollte das Format https://name:port verwendet werden.
    
     Sie können einen NETBIOS-Namen oder einen FQDN verwenden. Sie können den Namen verwenden,  der auch als subject- oder **subject Alternative Names** des Zertifikats im Listenerdienst angegeben ist, dies ist jedoch keine Anforderung.
    
   - **Dienstfingerabdruck:** Dies ist der Fingerabdruck des SSL-Zertifikats, das der Listener verwendet. Der Agent verwendet diesen Fingerabdruck, um sich beim Listener zu authentifizieren. (Die Zertifikatüberprüfung wird nicht vollständig abgeschlossen, da selbst signierte Zertifikate verwendet werden können.)
    
   - **Installieren Sie Dir:** Dies ist das Verzeichnis, in dem die Binärdateien installiert werden. Sie können die Standardeinstellung ändern, indem Sie die Schaltfläche **"Durchsuchen..."** verwenden.
    
   - **AppData Dir:** Dies ist das Verzeichnis, in dem der Ordner "Logs" und die verschlüsselte password.txt gespeichert werden. Sie können es von der Standardeinstellung ändern. Sie wird bei der Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Wenn Sie einen Agent auf zahlreichen Computern installieren, möchten Sie dies wahrscheinlich im unbeaufsichtigten Modus tun. Beispiel: 
  
```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importieren der Topologie
<a name="BKMK_ImportTopology"> </a>

Nachdem Statistics Manager installiert und ausgeführt wurde, müssen Sie die Skype for Business Server-Topologie importieren, damit Statistics Manager den Standort, pool und die Rolle der einzelnen Server kennt. Zum Importieren Ihrer Skype for Business Server-Topologie verwenden Sie das [Cmdlet "Get-CsPool",](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) um Informationen zu jedem in Ihrer Organisation verwendeten Pool abzurufen und diese Informationen dann in Statistics Manager zu importieren.
  
Führen Sie die folgenden Schritte aus, um die Skype for Business Server-Topologie zu importieren:
  
1. Auf einem Host mit den Skype for Business Server PowerShell-Cmdlets:
    
    a. Führen Sie den folgenden Befehl aus: 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Kopieren Sie die Datei "mypoolinfo.xml" auf den Server, auf dem der Listener ausgeführt wird.
    
2. Auf dem Host, auf dem der Listener ausgeführt wird:
    
   a. Führen Sie PowerShell aus.
    
   b. Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist. Der Standardwert ist: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Führen Sie den folgenden Befehl aus, um zu bestätigen, welche Server hinzugefügt und aktualisiert werden:
    
   ```console
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

Mit dem folgenden Befehl können Sie alle Optionen anzeigen:
  
```powershell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Führen Sie das folgende Skript aus, um die aktuell importierten Serverinformationen zu sehen: 
  
```powershell
.\Get-StatsManServerInfo.ps1
```

Wenn Sie Server überwachen möchten, die sich nicht in Ihrer Skype for Business Server-Topologie befinden , z. B. ein Exchange Server, können Sie einen Import mit einem einzelnen Server auf dem Host, auf dem der Listener ausgeführt wird, tun. Führen Sie die folgenden Schritte aus, um einen Import mit einem einzelnen Server durchführen zu können:
  
1. Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist. Der Standardwert ist: 
    
   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Führen Sie den folgenden Befehl aus:
    
   ```powershell
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Problembehandlung für Ihre Bereitstellung
<a name="BKMK_Troubleshoot"> </a>

Wenn ein Agent nicht gestartet werden kann, überprüfen Sie Folgendes: 
  
- Ist der Agent im Statistics Manager registriert?
    
    1. Stellen Sie sicher, dass Sie die Anweisungen zum Importieren der Topologie befolgt haben. Siehe ["Importieren der Topologie".](deploy.md#BKMK_ImportTopology)
        
    2. Wenn sich der Agent auf einem Server befindet, der nicht in der Topologie aufgeführt ist (z. B. die Knoten in einem SQL AlwaysOn-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anweisungen unter ["Topologie](deploy.md#BKMK_ImportTopology)importieren" befolgen.
    
- Kann der Agent den Listener kontaktieren?
    
    1. Stellen Sie sicher, dass der Listenerdienst ausgeführt wird. 
        
        Wenn er nicht ausgeführt wird, stellen Sie sicher, dass Redis ausgeführt wird, und versuchen Sie dann, den Listener neu zu starten.
        
    2. Stellen Sie sicher, dass der Port für den Listenerdienst geöffnet ist und dass der Agentcomputer mit dem Port kommunizieren kann.
    
- Um sicherzustellen, dass Statistics Manager Daten erfasst, können Sie die DATEI "CSV" wie folgt überprüfen. 
    
    Der folgende Befehl ruft die Speichernamen der Leistungsindikatoren ab: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Der nächste Befehl ruft die Werte für die angegebenen Leistungsindikatoren ab: 
    
  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Informationen zu allen Ereignissen, die möglicherweise im Anwendungsereignisprotokoll angezeigt werden, finden Sie unter [Problembehandlung](troubleshoot.md)für Statistics Manager für Skype for Business Server .
  
## <a name="create-a-self-signed-certificate"></a>Erstellen eines selbst signierten Zertifikats
<a name="BKMK_SelfCert"> </a>

Microsoft empfiehlt dringend, ein Von einer vertrauenswürdigen Zertifizierungsstelle signiertes Zertifikat zu verwenden. Wenn Sie jedoch ein selbst signiertes Zertifikat zu Testzwecken verwenden möchten, gehen Sie wie folgt vor: 
  
1. Geben Sie in einer PowerShell-Konsole, die als Administrator angemeldet ist, Folgendes ein:
    
   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Typ  `certlm.msc` . Dadurch wird der Zertifikat-Manager für den lokalen Computer geöffnet.
    
3. Navigieren Sie zu **"Persönlich",** und öffnen Sie **dann Zertifikate.**
    
4. Right click on **StatsManListener- \> All Tasks- \> Manage Private Keys...**
    
5. Klicken Sie auf **Hinzufügen**.
    
6. Geben Sie **im Feld "Geben Sie die zu verwendende** Objektnamen ein" Folgendes ein: Netzwerkdienst
    
7. Klicken Sie auf **OK**.
    
8. Aktivieren **Sie unter Vollschutz** das Kontrollkästchen **"Zulassen".** (Nur Lesezugriff ist erforderlich.)
    
9. Klicken Sie auf **OK**.
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_SelfCert"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)
    
- [Problembehandlung für Statistics Manager für Skype for Business Server](troubleshoot.md) ß
