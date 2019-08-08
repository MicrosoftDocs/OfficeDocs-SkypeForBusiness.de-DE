---
title: Implementieren von QoS und Überwachung der Anrufanalyse in Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: jambirk
description: Verwenden Sie Quality of Service (QoS)-Einstellungen, und rufen Sie dann Analytics und das Dashboard für die Anrufqualität in Microsoft Teams auf.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70e862adf2aad795a9ef1ab34eaa2de21240a388
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239253"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementieren von QoS und Überwachen der Anrufqualität in Microsoft Teams

## <a name="get-started"></a>Erste Schritte

Wenn Ihre Benutzer mit der Verwendung von Teams für Anrufe und Besprechungen beginnen, kann es vorkommen, dass die Stimme eines Anrufers in einen Anruf oder eine Besprechung zerlegt oder abgehackt wird. Freigegebene Videos können einfrieren oder Pixeln oder überhaupt nicht funktionieren. Dies ist auf die IP-Pakete zurückzuführen, die Sprach-und Videodatenverkehr darstellen, die zu einer Überlastung des Netzwerks führen und außerhalb der Reihenfolge oder gar nicht ankommen. Es gibt Möglichkeiten, diese Probleme zu erkennen, wenn diese auftreten, und deren Rückgabe, in erster Linie Quality of Service (QoS), zu verhindern.

**Quality of Service (QoS)** ist eine Möglichkeit, Netzwerkdatenverkehr in Echtzeit (wie Sprach-oder Videostreams) zu ermöglichen, die für Netzwerkverzögerungen anfällig sind, um vor dem Verkehr, der weniger sensibel ist (wie beim Herunterladen einer neuen App, wo eine zusätzliche Sekunde heruntergeladen werden kann, "Cut in the Front"). Das ist keine große Sache). QoS identifiziert und kennzeichnet alle Pakete in Echtzeit-Streams unter Verwendung von Windows-Gruppenrichtlinienobjekten und einem Routing-Feature namens Port basierten Zugriffskontrolllisten, das Ihrem Netzwerk dann dabei hilft, sprach-, Video-und Bildschirmfreigabe Datenströme über eigene dedizierte Abschnitte zu senden. Netzwerkbandbreite.

 Im Moment sagen wir einfach, dass es sehr ähnlich ist, wenn Sie einen Brief über die e-Mail senden: Wenn Sie ihm die Buch Gebühr senden, wird es ziemlich bald und das ist gut genug, wenn Sie es First Class senden, wird es wesentlich schneller, und wenn Sie es als Priority-Mail senden , es wird innerhalb von zwei Tagen abgerufen. Natürlich werden Netzwerke schneller ausgeführt als die e-Mail, doch es wird immer noch wahr ausgeführt, dass die Geschwindigkeit für einige Anwendungen kritisch ist und für andere nicht so wichtig ist. Dieses Thema ist von Natur aus detailliert und schwierig zu verstehen, doch es macht einen großen Unterschied in der Benutzererfahrung aus, daher lohnt es sich, Zeit und Energie im Voraus zu investieren. Eine ausführlichere Erläuterung finden Sie [unter Implementieren von Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md) .

Im Idealfall würden Sie QoS in Ihrem internen Netzwerk beim Einrichten von Teams implementieren, doch wenn Sie klein genug sind, kann dies optional sein. Auf diese Weise kann der Verzögerungsabhängige sprach-und Videoverkehr vor dem anderen Datenverkehr priorisiert werden. Sie würden diese Priorisierung auf allen [Clientgeräten](QoS-in-Teams-clients.md), im [Microsoft Teams Admin Center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)sowie auf den Switches und Routern in Ihrem Netzwerk ausführen.

Das Dashboard für die [**anrufanalyse und die Anrufqualität**](difference-between-call-analytics-and-call-quality-dashboard.md) wird verwendet, um im laufenden Betrieb auftretende Probleme zu finden und zu beheben.  

In der **anrufanalyse** werden detaillierte Informationen zu den Geräten, Netzwerken und Verbindungen zu ***bestimmten anrufen und Besprechungen*** für jeden Benutzer in einem Microsoft Teams-oder Skype for Business-Konto angezeigt. Wenn Sie ein Office 365-Administrator sind, können Sie die anrufanalyse verwenden, um die Anrufqualität und Verbindungsprobleme in einem bestimmten Anruf zu beheben. Dies kann Ihnen helfen, Probleme zu erkennen und zu beheben.

Das Dashboard für die **Anrufqualität (CQD)** soll Administratoren und Netzwerk Ingenieuren helfen, Ihr ***Netzwerk***zu optimieren, nicht zu analysieren und einen einzelnen Anruf zu beheben. CQD verschiebt den Fokus von bestimmten Benutzern, um aggregierte Informationen für eine gesamte Organisation zu sehen. Dies kann Ihnen auch helfen, Probleme zu erkennen und zu beheben.

## <a name="related-topics"></a>Verwandte Themen

[Implementieren von Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md)

[Video: Übersicht über die Anrufqualität](https://aka.ms/teams-quality)

[Einrichten von Anrufanalyse](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Aktivieren und Verwenden des Dashboards für Anrufqualität](turning-on-and-using-call-quality-dashboard.md)

[Im Anrufqualitäts-Dashboard verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstromklassifizierung im Dashboard für Anrufqualität](stream-classification-in-call-quality-dashboard.md)