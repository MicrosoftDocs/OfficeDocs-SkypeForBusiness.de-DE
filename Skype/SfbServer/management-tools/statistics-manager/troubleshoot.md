---
title: Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
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
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Probleme bei der Bereitstellung von Statistics Manager für Skype for Business Server zu beheben.'
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675277"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server

**Zusammenfassung:** Lesen Sie dieses Thema, um Probleme bei der Bereitstellung von Statistics Manager für Skype for Business Server zu beheben.

In diesem Thema wird beschrieben, wie Sie probleme mit Ihrer Statistics Manager-Bereitstellung beheben, indem Ereignisse beschrieben werden, die möglicherweise im Anwendungsereignisprotokoll angezeigt werden, und geeignete Aktionen, die Sie zur Korrektur des Ereignisses ergreifen können. Dieses Thema enthält die folgenden Abschnitte:

- [Agent-Ereignisse](troubleshoot.md#BKMK_Agent)

- [Listener-Ereignisse](troubleshoot.md#BKMK_Listener)

- [Websiteprobleme](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>Agent-Ereignisse
<a name="BKMK_Agent"> </a>

- **1000** – Prozessorgrenzer kann nicht eingerichtet werden (Auftragsobjekt) – Unbekannter Grund

- **1001** – Prozessbegrenzung ist für den Prozess nicht zulässig (wahrscheinlich bereits innerhalb eines Auftragsobjekts)

    Der Agent wird innerhalb eines Windows Auftragsobjekts ausgeführt, um den Speicherbedarf automatisch zu begrenzen. Wenn der Agent nicht gestartet wird und diese Ereigniseinträge im Ereignisprotokoll vorhanden sind, kann das Auftragsobjekt nicht auf dem Server instanziiert werden. Um dies zu umgehen, kann der obere Speichergrenzwert entfernt werden, indem ein Wert in der Konfigurationsdatei geändert wird:

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Suchen Sie nach "MaxProcessMemoryMB", und ändern Sie den Wert wie gezeigt in "0":

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Wenn diese Änderung vorgenommen wird, verbraucht \< der Agent in der Regel immer noch 100 MB Arbeitsspeicher, ist jedoch nicht wie die Standardeinstellung erzwungen auf 300 MB beschränkt. Wenn diese Änderung vorgenommen wird, empfehlen wir, die Speicherauslastung genau zu überwachen, um sicherzustellen, dass der Agent auf seinem Hostcomputer keine große Menge an Arbeitsspeicher belegt.

- **2000** – Clientinitialisierungsfehler

- **2001**: Es konnte keine Verbindung mit dem Dienst über eine Quell-IP hergestellt werden.

  Wenn der Agent keine Verbindung mit dem Listener-Computer herstellen kann, überprüfen Sie Folgendes:

  1. Stellen Sie sicher, dass der Listener-Dienst auf dem Listener-Computer ausgeführt wird. Wenn dies nicht der Fall ist, stellen Sie sicher, dass Redis auf diesem Server ausgeführt wird, und starten Sie dann den Listener-Dienst neu.

     Überprüfen Sie das Statistics Manager-Ereignisprotokoll auf dem Listener-Computer, um sicherzustellen, dass keine Probleme mit dem Statistics Manager Listener-Dienst selbst auftreten.

  2. Verwenden Sie ein Verbindungstool wie telnet, um die Konnektivität vom Agentcomputer zum Listener am richtigen Port zu überprüfen.

     Falls nicht, stellen Sie sicher, dass die Posteingangsfirewallregel auf dem Listener-Computer für den Netzwerktyp aktiviert ist, mit dem der Listener-Computer verbunden ist (privat/öffentlich/domäne). Wenn der Listener-Computer nicht mit einer Domäne verbunden ist, wird das Netzwerk möglicherweise als öffentlich aufgeführt, und in diesem Fall gelten die mit Statistics Manager installierten Firewallregeln standardmäßig nicht.

- **4000** – Fehler beim Herunterladen von Serverinformationen vom Listener (unbekannter Grund)

  - **4001** – Server in Listener-Topologie nicht gefunden

    Dieser Fehler tritt auf, wenn der Server erfolgreich eine Verbindung mit dem Listener herstellt, der Server jedoch nicht zur Topologie im Listenercache hinzugefügt wurde. Auflösungsoptionen:

  - Stellen Sie sicher, dass Sie die Anweisungen zum Importieren der Topologie befolgt haben. Siehe [Importieren der Topologie](deploy.md#BKMK_ImportTopology).

  - Wenn sich der Agent auf einem Server befindet, der nicht in der Topologie aufgeführt ist (z. B. die Knoten in einem SQL AlwaysOn-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anweisungen im [Importieren der Topologie](deploy.md#BKMK_ImportTopology) befolgen.

  - **4002** – Ungültiges Listener-Kennwort

    Das verschlüsselte Kennwort, das der Agent zu verwenden versucht, stimmt nicht mit dem Dienstkennwort auf dem Listener selbst überein. Deinstallieren Sie den Agent, und installieren Sie ihn erneut mit dem richtigen Dienstkennwort.

  - **4003** – Zertifikatfingerabdruck stimmt nicht überein

    Der Zertifikatfingerabdruck, der zum Zeitpunkt der Installation an den Agent übergeben wird, stimmt nicht mit dem Fingerabdruck auf dem Zertifikat überein, das der Listener derzeit verwendet, und daher wird die Verbindung verweigert. Deinstallieren Sie den Agent, und installieren Sie ihn mit dem richtigen Zertifikatfingerabdruck erneut.

  - **4004** – Ungültige Antwort oder HttpStatusCode

    Der Listener reagiert nicht mit einem erwarteten Status.

  - Wenn die Verbindung proxied ist, überprüfen Sie die Proxykonfiguration.

  - Überprüfen Sie das StatsMan-Protokoll des Listener-Computers auf Probleme mit der Konfiguration.

  - **4005** – Die Xml-Datei konnte nicht ents serialisiert werden.

    Die Serverinformationen auf dem Listener-Server sind beschädigt, oder es besteht ein Versionskonflikt zwischen dem Agent und den Listener-Computern. Stellen Sie sicher, dass die Versionen übereinstimmen, und überprüfen Sie das Listener-Ereignisprotokoll auf Probleme.

## <a name="listener-events"></a>Listener-Ereignisse
<a name="BKMK_Listener"> </a>

- **10000** – Startfehler Unbekannter Grund (diese sind nicht behebbar, und der Dienst wird dadurch beendet/abgestürzt)

  - **10001** – Konfigurationsproblem

    Im Allgemeinen tritt dies auf, wenn die Datei [listener_install_location]\PerfAgentListener.exe.config manuell geändert wurde und von der Anwendung nicht gelesen werden kann.

  - **10002** – HTTP Listener-Initialisierungsfehler

    Dieses Ereignis wird in der Regel protokolliert, wenn die URL-ACL während der Installation nicht ordnungsgemäß festgelegt wurde oder das SSL-Zertifikat ungültig ist. Stellen Sie sicher, dass das Zertifikat in Ihrer Konfiguration gültig ist. Falls ja, installieren Sie den Listener gemäß den Anweisungen in [Deploy Statistics Manager](deploy.md#BKMK_Deploy) erneut.

  - **10003** – Redis-Fehler

  - **10004** – Fehler bei der Cacheinfrastruktur

  - **10007** — Einstellungen (gespeichert in Redis)

    Der Listener konnte redis nicht kontaktieren oder wohlgeformte Daten aus dem Cache abrufen und konnte nicht starten. Stellen Sie sicher, dass der Redis-Dienst auf dem Server gestartet und ordnungsgemäß konfiguriert ist.

  - **10005** – Abrufen/Analysieren von Serverinformationen

    Die Topologieinformationen im Redis-Cache sind ungültig. Versuchen Sie zunächst, Redis und den Listener neu zu starten. Wenn der Fehler weiterhin auftritt, lesen [Sie "Importieren der Topologie](deploy.md#BKMK_ImportTopology) ", um die Topologiedaten neu zu erstellen.

- **10100** – Redis PING-Ausfall

  - **10101** – Redis PING setzte den Ausfall fort (alle 60 Sekunden)

  - **30100** – Redis PING-Ausfall wiederhergestellt

    Diese werden protokolliert, wenn der Listener keine Verbindung mit Redis herstellen kann. Stellen Sie sicher, dass Redis gestartet wird und die Netzwerkverbindung zwischen Listener und Redis verfügbar ist.

- **10200** – Redis Write-Ausfall

  - **10201** – Redis Schreibausfall fortgesetzt (alle 60 Sekunden)

  - **30100** – Redis Write-Ausfall behoben

    Diese werden protokolliert, wenn der Listener nicht in den Redis-Cache schreiben kann. Stellen Sie sicher, dass Redis gestartet wird und die Netzwerkverbindung zwischen Listener und Redis verfügbar ist.

- **30000** – Erfolgreich gestartet

    Wird jedes Mal protokolliert, wenn der Listener gestartet wird.

- **22000** – Die Initialisierung des Statistics Manager-Agents war erfolgreich.

- **23000** – Die Initialisierung von EventLogQueryManager war erfolgreich (erstmalig oder nach einem Fehler)

- **24000** – Die Initialisierung von serverinfo war erfolgreich (erstmalig oder nach einem Fehler)

- **25000** – Listener ist wieder online, nachdem der Beitrag fehlgeschlagen ist (oder der erste erfolgreiche Beitrag)

- **5000** – Start des Listeners für das Veröffentlichen von Daten offline

- **5001** – Listener ist noch für einen längeren Zeitraum offline

    Diese Ereignisse können für Überwachungs-,Warnungs-/Clearingprobleme nützlich sein.

## <a name="website-issues"></a>Websiteprobleme
<a name="BKMK_Website"> </a>

- Wiederholte Anmeldeaufforderungen in Chrome – dies war ein Fehler, der in Version 1.1 behoben wurde. Achten Sie darauf, dass Sie auf die neueste Version von Statistics Manager aktualisiert haben, wenn im Chrome-Browser wiederholte Anmeldeaufforderungen angezeigt werden. So überprüfen Sie die Version der Website, die Sie ausführen:

  - Öffnen Sie in Explorer (Standardverzeichnis)

  - Klicken Sie mit der rechten Maustaste auf StatsManHubWebSite.dll, und zeigen Sie dessen Eigenschaften an.

  - Wenn ein Computer in der KHI-Querformatansicht oder in der Ansicht "Leistungsindikatordetails" nicht gefunden werden kann, stellen Sie sicher, dass er Mitglied einer Website und eines Pools ist. Andernfalls wird sie in diesen Ansichten nicht angezeigt. Informationen zum Definieren eines Standorts und Pools für einen Server in der Topologie finden Sie unter [Importieren der Topologie](deploy.md#BKMK_ImportTopology).

  - Die Produktversion wird in den Beschreibungsdetails angezeigt.

## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Website"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:

- [Planen von Statistics Manager für Skype for Business Server](plan.md)

- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)

- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)
