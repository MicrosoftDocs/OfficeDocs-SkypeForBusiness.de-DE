---
title: Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Probleme bei der Bereitstellung von Statistics Manager für Skype for Business Server zu beheben.'
ms.openlocfilehash: 6e6edefe8d6070a917f817b3b6d79bf35ff36599
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857342"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Probleme bei der Bereitstellung von Statistics Manager für Skype for Business Server zu behandeln.
  
In diesem Thema wird beschrieben, wie Sie Ihre Statistics Manager-Bereitstellung beheben, indem Ereignisse beschrieben werden, die möglicherweise im Anwendungsereignisprotokoll angezeigt werden, und entsprechende Maßnahmen, die Sie zur Behebung des Ereignisses ergreifen können. Dieses Thema enthält die folgenden Abschnitte:
  
- [Agent-Ereignisse](troubleshoot.md#BKMK_Agent)
    
- [Listener-Ereignisse](troubleshoot.md#BKMK_Listener)
    
- [Websiteprobleme](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Agent-Ereignisse
<a name="BKMK_Agent"> </a>

- **1000** - Prozessorlimiter (Job-Objekt) kann nicht eingerichtet werden - Unbekannter Grund
    
- **1001** - Prozessbegrenzung ist für den Prozess nicht zulässig (wahrscheinlich bereits innerhalb eines Auftragsobjekts)
    
    Der Agent wird innerhalb eines Windows Auftragsobjekts ausgeführt, um den Speicherbedarf automatisch zu begrenzen. Wenn der Agent nicht gestartet wird und diese Ereigniseinträge im Ereignisprotokoll vorhanden sind, kann das Auftragsobjekt nicht auf dem Server instanziiert werden. Um dies zu umgehen, kann der obere Speichergrenzwert entfernt werden, indem ein Wert in der Konfigurationsdatei geändert wird:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Suchen Sie nach "MaxProcessMemoryMB", und ändern Sie den Wert wie dargestellt in "0":
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Wenn diese Änderung vorgenommen wird, verbraucht der Agent in der Regel immer noch \< 100 MB Arbeitsspeicher. Er wird jedoch nicht erzwungen auf 300 MB beschränkt, wie es der Standardwert ist. Wenn diese Änderung vorgenommen wird, wird empfohlen, die Speichernutzung genau zu überwachen, um sicherzustellen, dass der Agent auf seinem Hostcomputer keine große Menge Arbeitsspeicher verbraucht. 
  
- **2000** – Clientinitialisierungsfehler
    
- **2001**: Es konnte keine Verbindung mit dem Dienst in einer Quell-IP hergestellt werden.
    
    Wenn der Agent keine Verbindung mit dem Listener-Computer herstellen kann, überprüfen Sie Folgendes:
    
    1. Stellen Sie sicher, dass der Listener-Dienst auf dem Listener-Computer ausgeführt wird. Wenn nicht, stellen Sie sicher, dass Redis auf diesem Server ausgeführt wird, und starten Sie dann den Listener-Dienst neu.
        
        Überprüfen Sie das Statistics Manager-Ereignisprotokoll auf dem Listener-Computer, um sicherzustellen, dass keine Probleme mit dem Statistics Manager Listener-Dienst selbst auftreten.
        
    2. Verwenden Sie ein Verbindungstool wie Telnet, um die Konnektivität zwischen dem Agent-Computer und dem Listener am richtigen Port zu überprüfen.
        
        Wenn nicht, stellen Sie sicher, dass die Eingehende Firewallregel auf dem Listener-Computer für den Netzwerktyp aktiviert ist, mit dem der Listener-Computer verbunden ist (privat/öffentlich/Domäne). Wenn der Listener-Computer nicht mit einer Domäne verbunden ist, wird das Netzwerk möglicherweise als öffentlich aufgeführt, und in diesem Fall gelten die mit Statistics Manager installierten Firewallregeln nicht standardmäßig.
    
- **4000** – Fehler beim Herunterladen von Serverinformationen vom Listener (unbekannter Grund)
    
  - **4001** - Server in Listener-Topologie nicht gefunden
    
    Dieser Fehler tritt auf, wenn der Server erfolgreich eine Verbindung mit dem Listener herstellt, der Server jedoch nicht zur Topologie im Cache des Listeners hinzugefügt wurde. Lösungsoptionen:
    
  - Stellen Sie sicher, dass Sie die Anweisungen zum Importieren der Topologie befolgt haben. Weitere Informationen finden Sie unter [Importieren der Topologie.](deploy.md#BKMK_ImportTopology) 
    
  - Wenn sich der Agent auf einem Server befindet, der nicht in der Topologie aufgeführt ist (z. B. die Knoten in einem SQL AlwaysOn-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anweisungen unter [Importieren der Topologie](deploy.md#BKMK_ImportTopology)befolgen.
    
  - **4002** - Ungültiges Listener-Kennwort
    
    Das verschlüsselte Kennwort, das der Agent zu verwenden versucht, stimmt nicht mit dem Dienstkennwort auf dem Listener selbst überein. Deinstallieren Sie den Agent, und installieren Sie ihn mit dem richtigen Dienstkennwort erneut.
    
  - **4003** – Nichtübereinstimmung beim Fingerabdruck des Zertifikats
    
    Der Zertifikatfingerabdruck, der dem Agent zur Installationszeit zugewiesen wurde, entspricht nicht dem Fingerabdruck auf dem Zertifikat, das der Listener derzeit verwendet, und daher wird die Verbindung verweigert. Deinstallieren Sie den Agent, und installieren Sie ihn mit dem korrekten Zertifikatfingerabdruck erneut.
    
  - **4004** - Ungültige Antwort oder HttpStatusCode
    
    Der Listener antwortet nicht mit einem erwarteten Status. 
    
  - Wenn die Verbindung proxied ist, überprüfen Sie die Proxykonfiguration.
    
  - Überprüfen Sie das StatsMan-Protokoll des Listener-Computers auf Probleme mit der Konfiguration.
    
  - **4005** - Xml konnte nicht de serialisiert werden
    
    Die Serverinformationen auf dem Listener-Server sind beschädigt, oder es liegt möglicherweise ein Versionskonflikt zwischen dem Agent und den Listener-Computern vor. Stellen Sie sicher, dass die Versionen übereinstimmen, und überprüfen Sie das Listener-Ereignisprotokoll auf Probleme.
    
## <a name="listener-events"></a>Listener-Ereignisse
<a name="BKMK_Listener"> </a>

- **10000** – Startfehler Unbekannter Grund (diese sind nicht behebbar, und der Dienst wird daraufhin beendet/abstürzt)
    
  - **10001** – Konfigurationsproblem
    
    In der Regel tritt dies auf, wenn die Datei [listener_install_location]\PerfAgentListener.exe.config von Hand geändert wurde und von der Anwendung nicht gelesen werden kann.
    
  - **10002** - HTTP-Listener-Initialisierungsfehler
    
    Dieses Ereignis wird in der Regel protokolliert, wenn die URL-ACL während der Installation nicht ordnungsgemäß festgelegt wurde oder das SSL-Zertifikat ungültig ist. Stellen Sie sicher, dass das Zertifikat in Ihrer Konfiguration gültig ist. Falls ja, installieren Sie den Listener gemäß den Anweisungen in [Deploy Statistics Manager](deploy.md#BKMK_Deploy)neu.
    
  - **10003** – Redis-Fehler
    
  - **10004** – Fehler bei der Zwischenspeicherung der Infrastruktur
    
  - **10007** - Einstellungen (in Redis gespeichert)
    
    Der Listener konnte redis nicht kontaktieren oder wohlgeformte Daten aus dem Cache abrufen und konnte nicht gestartet werden. Stellen Sie sicher, dass der Redis-Dienst auf dem Server gestartet und ordnungsgemäß konfiguriert ist.
    
  - **10005** – Abrufen/Analysieren von Serverinformationen
    
    Die Topologieinformationen im Redis-Cache sind ungültig. Versuchen Sie zunächst, Redis und den Listener neu zu starten. Wenn der Fehler weiterhin besteht, lesen [Sie "Importieren der Topologie",](deploy.md#BKMK_ImportTopology) um die Topologiedaten neu zu erstellen.
    
- **10100** – Redis PING-Ausfall
    
  - **10101** – Redis-PING-Fortsetzungsausfall (alle 60 Sekunden)
    
  - **30100** – Redis-PING-Ausfall wiederhergestellt
    
    Diese werden protokolliert, wenn der Listener keine Verbindung mit Redis herstellen kann. Stellen Sie sicher, dass Redis gestartet und netzwerkkonnektivität zwischen Listener und Redis verfügbar ist.
    
- **10200** – Redis Write-Ausfall
    
  - **10201** – Redis Write-Ausfall fortgesetzt (alle 60 Sekunden)
    
  - **30100** – Redis Write-Ausfall behoben
    
    Diese werden protokolliert, wenn der Listener nicht in den Redis-Cache schreiben kann. Stellen Sie sicher, dass Redis gestartet und netzwerkkonnektivität zwischen Listener und Redis verfügbar ist.
    
- **30000** – Erfolgreich gestartet
    
    Jedes Mal protokolliert, wenn der Listener gestartet wird.
    
- **22000** – Initialisierung des Statistics Manager-Agenten erfolgreich.
    
- **23000** – Initialisierung von EventLogQueryManager erfolgreich (erstmalig oder nach einem Fehler)
    
- **24000** – Initialisierung von serverinfo erfolgreich (erstmalig oder nach einem Fehler)
    
- **25000** – Listener ist wieder online, nachdem er keine Beiträge (oder ersten erfolgreichen Beitrag) veröffentlicht hat
    
- **5000** - Start des Listeners offline für die Veröffentlichung von Daten
    
- **5001** - Listener ist noch über einen längeren Zeitraum offline
    
    Diese Ereignisse können für Überwachungs-/Warnungs-/Clearingprobleme hilfreich sein.
    
## <a name="website-issues"></a>Websiteprobleme
<a name="BKMK_Website"> </a>

- Wiederholte Anmeldeaufforderungen in Chrome – dies war ein Fehler, der in Version 1.1 behoben wurde. Stellen Sie sicher, dass Sie auf die neueste Version von Statistics Manager aktualisiert haben, wenn wiederholte Anmeldeaufforderungen im Chrome-Browser angezeigt werden. So überprüfen Sie die Version der Website, die Sie ausführen:
    
  - Öffnen Sie im Datei-Explorer (Standardverzeichnis)
    
  - Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite.dll, und zeigen Sie dessen Eigenschaften an.
    
  - Wenn ein Computer in der KHI-Querformatansicht oder in der Ansicht "Zählerdetails" nicht gefunden werden kann, stellen Sie sicher, dass er Mitglied einer Website und eines Pools ist. Ist dies nicht der Typ, wird er in diesen Ansichten nicht angezeigt. Informationen zum Definieren eines Standorts und Pools für einen Server in der Topologie finden Sie unter [Importieren der Topologie.](deploy.md#BKMK_ImportTopology)
    
  - Die Produktversion wird in den Beschreibungsdetails angezeigt.
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Website"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)
    
- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)
