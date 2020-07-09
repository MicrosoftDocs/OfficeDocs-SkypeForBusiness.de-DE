---
title: Überwachen und verbessern der Anrufqualität für Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Verwenden Sie Quality of Service (QoS)-Einstellungen, und rufen Sie dann Analytics und das Dashboard für die Anrufqualität in Microsoft Teams auf.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085946"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Überwachen und verbessern der Anrufqualität für Microsoft Teams

In diesem Artikel werden drei wichtige Tools vorgestellt, die Sie verwenden können, um die Anrufqualität in Microsoft Teams zu überwachen, zu beheben, zu verwalten und zu verbessern. 

- **Dashboard zur Anrufqualität (CQD)**: Analysieren von organisationsweiten Trends oder Problemen, verbessern der Leistung

- **Anrufanalyse**: So analysieren Sie die Anruf-und Besprechungs Qualität für einzelne Benutzer

- **Quality of Service (QoS)**: so priorisieren Sie wichtigen Netzwerkdatenverkehr



## <a name="monitor-and-troubleshoot-call-quality"></a>Überwachen und behandeln von Problemen mit der Anrufqualität
Sie verwenden pro-Benutzer- **anrufanalyse** und **Anruf Qualitäts Dashboard** , um Probleme mit der Anrufqualität zu finden und zu beheben, die während des laufenden Vorgangs auftreten. Auf diese Weise können Sie Leistungsverbesserungen im gesamten Netzwerk steuern. Beide Tools sind im Team Admin Center zu finden.

 - Die **anrufanalyse** zeigt detaillierte Informationen zu den Geräten, Netzwerken und Verbindungen, die sich auf ***bestimmte Anrufe und Besprechungen*** für jeden Benutzer in Teams beziehen. Teams-Administrator und Helpdesk-Agents verwenden diese Informationen, um die Anrufqualität und Verbindungsprobleme in einem bestimmten Anruf zu beheben. Weitere Informationen finden Sie unter [Einrichten der anrufanalyse](set-up-call-analytics.md) und [Verwenden der anrufanalyse für die Problembehandlung bei schlechter Anrufqualität](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - Das Dashboard für die **Anrufqualität (CQD)** bietet eine ***netzwerkweite Übersicht*** über die Anrufqualität in Ihrer Organisation. Verwenden Sie CQD-Informationen, um Probleme zu erkennen und zu beheben. [Richten Sie zunächst CQD](turning-on-and-using-call-quality-dashboard.md)ein. Lesen Sie dann [Verwalten von Anruf-und Besprechungs Qualität in Teams](quality-of-experience-review-guide.md).

 Anrufanalyse-und CQD werden parallel ausgeführt und können unabhängig oder zusammen verwendet werden. Wenn beispielsweise ein Spezialist für Kommunikationsunterstützung feststellt, dass er weitere Hilfe bei der Problembehandlung des Anruf Problems eines Benutzers benötigt, eskaliert er den Anruf an einen Communications Support Engineer, der Zugriff auf zusätzliche Informationen über den Anruf hat. Der Communications Support Engineer benachrichtigt einen Netzwerktechniker wiederum zu einem möglichen Website bezogenen Problem, das Ihnen in der anrufanalyse aufgefallen ist. Der Netzwerktechniker überprüft CQD, ob ein Problem mit der allgemeinen Website eine Ursache für das Anruf Problem des Benutzers sein könnte.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorisieren von wichtigem Netzwerkdatenverkehr mithilfe von QoS
Wenn Ihre Benutzer Teams für Anrufe und Besprechungen verwenden, kann dies dazu führen, dass die Stimme eines Anrufers die Sprache eines Anrufs oder einer Besprechung aufbricht oder schneidet. Freigegebene Videos können einfrieren oder Pixeln oder überhaupt nicht funktionieren. Dies ist auf die IP-Pakete zurückzuführen, die Sprach-und Videodatenverkehr darstellen, die zu einer Überlastung des Netzwerks führen und außerhalb der Reihenfolge oder gar nicht ankommen. In diesem Fall verwenden Sie **Quality of Service (QoS)**, wenn dies geschieht (oder um zu verhindern, dass dies an erster Stelle geschieht). 

Mit QoS priorisieren Sie den Verzögerungs empfindlichen Netzwerkverkehr (beispielsweise sprach-oder Videodatenströme), sodass er vor dem Verkehr, der weniger sensibel ist (wie beim Herunterladen einer neuen App, bei der eine zusätzliche Sekunde zum herunterladen keine große Sache ist), "in der Zeile" abschneiden kann. QoS identifiziert und kennzeichnet alle Pakete in Echtzeit-Streams unter Verwendung von Windows-Gruppenrichtlinienobjekten und einem Routing-Feature namens Port basierten Zugriffskontrolllisten, das Ihr Netzwerk anweist, sprach-, Video-und Bildschirmfreigabe eigene dedizierte Netzwerkbandbreite zu verleihen.

Im Idealfall implementieren Sie QoS in Ihrem internen Netzwerk, während Sie sich für das Rollout von Teams vorbereiten, aber Sie können es jederzeit tun. Wenn Sie klein genug sind, benötigen Sie möglicherweise keine QoS.

Wenn Sie bereit sind, lesen Sie [Implementieren von Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).

Wenn Sie QoS zum Verwalten des Besprechungs Verkehrs verwenden möchten, lesen Sie so [legen Sie fest, wie der Mediendatenverkehr in Echtzeit für Teams-Besprechungen gehandhabt werden soll](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Verwandte Themen

[Einrichten der anrufanalyse](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Einrichten von CQD](turning-on-and-using-call-quality-dashboard.md)

[Verwalten von Anruf-und Besprechungs Qualität in Teams](quality-of-experience-review-guide.md)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

