---
title: Überwachen Microsoft Teams-Räume Geräte mit Azure Monitor
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: In diesem Artikel wird erläutert, wie Microsoft Teams-Räume Geräte integriert mithilfe von Azure Monitor überwacht werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 38238d4b1d0bc33182f002e7dcf6389028315c48
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880209"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Überwachen Microsoft Teams-Räume Geräte mit Azure Monitor

In diesem Artikel wird erläutert, wie sie Microsoft Teams-Räume auf integrierte Weise mithilfe von Azure Monitor überwachen.

Sie können Azure Monitor so konfigurieren, dass grundlegende Telemetriedaten bereitgestellt werden, die Ihnen bei der Überwachung von Microsoft Teams-Besprechungsräumen-Geräten helfen. Ausführliche Informationen finden Sie unter [Plan Microsoft Teams-Räume management with Azure Monitor](azure-monitor-plan.md) and [Deploy Microsoft Teams-Räume management with Azure Monitor](azure-monitor-deploy.md). Wenn Ihre Überwachungslösung ausgereift ist, können Sie andere Daten und Überwachungsfunktionen verwenden, um eine detailliertere Ansicht der Geräteleistung zu erstellen.

## <a name="understand-the-log-entries"></a>Verstehen der Protokolleinträge

Die folgenden Ereignisbeschreibungen werden alle fünf Minuten in das Feld "Ereignisprotokollbeschreibung" eingefügt, wenn die Microsoft Teams-Räume-App die entsprechenden Informationen im Windows-Ereignisprotokoll aufzeichnet. Der Microsoft Monitoring Agent übergibt diese Datensätze an Log Analytics in Azure Monitor, wodurch sie in das Dashboard analysiert werden, das Sie in ["Bereitstellen Microsoft Teams-Räume Überwachung mit Azure Monitor](azure-monitor-deploy.md)" erstellt haben. Mit dem Dashboard können Sie sich einzelne Protokolleinträge ansehen, um bei Bedarf Handlungsläufe zu ermitteln.

Die Ereignis-IDs 2000 und 3000 geben an, dass Teams-Räume wie erwartet funktioniert. Ereignis-IDs 2001 und 3001 deuten darauf hin, dass ein Problem gefunden wurde. Ereignis-ID 4000 erfordert möglicherweise Eine Aktion, wenn sie häufiger als erwartet angezeigt wird, im Vergleich zu einem von Ihnen festgelegten Basisplan oder mit anderen bereitgestellten Geräten in Ihrer Organisation.

Wenn Sie diese Ereignisbeschreibungen verstehen, werden Sie schnell über Probleme informiert und wissen, wo Ihr Ansatz für die weitere Problembehebung sein kann.

| Ereignis-ID-Ebene&nbsp;&nbsp;|Ereignisverhalten&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Ereignisbeschreibung&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informationen | Dies ist ein Ereignis über einen fehlerfreien Takt. Alle 5 Minuten überprüft Microsoft Teams-Räume, ob es bei Microsoft Teams oder Skype for Business angemeldet ist und über Netzwerk- und Exchange-Konnektivität verfügt. <br> Wenn alle drei Faktoren zutreffen, wird alle 5 Minuten die Ereignis-ID 2000 in das Ereignisprotokoll geschrieben, bis das Gerät offline ist oder mindestens eine der Bedingungen nicht mehr erfüllt ist. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> In diesem Beispiel wurden alle Taktbedingungen erfüllt, und das Microsoft Teams-Räume Gerät wurde als fehlerfrei markiert. Bei dem Auftreten von Fehlern hätte die App stattdessen Ereignis-ID 2001 aufgezeichnet. |
| 2001  <br> Fehler | Dies ist ein App-Fehlerereignis. Alle 5 Minuten überprüft Microsoft Teams-Räume, ob es bei Microsoft Teams oder Skype for Business mit Netzwerk- und Exchange-Konnektivität angemeldet ist. Wenn mindestens ein Faktor nicht zutrifft, wird EventID 2001 alle 5 Minuten in das Ereignisprotokoll geschrieben, bis das Gerät offline ist oder alle Bedingungen erneut erfüllt sind.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Sign in status: Unhealthy. Teams sign in status: Healthy.", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  In diesem Beispiel Microsoft Teams-Räume festgestellt, dass die Netzwerkverbindung fehlerfrei war und die App mit Exchange verbunden war, aber der fett formatierte Teil gibt an, dass die App nicht verbunden ist. Dies kann ein Konfigurationsproblem auf dem Gerät oder Host sein.  <br> <br> Der Netzwerkstatus wird als "Fehlerfrei" oder "Fehlerhaft" angezeigt. Wenn der Status fehlerhaft ist, liegt möglicherweise ein Netzwerkproblem vor, oder das Gerät wurde möglicherweise nicht angeschlossen (sie verfügen dann aber wahrscheinlich auch über Exchange und Microsoft Teams oder Skype for Business Fehler).  <br><br> Der Exchange-Status wird entweder als verbunden oder als einer der folgenden Angezeigt: "Getrennt", "Verbinden", "AutoErmittlungFehler" (der am häufigsten angezeigte Fehler), "GeneralError" oder "ServerVersionNotSupported". Wenn der Status "Verbinden" lautet, warten Sie, bis die nächste Integritätsnachricht gesendet wird. Andere Fehler verweisen das Problem auf einen Administrator mit Erfahrung bei der Lösung von Exchange-Problemen.  <br><br>  Der _Anmeldestatus_/ von _Teams-Anmeldestatus_ (der angibt, dass die App bei Skype for Business oder Teams angemeldet ist) wird als _"Fehlerfrei_" oder "_Fehlerhaft_" angezeigt. Wenn der Status fehlerhaft ist, senden Sie einen Techniker, um dies weiter zu untersuchen. |
| 3000  <br> Informationen | Dieses Ereignis überprüft, ob eine Hardwareüberprüfung ausgeführt wurde und als fehlerfrei befunden wurde. Alle 5 Minuten überprüft Microsoft Teams-Räume, ob konfigurierte Hardwarekomponenten wie Anzeige vor dem Raum, Mikrofon, Lautsprecher und Kamera angeschlossen sind und funktionieren. Wenn alle Komponenten fehlerfrei sind, wird EventID 3000 in das Ereignisprotokoll geschrieben. Dieses Ereignis wird alle 5 Minuten geschrieben, es sei denn, es liegt ein Problem mit einem verbundenen Gerät vor.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> In diesem Beispiel sind bei keiner Hardwareüberprüfung Fehler aufgetreten. Wenn Fehler aufgetreten sind, würde die App stattdessen die Ereignis-ID 3001 aufzeichnen. |
| 3001  <br> Error-Ereignis  | Dies ist ein Hardwarefehlerereignis. Die Microsoft Teams-Räume-App verfügt über einen Prozess, der alle 5 Minuten den Status verbundener Hardwarekomponenten (Vorraum, Mikrofon, Lautsprecher, Kamera) überprüft. Wenn mindestens eine der Komponenten fehlerhaft ist, wird EventID 3001 in das Ereignisprotokoll geschrieben. Dieses Ereignis wird alle 5 Minuten geschrieben, bis das Problem mit dem Gerät behoben ist.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Die Hardware-Peripheriegeräte werden entweder als „Healthy“ (Fehlerfrei) oder „Unhealthy“ (Fehlerhaft) angezeigt.  <br> In diesem Beispiel sind zwei _Front-of-Room-Displays_ konfiguriert, und derzeit ist keine davon verfügbar. Der _Status des Konferenzmikrofons_ ist _fehlerhaft_, was mehrere mögliche Ursachen haben kann. Da mindestens eine Ressource die Überprüfung nicht bestanden hat, wird "ResourceState" als "Ungesund" aufgeführt. Senden Sie einen Techniker, um weitere Untersuchungen zu unternehmen. |
| 4000  <br> Informationen  <br> | Dies ist ein App-Neustartereignis. Immer, wenn die App neu gestartet wird, wird dieses Ereignis im Windows-Fehlerprotokoll protokolliert.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Die App kann aus verschiedenen Gründen neu gestartet werden. Vergleichen Sie die Neustarthäufigkeit von Geräten im selben Gebäude und in verschiedenen Gebäuden. Bedenken Sie bekannte Probleme wie Stromschwankungen und Ausfälle, da dies Hinweise auf Infrastrukturprobleme geben kann.|

## <a name="related-topics"></a>Verwandte Themen
 

[Planen Microsoft Teams-Räume Überwachung mit Azure Monitor](azure-monitor-plan.md)

[Bereitstellen Microsoft Teams-Räume Überwachung mit Azure Monitor](azure-monitor-deploy.md)
