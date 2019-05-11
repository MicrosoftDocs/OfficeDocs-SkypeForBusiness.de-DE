---
title: Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Zusammenfassung: Lesen Sie dieses Thema, um die Bereitstellung von Statistiken Manager für Skype für Business Server zu beheben.'
ms.openlocfilehash: dbdf536b43006f5619330e93de0b8aba5024a1ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906683"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server
 
**Zusammenfassung:** Lesen Sie dieses Thema, um die Bereitstellung von Statistiken Manager für Skype für Business Server zu beheben.
  
In diesem Thema wird beschrieben, wie für die Problembehandlung bei der Bereitstellung von Statistiken-Manager mit der Beschreibung der Ereignisse, die möglicherweise im Ereignisprotokoll Anwendung angezeigt, und die entsprechenden Aktionen, die Sie ergreifen können, das Ereignis zu beheben. Dieses Thema enthält die folgenden Abschnitte:
  
- [Agent-Ereignisse](troubleshoot.md#BKMK_Agent)
    
- [Listener-Ereignisse](troubleshoot.md#BKMK_Listener)
    
- [Websiteprobleme](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Agent-Ereignisse
<a name="BKMK_Agent"> </a>

- **1000** – Prozessor-Limiter (Auftragsobjekt) kann nicht eingerichtet werden – unbekannte Ursache
    
- **1001** – Prozess eingeschränkt ist nicht zulässig für den Prozess (möglicherweise bereits in einem Auftrag-Objekt)
    
    Der Agent wird innerhalb eines Windows-Auftragsobjekts ausgeführt, um automatisch dessen Speicherbedarf zu begrenzen. Falls der Agent nicht gestartet wird und diese Ereigniseinträge im Ereignisprotokoll zu finden sind, kann das Auftragsobjekt auf dem Server nicht instanziiert werden. Um das Problem zu umgehen, kann die obere Speicherbegrenzung aufgehoben werden, indem ein Wert in der Konfigurationsdatei geändert wird:
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Suchen Sie nach "MaxProcessMemoryMB", und ändern Sie den Wert auf "0" wie dargestellt:
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Wenn diese Änderung vorgenommen wurde, wird der Agent im Allgemeinen weiterhin nutzen \< 100 MB Arbeitsspeicher, jedoch es nicht erzwingen auf 300 MB beschränkt werden wie der Standardwert ist. Wenn diese Änderung vorgenommen wird, ist zu empfehlen, den Speicherverbrauch genau im Auge zu behalten, um sicherzustellen, dass der Agent nicht sehr viel Speicher auf seinem Hostcomputer in Anspruch nimmt. 
  
- **2000** – Fehler bei der Clientinitialisierung
    
- **2001** – Unter keiner Quell-IP konnte eine Verbindung mit dem Dienst hergestellt werden.
    
    Wenn der Agent keine Verbindung zum Listener-Computer herstellen kann, überprüfen Sie die folgenden Punkte:
    
1. Stellen Sie sicher, dass der Listener-Dienst auf dem Listener-Computer ausgeführt wird. Ist das nicht der Fall, stellen Sie sicher, dass Redis auf diesem Server ausgeführt wird, und starten Sie anschließend den Listener-Dienst neu.
    
    Überprüfen Sie das Ereignisprotokoll Statistiken-Manager auf dem Computer Listener, um sicherzustellen, dass es sind keine Probleme mit den Statistiken Manager Listener-Dienst selbst.
    
2. Verwenden Sie ein Connectivity Tool wie Telnet, um die Verbindung vom Agent- zum Listener-Computer auf dem richtigen Port zu überprüfen.
    
    Ist diese Verbindung nicht gegeben, stellen Sie sicher, dass die Firewallregel für eingehenden Verkehr für die Art von Netzwerk aktiviert ist, mit dem der Listener-Computer verbunden ist (privat/öffentlich/Domäne). Wenn der Listener-Computer nicht Mitglied einer Domäne ist, im Netzwerk werden möglicherweise als öffentliche aufgelistet und in diesem Fall die Firewall-Regeln mit Statistiken Manager installiert standardmäßig nicht angewendet werden.
    
- **4000** – Fehler beim Herunterladen von Serverinformationen vom Listener-Computer (unbekannte Ursache)
    
  - **4001** – Server in Listener-Topologie nicht gefunden
    
    Dieser Fehler tritt auf, wenn der Server erfolgreich eine mit dem Listener Verbindung, aber der Server nicht auf die Topologie in der Listener Cache hinzugefügt wurde. Lösungsmöglichkeiten:
    
  - 	Stellen Sie sicher, dass Sie die Anweisungen für den Import der Topologie befolgt haben. Siehe auch [Import the topology](deploy.md#BKMK_ImportTopology).   
    
  - Wenn sich der Agent auf einem Server befindet, der in der Topologie nicht aufgeführt ist (zum Beispiel die Knoten in einem SQL-„AlwaysOn“-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anleitungen in [Import the topology](deploy.md#BKMK_ImportTopology) ausführen.
    
  - **4002** – Ungültiges Listener-Kennwort
    
    Das verschlüsselte Kennwort, das der Agent zu verwenden versucht, stimmt nicht mit dem Servicekennwort auf dem Listener selbst überein. Deinstallieren Sie den Agent und installieren Sie ihn neu, indem Sie dabei das richtige Servicekennwort verwenden.
    
  - **4003** – Zertifikatfingerabdruck-Konflikt
    
    Den Fingerabdruck des Zertifikats an den Agent bei der Installation angegeben nicht übereinstimmt, die der Fingerabdruck des Zertifikats dem Listener derzeit verwendet wird und daher die Verbindung werden abgelehnt. Deinstallieren Sie den Agent, und installieren Sie ihn mithilfe des richtigen Zertifikatfingerabdrucks neu.
    
  - **4004** – Ungültige Antwort oder HttpStatusCode ungültig
    
    Der Listener reagiert nicht mit einem erwarteten Status.   
    
  - Läuft die Verbindung über einen Proxy, überprüfen Sie die Proxy-Konfiguration.
    
  - Überprüfen des Computers Listener StatsMan Protokoll bei Problemen mit der Konfiguration.
    
  - **4005** – XML-Deserialisierung nicht möglich
    
    Die Serverinformationen auf dem Listener-Server sind beschädigt oder es gibt möglicherweise einen Versionskonflikt zwischen dem Agent und dem Listener-Computer. Stellen Sie sicher, dass die Versionen übereinstimmen und überprüfen Sie das Listener-Ereignisprotokoll auf Probleme.
    
## <a name="listener-events"></a>Listener-Ereignisse
<a name="BKMK_Listener"> </a>

- **10000** – Startfehler aus unbekannten Gründen (nicht zu beheben; in der Folge stellt der Dienst die Arbeit ein oder stürzt ab)
    
  - **10001** – Konfigurationsproblem
    
    Im Allgemeinen tritt dieses Problem auf, wenn die Datei [listener_install_location]\PerfAgentListener.exe.config von Hand geändert wurde und von der Anwendung nicht mehr gelesen werden kann.
    
  - **10002** – HTTP-Listener-Initialisierungsfehler
    
    Dieses Ereignis wird im Allgemeinen protokolliert, wenn die URL-ACL bei der Installation nicht ordnungsgemäß eingerichtet wurde oder wenn das SSL-Zertifikat ungültig ist. Stellen Sie sicher, dass das Zertifikat in Ihrer Konfiguration gültig ist. Ist das der Fall, installieren Sie den Listener gemäß den Anweisungen in [Deploy Statistics Manager](deploy.md#BKMK_Deploy) neu.
    
  - **10003** – Redis-Fehler
    
  - **10004** – Cache-Infrastruktur-Fehler
    
  - **10007** – Einstellungen (in Redis gespeichert)
    
    Der Listener konnte keinen Kontakt zu Redis herstellen oder keine wohlgeformten Daten aus dem Cache abrufen und deshalb nicht gestartet werden. Stellen Sie sicher, dass der Redis-Dienst auf dem Server gestartet und ordnungsgemäß konfiguriert ist.
    
  - **10005** – Abrufen/Analysieren von Serverinformationen
    
    Die Topologieinformationen im Redis-Cache sind ungültig. Versuchen Sie zunächst, Redis und den Listener neu zu starten. Wenn der Fehler weiterhin besteht, schlagen Sie unter [Import the topology](deploy.md#BKMK_ImportTopology) nach, um die Topologiedaten neu zu erstellen.
    
- **10100** – Redis-PING-Ausfall
    
  - **10101** – Fortgesetzter Redis-PING-Ausfall (alle 60 Sekunden)
    
  - **30100** – Redis-PING-Ausfall wiederhergestellt
    
    Diese Fehler werden protokolliert, wenn der Listener keine Verbindung zu Redis herstellen kann. Stellen Sie sicher, dass Redis gestartet ist und dass Netzwerkkonnektivität zwischen Listener und Redis zur Verfügung steht.
    
- **10200** – Redis-Write-Ausfall
    
  - **10201** – Fortgesetzter Redis-Write-Ausfall (alle 60 Sekunden)
    
  - **30100** – Redis-Write-Ausfall gelöst
    
    Diese Fehler werden protokolliert, wenn der Listener keine Verbindung zum Redis-Cache herstellen kann. Stellen Sie sicher, dass Redis gestartet ist und dass Netzwerkkonnektivität zwischen Listener und Redis zur Verfügung steht.
    
- **30000** – Erfolgreich gestartet
    
    Wird bei jedem Start des Listeners protokolliert.
    
- **22000** – Initialisierung von Statistiken Manager-Agent erfolgreich abgeschlossen wurde.
    
- **23000** – Initialisierung von „EventLogQueryManager“ war erfolgreich (beim ersten Mal oder nach Fehlversuch).
    
- **24000** – Initialisierung von „serverinfo“ war erfolgreich (beim ersten Mal oder nach Fehlversuch).
    
- **25000** – Listener ist nach Sendefehlversuch (oder erstem erfolgreichen Senden) wieder online.
    
- **5000** – Offlinestart des Listeners für das Senden von Daten
    
- **5001** – Listener ist für längere Zeit weiterhin offline.
    
    Diese Ereignisse können bei Überwachungs-/Benachrichtigungs-/Löschproblemen nützlich sein.
    
## <a name="website-issues"></a>Websiteprobleme
<a name="BKMK_Website"> </a>

- Sich wiederholende Anmeldung, eingabeaufforderungen in Chrome – dies wurde ein Fehler, der in Version 1.1 aufgelöst wurde. Stellen Sie sicher, dass Sie auf die neueste Version von Statistiken Manager aktualisiert haben, wenn Sie wiederholt Anmeldung Anweisungen im Chrome-Browsers angezeigt werden. Folgendermaßen können Sie feststellen, welche Version der Website Sie ausführen:
    
  - 	Öffnen Sie im Datei-Explorer (Standardverzeichnis).
    
  - Klicken Sie mit der rechten Maustaste auf „StatsManHubWebSite.dll“ und lassen Sie die entsprechenden Eigenschaften anzeigen.
    
  - Wenn ein Computer in der KHI-Querformatansicht oder der Zählerangabenansicht nicht gefunden werden kann, stellen Sie sicher, dass der Computer Mitglied einer Website und eines Pools ist. Ist er das nicht, taucht er in diesen Ansichten auch nicht auf. Mehr über die Definition einer Website und eines Pools für einen Server in der Topologie erfahren Sie unter [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - Die Produktversion wird unter den Beschreibungsangaben angezeigt.
    
## <a name="for-more-information"></a>Weitere Informationen
<a name="BKMK_Website"> </a>

Weitere Informationen finden Sie unter den folgenden Themen:
  
- [Planen von Statistics Manager für Skype for Business Server](plan.md)
    
- [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md)
    
- [Aktualisieren von Statistics Manager für Skype for Business Server](upgrade.md)
