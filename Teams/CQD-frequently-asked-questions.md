---
title: Anrufqualitätsdashboard (CQD) Häufig gestellte Fragen (FAQ)
ms.author: serdars
author: SerdarSoysal
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
description: Lesen Sie häufig gestellte Fragen (FAQ) und Antworten zu Microsoft Teams Call Quality Dashboard (CQD).
ms.openlocfilehash: 3b527b32e194b531be5003c5f8b180a00976cf8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111531"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Anrufqualitätsdashboard (CQD) Häufig gestellte Fragen (FAQ)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

[Warum wird ein Anruf von CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Warum wird eine Differenz von bis zu 0,2 % bei Anruf- und Benutzeranzahlwerten für Measures angezeigt und wie kann ich die genauesten Volumina erhalten? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Warum unterscheiden sich CQD-Daten aus Skype for Business von CQD-Daten von Teams? ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Warum wird EUII in CQD nicht sehen?](#why-cant-i-see-euii-in-cqd)

[Warum werden Skype for Business-Informationen in CQD angezeigt, wenn ich nur nach Teams gefiltert habe?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es weitere Einträge geben sollte?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Warum wird ein Anruf von CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?

Schauen Sie sich die Regeln an, die CQD für die [Datenstromklassifizierung verwendet.](stream-classification-in-call-quality-dashboard.md)
 
Bei Audiodatenströmen kann jeder der fünf Klassifikatoren, die für den Mittelwert basierend auf der Länge des Aufrufs berechnet werden, innerhalb von "guten" Parametern liegen. Dies bedeutet nicht, dass die Benutzer etwas nicht gefunden haben, das zu einem Audio-Drop-Out, statischen oder Glitch beigetragen hat. 

Wenn Sie ermitteln möchten, ob es sich um ein Netzwerkproblem gab, sehen Sie sich das Delta zwischen den Durchschnittswerten für die Sitzung und den maximalen Werten an. Max. Werte sind die maximal erkannten und während der Sitzung gemeldeten Werte.
 
Hier ist ein Beispiel für die Problembehandlung dieser Situation. Angenommen, Sie nehmen während eines Anrufs eine Netzwerkverfolgung an, und in den ersten 20 Minuten gibt es keine verlorenen Pakete, aber dann haben Sie eine Lücke von 1,5 Sekunden Paketen und sind dann für den Rest des Anrufs gut. Der Durchschnitt beträgt <10 % (0,1) Paketverlust selbst bei einer RTP-Analyse der Wireshark-Ablaufverfolgung. Was war der max. Paketverlust? 1,5 Sekunden in einem Zeitraum von 5 Sekunden wären 30 % (0,3). Ist dies innerhalb des fünf zweiten Stichprobenzeitraums geschehen (möglicherweise oder könnte er über den Stichprobenzeitraum aufgeteilt werden)?
 
Wenn Die Netzwerkmetriken in den Mittelwerten und max. Werten gut aussehen, sehen Sie sich andere Telemetriedaten an: 
- Überprüfen Sie CPU Insufficient Event Ratio, um zu überprüfen, ob die erkannten CPU-Ressourcen nicht ausreichend waren und eine schlechte Qualität verursacht haben. 
- Wurde das Audiogerät im Halbduplexmodus verwendet, um Feedback aufgrund von Mikrofonen zu verhindern, die sich in der Nähe von Lautsprechern befinden? 
- Überprüfen Sie das Geräte-Halbduplex-AEC-Ereignisverhältnis. Wurde beim Anschließen an einen Hub oder eine Dockingstation das Gerät bzw. das Mikrofon aufgrund von USB-Audio-Drop-Outs mit Geräuschen oder statischen Geräuschen oder statischen Geräuschen verbunden:  
- Überprüfen Sie die Ereignisverhältnisse "Geräteschleichen" und "Mikrofon". Funktionierte das Gerät selbst ordnungsgemäß?  
- Überprüfen Sie die Ereignisverhältnisse "Aufnahme- und Rendergerät nicht funktionsfähig".


Weitere Informationen zu Dimensionen und Measures, die in der CQD-Telemetrie verfügbar sind, finden Sie unter Abmessungen und Maße, die [im Anrufqualitätsdashboard verfügbar sind.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Überprüfen Sie für Hintergrundgeräusche das Stummschaltereignisverhältnis, um die Dauer der Stummschaltung der Teilnehmer zu sehen.
 
Erstellen Sie detaillierte Berichte in CQD, und filtern Sie nach Besprechungs-ID, um alle Benutzer und Datenströme in einer Besprechung zu betrachten und die Felder hinzuzufügen, die Sie interessieren. Ein Benutzer, der das Problem meldet, ist möglicherweise nicht der Benutzer, der das Problem hatte. Sie berichten lediglich über die Erfahrung.
 
Die Telemetrie führt das Problem nicht unbedingt auf, kann Ihnen aber helfen, besser zu verstehen, wo Sie Ihre Entscheidungen suchen und informieren können. Handelt es sich um Netzwerk-, Geräte-, Treiber- oder Firmwareupdates, die Nutzung oder den Benutzer?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Warum wird eine Differenz von bis zu 0,2 % bei Anruf- und Benutzeranzahlwerten für Measures angezeigt und wie kann ich die genauesten Volumina erhalten? 
Zum Berechnen von Anrufanzahl- und Benutzeranzahlskennzeichen wird ein eindeutiger Countif-Vorgang für den Aufruf oder benutzerbezeichner im Datensatz ausgeführt. Bei großen Datensätzen gibt es einen Fehler von bis zu 0,2 %, der dem eindeutigen Countif-Vorgang innewohnt. Für die genaueste Lautstärke sollten Sie sich auf Datenstromanzahl-Measures verlassen, da sie nicht auf diesem eindeutigen Zählenwenn-Vorgang angewiesen sind. Das Filtern zur Verringerung des Datenvolumens kann den Fehler verringern, diese Fehlerquelle jedoch nicht in unterschiedlichen Aufruf- und Benutzeranzahlen beseitigen. Weitere Informationen [finden Sie unter Abmessungen und Maße, die im Anrufqualitätsdashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) verfügbar sind, für die Measures betroffen sind.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Warum unterscheiden sich CQD-Daten aus Skype for Business von CQD-Daten von Teams? 


> [!IMPORTANT]
> Seit dem 1. Juli 2020 verwendet der ältere CQD (CQD.lync.com) Daten aus dem neuesten CQD (CQD. Teams.microsoft.com). Die älteren CQD-Daten sind nicht mehr verfügbar, und Sie können Ihre Gebäude- oder Berichtsdaten nicht exportieren. Sie können die CQD.lync.com (über das Skype for Business Admin Center verfügbar) verwenden, aber wir werden den Zugriff auf CQD.lync.com bald deaktivieren, daher sollten Sie zu CQD wechseln. Teams.microsoft.com, wenn Sie dies noch nicht getan haben.


Wenn Sie versuchen, Daten zwischen dem älteren CQD aus dem Skype for Business Legacy Portal (cqd.lync.com) und dem neuesten CQD aus dem Teams Admin Center (cqd.teams.microsoft.com) zu vergleichen, werden Sie schnell feststellen, dass die Daten nicht übereinstimmen. Der Grund dafür ist, dass die neuesten CQD-Berichte über viele weitere Anrufszenarien berichten. Wenn Sie weiterhin Berichte aus dem älteren CQD verwenden, verwenden Sie diesen Artikel, um Sie bei der Interpretation dieser Berichte zu unterstützen: Anrufqualitätsdashboard [für Skype for Business Server](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard).


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum wird EUII in CQD nicht sehen?

Diese Administratorrollen können auf CQD zugreifen, aber sie können EUII (identifizierbare Informationen für Endbenutzer) nicht anzeigen:
- Microsoft 365 Reports Reader
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf CQD zugreifen können , einschließlich EUII, finden Sie unter Zuweisen von Rollen für den Zugriff [auf CQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden Skype for Business-Informationen in CQD angezeigt, wenn ich nur nach Teams gefiltert habe?

Wenn Sie nur in CQD-Berichten nach Teams filtern (istTeams = 1), filtern Sie nach allen Anrufen, bei denen der *erste* Endpunkt Teams ist. Wenn der *zweite Endpunkt* Skype for Business ist, werden diese Informationen in Ihrem CQD-Bericht gezeigt.

CQDv2 und CQDv3 haben immer unterschiedliche Gesamtanzahlen, da CQDv3 neue Szenarien hat, die CQDv2 nicht hat. Aus diesem Grund hat der Vergleich von Zusammenfassungssummen- oder Aggregierten Gesamtzahlen ohne Filter diese erwarteten Unterschiede.  

Je nach Kundenszenario umfasst CQDv3 lokale SFB 2019-Anrufe (wenn SFB 2019 mit einem Datenconnector verwendet wird), Skype #A0 (AA, CVI, VDI), Liveereignisse und PSTN-Anrufe. Szenarien/Features, die für die Kunden verfügbar sind, deren Daten sich jedoch nicht in CQD V2 befinden.

Es wird beispielsweise erwartet, dass Ihre Kunden und Sie 200.000 Audiodatenströme mit 5000 Fehlern im Zusammenfassungsbericht von CQD V2 sehen. im Vergleich zu 300.000 Audiodatenströmen mit 5500 Fehlern (die von 2019-Vorabanrufen, #A0, #A0 usw.) in CQD V3 kommen.

Um festzustellen, ob unerwartete Unterschiede bestehen, müssen Sie sich verschiedene Aufschlüsselungen der Gesamtdaten anschauen.  Vergleichen Sie mit Absicht.  Das Zuordnen der Daten nach Benutzer-Agent-Kategoriepaar ist eines der ersten Dinge, die wir empfehlen.  *First Product* und *Second Product* sind auch gute Datenschnitte.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es weitere Einträge geben sollte?

CQD ist für zusammengefasste Datenabfragen konzipiert und nicht für den Datenexport ausgelegt. Wir empfehlen, Ihre Berichte nach Möglichkeit neu zu strukturieren, um zu verhindern, dass das Limit von 10.000 Zeilen überschritten wird. Sehen Sie sich zunächst Ihre KPIs mit breiteren, niedrigeren Kardinalitätsdimensionen an, z. B. Monat, Jahr, Datum, Region, Land usw. Von dort aus können Sie einen Drilldown zu immer höheren Kardinalitätsdimensionen erstellen. Das Helpdesk und Location-Enhanced-Berichte bieten gute Beispiele für diesen Drilldownworkflow.

## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)