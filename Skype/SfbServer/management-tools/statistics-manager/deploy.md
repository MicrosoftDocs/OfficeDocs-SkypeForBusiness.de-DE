---
title: Bereitstellen von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server bereitstellen.'
ms.openlocfilehash: 1debe0c38b3e3df0b6be193e892991c09e15fb61
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675987"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a>Bereitstellen von Statistics Manager für Skype for Business Server

**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server bereitstellen.

 Statistics Manager für Skype for Business Server ist ein leistungsstarkes Tool, mit dem Sie Skype for Business Server Integritäts- und Leistungsdaten in Echtzeit anzeigen können. Sie können Leistungsdaten alle paar Sekunden auf Hunderten von Servern abfragen und die Ergebnisse sofort auf der Statistics Manager-Website anzeigen.

Bevor Sie versuchen, Statistics Manager zu installieren, sollten Sie mit den Software-, Netzwerk- und Hardwareanforderungen vertraut sein. Weitere Informationen finden Sie unter [Plan for Statistics Manager for Skype for Business Server](plan.md).

> [!NOTE]
> Wenn Sie ein Upgrade von einer früheren Version von Statistics Manager durchführen, lesen Sie [upgrade Statistics Manager für Skype for Business Server](upgrade.md).

> [!NOTE]
> Die Statistics Manager-Website wurde getestet und funktioniert ordnungsgemäß unter Internet Explorer 11+, Edge 20.10240+ und Chrome 46+ (aktuelle Evergreen-Version).

Sie finden den Statistics Manager herunterladbar unter [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).

Dieses Thema enthält die folgenden Abschnitte:

- [Bereitstellen von Statistics Manager](deploy.md#BKMK_Deploy)

- [Problembehandlung bei der Bereitstellung](deploy.md#BKMK_Troubleshoot)

- [Erstellen eines selbstsignierten Zertifikats](deploy.md#BKMK_SelfCert)

## <a name="deploy-statistics-manager"></a>Bereitstellen von Statistics Manager
<a name="BKMK_Deploy"> </a>

Führen Sie die folgenden Schritte aus, um Statistics Manager bereitzustellen:

1. Bereiten Sie den Listener-Hostcomputer vor, indem Sie das Speicherzwischenspeichersystem Redis installieren und sicherstellen, dass Sie die entsprechenden Zertifikate installiert haben.

2. Installieren Sie den Listener-Dienst auf dem Hostcomputer.

3. Installieren Sie die Website auf dem Hostcomputer.

4. Installieren Sie einen Agent auf jedem Skype for Business Server Computer, den Sie überwachen möchten.

5. Importieren Sie die Topologie für die Server, die Sie überwachen.

> [!NOTE]
> Redis, der Listener-Dienst und die Website müssen alle auf demselben Hostcomputer installiert sein. Stellen Sie sicher, dass auf dem Hostcomputer keine Skype for Business Server installiert sind.

### <a name="prepare-the-listener-host-machine"></a>Vorbereiten des Listener-Hostcomputers

Um den Hostcomputer vorzubereiten, müssen Sie das Speicherzwischenspeicherungssystem Redis installieren und sicherstellen, dass sich ein gültiges Zertifikat auf dem Computer befindet. Microsoft empfiehlt, den neuesten stabilen Build von Redis 3.0 zu installieren. Statistics Manager Version 2.0 wurde mit Redis 3.2.100 getestet.

1. Laden Sie Redis von der folgenden Website herunter: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).

    Nicht signierte Installationsprogramme können von [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)

    Signierte Binärdateien sind über beliebte Paketmanager verfügbar: [Nuget](https://www.nuget.org/packages/Redis-64/) und [Choclatey](https://chocolatey.org/packages/redis-64).

   - Führen Sie die bereitgestellte MSI-Datei aus, und folgen Sie den Anweisungen.

   - Aktivieren Sie das Kontrollkästchen nicht, um eine Firewallregel hinzuzufügen.

2. Der Listener-Dienst erfordert ein Zertifikat. Microsoft empfiehlt dringend, dass Sie ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle signiert haben.

    Wenn Sie ein selbstsigniertes Zertifikat verwenden möchten , z. B. zu Testzwecken in einem Labor, lesen Sie " [Erstellen eines selbstsignierten Zertifikats](deploy.md#BKMK_SelfCert)".

    Der Agent verwendet die Überprüfung des Zertifikatfingerabdrucks (anstelle der Kettenüberprüfung). Die vollständige Zertifikatüberprüfung wird nicht erfolgen, da es möglich ist, selbstsignierte Zertifikate zu verwenden.

### <a name="install-the-listener-service"></a>Installieren des Listener-Diensts

Installieren Sie den Listener-Dienst auf dem Hostcomputer, indem Sie die StatsManPerfAgentListener.msi ausführen und Folgendes angeben:

1. Überprüfen Sie den Lizenzvertrag, und wenn Sie damit einverstanden sind, wählen Sie **"Ich stimme den Bedingungen im Lizenzvertrag** zu" und klicken Sie dann auf **"Weiter**".

2. Geben Sie auf der nächsten Seite die folgenden Informationen an:

   - **Dienstkennwort:** Dieses Kennwort wird von den Remote-Agents verwendet, um sich beim Listener-Dienst zu authentifizieren.

   - **Dienstport:** Diese HTTPS-Portnummer wird vom Listener für die Kommunikation mit den Agents verwendet. Während der Installation wird dieser Port über die lokale Firewall zugelassen, eine URL-ACL wird erstellt, und ein SSL-Zertifikat wird an diesen Port gebunden. Der Standardwert ist 8443.

   - **Zertifikatfingerabdruck:** Dieses Zertifikat wird vom Listener verwendet, um das HTTPS-Protokoll zu verschlüsseln. Der Netzwerkdienst muss Lesezugriff auf den privaten Schlüssel haben.

     Klicken Sie auf die Schaltfläche **"Auswählen...** ", um den Fingerabdruck auszuwählen.

     Sie finden den Zertifikatfingerabdruck mithilfe des Zertifikat-Managers oder mithilfe des folgenden PowerShell-Befehls:

      ```PowerShell
      Get-ChildItem -path cert:\LocalMachine\My
      ```

   - **Installationsverzeichnis:** In diesem Verzeichnis werden die Binärdateien installiert. Sie können dies mithilfe der Schaltfläche Durchsuchen **...** von der Standardeinstellung ändern.

   - **AppData Dir:** In diesem Verzeichnis werden der Ordner "Protokolle" und andere Daten gespeichert. Sie können es von der Standardeinstellung ändern. Sie wird bei der Deinstallation nicht gelöscht.

3. Klicken Sie auf **Installieren**.

Führen Sie die folgenden Schritte aus, um die Installation zu überprüfen:

1. Öffnen Sie einen Browser, und navigieren Sie zu `https://localhost:<service-port>/healthcheck/`.

    Standardmäßig ist der Dienstport 8443 (es sei denn, Sie haben einen anderen Port angegeben).

2. Um sicherzustellen, dass der Listener ordnungsgemäß installiert ist, suchen Sie nach Folgendem:

   - Wenn die Seite "Integritätsüberprüfung" angezeigt wird, war die Listener-Installation erfolgreich.

   - Wenn "KnownServerCount" 1 oder höher ist, wird die Verbindung mit Redis hergestellt.

   - Nachdem Sie einige Minuten gewartet haben und mindestens ein Agent installiert wurde, überprüfen Sie, ob der ValuesWritten-Zähler erhöht wird.

### <a name="install-the-website"></a>Installieren der Website

Installieren Sie die Website auf dem Hostcomputer, indem Sie die StatsManWebSite.msi (im Lieferumfang [von Skype for Business Server, Real-Time Statistics Manager (64-Bit)](https://www.microsoft.com/download/details.aspx?id=57518)) ausführen:

1. Überprüfen Sie den Lizenzvertrag, und wenn Sie damit einverstanden sind, wählen Sie **"Ich stimme den Bedingungen im Lizenzvertrag** zu" und klicken Sie dann auf **"Weiter**".

2. Geben Sie auf der nächsten Seite die folgenden Informationen an:

   - **Dienstport:** An diesem TCP-Port lauscht die Website. Sie können sie später mithilfe der IIS-Managerbindung ändern. Während der Installation wird dieser Port über die lokale Firewall zugelassen.

   - **Installationsverzeichnis:** In diesem Verzeichnis werden die Binärdateien installiert. Sie können dies mithilfe der Schaltfläche Durchsuchen **...** von der Standardeinstellung ändern.

   - **AppData Dir:** In diesem Verzeichnis werden der Ordner "Protokolle" und andere Daten gespeichert. Sie können es von der Standardeinstellung ändern. Sie wird bei der Deinstallation nicht gelöscht.

3. Klicken Sie auf **Installieren**.

Um die Website anzuzeigen, öffnen Sie einen Browser, und navigieren Sie zu: `http://<localhost:webport/>`.

Um nur Integritätsinformationen anzuzeigen, öffnen Sie einen Browser, und navigieren Sie zu: `http://localhost:<webport>/healthcheck/`.

Standardmäßig lautet die Webportnummer 8080. Sie können die Portbindung der Website mithilfe des IIS-Managers ändern.

Das Webinstallationsprogramm fügt eine lokale Sicherheitsgruppe mit dem Namen StatsManWebSiteUsers hinzu. Sie können dieser Sicherheitsgruppe Konten hinzufügen, um Zugriff auf die Website zu gewähren.

### <a name="install-the-agents"></a>Installieren der Agents

Installieren Sie einen Agent auf jeder Skype for Business Server, die Sie überwachen möchten, indem Sie die StatsManPerfAgent.msi ausführen:

1. Überprüfen Sie den Lizenzvertrag, und wenn Sie damit einverstanden sind, wählen Sie **"Ich stimme den Bedingungen im Lizenzvertrag** zu" und klicken Sie dann auf **"Weiter**".

2. Geben Sie auf der nächsten Seite die folgenden Informationen an:

   - **Dienstkennwort:** Dieses Kennwort wird vom Remote-Agent verwendet, um sich beim Listener-Dienst zu authentifizieren.

   - **Dienst-URI:** Unter dieser URL befindet sich der Listener. Verwenden Sie das `https://name:port` Format.

     Sie können einen NETBIOS-Namen oder einen FQDN verwenden. Sie können den Namen verwenden, der auch als **alternative Antragsteller****- oder Antragstellernamen** des Zertifikats im Listener-Dienst angegeben ist, dies ist jedoch keine Anforderung.

   - **Dienstfingerabdruck:** Dieses SS:-Zertifikat wird vom Listener verwendet. Der Agent verwendet diesen Fingerabdruck, um sich beim Listener zu authentifizieren. Die vollständige Zertifikatüberprüfung wird nicht erfolgen, da es möglich ist, selbstsignierte Zertifikate zu verwenden.

   - **Installationsverzeichnis:** In diesem Verzeichnis werden die Binärdateien installiert. Sie können dies mithilfe der Schaltfläche Durchsuchen **...** von der Standardeinstellung ändern.

   - **AppData Dir:** In diesem Verzeichnis werden der Ordner "Logs" und die verschlüsselte password.txt-Datei gespeichert. Sie können sich dafür bedanken, dass Sie es von der Standardeinstellung ändern. Sie wird bei der Deinstallation nicht gelöscht.

3. Klicken Sie auf **Installieren**.

Wenn Sie einen Agent auf zahlreichen Computern installieren, sollten Sie dies wahrscheinlich im unbeaufsichtigten Modus tun. Beispiel:

```console
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a>Importieren der Topologie
<a name="BKMK_ImportTopology"> </a>

Nachdem Statistics Manager installiert und ausgeführt wurde, müssen Sie die Skype for Business Server Topologie importieren, damit Statistics Manager den Standort, den Pool und die Rolle jedes Servers kennt. Um Ihre Skype for Business Server Topologie zu importieren, verwenden Sie das [Cmdlet "Get-CsPool](/powershell/module/skype/get-cspool)", um Informationen zu jedem pool abzurufen, der in Ihrer Organisation verwendet wird, und importieren diese Informationen dann in Statistics Manager.

Führen Sie die folgenden Schritte aus, um die Skype for Business Server Topologie zu importieren:

1. Auf einem Host mit den Skype for Business Server PowerShell-Cmdlets:

    a. Führen Sie den folgenden Befehl aus:

   ```PowerShell
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```

    b. Kopieren Sie die Datei "mypoolinfo.xml" auf den Server, auf dem der Listener ausgeführt wird.

2. Auf dem Host, auf dem der Listener ausgeführt wird:

   a. Führen Sie PowerShell aus.

   b. Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist. Die Standardeinstellung ist:

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

Führen Sie das folgende Skript aus, um die aktuell importierten Serverinformationen anzuzeigen:

```powershell
.\Get-StatsManServerInfo.ps1
```

Wenn Sie Server überwachen möchten, die sich nicht in Ihrer Skype for Business Server Topologie befinden – z. B. ein Exchange Server –, können Sie einen Einzelserverimport auf dem Host durchführen, auf dem der Listener ausgeführt wird. Führen Sie die folgenden Schritte aus, um einen Einzelserverimport auszuführen:

1. Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist. Die Standardeinstellung ist:

   ```console
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. Führen Sie den folgenden Befehl aus:

   ```powershell
   .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a>Problembehandlung bei der Bereitstellung
<a name="BKMK_Troubleshoot"> </a>

Wenn ein Agent nicht gestartet werden kann, überprüfen Sie die folgenden Probleme:

- Ist der Agent im Statistics Manager registriert?

   1. Stellen Sie sicher, dass Sie die Anweisungen zum Importieren der Topologie befolgt haben. Siehe [Importieren der Topologie](deploy.md#BKMK_ImportTopology).

   2. Wenn sich der Agent auf einem Server befindet, der nicht in der Topologie aufgeführt ist (z. B. die Knoten in einem SQL AlwaysOn-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anweisungen im [Importieren der Topologie](deploy.md#BKMK_ImportTopology) befolgen.

- Kann der Agent den Listener kontaktieren?

   1. Stellen Sie sicher, dass der Listener-Dienst ausgeführt wird.

      Wenn sie nicht ausgeführt wird, stellen Sie sicher, dass Redis ausgeführt wird, und versuchen Sie dann, den Listener neu zu starten.

   2. Stellen Sie sicher, dass der Port für den Listener-Dienst geöffnet ist und dass der Agentcomputer mit dem Port kommunizieren kann.

- Um sicherzustellen, dass Statistics Manager Daten sammelt, können Sie die CSV-Datei wie folgt überprüfen.

    Mit dem folgenden Befehl werden die Speichernamen des Zählers abgerufen:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    Der nächste Befehl ruft die Werte für die angegebenen Leistungsindikatoren ab:

  ```console
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

Informationen zu allen Ereignissen, die möglicherweise im Anwendungsereignisprotokoll angezeigt werden, finden Sie unter [Problembehandlung im Statistics Manager für Skype for Business Server](troubleshoot.md).

## <a name="create-a-self-signed-certificate"></a>Erstellen eines selbstsignierten Zertifikats
<a name="BKMK_SelfCert"> </a>

Microsoft empfiehlt dringend die Verwendung eines Zertifikats, das von einer vertrauenswürdigen Zertifizierungsstelle signiert wurde. Wenn Sie jedoch ein selbstsigniertes Zertifikat zu Testzwecken verwenden möchten, führen Sie die folgenden Schritte aus:

1. Führen Sie von einer PowerShell-Konsole aus, während Sie als Administrator angemeldet sind, den folgenden Befehl aus:

   ```powershell
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. Geben Sie  `certlm.msc`ein . Dadurch wird der Zertifikat-Manager für den lokalen Computer geöffnet.

3. Navigieren Sie zu **"Persönlich"**, und öffnen **Sie dann Zertifikate**.

4. Klicken Sie mit der rechten Maustaste auf **StatsManListener- \> Alle Aufgaben- \>Private Schlüssel verwalten...**

5. Klicken Sie auf **Hinzufügen**.

6. Geben Sie in das Feld **"Objektnamen eingeben"** den folgenden Text ein: Netzwerkdienst

7. Klicken Sie auf **OK**.

8. Deaktivieren Sie unter **"Vollzugriff**" das Kontrollkästchen **"Zulassen** ". (Nur Lesezugriff ist erforderlich.)

9. Klicken Sie auf **OK**.

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_SelfCert"> </a>

Weitere Informationen finden Sie in den folgenden Themen:

- [Planen von Statistics Manager für Skype for Business Server](plan.md)

- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)

- [Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server](troubleshoot.md)
