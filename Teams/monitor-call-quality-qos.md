---
title: Überwachen und Verbessern der Anrufqualität für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Verwenden Sie die QoS-Einstellungen (Quality of Service), und wählen Sie dann Anrufanalyse und Anrufqualitätsdashboard in Microsoft Teams aus.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162688"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Überwachen und Verbessern der Anrufqualität für Microsoft Teams

In diesem Artikel werden drei wichtige Tools zur Überwachung, Problembehandlung, Verwaltung und Verbesserung der Anrufqualität in Microsoft Teams beschrieben. 

- **Anrufqualitätsdashboard (CQD):** Um organisationsweite Trends oder Probleme zu analysieren, verbessern Sie die Leistung

- **Anrufanalyse:** So analysieren Sie die Anruf- und Besprechungsqualität für einzelne Benutzer

- **Quality of Service (QoS):** So priorisieren Sie wichtigen Netzwerkdatenverkehr



## <a name="monitor-and-troubleshoot-call-quality"></a>Überwachen und Behandeln von Anrufqualität
Sie verwenden die Anrufanalyse pro  Benutzer und das Anrufqualitätsdashboard, um Probleme mit der Anrufqualität zu finden und zu beheben, die während des laufenden Betriebs auftreten.  Auf diese Weise können Sie Leistungsverbesserungen im gesamten Netzwerk erzielen. Beide Tools befinden sich im Teams Admin Center.

 - **Die Anrufanalyse** zeigt detaillierte Informationen zu den **** Geräten, Netzwerken und Konnektivität im Zusammenhang mit bestimmten Anrufen und Besprechungen für jeden Benutzer in Teams. Teams-Administratoren und Helpdeskmitarbeiter verwenden diese Informationen, um Probleme mit der Anrufqualität und Verbindungen in einem bestimmten Anruf zu beheben. Weitere Informationen finden Sie unter [Einrichten der Anrufanalyse](set-up-call-analytics.md) und Verwenden der Anrufanalyse zur Problembehandlung [bei schlechter Anrufqualität.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **Das Anrufqualitätsdashboard (CQD)** bietet Ihnen eine **_netzwerkweite_** Ansicht der Anrufqualität in Der gesamten Organisation. Verwenden Sie CQD-Informationen, um Probleme zu erkennen und zu beheben. Richten Sie [zuerst CQD ein.](turning-on-and-using-call-quality-dashboard.md) Lesen Sie dann [Verwalten der Anruf- und Besprechungsqualität in Teams.](quality-of-experience-review-guide.md)

 Anrufanalysen und CQD werden parallel ausgeführt und können unabhängig oder zusammen verwendet werden. Wenn beispielsweise ein Kommunikationssupportspezialist feststellt, dass er weitere Hilfe bei der Behandlung des Anrufproblems eines Benutzers benötigt, eskaliert er den Anruf an einen Kommunikationssupporttechniker, der Zugriff auf zusätzliche Informationen zum Anruf hat. Der Kommunikationssupporttechniker wiederum warnt einen Netzwerktechniker auf ein mögliches websitebezogenes Problem, das er in der Anrufanalyse bemerkt hat. Der Netzwerktechniker überprüft CQD, um zu prüfen, ob ein allgemeines websitebezogenes Problem eine ursache für das Anrufproblem des Benutzers sein kann.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorisieren des wichtigen Netzwerkdatenverkehrs mithilfe von QoS
Wenn Ihre Benutzer Teams für Anrufe und Besprechungen verwenden, kann es sein, dass die Stimme eines Anrufers einbricht oder aus einem Anruf oder einer Besprechung ausbricht. Freigegebene Videos können fixieren oder verpixeln oder ganz fehlschlagen. Dies liegt an den IP-Paketen, die Sprach- und Videodatenverkehr darstellen, bei dem eine Netzwerküberlastung vorkommt und die Nichtabfolge oder gar nicht eintreffen. Wenn dies geschieht (oder um zu verhindern, dass dies von vorn geht), verwenden Sie **QoS (Quality of Service).** 

Mit QoS priorisieren Sie den verzögerungsempfindlichen Netzwerkdatenverkehr (z. B. Sprach- oder Videodatenströme), sodass er vor weniger sensiblem Datenverkehr "in Zeile" ausschneiden kann (z. B. das Herunterladen einer neuen App, bei der eine zusätzliche Sekunde zum Herunterladen keine große Sache ist). QoS identifiziert und kennzeichnet alle Pakete in Echtzeitdatenströmen mithilfe von Windows-Gruppenrichtlinienobjekten und einem Routingfeature namens Portbasierte Zugriffssteuerungslisten, mit dem Ihr Netzwerk angewiesen wird, Sprach-, Video- und Bildschirmfreigaben für eigene dedizierte Netzwerkbandbreiten zu verwenden.

Im Idealfall implementieren Sie QoS in Ihrem internen Netzwerk, während Sie mit dem Rollout von Teams fertig sind, aber Sie können dies jederzeit tun. Wenn Sie klein genug sind, benötigen Sie möglicherweise kein QoS.

Wenn Sie fertig sind, lesen Sie [Implementieren der Dienstqualität (QoS) in Microsoft Teams.](QoS-in-Teams.md)

Informationen zum Verwalten des Besprechungsverkehrs mithilfe von QoS finden Sie unter Festlegen der Art und Weise, wie Sie den Mediendatenverkehr in Echtzeit [für Teams-Besprechungen behandeln möchten.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Einrichten von CQD](turning-on-and-using-call-quality-dashboard.md)

[Verwalten der Anruf- und Besprechungsqualität in Teams](quality-of-experience-review-guide.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)