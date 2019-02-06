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
ms.openlocfilehash: 505409ac51552a99fabc4eb41801a1f19a737877
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742950"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementieren Sie QoS und Monitor Anrufqualität in Microsoft-Teams

## <a name="get-started"></a>Erste Schritte

Wenn Ihre Benutzer mit Teams zum Tätigen von Anrufen und Aufbewahren von Besprechungen beginnen, sie können hier finden Sie Lautsprecher neueste USV oder zerkleinert innerhalb und außerhalb eines Anrufs oder einer Besprechung. Freigegebene Video reagiert möglicherweise nicht mehr oder pixellate, oder schlagen fehl. Dies ist aufgrund der IP-Pakete, die VoIP und video-Datenverkehr Überlastung des Netzwerks auftreten und eingehenden außerhalb der Reihenfolge oder überhaupt nicht darstellen. Es gibt Methoden, um zu verhindern, dass diese und andere Probleme zu identifizieren, wenn sie Fläche, hauptsächlich Quality of Service (QoS).

[**Quality of Service (QoS)**](monitor-call-quality-qos.md) ist eine Möglichkeit zum Identifizieren der Pakete, die vertrauliche Überlastung zu Verzögerungen sind, und geben Sie die Pakete mit bevorzugte Behandlung damit weitaus weniger Überlastung auftretenden. Jetzt wir werden nur sagen, dass es viel ist wie ein Briefs über die e-Mail-Nachricht senden: Wenn Sie es Adressbuch Rate senden es ruft es ziemlich bald und das reicht, wenn Sie diese erste Klasse senden es ruft es viel schneller und Priorität E-Mail senden , ruft es innerhalb von zwei Tagen. Natürlich Netzwerke schneller als die e-Mail-Nachricht ausgeführt, aber es weiter ausgeführt wird, dass die Geschwindigkeit ist ein entscheidender Faktor bei einigen Applikationen und ist nicht so wichtig für andere Benutzer. Dieses Thema ist grundsätzlich eine detaillierte und schwierig, zunächst zu verstehen, aber es spielt eine große Rolle der Benutzer auftreten, dies ist im Wert von Zeit und weniger Energie vorab investieren.

Im Idealfall implementieren Sie QoS auf dem internen Netzwerk während der Einrichtung von Teams, jedoch klein genug es kann sein, optional. Dadurch wird die Verzögerung vertrauliche VoIP und video-Datenverkehr vor anderen Datenverkehr priorisiert abrufen. Sie würden diese Priorisierung auf allen Clientgeräten und der Switches und Router in Ihrem Netzwerk ausführen.

[**Analytics aufrufen, und rufen Sie Qualitätsdashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) dienen zum Suchen und Behandeln von Problemen, die während der laufenden Betrieb auftreten.  

Anruf Analytics zeigt detaillierte Informationen zu den Geräten, Netzwerke und im Zusammenhang mit der bestimmte Aufrufe und Besprechungen für jeden Benutzer in einem Microsoft-Teams oder Skype für Konto Business Connectivity. Wenn Sie ein Office 365-Administrator sind, können Sie Analytics aufrufen, Anruf Qualität und Verbindung auftraten in einem Aufruf der bestimmten Problemen. Dies hilft Ihnen zu identifizieren und Probleme zu vermeiden.

Anruf Quality Dashboard (CQD) soll helfen, Administratoren und Netzwerktechniker Optimieren der Leistung von einem **Netzwerk**, nicht analysieren und Problembehandlung bei einem einzigen Aufruf. CQD verschiebt den Fokus von bestimmten Benutzern aggregierten Informationen für eine ganze Organisation anzuzeigen. Dies hilft Ihnen zu identifizieren und Probleme zu vermeiden.

## <a name="related-topics"></a>Verwandte Themen

[Video: Übersicht über die Qualität aufrufen](https://aka.ms/teams-quality)

[Einrichten von Anrufen Analytics](set-up-call-analytics.md)

[Verwenden der Anrufanalyse zur Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Aktivieren und verwenden Qualität Dashboards aufrufen](turning-on-and-using-call-quality-dashboard.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Anrufqualitäts-Dashboard](stream-classification-in-call-quality-dashboard.md)