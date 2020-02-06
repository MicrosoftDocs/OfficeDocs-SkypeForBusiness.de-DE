---
title: Bereitstellen von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server bereitstellen können.'
ms.openlocfilehash: 44aad14970716f00550255855d251919a767a268
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803965"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Bereitstellen von Statistics Manager für Skype for Business Server
 
**Zusammenfassung**: In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server bereitstellen können.
  
 Statistics Manager für Skype for Business Server ist ein leistungsfähiges Tool, mit dem Sie Skype for Business Server-Status- und -Leistungsdaten in Echtzeit anzeigen können. Sie können Leistungsdaten von Hunderten von Servern innerhalb von Sekunden abfragen und die Ergebnisse unmittelbar auf der Statistics Manager-Website anzeigen.
  
Stellen Sie vor der Installation von Statistics Manager sicher, dass Sie mit der Software, der Vernetzung und den Hardwareanforderungen vertraut sind. Weitere Informationen finden Sie unter [Planen von Statistics Manager für Skype for Business Server](plan.md).
  
> [!NOTE]
> Lesen Sie vor einem Upgrade von einer früheren Version von Statistics Manager Folgendes: [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md). 
  
> [!NOTE]
> Die Statistics Manager-Website wurde getestet und funktioniert ordnungsgemäß unter Internet Explorer 11+, Edge 20.10240+ und Chrome 46+ (aktuelle Evergreen-Version). 
  
Den Download für Statistics Manager finden Sie unter [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload). 
  
Dieses Thema enthält die folgenden Abschnitte:
  
- [Bereitstellen von Statistics Manager](deploy.md#BKMK_Deploy)
    
- [Problembehandlung Ihrer Bereitstellung](deploy.md#BKMK_Troubleshoot)
    
- [Erstellen eines selbstsignierten Zertifikats](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Bereitstellen von Statistics Manager
<a name="BKMK_Deploy"> </a>

Zum Bereitstellen von Statistics Manager gehen Sie wie folgt vor:
  
1. Bereiten Sie einen Listener-Hostcomputer vor, indem Sie das Redis-System für die InMemory-Zwischenspeicherung installieren und sicherstellen, dass die entsprechenden Zertifikate installiert sind.
    
2. Installieren Sie den Listener-Dienst auf dem Hostcomputer. 
    
3. Installieren Sie die Website auf dem Hostcomputer.
    
4. Installieren Sie auf jedem Skype for Business Server-Computer, den Sie überwachen möchten, einen Agent.
    
5. Importieren Sie die Topologie für die Server, die Sie überwachen.
    
> [!NOTE]
> Redis, der Listener-Dienst, und die Website müssen alle auf demselben Hostcomputer installiert werden. Achten Sie darauf, dass auf dem Hostcomputer nicht Skype for Business Server installiert ist. 
  
### <a name="prepare-the-listener-host-machine"></a>Vorbereitung des Listener-Hostcomputers

Um den Hostcomputer vorzubereiten, müssen Sie das Redis-System für die InMemory-Zwischenspeicherung installieren und sicherstellen, dass ein gültiges Zertifikat auf dem Computer vorhanden ist. Microsoft empfiehlt die Installation des letzten stabilen Builds von Redis 3.0. Statistics Manager Version 2.0 wurde mit Redis 3.2.100 getestet. 
  
1. Laden Sie Redis von der folgenden Website herunter: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    Nicht signierte Installationsprogramme können unter [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases) heruntergeladen werden.
    
    Falls erforderlich, sind signierte Binärdateien über gängige Paketmanager verfügbar: [Nuget](https://www.nuget.org/packages/Redis-64/) und [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Führen Sie die bereitgestellte MSI-Datei aus und folgen Sie den Aufforderungen.
    
   - Das Kontrollkästchen zum Hinzufügen einer Firewallregel nicht aktivieren.
    
2. Der Listener-Dienst erfordert ein Zertifikat. Microsoft empfiehlt dringend die Verwendung eines Zertifikats, das von einer vertrauenswürdigen Zertifizierungsstelle signiert ist. 
    
    Wenn Sie ein selbstsigniertes Zertifikat verwenden möchten, z. B. für Testzwecke in einem Labor, siehe [Erstellen eines selbstsignierten Zertifikats](deploy.md#BKMK_SelfCert).
    
    Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung). Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.
    
### <a name="install-the-listener-service"></a>Installation des Listener-Diensts

Installieren Sie den Listener-Dienst auf dem Hostcomputer, indem Sie die Datei StatsManPerfAgentListener.msi ausführen und Folgendes angeben:
  
1. Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**.  
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen ein:
    
   - **Dienstkennwort:** Dies ist das Kennwort, mit dem die Remote-Agents den Listener-Dienst authentifizieren.
    
   - **Dienstport:** Dies ist die HTTPS-Portnummer, die der Listener für die Kommunikation mit den Agents verwendet. Bei der Installation wird dieser Port durch eine lokale Firewall durchgelassen, es wird eine URL-ACL erstellt und ein SSL-Zertifikat wird an diesen Port gebunden. Der Standardwert ist 8443.
    
   - **Zertifikatfingerabdruck:** Dies ist der Zertifikatfingerabdruck, den der Listener für die Verschlüsselung des HTTPS-Protokolls verwendet. Der Netzwerkdienst muss über eine Leseberechtigung für den privaten Schlüssel verfügen.
    
     Klicken Sie auf die Schaltfläche **Auswählen...**, um den Fingerabdruck auszuwählen.
    
     Sie finden den Zertifikatfingerabdruck, indem Sie den Zertifikat-Manager oder den folgenden PowerShell-Befehl verwenden:
    
   ```PowerShell
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Installationsverzeichnis:** In diesem Verzeichnis werden die Binärdateien installiert. Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.
    
   - **AppData-Verzeichnis:** In diesem Verzeichnis werden der Protokollordner und andere Daten gespeichert. Sie können den Standardprotokollordner ändern. Er wird bei einer Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Um die Installation zu validieren, gehen Sie wie folgt vor:
  
1. Öffnen Sie einen Browser, und navigieren Sie zu https://localhost:\<service-port\>/healthcheck/.
    
    Die Standardeinstellung ist Dienstport 8443 (sofern Sie nicht einen anderen Port festgelegt haben).
    
2. Um die ordnungsgemäße Installation des Listeners sicherzustellen, überprüfen Sie Folgendes:
    
   - Wenn die Seite für die Integritätsprüfung angezeigt wird, war die Listener-Installation erfolgreich.
    
   - Wenn die KnownServerCount 1 oder höher ist, wird die Verbindung mit dem 4/2-Wert festgelegt.
    
   - Nachdem Sie einige Minuten abgewartet haben und nachdem mindestens ein Agent installiert wurde, überprüfen Sie, ob sich der Leistungsindikator erhöht.
    
### <a name="install-the-website"></a>Installieren der Website

Installieren Sie die Website auf dem Hostcomputer durch Ausführen der Datei StatsManWebSite.msi (im Lieferumfang von [Skype for Business Server, Real-Time Statistics Manager (64 Bit) enthalten](https://www.microsoft.com/en-in/download/details.aspx?id=57518)) und geben Sie Folgendes an:
  
1. Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**.  
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen ein:
    
   - **Dienstport:** Dies ist die Nummer des Ports, den die Website überwacht. Sie können sie später über eine IIS-Manager-Bindung ändern. Bei der Installation wird dieser Port durch die lokale Firewall durchgelassen.
    
   - **Installationsverzeichnis:** In diesem Verzeichnis werden die Binärdateien installiert. Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.
    
   - **AppData-Verzeichnis:** In diesem Verzeichnis werden der Protokollordner und andere Daten gespeichert. Sie können den Standardprotokollordner ändern. Er wird bei einer Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Um die Website anzuzeigen, öffnen Sie einen Browser und navigieren Sie zu: http://localhost,webport\>/
  
Um nur die Informationen zur Integrität anzuzeigen, öffnen Sie einen Browser und navigieren Sie zu: http://localhost:\<webport\>/healthcheck/.
  
Der Standardwert für die Webportnummer lautet 8080. Sie können die Portbindung der Website über den IIS-Manager ändern.
  
Das Website-Installationsprogramm fügt eine lokale Sicherheitsgruppe mit dem Namen StatsManWebSiteUsers hinzu. Sie können dieser Sicherheitsgruppe Konten hinzufügen, um Zugriff auf die Website zu gewähren. 
  
### <a name="install-the-agents"></a>Installation der Agents

Installieren Sie einen Agent auf jedem Skype for Business Server, auf dem eine Überwachung über die Ausführung von StatsManPerfAgent.msi erfolgen soll, und geben Sie Folgendes an:
  
1. Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**.  
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen ein:
    
   - **Dienstkennwort:** Dies ist das Kennwort, mit dem der Remote-Agent den Listener-Dienst authentifiziert.
    
   - **Dienst-URI:** Dies ist der URI, an dem sich der Listener befindet. Er sollte das https://name:port-Format verwenden.
    
     Sie können einen NETBIOS-Namen oder einen FQDN verwenden. Sie können den Namen verwenden, der zudem als **Antragsteller** oder als der **alternative Antragstellername** des Zertifikats des Listener-Diensts angegeben ist, aber dies stellt keine Anforderung dar.
    
   - **Dienstfingerabdruck:** Dies ist der Fingerabdruck des SSL-Zertifikats, den der Listener verwendet. Der Agent verwendet diesen Fingerabdruck zur Authentifizierung des Listeners. (Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.)
    
   - **Installationsverzeichnis:** In diesem Verzeichnis werden die Binärdateien installiert. Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.
    
   - **AppData-Verzeichnis:** In diesem Verzeichnis werden der Protokollordner und die verschlüsselte Datei password.txt gespeichert. Sie können den Standardprotokollordner ändern. Er wird bei einer Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Wenn Sie einen Agent auf einer Reihe von Computern installieren, werden Sie dies wahrscheinlich im unbeaufsichtigten Modus durchführen wollen. Beispiel: 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Import der Topologie
<a name="BKMK_ImportTopology"> </a>

Nachdem Statistics Manager installiert wurde und ausgeführt wird, müssen Sie die Skype for Business Server-Topologie importieren, damit Statistics Manager den Standort, den Pool und die Rolle der einzelnen Server erkennt. Verwenden Sie für den Import der Skype for Business Server-Topologie das Cmdlet [Get-CSPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps), um die Informationen über die einzelnen Pools in Ihrer Organisation abzurufen, und importieren Sie diese Informationen in den Statistics Manager.
  
Um die Skype for Business Server-Topologie zu importieren, gehen Sie folgendermaßen vor:
  
1. Auf einem Host, der über die Skype for Business Server PowerShell-Cmdlets verfügt:
    
    a. Führen Sie den folgenden Befehl aus: 
    
   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Kopieren Sie die Datei „mypoolinfo.xml“ auf den Server, auf dem der Listener ausgeführt wird.
    
2. Auf dem Host, auf dem der Listener ausgeführt wird:
    
   a. Führen Sie PowerShell aus.
    
   b. Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist. Die Standardeinstellung ist: 
    
   ```PowerShell
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Führen Sie den folgenden Befehl aus, um zu bestätigen, welche Server hinzugefügt und aktualisiert werden:
    
   ```PowerShell
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

Mit dem folgenden Befehl können Sie alle Optionen anzeigen:
  
```PowerShell
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Führen Sie das folgende Skript aus, um die Informationen zu den aktuell importierten Servern anzuzeigen: 
  
```PowerShell
.\Get-StatsManServerInfo.ps1
```

Wenn Sie die Server überwachen möchten, die sich nicht in Ihrer Skype for Business Server-Topologie befinden, z. B. einen Exchange-Server, können Sie auf dem Host, auf dem der Listener ausgeführt wird, einen einzelnen Server importieren. Wenn Sie nur einen einzelnen Server importieren möchten, gehen Sie wie folgt vor:
  
1. Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist. Die Standardeinstellung ist: 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Führen Sie den folgenden Befehl aus:
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Problembehandlung Ihrer Bereitstellung
<a name="BKMK_Troubleshoot"> </a>

Fall ein Agent nicht startet, überprüfen Sie Folgendes: 
  
- Ist der Agent im Statistics Manager registriert?
    
1. 	Stellen Sie sicher, dass Sie die Anweisungen für den Import der Topologie befolgt haben. Siehe auch [Import the topology](deploy.md#BKMK_ImportTopology).  
    
2. Wenn sich der Agent auf einem Server befindet, der in der Topologie nicht aufgeführt ist (zum Beispiel die Knoten in einem SQL-„AlwaysOn“-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anleitungen in [Import the topology](deploy.md#BKMK_ImportTopology) ausführen.
    
- Kann der Agent den Listener kontaktieren?
    
1. Stellen Sie sicher, dass der Listener-Dienst ausgeführt wird. 
    
    Wenn der Listener nicht ausgeführt wird, stellen Sie sicher, dass Redis ausgeführt wird, und versuchen Sie anschließend, den Listener neu zu starten.
    
2. Stellen Sie sicher, dass der Port für den Listener-Dienst geöffnet ist und dass der Agent-Computer mit dem Port kommunizieren kann.
    
- Um sicherzustellen, dass Statistics Manager Daten erfasst, können Sie die CSV-Datei wie folgt überprüfen. 
    
    Der folgende Befehl ruft die Computer-Speichernamen ab: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Der nächste Befehl ruft die Werte ab für die angegebenen Zähler ab: 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Informationen über die verschiedenen Ereignisse, die ggf. im Ereignisprotokoll „Anwendung“ angezeigt werden, finden Sie unter [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Erstellen eines selbstsignierten Zertifikats
<a name="BKMK_SelfCert"> </a>

Microsoft empfiehlt dringend die Verwendung eines Zertifikats, das von einer vertrauenswürdigen Zertifizierungsstelle signiert ist. Wenn Sie jedoch zu Testzwecken ein selbst-signiertes Zertifikat verwenden möchten, gehen Sie wie folgt vor: 
  
1. Melden Sie sich als Administrator an und geben Sie in einer PowerShell-Konsole Folgendes ein:
    
   ```PowerShell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Geben Sie `certlm.msc` ein. Dadurch öffnet sich der Zertifikat-Manager für den lokalen Computer.
    
3. Navigieren Sie zu **Eigene Zertifikate** und öffnen Sie **Zertifikate**.
    
4. Klicken Sie mit der rechten Maustaste auf **StatsManListener-\>Alle Aufgaben-\>Private Schlüssel verwalten…**
    
5. Klicken Sie auf **Hinzufügen**.
    
6. Geben Sie im Feld **Geben Sie die zu verwendenden Objektnamen ein** folgenden Text ein: Netzwerkdienst
    
7. Klicken Sie auf **OK**.
    
8. Deaktivieren Sie unter **Vollzugriff** das Kontrollkästchen **Zulassen**. (Nur Leseberechtigung erforderlich)
    
9. Klicken Sie auf **OK**.
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_SelfCert"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)
    
- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)
