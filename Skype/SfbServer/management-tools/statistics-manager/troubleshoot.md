---
title: Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Probleme mit der Bereitstellung von Statistics Manager für Skype for Business Server zu beheben.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821775"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um Probleme mit der Bereitstellung von Statistics Manager für Skype for Business Server zu beheben.
  
In diesem Thema wird beschrieben, wie Sie eine Problembehandlung für Die Statistics -Manager-Bereitstellung durchführen, indem Ereignisse beschrieben werden, die möglicherweise im Anwendungsereignisprotokoll angezeigt werden, und geeignete Maßnahmen, die Sie zur Behebung des Ereignisses ergreifen können. Dieses Thema enthält die folgenden Abschnitte:
  
- [Agentereignisse](troubleshoot.md#BKMK_Agent)
    
- [Listenerereignisse](troubleshoot.md#BKMK_Listener)
    
- [Websiteprobleme](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Agentereignisse
<a name="BKMK_Agent"> </a>

- **1000** – Prozessorgrenzwert kann nicht eingerichtet werden (Auftragsobjekt) – Unbekannter Grund
    
- **1001** – Prozessbegrenzung ist für den Prozess nicht zulässig (wahrscheinlich bereits innerhalb eines Auftragsobjekts)
    
    Der Agent wird innerhalb eines Windows-Auftragsobjekts ausgeführt, um den Speicherbedarf automatisch zu begrenzen. Wenn der Agent nicht gestartet wird und diese Ereigniseinträge im Ereignisprotokoll vorhanden sind, kann das Auftragsobjekt nicht auf dem Server instanziiert werden. Um dies zu ändern, kann der obere Speichergrenzwert durch Ändern eines Werts in der Konfigurationsdatei entfernt werden:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Suchen Sie nach "MaxProcessMemoryMB", und ändern Sie den Wert wie gezeigt in "0":
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Wenn diese Änderung vorgenommen wird, verbraucht der Agent im Allgemeinen weiterhin 100 MB Arbeitsspeicher, wird jedoch nicht wie standardmäßig auf \< 300 MB beschränkt. Wenn diese Änderung vorgenommen wird, wird empfohlen, die Speicherauslastung genau zu überwachen, um sicherzustellen, dass der Agent nicht viel Arbeitsspeicher auf seinem Hostcomputer verbraucht. 
  
- **2000** – Fehler bei der Client initialisierung
    
- **2001**– Es konnte keine Verbindung mit dem Dienst über eine Quell-IP hergestellt werden.
    
    Wenn der Agent keine Verbindung mit dem Listenercomputer herstellen kann, überprüfen Sie Folgendes:
    
    1. Stellen Sie sicher, dass der Listenerdienst auf dem Computer listener ausgeführt wird. Falls nicht, stellen Sie sicher, dass Redis auf diesem Server ausgeführt wird, und starten Sie dann den Listenerdienst neu.
        
        Überprüfen Sie das Statistics Manager-Ereignisprotokoll auf dem Listener-Computer, um sicherzustellen, dass keine Probleme mit dem Statistics Manager Listener Service selbst auftreten.
        
    2. Verwenden Sie ein Konnektivitätstool wie telnet, um die Konnektivität zwischen dem Agentcomputer und dem Listener am richtigen Port zu überprüfen.
        
        Falls nicht, stellen Sie sicher, dass die Regel für eingehende Firewalls auf dem Computer "Listener" für den Netzwerktyp aktiviert ist, mit dem der Computer "Listener" verbunden ist (privat/öffentlich/Domäne). Wenn der Computer "Listener" nicht mit einer Domäne verbunden ist, wird das Netzwerk möglicherweise als öffentlich aufgeführt, und in diesem Fall gelten die mit Statistics Manager installierten Firewallregeln standardmäßig nicht.
    
- **4000** – Fehler beim Herunterladen von Serverinformationen vom Listener (unbekannter Grund)
    
  - **4001** – Server in Listenertopologie nicht gefunden
    
    Dieser Fehler tritt auf, wenn der Server erfolgreich eine Verbindung mit dem Listener herstellen kann, der Server jedoch nicht zur Topologie im Cache des Listeners hinzugefügt wurde. Lösungsoptionen:
    
  - Stellen Sie sicher, dass Sie die Anweisungen zum Importieren der Topologie befolgt haben. Siehe ["Importieren der Topologie".](deploy.md#BKMK_ImportTopology) 
    
  - Wenn sich der Agent auf einem Server befindet, der nicht in der Topologie aufgeführt ist (z. B. die Knoten in einem SQL AlwaysOn-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anweisungen unter ["Topologie](deploy.md#BKMK_ImportTopology)importieren" befolgen.
    
  - **4002** – Ungültiges Listenerkennwort
    
    Das verschlüsselte Kennwort, das der Agent zu verwenden versucht, ist nicht mit dem Dienstkennwort auf dem Listener selbst übereinstimmen. Deinstallieren Sie den Agent, und installieren Sie ihn erneut, indem Sie das richtige Dienstkennwort verwenden.
    
  - **4003** – Zertifikatfingerabdruck – Konflikt
    
    Der Zertifikatfingerabdruck, der dem Agent zur Installationszeit gegeben wurde, passt nicht zum Fingerabdruck des Zertifikats, das der Listener derzeit verwendet, und deshalb wird die Verbindung verweigert. Deinstallieren Sie den Agent, und installieren Sie ihn mithilfe des richtigen Zertifikatfingerabdrucks erneut.
    
  - **4004 –** Ungültige Antwort oder HttpStatusCode
    
    Der Listener reagiert nicht mit einem erwarteten Status. 
    
  - Wenn die Verbindung über eine Proxyverbindung hergestellt wird, überprüfen Sie die Proxykonfiguration.
    
  - Überprüfen Sie das StatsMan-Protokoll des Listenercomputers auf Probleme mit der Konfiguration.
    
  - **4005** – Die Serialisierung des XML konnte nicht de serialisiert werden
    
    Die Serverinformationen auf dem Listenerserver sind beschädigt, oder es besteht ein Versionskonflikt zwischen dem Agent und den Listener-Computern. Stellen Sie sicher, dass die Versionen übereinstimmen, und überprüfen Sie das Listener-Ereignisprotokoll auf Probleme.
    
## <a name="listener-events"></a>Listenerereignisse
<a name="BKMK_Listener"> </a>

- **10000** – Startfehler Unbekannter Grund (diese sind nicht behebbar, und der Dienst wird beendet/abstürzen)
    
  - **10001** – Konfigurationsproblem
    
    Im Allgemeinen tritt dies auf, wenn listener_install_location]-\PerfAgentListener.exe.config Datei von Hand geändert wurde und von der Anwendung nicht gelesen werden kann.
    
  - **10002** – Http Listener Initialisierungsfehler
    
    Dieses Ereignis wird in der Regel protokolliert, wenn die URL-ACL während der Installation nicht ordnungsgemäß festgelegt wurde oder das #A0 ungültig ist. Stellen Sie sicher, dass das Zertifikat in Ihrer Konfiguration gültig ist. Installieren Sie den Listener in diesem Falls entsprechend den Anweisungen in [Deploy Statistics Manager neu.](deploy.md#BKMK_Deploy)
    
  - **10003** – Redis-Fehler
    
  - **10004 –** Fehler bei der Zwischenspeicherungsinfrastruktur
    
  - **10007** – Einstellungen (in Redis gespeichert)
    
    Der Listener konnte Redis nicht kontaktieren oder wohlgeformte Daten aus dem Cache abrufen und konnte nicht gestartet werden. Stellen Sie sicher, dass der Dienst Redis auf dem Server ordnungsgemäß gestartet und konfiguriert ist.
    
  - **10005** – Abrufen/Analyse von Serverinformationen
    
    Die Topologieinformationen im Redis-Cache sind ungültig. Versuchen Sie zunächst, Redis und den Listener neu zu starten. Wenn der Fehler weiterhin besteht, lesen Sie ["Importieren der Topologie",](deploy.md#BKMK_ImportTopology) um die Topologiedaten neu zu erstellen.
    
- **10100** – Redis -PING-Ausfall
    
  - **10101** – Redis PING fortgesetzter Ausfall (alle 60 Sekunden)
    
  - **30100** – Redis -PING-Ausfall wiederhergestellt
    
    Diese werden protokolliert, wenn der Listener keine Verbindung mit Redis herstellen kann. Stellen Sie sicher, dass Redis gestartet ist und die Netzwerkverbindung zwischen Listener und Redis verfügbar ist.
    
- **10200** – Redis Write-Ausfall
    
  - **10201** – Redis Write-Ausfall fortgesetzt (alle 60 Sekunden)
    
  - **30100** – Redis Write-Ausfall behoben
    
    Diese werden protokolliert, wenn der Listener nicht in den Redis-Cache schreiben kann. Stellen Sie sicher, dass Redis gestartet ist und die Netzwerkverbindung zwischen Listener und Redis verfügbar ist.
    
- **30000** – Erfolgreich gestartet
    
    Wird jedes Mal protokolliert, wenn der Listener gestartet wird.
    
- **22000** – Initialisierung des Statistics Manager Agent erfolgreich.
    
- **23000** – Initialisierung von EventLogQueryManager erfolgreich (erstes Mal oder nach einem Fehler)
    
- **24000** – Initialisierung von serverinfo erfolgreich (beim ersten Mal oder nach einem Fehler)
    
- **25000** – Listener ist nach dem Fehler beim Veröffentlichen (oder ersten erfolgreichen Beitrag) wieder online
    
- **5000** – Start des Listeners offline für die Veröffentlichung von Daten
    
- **5001** – Listener ist noch für einen längeren Zeitraum offline
    
    Diese Ereignisse können hilfreich sein, um Probleme zu überwachen/zu warnen/zu löschen.
    
## <a name="website-issues"></a>Websiteprobleme
<a name="BKMK_Website"> </a>

- Wiederholte Anmeldeaufforderungen in Chrome – dies war ein Fehler, der in Version 1.1 behoben wurde. Stellen Sie sicher, dass Sie auf die neueste Version von Statistics Manager aktualisiert haben, wenn wiederholt Anmeldeaufforderungen im Browser Chrome angezeigt werden. So überprüfen Sie die Version der Website, die Sie ausführen:
    
  - Öffnen Sie im Datei-Explorer (Standardverzeichnis)
    
  - Klicken Sie mit der StatsManHubWebSite.dll, und zeigen Sie dessen Eigenschaften an.
    
  - Wenn ein Computer in der Ansicht "KHI-Querformat" oder "Leistungsindikatordetails" nicht gefunden werden kann, stellen Sie sicher, dass er Mitglied eines Standorts und eines Pools ist. Ist dies nicht der Ansicht, wird sie in diesen Ansichten nicht angezeigt. Informationen zum Definieren eines Standorts und Pools für einen Server in der Topologie finden Sie unter [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - Die Produktversion wird in den Beschreibungsdetails angezeigt.
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Website"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)
    
- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)
