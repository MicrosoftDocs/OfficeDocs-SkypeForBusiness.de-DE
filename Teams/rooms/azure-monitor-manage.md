---
title: Verwalten von Microsoft Teams rooms-Geräten mit Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: In diesem Artikel wird erläutert, wie Sie Microsoft Teams rooms-Geräte auf integrierte Weise mithilfe von Azure Monitor verwalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16105e77c8e66afa00f089d1337984b7e7d9a502
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662050"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Verwalten von Microsoft Teams rooms-Geräten mit Azure Monitor

In diesem Artikel wird erläutert, wie Sie Microsoft Teams rooms-Geräte auf integrierte Weise mithilfe von Azure Monitor verwalten.

Sie können Azure Monitor so konfigurieren, dass Sie grundlegende Telemetrie zur Verwaltung von Skype-Besprechungsraum Geräten bereitstellen. Weitere Informationen finden Sie unter [Planen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-plan.md) und [Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md) . Wenn Ihre Verwaltungslösung ausgereift ist, können Sie zusätzliche Daten-und Verwaltungsfunktionen verwenden, um eine detailliertere Ansicht der Geräteleistung zu erstellen.

## <a name="understand-the-log-entries"></a>Verstehen der Protokolleinträge

Die folgenden Ereignisbeschreibungen werden alle fünf Minuten in das Feld Ereignisprotokoll Beschreibung eingefügt, wenn die Microsoft Teams rooms-APP die entsprechenden Informationen im Windows-Ereignisprotokoll speichert. Der Microsoft-Überwachungs-Agent übergibt diese Datensätze an die Protokollanalyse in Azure Monitor, die Sie in das Dashboard analysiert, das Sie in [Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md)erstellt haben. Mithilfe des Dashboards können Sie einzelne Protokolleinträge anzeigen, um bei Bedarf Aktions Kurse zu ermitteln.

Ereignis-IDs 2000 und 3000 deuten darauf hin, dass das fragliche Gerät wie erwartet funktioniert. Ereignis-IDs 2001 und 3001 deuten darauf hin, dass ein Problem gefunden wurde. Die Ereignis-ID 4000 kann eine Aktion erfordern, wenn Sie häufiger als erwartet angezeigt wird, im Vergleich zu einem von Ihnen festgelegten Basisplan oder anderen bereitgestellten Geräten in Ihrer Organisation.

Wenn Sie diese Ereignisbeschreibungen verstehen, werden Sie schnell über Probleme informiert und wissen, wo Ihr Ansatz für die weitere Problembehebung sein kann.

| Ereignis &nbsp; -ID- &nbsp; Ebene|Ereignis &nbsp; Verhalten&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Ereignis &nbsp; Beschreibung&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informationen | Dies ist ein Ereignis über einen fehlerfreien Takt. Alle 5 Minuten überprüft Microsoft Teams rooms, ob Sie bei Microsoft Teams oder Skype for Business angemeldet sind und über Netzwerk-und Exchange-Konnektivität verfügen. <br> Wenn alle drei Faktoren wahr sind, schreibt Sie die Ereignis-ID 2000 alle 5 Minuten in das Ereignisprotokoll, bis das Gerät offline ist oder mindestens eine der Bedingungen nicht mehr erfüllt ist. | {"Description": "Heartbeat ist fehlerfrei"; "ResourceState": "fehlerfrei"; "OperationName": "Heartbeat", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "Alias <span></span> @contoso. com", "DisplayName": "Anzeigename", "appVersion": "1.0.38.0"; "IPv4Address": "10.10.10.10"; "IPv6": "IP-v6-Adresse"} <br><br> In diesem Beispiel wurden alle Heartbeat-Bedingungen erfüllt, und das Microsoft Teams rooms-Gerät wurde als "fehlerfrei" gekennzeichnet. Bei dem Auftreten von Fehlern hätte die App stattdessen Ereignis-ID 2001 aufgezeichnet. |
| 2001  <br> Fehler | Hierbei handelt es sich um ein App-Fehlerereignis. Alle 5 Minuten überprüft Microsoft Teams rooms, ob Sie bei Microsoft Teams oder Skype for Business mit Netzwerk-und Exchange-Konnektivität angemeldet sind. Wenn mindestens ein Faktor nicht wahr ist, schreibt er die Ereignis-2001 alle 5 Minuten in das Ereignisprotokoll, bis das Gerät offline ist oder alle Bedingungen wieder erfüllt sind.  | {"Description":"Network status : Healthy. Exchange status : Connected. **Signin status: Unhealthy.** "," ResourceState ":" ungesund ";" OperationName ":" Heartbeat "," OperationResult ":" Fehler "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.693 "," Alias ":" "," DisplayName ":" Anzeige Name "," appVersion ":" 1.0.38.0 ";" IPv4Address ":" 10.10.10.10 ";" IPv6 ":" IP-v6-Adresse "} <br><br>  In diesem Beispiel wurde in Microsoft Teams-Räumen festgestellt, dass die Netzwerkverbindung fehlerfrei war und die APP mit Exchange verbunden war, der Fett gedruckte Teil jedoch angibt, dass die APP nicht verbunden ist. Dies kann ein Konfigurationsproblem auf dem Gerät oder dem Host sein.  <br> <br> Der Netzwerkstatus wird entweder als "gesund" oder "unschädlich" angezeigt. Wenn der Status fehlerhaft ist, haben Sie möglicherweise ein Netzwerkproblem, oder das Gerät wurde nicht angeschlossen (aber Sie hätten wahrscheinlich auch Exchange-und Microsoft Teams oder Skype for Business-Fehler).  <br><br> Der Exchange-Status wird entweder als verbunden oder als einer der folgenden Optionen angezeigt: getrennt, Verbindung, AutodiscoveryError (der am häufigsten angezeigte Fehler), GeneralError oder ServerVersionNotSupported. Wenn der Status eine Verbindung herstellt, warten Sie, bis die nächste Integritäts Meldung gesendet wird, für andere Fehler verweisen Sie das Problem an einen Administrator mit der Erfahrung bei der Lösung von Exchange-Problemen.  <br><br>  Der SignIn-Status (der angibt, dass die App angemeldet ist) wird als "fehlerfrei" oder "unschädlich" angezeigt. Wenn der Status fehlerhaft ist, senden Sie einen Techniker, um weiter zu untersuchen. |
| 3000  <br> Informationen | Dieses Ereignis überprüft, ob eine Hardwareüberprüfung ausgeführt wurde und als fehlerfrei festgestellt wurde. Alle 5 Minuten Microsoft Teams-Räume überprüft, ob konfigurierte Hardwarekomponenten wie Front-Room-Anzeige, Mikrofon, Lautsprecher und Kamera angeschlossen sind und funktionieren. Wenn alle Komponentenfehler frei sind, schreibt Sie die Ereignis 3000 in das Ereignisprotokoll. Dieses Ereignis wird alle 5 Minuten geschrieben, es sei denn, es liegt ein Problem mit einem verbundenen Gerät vor.  <br> | {"Description": "HardwareCheckEngine ist fehlerfrei."; "ResourceState": "fehlerfrei"; "OperationName": "HardwareCheckEngine", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "Alias <span></span> @contoso. com", "DisplayName": "Anzeige Name", "appVersion": "1.0.38.0"; "IPv4Address": "10.10.10.10"; "IPv6": "IP-v6-Adresse"}  <br><br> In diesem Beispiel sind bei keiner Hardwareüberprüfung Fehler aufgetreten. Wenn Fehler aufgetreten sind, zeichnet die APP stattdessen die Ereignis-ID 3001 auf. |
| 3001  <br> Error-Ereignis  | Hierbei handelt es sich um ein Hardwarefehler Ereignis. Die Microsoft Teams rooms-App verfügt über einen Prozess, der alle 5 Minuten den Zustand der verbundenen Hardwarekomponenten (Front of room, Mikrofon, Lautsprecher, Kamera) überprüft. Wenn eine oder mehrere Komponentenfehler Haft sind, schreibt Sie die Ereignis 3001 in das Ereignisprotokoll. Dieses Ereignis wird alle 5 Minuten geschrieben, bis das Problem mit dem Gerät behoben ist.   | {"Description": " **Front of room Display Status: ungesund.** Configured display count is 2. Real display count is 0. **Conference Microphone status : Unhealthy.** Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera Status: Healthy. "," ResourceState ":" unhealthd "," OperationName ":" HardwareCheckEngine "," OperationResult ":" Fail "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.1198 "," Alias ":" Alias <span></span> @contoso. com ";" DisplayName ":" Yosemite-Konferenzraum "," appVersion ":" 2.0.58.0 ";" IPv4Address ":" 10.10.10.10 ";" IPv6 ":" IPv6 ";" IPv4Address2 ":" 10.10.10.10 "} <br><br>  Die Hardware-Peripheriegeräte werden entweder als „Healthy“ (Fehlerfrei) oder „Unhealthy“ (Fehlerhaft) angezeigt. <br> In diesem Beispiel sind zwei Front-of-room-anzeigen konfiguriert, die derzeit nicht verfügbar sind. Der Status des Konferenz Mikrofons ist unschädlich, was mehrere mögliche Ursachen haben kann. Da mindestens eine Ressource die Prüfung nicht bestanden hat, wird die ResourceState als fehlerhaft aufgelistet. Senden Sie einen Techniker zur weiteren Untersuchung. |
| 4000  <br> Informationen  <br> | Dies ist ein App-Neustartereignis. Immer, wenn die App neu gestartet wird, wird dieses Ereignis im Windows-Fehlerprotokoll protokolliert.  <br> | {"Description": "App-Neustarts."; "ResourceState": "fehlerfrei", "OperationName": "Restart", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "Alias": "Alias <span></span> @Domain. com"; "DisplayName": "Anzeige Name"; "appVersion": "1.0.38.0"; "IPv4Address": "10.10.10.10"; "IPv6": "IP-v6-Adresse"} <br><br> Die APP kann aus verschiedenen Gründen neu gestartet werden. Vergleichen Sie die Häufigkeit des Neustarts von Geräten im gleichen Gebäude und in verschiedenen Gebäuden. Beachten Sie bekannte Probleme wie Leistungsschwankungen und-Ausfälle, da dies Anhaltspunkte für Infrastrukturprobleme liefern kann.|

## <a name="related-topics"></a>Verwandte Themen
 

[Planen der Verwaltung von Microsoft Teams Rooms mit Azure Monitor](azure-monitor-plan.md)

[Bereitstellen von Microsoft Teams rooms Management mit Azure Monitor](azure-monitor-deploy.md)
