---
title: Die Anrufqualität von Microsoft Teams überwachen und verbessern
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Verwenden Sie QoS-Einstellungen (Quality of Service) und dann Anrufanalyse und Anrufqualitäts-Dashboard in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed9bab3ad0cde91bc8faa4298956b07f73438e823e3e3c110ce09610fee5e7c0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286264"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Die Anrufqualität von Microsoft Teams überwachen und verbessern

In diesem Artikel werden drei wichtige Tools vorgestellt, die Sie zum Überwachen, Beheben, Verwalten und Verbessern der Anrufqualität in Microsoft Teams verwenden können. 

- **Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD):** Um organisationsweite Trends oder Probleme zu analysieren, steigern Sie die Leistung

- **Anrufanalyse:** So analysieren Sie die Anruf- und Besprechungsqualität für einzelne Benutzer

- **Quality of Service (QoS):** So priorisieren Sie wichtigen Netzwerkdatenverkehr



## <a name="monitor-and-troubleshoot-call-quality"></a>Überwachen und Beheben von Problemen mit der Anrufqualität
Sie verwenden die **Anrufanalyse** pro Benutzer und **das Anrufqualitäts-Dashboard,** um Probleme mit der Anrufqualität zu finden und zu beheben, die während des laufenden Betriebs auftreten. Auf diese Weise können Sie Leistungsverbesserungen in Ihrem Netzwerk erzielen. Beide Tools befinden sich im Teams Admin Center.

 - **Die Anrufanalyse** zeigt detaillierte Informationen zu den Geräten, Netzwerken und Konnektivität im Zusammenhang mit **_bestimmten Anrufen und Besprechungen_** für jeden Benutzer in Teams. Teams Administrator- und Helpdesk-Agents verwenden diese Informationen, um Probleme mit der Anrufqualität und der Verbindung in einem bestimmten Anruf zu beheben. Weitere Informationen finden Sie unter Einrichten der [Anrufanalyse](set-up-call-analytics.md) und [Verwenden der Anrufanalyse, um Probleme mit schlechter Anrufqualität zu beheben.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - Das **Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD)** bietet Ihnen eine **_netzwerkweite Übersicht über_** die Anrufqualität in Ihrer Organisation. Verwenden Sie CQD-Informationen, um Probleme zu erkennen und zu beheben. Richten Sie zunächst [CQD ein.](turning-on-and-using-call-quality-dashboard.md) Lesen Sie dann ["Anruf- und Besprechungsqualität verwalten" in Teams.](quality-of-experience-review-guide.md)

 Anrufanalyse und CQD werden parallel ausgeführt und können unabhängig oder gemeinsam verwendet werden. Wenn z. B. ein Kommunikationssupport-Spezialist feststellt, dass er mehr Hilfe bei der Behandlung des Anrufproblems eines Benutzers benötigt, eskaliert er den Anruf an einen Kommunikationssupporttechniker, der Zugriff auf zusätzliche Informationen zu dem Anruf hat. Der Kommunikationssupporttechniker warnt wiederum einen Netzwerktechniker vor einem möglichen standortbezogenen Problem, das er bei der Anrufanalyse bemerkt hat. Der Netzwerktechniker überprüft das CQD, um festzustellen, ob ein allgemeines standortbezogenes Problem eine ursache für das Anrufproblem des Benutzers sein könnte.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorisieren von wichtigem Netzwerkdatenverkehr mit QoS
Wenn Ihre Benutzer beginnen, Teams für Anrufe und Besprechungen zu verwenden, kann es vorkommen, dass die Stimme eines Anrufers ein- oder ausgeschnitten wird. Freigegebene Videos können fixieren oder pixeln oder komplett fehlschlagen. Dies liegt an den IP-Paketen, die VoIP- und Videodatenverkehr darstellen, der auf Netzwerküberlastung trifft und außerhalb der Sequenz ankommt oder überhaupt nicht. Wenn dies geschieht (oder um zu verhindern, dass dies überhaupt geschieht), verwenden Sie **Quality of Service (QoS).** 

Mit QoS priorisieren Sie verzögerungssensiblen Netzwerkdatenverkehr (z. B. Sprach- oder Videodatenströme), sodass er vor weniger sensiblem Datenverkehr "in die Linie schneiden" kann (z. B. das Herunterladen einer neuen App, bei der eine zusätzliche Sekunde zum Herunterladen keine große Aufgabe ist). QoS identifiziert und kennzeichnet alle Pakete in Echtzeitdatenströmen mit Windows Gruppenrichtlinienobjekten und einem Routingfeature namens portbasierten Zugriffssteuerungslisten, das Ihr Netzwerk anweist, VoIP-, Video- und Bildschirmfreigaben eine eigene dedizierte Netzwerkbandbreite zuzuweisen.

Idealerweise implementieren Sie QoS in Ihrem internen Netzwerk, während Sie sich auf das Rollout Teams vorbereiten, aber Sie können dies jederzeit tun. Wenn Sie klein genug sind, benötigen Sie möglicherweise QoS nicht.

Wenn Sie bereit sind, lesen [Sie "Quality of Service (QoS) implementieren" in Microsoft Teams.](QoS-in-Teams.md)

Wenn Sie QoS zum Verwalten des Besprechungsdatenverkehrs verwenden möchten, lesen [Sie "Festlegen, wie Der Mediendatenverkehr in Echtzeit für Teams Besprechungen behandelt werden soll."](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse](set-up-call-analytics.md)

[Verwenden Sie Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Einrichten von CQD](turning-on-and-using-call-quality-dashboard.md)

[Verwalten der Anruf- und Besprechungsqualität in Teams](quality-of-experience-review-guide.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)