---
title: Überwachen und Verbessern der Anrufqualität für Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Verwenden Sie QoS-Einstellungen (Quality of Service) und dann anrufanalyse und Anrufqualitätsdashboard in Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ac317ff6ac17a2b6a0e94c0fa5683979cb887b90
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2022
ms.locfileid: "66793242"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Überwachen und Verbessern der Anrufqualität für Microsoft Teams

In diesem Artikel werden drei wichtige Tools vorgestellt, mit denen Sie die Anrufqualität in Microsoft Teams überwachen, behandeln, verwalten und verbessern können. 

- **Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD)**: Um organisationsweite Trends oder Probleme zu analysieren, steigern Sie die Leistung

- **Anrufanalyse**: So analysieren Sie die Anruf- und Besprechungsqualität für einzelne Benutzer

- **Quality of Service (QoS)**: So priorisieren Sie wichtigen Netzwerkdatenverkehr



## <a name="monitor-and-troubleshoot-call-quality"></a>Überwachen und Behandeln von Problemen mit der Anrufqualität
Sie verwenden die **Anrufanalyse** pro Benutzer und **das Anrufqualitätsdashboard** , um Probleme mit der Anrufqualität zu finden und zu beheben, die während des laufenden Betriebs auftreten. Auf diese Weise können Sie Leistungsverbesserungen in Ihrem Netzwerk fördern. Beide Tools befinden sich im Teams Admin Center.

 - **Die Anrufanalyse** zeigt detaillierte Informationen zu den Geräten, Netzwerken und Konnektivität im Zusammenhang mit  **_bestimmten Anrufen und Besprechungen_** für jeden Benutzer in Teams. Teams-Administratoren und Helpdesk-Agents verwenden diese Informationen, um Probleme mit der Anrufqualität und -verbindung in einem bestimmten Anruf zu beheben. Weitere Informationen finden Sie unter ["Einrichten der Anrufanalyse](set-up-call-analytics.md) " und ["Anrufanalyse verwenden", um probleme mit schlechter Anrufqualität zu beheben](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - Das **Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD)** bietet Ihnen eine **_netzwerkweite Ansicht_** der Anrufqualität in Ihrer Organisation. Verwenden Sie CQD-Informationen, um Probleme zu identifizieren und zu beheben. [Richten Sie zuerst CQD ein](turning-on-and-using-call-quality-dashboard.md). Lesen Sie dann ["Anruf verwalten und Besprechungsqualität in Teams verwalten](quality-of-experience-review-guide.md)".

 Anrufanalyse und CQD werden parallel ausgeführt und können unabhängig oder gemeinsam verwendet werden. Wenn beispielsweise ein Kommunikationssupportspezialist feststellt, dass er mehr Hilfe bei der Behandlung des Anrufproblems eines Benutzers benötigt, eskaliert er den Anruf an einen Kommunikationssupporttechniker, der Zugriff auf zusätzliche Informationen über den Anruf hat. Der Kommunikationssupporttechniker wiederum benachrichtigt einen Netzwerktechniker über ein mögliches standortbezogenes Problem, das sie bei der Anrufanalyse bemerkt haben. Der Netzwerktechniker überprüft den CQD, um festzustellen, ob ein allgemeines standortbezogenes Problem eine Ursache für das Anrufproblem des Benutzers sein könnte.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorisieren von wichtigem Netzwerkdatenverkehr mit QoS
Wenn Ihre Benutzer Teams für Anrufe und Besprechungen verwenden, kann es vorkommen, dass die Stimme eines Anrufers ein- oder ausbricht oder aus einem Anruf oder einer Besprechung ausschneidet. Freigegebene Videos können fixieren oder verpixeln oder insgesamt fehlschlagen. Dies liegt an den IP-Paketen, die Denk- und Videodatenverkehr darstellen, der auf Netzwerküberlastungen stößt und aus der Sequenz kommt oder überhaupt nicht. Wenn dies geschieht (oder um dies zu verhindern), verwenden Sie **Quality of Service (QoS)**. 

Mit QoS priorisieren Sie verzögerungsempfindlichen Netzwerkdatenverkehr (z. B. Sprach- oder Videostreams), sodass er vor weniger sensiblem Datenverkehr "abgeschnitten" werden kann (z. B. beim Herunterladen einer neuen App, bei der eine zusätzliche Sekunde zum Herunterladen keine große Sache ist). QoS identifiziert und kennzeichnet alle Pakete in Echtzeitdatenströmen mithilfe von Windows Gruppenrichtlinie-Objekten und einem Routingfeature namens "Portbasierte Access Control Listen", das Ihr Netzwerk anweist, Sprach-, Video- und Bildschirmfreigaben eigene dedizierte Netzwerkbandbreite zu geben.

Im Idealfall implementieren Sie QoS in Ihrem internen Netzwerk, während Sie sich auf das Rollout von Teams vorbereiten, aber Sie können dies jederzeit tun. Wenn Sie klein genug sind, benötigen Sie QoS möglicherweise nicht.

Wenn Sie fertig sind, lesen Sie ["Implementieren von Quality of Service (QoS)" in Microsoft Teams](QoS-in-Teams.md).

Wenn Sie QoS zum Verwalten des Besprechungsdatenverkehrs verwenden möchten, lesen [Sie "Festlegen, wie Der Mediendatenverkehr in Echtzeit für Teams-Besprechungen behandelt werden soll](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)".


## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Einrichten von CQD](turning-on-and-using-call-quality-dashboard.md)

[Verwalten der Anruf- und Besprechungsqualität in Teams](quality-of-experience-review-guide.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
