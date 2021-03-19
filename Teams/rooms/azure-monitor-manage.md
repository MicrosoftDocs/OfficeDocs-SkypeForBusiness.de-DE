---
title: Verwalten von Microsoft Teams Rooms-Geräten mit Azure Monitor
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
description: In diesem Artikel wird erläutert, wie Sie Microsoft Teams Rooms-Geräte mithilfe von Azure Monitor integriert verwalten.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41375c313940099b6ed6e102e2452290e0817bec
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874765"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Verwalten von Microsoft Teams Rooms-Geräten mit Azure Monitor

In diesem Artikel wird erläutert, wie Sie Microsoft Teams Rooms-Geräte mithilfe von Azure Monitor integriert verwalten.

Sie können Azure Monitor so konfigurieren, dass grundlegende Telemetriedaten bereitgestellt werden, damit Sie Microsoft Teams-Besprechungsraumgeräte verwalten können. Weitere Informationen finden Sie unter Planen der Verwaltung von [Microsoft Teams-Räumen mit Azure Monitor](azure-monitor-plan.md) und Bereitstellen der Verwaltung von Microsoft [Teams-Räumen](azure-monitor-deploy.md) mit Azure Monitor. Wenn Ihre Verwaltungslösung reift, können Sie zusätzliche Daten- und Verwaltungsfunktionen verwenden, um eine detailliertere Ansicht der Geräteleistung zu erstellen.

## <a name="understand-the-log-entries"></a>Verstehen der Protokolleinträge

Die folgenden Ereignisbeschreibungen werden alle fünf Minuten in das Feld "Ereignisprotokollbeschreibung" eingefügt, wenn die Microsoft Teams Rooms-App die entsprechenden Informationen im Windows-Ereignisprotokoll zeichnet. Der Microsoft Monitoring Agent übergibt diese Datensätze an die Protokollanalyse in Azure Monitor, die sie in dem Dashboard analysiert, das Sie unter Bereitstellen der Verwaltung von [Microsoft Teams-Räumen mit Azure Monitor erstellt haben.](azure-monitor-deploy.md) Mit dem Dashboard können Sie einzelne Protokolleinträge anzeigen, um bei Bedarf Aktionskurse zu ermitteln.

Die Ereignis-IDs 2000 und 3000 geben an, dass das in Frage kommende Gerät wie erwartet funktioniert. Die Ereignis-IDs 2001 und 3001 deuten darauf hin, dass ein Problem gefunden wurde. Die Ereignis-ID 4000 erfordert möglicherweise eine Aktion, wenn sie häufiger als erwartet angezeigt wird, im Vergleich zu einem von Ihnen festgelegten Basisplan oder anderen bereitgestellten Geräten in Ihrer Organisation.

Wenn Sie diese Ereignisbeschreibungen verstehen, werden Sie schnell über Probleme informiert und wissen, wo Ihr Ansatz für die weitere Problembehebung sein kann.

| &nbsp; &nbsp; Ereignis-ID-Ebene|&nbsp;Ereignisverhalten&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|&nbsp;Ereignisbeschreibung&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informationen | Dies ist ein Ereignis über einen fehlerfreien Takt. Alle 5 Minuten überprüft Microsoft Teams Rooms, ob es bei Microsoft Teams oder Skype for Business angemeldet ist und über Netzwerk- und Exchange-Konnektivität verfügt. <br> Wenn alle drei Faktoren zutreffen, schreibt sie alle 5 Minuten ereignis-ID 2000 in das Ereignisprotokoll, bis das Gerät offline ist oder eine oder mehrere bedingungen nicht mehr erfüllt sind. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> In diesem Beispiel wurden alle Herzschlagbedingungen erfüllt, und das Microsoft Teams Rooms-Gerät wurde als fehlerfrei gekennzeichnet. Bei dem Auftreten von Fehlern hätte die App stattdessen Ereignis-ID 2001 aufgezeichnet. |
| 2001  <br> Fehler | Dies ist ein App-Fehlerereignis. Alle 5 Minuten überprüft Microsoft Teams Rooms, ob es bei Microsoft Teams oder Skype for Business mit Netzwerk- und Exchange-Konnektivität angemeldet ist. Wenn ein oder mehrere Faktoren nicht zutreffen, schreibt es Alle 5 Minuten EventID 2001 in das Ereignisprotokoll, bis das Gerät offline ist oder alle Bedingungen erneut erfüllt sind.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  In diesem Beispiel hat Microsoft Teams Rooms festgestellt, dass die Netzwerkverbindung fehlerfrei war und die App mit Exchange verbunden war. Der fett formatierte Teil gibt jedoch an, dass die App nicht verbunden ist. Dies kann ein Konfigurationsproblem auf dem Gerät oder Host sein.  <br> <br> Der Netzwerkstatus wird entweder als "Fehlerfrei" oder "Fehlerhaft" angezeigt. Wenn der Status fehlerhaft ist, liegt möglicherweise ein Netzwerkproblem vor, oder das Gerät wurde möglicherweise getrennt (aber dann hätten Sie wahrscheinlich auch Exchange- und Microsoft Teams- oder Skype for Business-Fehler).  <br><br> Der Exchange-Status wird entweder als verbunden oder als eine der folgenden Angezeigt: Getrennt, Verbinden, AutoErmittlungFehler (am häufigsten angezeigter Fehler), GeneralError oder ServerVersionNotSupported. Wenn der Status Verbinden lautet, warten Sie, bis die nächste Integritätsnachricht gesendet wird, da andere Fehler das Problem an einen Administrator verweisen, der Erfahrungen mit der Lösung von Exchange-Problemen hat.  <br><br>  Der _Anmeldestatus_ (der angibt, dass die App angemeldet ist) wird entweder _als "Fehlerfrei"_ oder _"Fehlerhaft" angezeigt._ Wenn der Status fehlerhaft ist, senden Sie einen Techniker, um weitere Untersuchungen zu erhalten. |
| 3000  <br> Informationen | Dieses Ereignis überprüft, ob eine Hardwareüberprüfung ausgeführt und als fehlerfrei festgestellt wurde. Alle 5 Minuten überprüft Microsoft Teams Rooms, ob konfigurierte Hardwarekomponenten wie Vorraumanzeige, Mikrofon, Lautsprecher und Kamera angeschlossen sind und funktionieren. Wenn alle Komponenten fehlerfrei sind, wird EventID 3000 in das Ereignisprotokoll geschrieben. Dieses Ereignis wird alle 5 Minuten geschrieben, es sei denn, es liegt ein Problem mit einem verbundenen Gerät vor.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> In diesem Beispiel sind bei keiner Hardwareüberprüfung Fehler aufgetreten. Wenn Fehler aufgetreten sind, würde die App stattdessen die Ereignis-ID 3001 aufzeichnen. |
| 3001  <br> Fehlerereignis  | Dies ist ein Hardwarefehlerereignis. Die Microsoft Teams Rooms-App verfügt über einen Prozess, der den Zustand der verbundenen Hardwarekomponenten (vor dem Raum, Mikrofon, Lautsprecher, Kamera) alle 5 Minuten überprüft. Wenn eine oder mehrere Komponenten fehlerhaft sind, schreibt sie EventID 3001 in das Ereignisprotokoll. Dieses Ereignis wird alle 5 Minuten geschrieben, bis das Problem mit dem Gerät behoben ist.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Die Hardware-Peripheriegeräte werden entweder als „Healthy“ (Fehlerfrei) oder „Unhealthy“ (Fehlerhaft) angezeigt.  <br> In diesem Beispiel sind  zwei Vorraumanzeigen konfiguriert, die zurzeit nicht verfügbar sind. Der _Status des Konferenzmikrofons_ _ist fehlerhaft,_ was mehrere mögliche Ursachen haben kann. Da mindestens eine Ressource die Überprüfung nicht bestanden hat, wird der ResourceState als Fehlerhaft aufgelistet. Senden Sie einen Techniker, um weitere Untersuchungen zu untersuchen. |
| 4000  <br> Informationen  <br> | Dies ist ein App-Neustartereignis. Immer, wenn die App neu gestartet wird, wird dieses Ereignis im Windows-Fehlerprotokoll protokolliert.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Die App kann aus verschiedenen Gründen neu gestartet werden. Vergleichen Sie die Neustarthäufigkeit von Geräten im gleichen Gebäude und in verschiedenen Gebäuden. Beachten Sie bekannte Probleme wie Stromschwankungen und -ausfälle, da dies Hinweise auf Infrastrukturprobleme liefern kann.|

## <a name="related-topics"></a>Verwandte Themen
 

[Planen der Verwaltung von Microsoft Teams-Räumen mit Azure Monitor](azure-monitor-plan.md)

[Bereitstellen der Verwaltung von Microsoft Teams-Räumen mit Azure Monitor](azure-monitor-deploy.md)
