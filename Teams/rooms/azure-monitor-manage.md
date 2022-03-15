---
title: Überwachen Microsoft Teams-Räume mit Azure Monitor
ms.author: czawideh
author: cazawideh
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
description: In diesem Artikel wird erläutert, wie Sie Microsoft Teams-Räume mit Azure Monitor integriert überwachen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fa0aeac082a31ea603afda7f0643ef961b127619
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504052"
---
# <a name="monitor-microsoft-teams-rooms-devices-with-azure-monitor"></a>Überwachen Microsoft Teams-Räume mit Azure Monitor

In diesem Artikel wird erläutert, wie Sie Microsoft Teams-Räume mit Azure Monitor integriert überwachen.

Sie können Den Azure Monitor so konfigurieren, dass er einfache Telemetrie für die Überwachung ihrer Microsoft Teams von Besprechungsräumen bietet. Weitere [Informationen finden Microsoft Teams-Räume](azure-monitor-plan.md) Unter Planen Microsoft Teams-Räume Verwaltung von Azure Monitor und Bereitstellen Microsoft Teams-Räume [mit Azure Monitor](azure-monitor-deploy.md). Wenn Ihre Überwachungslösung reift, können Sie zusätzliche Daten- und Überwachungsfunktionen verwenden, um eine detailliertere Ansicht der Geräteleistung zu erstellen.

## <a name="understand-the-log-entries"></a>Verstehen der Protokolleinträge

Die folgenden Ereignisbeschreibungen werden alle fünf Minuten in das Beschreibungsfeld des Ereignisprotokolls eingefügt, wenn die Microsoft Teams-Räume-App die entsprechenden Informationen im Ereignisprotokoll Windows zeichnet. Die Microsoft Monitoring Agent diese Einträge an die Protokollanalyse in Azure Monitor weiter, wodurch sie in dem Dashboard analysiert werden, das Sie unter Bereitstellen [Microsoft Teams-Räume Überwachung mit Azure Monitor erstellt haben](azure-monitor-deploy.md). Mit dem Dashboard können Sie einzelne Protokolleinträge anzeigen, um bei Bedarf die erforderlichen Schritte zu ermitteln.

Die Ereignis-IDs 2000 und 3000 geben an, dass Teams-Räume wie erwartet funktioniert. Die Ereignis-IDs 2001 und 3001 geben an, dass ein Problem gefunden wurde. Die Ereignis-ID 4000 erfordert möglicherweise eine Aktion, wenn diese häufiger als erwartet angezeigt wird, im Vergleich zu einem von Ihnen festgelegten Basiswert oder anderen bereitgestellten Geräten in Ihrer Organisation.

Wenn Sie diese Ereignisbeschreibungen verstehen, werden Sie schnell über Probleme informiert und wissen, wo Ihr Ansatz für die weitere Problembehebung sein kann.

| EventIDlevel&nbsp;&nbsp;|Eventbehavior&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|EventDescription&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informationen | Dies ist ein Ereignis über einen fehlerfreien Takt. Alle 5 Minuten überprüft Microsoft Teams-Räume, ob er bei einem Microsoft Teams oder Skype for Business angemeldet ist und netzwerk- und Exchange ist. <br> Wenn alle drei Faktoren zutreffen, werden die Ereignis-ID 2000 alle 5 Minuten in das Ereignisprotokoll geschrieben, bis das Gerät offline ist oder mindestens eine der Bedingungen nicht mehr erfüllt ist. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> In diesem Beispiel wurden alle Heartbeat-Bedingungen erfüllt, und Microsoft Teams-Räume Gerät wurde als fehlerfrei markiert. Bei dem Auftreten von Fehlern hätte die App stattdessen Ereignis-ID 2001 aufgezeichnet. |
| 2001  <br> Fehler | Dies ist ein App-Fehlerereignis. Alle 5 Minuten überprüft Microsoft Teams-Räume, ob er bei einem Microsoft Teams oder Skype for Business netzwerk- und Exchange angemeldet ist. Wenn mindestens ein Faktor nicht zutrifft, wird EventID 2001 alle 5 Minuten in das Ereignisprotokoll geschrieben, bis das Gerät offline ist oder alle Bedingungen erneut erfüllt sind.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  In diesem Beispiel hat Microsoft Teams-Räume ermittelt, dass die Netzwerkverbindung fehlerfrei war und die App mit Exchange verbunden war. Der fett formatierte Teil weist jedoch darauf hin, dass die App nicht verbunden ist. Dies kann ein Konfigurationsproblem auf dem Gerät oder Host sein.  <br> <br> Der Netzwerkstatus wird entweder als fehlerfrei oder fehlerhaft angezeigt. Wenn der Status fehlerhaft ist, liegt möglicherweise ein Netzwerkproblem vor, oder das Gerät wurde vom Netzkabel getrennt (dann haben Sie wahrscheinlich auch Exchange- und Microsoft Teams- oder Skype for Business-Fehler).  <br><br> Der Exchange wird entweder als Verbunden oder als eine der folgenden Optionen angezeigt: Getrennt, Verbindung herstellen, AutoErmittlungFehler (der am häufigsten angezeigte Fehler), GeneralError oder ServerVersionNotSupported. Wenn der Status Verbindung wird verbunden lautet, warten Sie, bis die nächste Integritätsnachricht gesendet wird, damit das Problem durch andere Fehler an einen Administrator mit Erfahrung beim Beheben von Exchange wird.  <br><br>  Der _Anmeldestatus_ (der angibt, dass die App angemeldet ist) wird entweder als fehlerfrei _oder_ _als fehlerhaft angezeigt_. Wenn der Status fehlerhaft ist, senden Sie einen Techniker zur weiteren Untersuchung. |
| 3000  <br> Informationen | Dieses Ereignis überprüft, ob eine Hardwareüberprüfung ausgeführt wurde und als fehlerfrei herausgefunden wurde. Alle 5 Microsoft Teams-Räume überprüft, ob konfigurierte Hardwarekomponenten wie vor der Raumanzeige, Mikrofon, Lautsprecher und Kamera angeschlossen sind und funktionieren. Wenn alle Komponenten fehlerfrei sind, wird EventID 3000 in das Ereignisprotokoll geschrieben. Dieses Ereignis wird alle 5 Minuten geschrieben, es sei denn, es liegt ein Problem mit einem verbundenen Gerät vor.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> In diesem Beispiel sind bei keiner Hardwareüberprüfung Fehler aufgetreten. Wenn Fehler aufgetreten sind, würde die App stattdessen die Ereignis-ID 3001 aufzeichnen. |
| 3001  <br> Fehlerereignis  | Dies ist ein Hardwarefehlerereignis. Die Microsoft Teams-Räume-App verfügt über einen Prozess, mit dem die Integrität verbundener Hardwarekomponenten (vor dem Raum, Mikrofon, Lautsprecher, Kamera) alle 5 Minuten überprüft wird. Wenn eine oder mehrere Komponenten fehlerhaft sind, wird EventID 3001 in das Ereignisprotokoll geschrieben. Dieses Ereignis wird alle 5 Minuten geschrieben, bis das Problem mit dem Gerät behoben ist.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Die Hardware-Peripheriegeräte werden entweder als „Healthy“ (Fehlerfrei) oder „Unhealthy“ (Fehlerhaft) angezeigt.  <br> In diesem Beispiel sind zwei _Front-of-Room-Anzeigen_ konfiguriert, und derzeit ist keine dieser Anzeigen verfügbar. Der _Status des Konferenzmikrofons_ _ist fehlerhaft_, und dies kann mehrere mögliche Ursachen haben. Da mindestens eine Ressource die Überprüfung nicht bestanden hat, ist ResourceState als fehlerhaft aufgelistet. Senden Sie einen Techniker zur weiteren Untersuchung. |
| 4000  <br> Informationen  <br> | Dies ist ein App-Neustartereignis. Immer, wenn die App neu gestartet wird, wird dieses Ereignis im Windows-Fehlerprotokoll protokolliert.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> Die App kann aus verschiedenen Gründen neu gestartet werden. Vergleichen Sie die Neustarthäufigkeit von Geräten im gleichen Gebäude und in verschiedenen Gebäuden. Beachten Sie bekannte Probleme wie Leistungsschwankungen und Fehler, da dies Hinweise auf Infrastrukturprobleme geben kann.|

## <a name="related-topics"></a>Verwandte Themen
 

[Planen Microsoft Teams-Räume der Überwachung mit Azure Monitor](azure-monitor-plan.md)

[Bereitstellen Microsoft Teams-Räume Überwachungsüberwachung mit Azure Monitor](azure-monitor-deploy.md)
