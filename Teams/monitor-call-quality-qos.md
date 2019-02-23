---
title: Implementieren von QoS und Überwachung der Anrufanalyse in Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: Verwenden Sie Quality of Service (QoS) Einstellungen und dann Analytics aufrufen und Aufrufen Qualitätsdashboard in Microsoft-Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 097426e60ebcd141d1c8375343509db5607c50e2
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205771"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementieren Sie QoS und Monitor Anrufqualität in Microsoft-Teams

## <a name="get-started"></a>Erste Schritte

Wenn Ihre Benutzer beginnen, Teams zum Tätigen von Anrufen und Aufbewahren von Besprechungen verwenden, können sie ein Anrufer VoIP Informationen zum Unterteilen von innerhalb und außerhalb eines Anrufs Zerkleinern oder meeting auftreten. Video Mai Shared einfrieren oder in Pixel auflösen, oder schlagen fehl. Dies ist aufgrund der IP-Pakete, die VoIP und video-Datenverkehr Überlastung des Netzwerks auftreten und eingehenden außerhalb der Reihenfolge oder überhaupt nicht darstellen. Es gibt Methoden, um diese Probleme zu identifizieren, wenn sie Offenlegen und zu verhindern, ihre Rückgabe in erster Linie Quality of Service (QoS dass).

**Quality of Service (QoS)** ist eine Möglichkeit zum Echtzeit Netzwerkdatenverkehr (wie VoIP oder Video-Streams) zulassen, ist Beachtung von netzwerkverzögerungen "in der Zeile vor den Datenverkehr, der weniger (wie eine neue app, herunterladen, wobei eine zusätzliche Sekunde bis zu laden vertraulicher ist Ausschneiden" ist keine große Sache). QoS identifiziert und markiert alle Pakete in Echtzeit Datenströme mithilfe von Windows Group Policy Objects und routing sogenannten Port-basierte Access Control Lists, der dann, Ihr Netzwerk hilft für Sprach-, Video- und Bildschirm freigeben ein als einen eigenen dedizierten Teile des Stream Netzwerkbandbreite.

 Jetzt wir werden nur sagen, dass es viel ist wie ein Briefs über die e-Mail-Nachricht senden: Wenn Sie es Adressbuch Rate senden es ruft es ziemlich bald und das reicht, wenn Sie diese erste Klasse senden es ruft es viel schneller und Priorität E-Mail senden , ruft es innerhalb von zwei Tagen. Natürlich Netzwerke schneller als die e-Mail-Nachricht ausgeführt, aber es weiter ausgeführt wird, dass die Geschwindigkeit ist ein entscheidender Faktor bei einigen Applikationen und ist nicht so wichtig für andere Benutzer. Dieses Thema ist grundsätzlich eine detaillierte und schwierig, zunächst zu verstehen, aber es spielt eine große Rolle der Benutzer auftreten, dies ist im Wert von Zeit und weniger Energie vorab investieren. Lesen Sie eine detailliertere Erläuterung [Implementieren Quality of Service (QoS) in Microsoft-Teams](QoS-in-Teams.md) .

Im Idealfall implementieren Sie QoS auf dem internen Netzwerk während der Einrichtung von Teams, jedoch klein genug es kann sein, optional. Dadurch wird die Verzögerung vertrauliche VoIP und video-Datenverkehr vor anderen Datenverkehr priorisiert abrufen. Sie würden diese Priorisierung alle [Clientgeräte](QoS-in-Teams-clients.md), in der [Microsoft-Teams, Administrationscenter](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), als auch auf die Switches und Router in Ihrem Netzwerk ausführen.

[**Analytics aufrufen, und rufen Sie Qualitätsdashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) dienen zum Suchen und Behandeln von Problemen, die während der laufenden Betrieb auftreten.  

**Rufen Sie Analytics** Zeigt ausführliche Informationen zu den Geräten, Netzwerke und im Zusammenhang mit ***bestimmten Anrufe und Besprechungen*** für jeden Benutzer in einem Microsoft-Teams oder Skype für Konto Business Connectivity. Wenn Sie ein Office 365-Administrator sind, können Sie Analytics aufrufen, Anruf Qualität und Verbindung auftraten in einem Aufruf der bestimmten Problemen. Dies hilft Ihnen zu identifizieren und Probleme zu vermeiden.

**Rufen Sie Quality Dashboard (CQD)** soll Administratoren helfen und Netzwerk-Techniker in ihrem ***Netzwerk***zu optimieren, nicht Analyse und Fehlerbehebung einen einzigen Anruf. CQD verschiebt den Fokus von bestimmten Benutzern aggregierten Informationen für eine ganze Organisation anzuzeigen. Dies hilft Ihnen zu identifizieren und Probleme zu vermeiden.

## <a name="related-topics"></a>Verwandte Themen

[Implementieren von Quality of Service (QoS) in Microsoft-Teams](QoS-in-Teams.md)

[Video: Übersicht über die Qualität aufrufen](https://aka.ms/teams-quality)

[Einrichten von Anrufanalyse](set-up-call-analytics.md)

[Verwenden Sie Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Aktivieren und Verwenden des Dashboards für Anrufqualität](turning-on-and-using-call-quality-dashboard.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Anrufqualitäts-Dashboard](stream-classification-in-call-quality-dashboard.md)