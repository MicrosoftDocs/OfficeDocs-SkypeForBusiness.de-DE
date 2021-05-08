---
title: Überwachen und Verbessern der Anrufqualität für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Verwenden Sie die QoS-Einstellungen (Quality of Service) und dann die Anrufanalyse und das Anrufqualitätsdashboard in Microsoft Teams.
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

In diesem Artikel werden drei wichtige Tools für die Überwachung, Problembehandlung, Verwaltung und Verbesserung der Anrufqualität in ihrer Microsoft Teams. 

- **Anrufqualitätsdashboard (CQD):** Um organisationsweite Trends oder Probleme zu analysieren, verbessern Sie die Leistung.

- **Anrufanalyse:** So analysieren Sie die Anruf- und Besprechungsqualität für einzelne Benutzer

- **Quality of Service (QoS):** So priorisieren Sie wichtigen Netzwerkdatenverkehr



## <a name="monitor-and-troubleshoot-call-quality"></a>Überwachen und Behandeln von Problemen mit der Anrufqualität
Sie verwenden die Anrufanalyse pro  Benutzer und das Anrufqualitätsdashboard, um Probleme mit der Anrufqualität zu finden und zu behandeln, die während des laufenden Betriebs auftreten.  Auf diese Weise können Sie Leistungsverbesserungen im gesamten Netzwerk erreichen. Beide Tools befinden sich im Teams Admin Center.

 - **Die Anrufanalyse** zeigt detaillierte Informationen zu den **** Geräten, Netzwerken und zur Konnektivität im Zusammenhang mit bestimmten Anrufen und Besprechungen für jeden Benutzer in Teams. Teams-Administrator und Helpdesk-Agents verwenden diese Informationen, um Probleme mit der Anrufqualität und verbindungen in einem bestimmten Anruf zu beheben. Weitere Informationen finden Sie unter Einrichten der [Anrufanalyse](set-up-call-analytics.md) und Verwenden der Anrufanalyse zur Problembehandlung bei [schlechter Anrufqualität.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **Das Anrufqualitätsdashboard (CQD)** bietet Ihnen eine **_netzwerkweite_** Ansicht der Anrufqualität in der gesamten Organisation. Verwenden Sie AQD-Informationen, um Probleme zu erkennen und zu beheben. Richten Sie [zuerst das CQD ein.](turning-on-and-using-call-quality-dashboard.md) Lesen Sie dann Verwalten [der Anruf- und Besprechungsqualität in Teams.](quality-of-experience-review-guide.md)

 Anrufanalyse und Anrufanalyse werden parallel ausgeführt und können unabhängig oder zusammen verwendet werden. Wenn beispielsweise ein Kommunikationssupportspezialist feststellt, dass er weitere Hilfe bei der Behandlung des Anrufproblems eines Benutzers benötigt, eskaliert er den Anruf an einen Kommunikationssupporttechniker, der Zugriff auf weitere Informationen zum Anruf hat. Der Kommunikationssupporttechniker wiederum warnt einen Netzwerktechniker auf ein mögliches standortbezogenes Problem, das er in der Anrufanalyse bemerkt hat. Der Netzwerktechniker überprüft das Anruf-AQD, um zu prüfen, ob ein allgemeines standortbezogenes Problem die Ursache des Anrufproblems des Benutzers sein könnte.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorisieren von wichtigem Netzwerkdatenverkehr mithilfe von QoS
Wenn Ihre Benutzer Teams für Anrufe und Besprechungen verwenden, kann es sein, dass die Stimme eines Anrufers einbricht oder aus einem Anruf oder einer Besprechung ausschneidet. Freigegebene Videos können einfrieren oder pixelig werden oder ganz fehlschlagen. Dies liegt an den IP-Paketen, die Sprach- und Videodatenverkehr darstellen, der eine Netzwerküberlastung verursacht und die Sequenz nicht oder überhaupt nicht überlasten. Wenn dies geschieht (oder um zu verhindern, dass dies zuerst der Fall ist), verwenden Sie **Quality of Service (QoS)**. 

Mit QoS priorisieren Sie verzögerungsempfindlichen Netzwerkdatenverkehr (z. B. Sprach- oder Videodatenströme) und ermöglichen es, vor weniger sensiblem Datenverkehr "in Zeile" zu kommen (z. B. beim Herunterladen einer neuen App, bei dem eine zusätzliche Sekunde zum Herunterladen keine große Sache ist). QoS identifiziert und markiert alle Pakete in Echtzeitstreams mit Windows-Gruppenrichtlinienobjekten und einem Routingfeature namens Portbasierte Zugriffssteuerungslisten, mit dem Ihr Netzwerk angewiesen wird, Die Sprach-, Video- und Bildschirmfreigabe für eigene dedizierte Netzwerkbandbreite zu verwenden.

Im Idealfall implementieren Sie QoS in Ihrem internen Netzwerk, während Sie sich auf den Rollout Teams, aber Sie können dies jederzeit tun. Wenn Sie klein genug sind, benötigen Sie möglicherweise kein QoS.

Wenn Sie fertig sind, lesen Sie [Implementieren von Quality of Service (QoS) in Microsoft Teams.](QoS-in-Teams.md)

Informationen zum Verwenden von QoS zum Verwalten des Besprechungsdatenverkehrs finden Sie unter Festlegen, wie [Echtzeitmedienverkehr](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)für Besprechungen Teams werden soll.


## <a name="related-topics"></a>Verwandte Themen

[Einrichten der Anrufanalyse](set-up-call-analytics.md)

[Verwenden von Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Einrichten des CQD](turning-on-and-using-call-quality-dashboard.md)

[Verwalten der Anruf- und Besprechungsqualität in Teams](quality-of-experience-review-guide.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)