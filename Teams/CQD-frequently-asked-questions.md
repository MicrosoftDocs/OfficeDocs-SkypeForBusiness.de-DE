---
title: Anruf Qualitäts-Dashboard (CQD) – häufig gestellte Fragen (FAQ)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lesen Sie häufig gestellte Fragen (FAQ) und Antworten zum Microsoft Teams Call Quality Dashboard (CQD).
ms.openlocfilehash: 43dd0f85c21914320ff48c2e0aab82614670ff90
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372124"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Anruf Qualitäts-Dashboard (CQD) – häufig gestellte Fragen (FAQ)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

[Warum markiert CQD einen Anruf als "gut", wenn ein oder mehrere Besprechungsteilnehmer schlechte Erfahrungen gemacht haben?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Warum sehe ich Unterschiede bei der Anruf-und Benutzeranzahl von bis zu 0,2% für Measures und wie erhalte ich die meisten exakten Volumes?](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Warum unterscheiden sich CQD-Daten von Skype for Business von CQD-Daten aus Teams?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Warum kann ich EUII in CQD nicht sehen?](#why-cant-i-see-euii-in-cqd)

[Warum werden in CQD Skype for Business-Informationen angezeigt, wenn ich nur für Teams gefiltert habe?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Warum markiert CQD einen Anruf als "gut", wenn ein oder mehrere Besprechungsteilnehmer schlechte Erfahrungen gemacht haben?

Schauen Sie sich die Regeln an, die CQD für die [Datenstrom Klassifizierung](stream-classification-in-call-quality-dashboard.md)verwendet.
 
Bei Audiostreams können alle 5 Klassifizierungen, die für den Mittelwert auf der Grundlage der Länge des Anrufs berechnet werden, alle innerhalb der "guten" Parameter liegen. Das bedeutet nicht, dass die Benutzer etwas nicht erlebt haben, das zu einem Audio-Drop-Out, statisch oder glitch beigetragen hat. 

Wenn Sie feststellen möchten, ob es sich um ein Netzwerkproblem handelt, schauen Sie sich das Delta zwischen den Mittelwerten für die Sitzung und den Max-Werten an. Max-Werte sind das Maximum, das während der Sitzung erkannt und gemeldet wurde.
 
Im folgenden finden Sie ein Beispiel für die Behandlung dieser Situation. Angenommen, Sie nehmen eine Netzwerkablaufverfolgung während eines Anrufs vor, und die ersten 20 Minuten gibt es keine verlorenen Pakete, aber dann haben Sie eine Lücke von 1,5 Sekunden Pakete und sind dann für den Rest des Anrufs gut. Der Mittelwert wird <10% (0,1)-Paketverlust auch in einer wireshark-Ablaufverfolgungs-RTP-Analyse sein. Was war der maximale Paketverlust? 1,5 Sekunden in einem Zeitraum von 5 Sekunden betragen 30% (0,3). Geschah dies innerhalb der fünf Sekunden-Stichproben Periode (vielleicht, oder Sie kann über den Stichproben Zeitraum aufgeteilt werden)?
 
Wenn die Netzwerk Metrik im Mittelwert und im Höchstwert gut aussieht, suchen Sie nach anderen Telemetrie-Daten: 
- Überprüfen Sie, ob die verfügbaren CPU-Ressourcen unzureichend sind und zu schlechter Qualität geführt haben. 
- War das Audiogerät im Halb Duplex Modus, um Feedback durch Mikrofone zu verhindern, die sich in der Nähe von Lautsprechern befinden? 
- Überprüfen Sie das Gerät Halb Duplex-AEC-Ereignis Verhältnis. War das Gerät Glitching oder das Mikrofon Glitching Einführung Rauschen oder statisch aufgrund von USB-Audio-Drop-outs beim Einstecken an einen Hub oder eine Docking-Station:  
- Überprüfen Sie die Ereignis Verhältnisse für Geräte Pannen und Mikrofon Störungen. Funktioniert das Gerät ordnungsgemäß?  
- Überprüfen Sie die Ereignis Verhältnisse für das Aufzeichnen und Rendern von Geräten, die nicht funktionieren.


Weitere Informationen zu den Dimensionen und Maßen, die in der CQD-Telemetrie verfügbar sind, finden Sie [im Dashboard für die Anrufqualität](dimensions-and-measures-available-in-call-quality-dashboard.md).

Für Hintergrundgeräusche aktivieren Sie das Kontrollkästchen "stumm schalten", um festzustellen, wie lange die Teilnehmer stumm geschaltet wurden.
 
Erstellen Sie detaillierte Berichte in CQD, und Filtern Sie nach Besprechungs-ID, um alle Benutzer und Datenströme in einer Besprechung zu sehen und die Felder hinzuzufügen, die Sie interessieren. Ein Benutzer, der das Problem meldet, ist möglicherweise nicht derjenige, der das Problem verursacht hat. Sie melden gerade die Erfahrung.
 
Die Telemetrie Ruft das Problem nicht unbedingt auf, aber es kann Ihnen helfen, besser zu verstehen, wo ihre Entscheidungen zu suchen sind. Handelt es sich um Netzwerk-, Geräte-, Treiber-oder Firmware-Updates, Verwendung oder Benutzer?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Warum sehe ich Unterschiede bei der Anruf-und Benutzeranzahl von bis zu 0,2% für Measures und wie erhalte ich die meisten exakten Volumes? 
Zum Berechnen der Anzahl von aufrufen und der Anzahl der Benutzer zählen wird ein unterschiedlicher ZÄHLENWENN-Vorgang für den Anruf oder die Benutzer-IDs in der Datengruppe ausgeführt. Bei umfangreichen Datensätzen liegt ein Fehler von bis zu 0,2% vor, der dem unterschiedlichen ZÄHLENWENN-Vorgang inhärent ist. Für die genaueste Lautstärke sollten Sie sich auf die Datenstromanzahl-Measures verlassen, da Sie nicht auf diesen eindeutigen ZÄHLENWENN-Vorgang angewiesen sind. Durch Filtern, um die Datenmenge zu verringern, kann der Fehler reduziert werden, diese Fehlerquelle kann jedoch nicht in unterschiedlichen Anruf-und Nutzerzahlen beseitigt werden. Beziehen Sie sich auf [Dimensionen und Maße, die im Dashboard für die Anrufqualität zur Verfügung stehen](dimensions-and-measures-available-in-call-quality-dashboard.md) , für die Maßnahmen betroffen sind.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Warum unterscheiden sich CQD-Daten von Skype for Business von CQD-Daten aus Teams? 


> [!IMPORTANT]
> Ab dem 1. Juli 2020 verwendet der ältere CQD (CQD.lync.com) Daten aus dem neuesten CQD (CQD. Teams.Microsoft.com). Die älteren CQD-Daten stehen nicht mehr zur Verfügung, und Sie können ihre Gebäude-oder Berichtsdaten nicht exportieren. Sie können weiterhin CQD.lync.com verwenden (im Skype for Business Admin Center verfügbar), aber wir werden den Zugriff auf CQD.lync.com bald deaktivieren, sodass Sie zu CQD wechseln sollten. Teams.Microsoft.com, wenn dies noch nicht geschehen ist.


Wenn Sie versuchen, Daten zwischen den älteren CQD aus dem Skype for Business Legacy-Portal (CQD.lync.com) und dem neuesten CQD aus dem Team Admin Center (CQD.Teams.Microsoft.com) zu vergleichen, werden Sie schnell feststellen, dass die Daten nicht übereinstimmen. Das liegt daran, dass die neuesten CQD-Berichte über viele zusätzliche Anrufszenarien erstellt werden. Wenn Sie weiterhin Berichte aus dem älteren CQD verwenden, verwenden Sie diesen Artikel, um Sie bei der Interpretation dieser Berichte zu unterstützen: [Anruf Qualitäts Dashboard für Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum kann ich EUII in CQD nicht sehen?

Diese Administratorrollen können auf CQD zugreifen, aber Sie können EUII (Endbenutzer identifizierbare Informationen) nicht anzeigen:
- Microsoft 365-berichtsleser
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf CQD zugreifen können – einschließlich EUII-Read [Zuweisen von Rollen für den Zugriff auf CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden in CQD Skype for Business-Informationen angezeigt, wenn ich nur für Teams gefiltert habe?

Wenn Sie nur in CQD-Berichten (isteams = 1) nach Teams filtern, Filtern Sie nach allen anrufen, wobei der *erste Endpunkt* Teams ist. Wenn es sich bei dem *zweiten Endpunkt* um Skype for Business handelt, werden diese Informationen in Ihrem CQD-Bericht angezeigt.

CQDv2 und CQDv3 haben immer unterschiedliche Gesamtanzahlen, da CQDv3 neue Szenarien hat, die CQDv2 nicht haben wird. Aus diesem Grund werden die erwarteten Unterschiede zwischen Zusammenfassungs-oder aggregierten Gesamtzahlen ohne Filter angezeigt.  

Je nach Kundenszenario umfasst CQDv3 SFB 2019 lokale Anrufe (wenn SFB 2019 mit einem Daten-Konnektor verwendet wird), Skype-bot-Anrufe (AA, CVI, VDI), Live-Events und PSTN-Anrufe. Szenarien/Features, die für die Kunden verfügbar sind, aber Ihre Daten nicht in CQD v2 vorhanden sind.

Es wird beispielsweise erwartet, dass Ihre Kunden und Sie 200.000-Audiostreams mit 5000-Fehlern in CQD v2-Zusammenfassungsbericht sehen können. im Vergleich zu 300.000-Audiostreams mit 5500-Fehlern (von 2019 auf-Prem-anrufen, CVI-anrufen, PSTN-anrufen usw.) in CQD v3.

Um festzustellen, ob unerwartete Unterschiede auftreten, müssen Sie verschiedene Aufschlüsselungen der Gesamtdaten beachten.  Mit Absicht vergleichen.  Das Aufteilen der Daten nach Benutzer-Agent-Kategorie-Paaren ist eine der ersten Schritten, die wir empfehlen.  Das *erste Produkt* und das *zweite Produkt* sind ebenfalls gute datenschnitte.  


## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Dashboards für die Anrufqualität (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten-und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und-Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten von Anruf-und Besprechungs Qualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Datenstrom Klassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)