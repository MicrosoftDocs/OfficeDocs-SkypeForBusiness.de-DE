---
title: Bereitstellen von Statistiken Manager für Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Statistiken Manager für Skype für Business Server bereitstellen.'
ms.openlocfilehash: 805026cbe04010a83503bb6069bea8522ac62068
ms.sourcegitcommit: 388f82c36e1c7bddf38298867882d992be989b87
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "26281340"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Bereitstellen von Statistiken Manager für Skype für Business Server
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie Statistiken Manager für Skype für Business Server bereitstellen.
  
 Statistiken-Manager für Skype für Business Server ist ein leistungsfähiges Tool, das Sie zum Anzeigen von Skype für Business Server Integrität und Leistung von Daten in Echtzeit ermöglicht. Sie können Leistungsdaten auf Hunderten von Servern kurzen Abständen Abfragen und sofort Anzeigen der Ergebnisse auf der Website Statistiken-Managers.
  
Bevor Sie versuchen, Statistiken Manager zu installieren, achten Sie darauf, dass Sie mit der Software, Netzwerk und Hardware Anforderungen vertraut sind. Weitere Informationen finden Sie unter [Planen für Statistiken Manager für Skype für Business Server](plan.md).
  
> [!NOTE]
> Wenn Sie von einer früheren Version von Statistiken Manager aktualisieren, finden Sie unter [Statistics-Manager für Skype für Business Server aktualisieren](upgrade.md). 
  
> [!NOTE]
> Die Statistics Manager-Website wurde getestet und funktioniert ordnungsgemäß unter Internet Explorer 11+, Edge 20.10240+ und Chrome 46+ (aktuelle Evergreen-Version). 
  
Finden Sie die Statistiken Manager unter [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload). 
  
Dieses Thema enthält die folgenden Abschnitte:
  
- [Bereitstellen von Statistics Manager](deploy.md#BKMK_Deploy)
    
- [Problembehandlung Ihrer Bereitstellung](deploy.md#BKMK_Troubleshoot)
    
- [Erstellen eines selbstsignierten Zertifikats](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a>Bereitstellen von Statistics Manager
<a name="BKMK_Deploy"> </a>

Gehen Sie folgendermaßen vor, um Statistiken Manager bereitstellen:
  
1. Bereiten Sie einen Listener-Hostcomputer vor, indem Sie das Redis-System für die InMemory-Zwischenspeicherung installieren und sicherstellen, dass die entsprechenden Zertifikate installiert sind.
    
2. Installieren Sie den Listener-Dienst auf dem Hostcomputer.  
    
3. Installieren Sie die Website auf dem Hostcomputer.
    
4. Installieren Sie einen Agent auf jedem Skype für Business Server-Computer, den Sie überwachen möchten.
    
5. Importieren Sie die Topologie für die Server, die Sie überwachen.
    
> [!NOTE]
> Redis, der Listener-Dienst, und die Website müssen alle auf demselben Hostcomputer installiert werden. Stellen Sie sicher, dass das Hostsystem nicht Skype für Business Server installiert. 
  
### <a name="prepare-the-listener-host-machine"></a>Vorbereitung des Listener-Hostcomputers

Um den Hostcomputer vorzubereiten, müssen Sie das Redis-System für die InMemory-Zwischenspeicherung installieren und sicherstellen, dass ein gültiges Zertifikat auf dem Computer vorhanden ist. Microsoft empfiehlt die Installation des letzten stabilen Builds von Redis 3.0. Statistiken Manager Version 1.1 für Redis getesteten 3.0.501 und Redis 2.8.2400. 
  
1. Redis von folgender Website herunterladen: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis). 
    
    Nicht signierte Installer können hier heruntergeladen werden[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)
    
    Bei Bedarf sind signierte Binärdateien über häufig verwendete Paketmanager verfügbar: [Nuget](https://www.nuget.org/packages/Redis-64/) und [Choclatey](https://chocolatey.org/packages/redis-64).
    
   - Führen Sie die bereitgestellte MSI-Datei aus und folgen Sie den Aufforderungen.
    
   - Das Kontrollkästchen zum Hinzufügen einer Firewallregel nicht aktivieren.
    
2. Der Listener-Dienst erfordert ein Zertifikat. Microsoft empfiehlt, dass ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle signiert ist. 
    
    Wenn Sie ein selbstsigniertes Zertifikat verwenden möchten, z. B. für Testzwecke in einem Labor, siehe [Erstellen eines selbstsignierten Zertifikats](deploy.md#BKMK_SelfCert).
    
    Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung). Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.
    
### <a name="install-the-listener-service"></a>Installation des Listener-Diensts

Installieren Sie den Listener-Dienst auf dem Hostcomputer durch Ausführen der StatsManPerfAgentListener.msi und angeben die folgenden:
  
1. Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**.  
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen ein:
    
   - **Dienstkennwort:** Dies ist das Kennwort, mit dem die Remote-Agents den Listener-Dienst authentifizieren.
    
   - **Dienst-Port:** Dies ist die HTTPS-Portnummer, die der Listener verwendet wird, um die Kommunikation mit dem Agenten. Bei der Installation wird dieser Port durch eine lokale Firewall durchgelassen, es wird eine URL-ACL erstellt und ein SSL-Zertifikat wird an diesen Port gebunden. Der Standardwert ist 8443.
    
   - **Zertifikat Fingerabdruck:** Hierbei handelt es sich um den Fingerabdruck des Zertifikats, mit denen der Listener das HTTPS-Protokoll zu verschlüsseln. Der Netzwerkdienst muss über eine Leseberechtigung für den privaten Schlüssel verfügen.
    
     Klicken Sie auf die Schaltfläche **Auswählen...**, um den Fingerabdruck auszuwählen.
    
     Sie finden den Zertifikatfingerabdruck, indem Sie den Zertifikat-Manager oder den folgenden PowerShell-Befehl verwenden:
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - **Dir installieren:** Dies ist das Verzeichnis auf dem die Binärdateien installiert werden. Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.
    
   - **Anwendungsdaten Dir:** Dies ist das Verzeichnis, in dem der Ordner Logs und andere Daten gespeichert werden. Sie können den Standardprotokollordner ändern. Er wird bei einer Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Um die Installation zu validieren, gehen Sie wie folgt vor:
  
1. Öffnen Sie einen Browser, und navigieren Sie zuhttps://localhost:\<service-port\>/healthcheck/
    
    Die Standardeinstellung ist Dienstport 8443 (sofern Sie nicht einen anderen Port festgelegt haben).
    
2. Um die ordnungsgemäße Installation des Listeners sicherzustellen, überprüfen Sie Folgendes:
    
   - Wenn die Seite für die Integritätsprüfung angezeigt wird, war die Listener-Installation erfolgreich.
    
   - Wenn der KnownServersCount-Wert 1 oder höher ist, ist die Verbindung mit Redis hergestellt.
    
   - Nachdem Sie einige Minuten abgewartet haben und nachdem mindestens ein Agent installiert wurde, überprüfen Sie, ob sich der Leistungsindikator erhöht.
    
### <a name="install-the-website"></a>Installieren der Website

Installieren Sie die Website auf dem Hostcomputer durch Ausführen der StatsManWebSite.msi und angeben die folgenden:
  
1. Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**.  
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen ein:
    
   - **Dienst-Port:** Dies ist die Portnummer an, der die Website überwacht wird. Sie können sie später über eine IIS-Manager-Bindung ändern. Bei der Installation wird dieser Port durch die lokale Firewall durchgelassen.
    
   - **Dir installieren:** Dies ist das Verzeichnis, in dem die Binärdateien installiert werden sollen. Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.
    
   - **Anwendungsdaten Dir:** Dies ist das Verzeichnis, in dem der Ordner Logs und andere Daten gespeichert werden. Sie können den Standardprotokollordner ändern. Er wird bei einer Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Um die Website anzeigen, öffnen Sie einen Browser, und navigieren Sie zu: http://localhost, Webport\>/.
  
Integritätsinformationen nur anzeigen, öffnen Sie einen Browser, und navigieren zu: http://localhost:\<webport\>/healthcheck/.
  
Der Standardwert für die Webportnummer lautet 8080. Sie können die Portbindung der Website über den IIS-Manager ändern.
  
Das Website-Installationsprogramm fügt eine lokale Sicherheitsgruppe mit dem Namen StatsManWebSiteUsers hinzu. Sie können dieser Sicherheitsgruppe Konten hinzufügen, um Zugriff auf die Website zu gewähren. 
  
### <a name="install-the-agents"></a>Installation der Agents

Installieren Sie einen Agent auf jedem Skype für Business Server, die Sie durch Ausführen der StatsManPerfAgent.msi und angeben die folgenden überwachen möchten:
  
1. Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**.  
    
2. Geben Sie auf der nächsten Seite die folgenden Informationen ein:
    
   - **Dienstkennwort:** Dies ist das Kennwort, mit dem der Remote-Agent den Listener-Dienst authentifiziert.
    
   - **Datendienst-URI:** Dies ist der URI der Listener sich befindet. Sollte die https://name:port Format.
    
     Sie können einen NETBIOS-Namen oder einen FQDN verwenden. Sie können den Namen, der auch als **Betreff** oder **Alternative Antragstellernamen** des Zertifikats auf den Listener-Dienst angegeben wird, aber dies ist nicht erforderlich.
    
   - **Service Fingerabdruck:** Hierbei handelt es sich um den Fingerabdruck des SSL-Zertifikats der Listener verwendeten. Der Agent verwendet diesen Fingerabdruck zur Authentifizierung des Listeners. (Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.)
    
   - **Dir installieren:** Dies ist das Verzeichnis auf dem die Binärdateien installiert werden. Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.
    
   - **Anwendungsdaten Dir:** Dies ist das Verzeichnis, in dem der Ordner Logs und die verschlüsselte Password.txt geschrieben gespeichert werden. Sie können den Standardprotokollordner ändern. Er wird bei einer Deinstallation nicht gelöscht.
    
3. Klicken Sie auf **Installieren**.
    
Wenn Sie einen Agent auf einer Reihe von Computern installieren, werden Sie dies wahrscheinlich im unbeaufsichtigten Modus durchführen wollen. Beispiel:   
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Import der Topologie
<a name="BKMK_ImportTopology"> </a>

Nachdem Statistiken Manager installiert ist und ausgeführt wird, Sie die Skype für Business Server-Topologie importieren müssen weiß also dieses Managers Statistiken der Website, den Pool und die Rolle der einzelnen Server. Um Ihre Skype für Business Server-Topologie zu importieren, werden Sie verwenden Sie das [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) -Cmdlet zum Abrufen von Informationen zu allen Pools in Ihrer Organisation und dann importieren diese Informationen in den Statistiken-Manager.
  
Gehen folgendermaßen Sie vor, um die Skype für Business Server-Topologie zu importieren:
  
1. Auf einem Host, der die Skype für Business Server PowerShell-Cmdlets verfügt:
    
    a. Führen Sie den folgenden Befehl aus: 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    b. Kopieren Sie die Datei "mypoolinfo.xml" auf den Server, der den Listener ausgeführt wird.
    
2. Auf dem Host, auf dem der Listener ausgeführt wird:
    
   a. Führen Sie PowerShell aus.
    
   b. Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist. Die Standardeinstellung ist: 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. Führen Sie den folgenden Befehl aus, um zu bestätigen, welche Server hinzugefügt und aktualisiert werden:
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

Mit dem folgenden Befehl können Sie alle Optionen anzeigen:
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

Um Ihre gerade importierten Serverinformationen anzuzeigen, führen Sie das folgende Skript aus: 
  
```
.\Get-StatsManServerInfo.ps1
```

Wenn Sie möchten, zum Überwachen von Servern, die nicht in Ihrer Skype für Business Server-Topologie – einen Exchange-Server sind beispielsweise--Möglichkeiten einen Einzelserver Import auf dem Host, die den Listener ausgeführt wird. Wenn Sie nur einen einzelnen Server importieren möchten, gehen Sie wie folgt vor:
  
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
  
- Ist der Agent im Statistik-Manager registriert?
    
1. 	Stellen Sie sicher, dass Sie die Anweisungen für den Import der Topologie befolgt haben. Siehe auch [Import the topology](deploy.md#BKMK_ImportTopology).  
    
2. Wenn sich der Agent auf einem Server befindet, der in der Topologie nicht aufgeführt ist (zum Beispiel die Knoten in einem SQL-„AlwaysOn“-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anleitungen in [Import the topology](deploy.md#BKMK_ImportTopology) ausführen.
    
- Kann der Agent den Listener kontaktieren?
    
1. Stellen Sie sicher, dass der Listener-Dienst ausgeführt wird.   
    
    Wenn der Listener nicht ausgeführt wird, stellen Sie sicher, dass Redis ausgeführt wird, und versuchen Sie anschließend, den Listener neu zu starten.
    
2. Stellen Sie sicher, der Port öffnen, um den Listener-Dienst ist und dass der Agent-Computer mit dem Port kommunizieren kann.
    
- Um sicherzustellen, dass Statistiken Manager Daten erfasst, können Sie die CSV-Datei wie folgt überprüfen. 
    
    Der folgende Befehl ruft die Computer-Speichernamen ab:   
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Der nächste Befehl ruft die Werte ab für die angegebenen Zähler ab:  
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Informationen über alle Ereignisse, die möglicherweise im Ereignisprotokoll Anwendung angezeigt finden Sie unter [Problembehandlung bei Statistiken Manager für Skype für Business Server](troubleshoot.md).
  
## <a name="create-a-self-signed-certificate"></a>Erstellen eines selbstsignierten Zertifikats
<a name="BKMK_SelfCert"> </a>

Microsoft empfiehlt dringend die Verwendung eines Zertifikats, das von einer vertrauenswürdigen Zertifizierungsstelle signiert ist. Wenn Sie jedoch zu Testzwecken ein selbst-signiertes Zertifikat verwenden möchten, gehen Sie wie folgt vor: 
  
1. Melden Sie sich als Administrator an und geben Sie in einer PowerShell-Konsole Folgendes ein:
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Typ `certlm.msc`. Dadurch öffent sich der Zertifikat-Manager für den lokalen Computer.
    
3. Navigieren Sie zur **persönlichen**, und öffnen Sie dann auf **Zertifikate**.
    
4. Klicken Sie mit der rechten Maustaste auf **StatsManListener -\>alle Aufgaben -\>Privatschlüssel verwalten**
    
5. Klicken Sie auf **Hinzufügen**.
    
6. Geben Sie im Feld **Geben Sie die zu verwendenden Objektnamen ein** folgenden Text ein: Netzwerkdienst
    
7. Klicken Sie anschließend auf **OK**.
    
8. Deaktivieren Sie unter **Vollzugriff** das Kontrollkästchen **Zulassen**. (Nur Leseberechtigung erforderlich)
    
9. Klicken Sie anschließend auf **OK**.
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_SelfCert"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen der Business Server für den Statistiken-Manager für Skype](plan.md)
    
- [Aktualisieren von Statistiken Manager für Skype für Business Server](upgrade.md)
    
- [Problembehandlung bei Statistiken Manager für Skype für Business Server](troubleshoot.md)
    
- [Skype for Business Server Statistics Manager-Blog](https://blogs.technet.microsoft.com/skypestatsman/)
    

