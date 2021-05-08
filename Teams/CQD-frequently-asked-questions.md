---
title: Häufig gestellte Fragen (FAQ) zum Anrufqualitätsdashboard (CQD)
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
description: Lesen Sie häufig gestellte Fragen (FAQ) und Antworten Microsoft Teams Anrufqualitäts-Dashboards (CQD).
ms.openlocfilehash: 3b527b32e194b531be5003c5f8b180a00976cf8e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111531"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ) zum Anrufqualitätsdashboard (CQD)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

[Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Warum sehe ich bis zu 0,2 % Differenz bei Anruf- und Benutzeranzahl-Werten für Measures und wie kann ich genaueste Mengen erhalten? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Warum unterscheiden sich AQD-daten Skype for Business CQD-Daten von Teams?](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Warum wird EUII im AQD nicht gefunden?](#why-cant-i-see-euii-in-cqd)

[Warum werden in Skype for Business AQD Informationen angezeigt, wenn ich nur nach Teams gefiltert habe?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es mehr Einträge geben soll?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?

Sehen Sie sich die Regeln an, die das AQD für die [Datenstromklassifizierung verwendet.](stream-classification-in-call-quality-dashboard.md)
 
Für Audiodatenströme kann jede der fünf Klassifizierungen, die basierend auf der Länge des Anrufs für den Mittelwert berechnet werden, innerhalb der "guten" Parameter liegen. Es bedeutet nicht, dass bei den Benutzern keine Probleme auft worden sind, die zu einem Audio-Drop-Out, einer statischen oder einer Störung bei der Audiowiedergabe beigetragen haben. 

Um festzustellen, ob es sich um ein Netzwerkproblem war, sehen Sie sich das Delta zwischen den Durchschnittswerten für die Sitzung und den Max-Werten an. Max-Werte sind die während der Sitzung maximal erkannten und gemeldeten Werte.
 
Hier ist ein Beispiel für die Problembehandlung in dieser Situation. Angenommen, Sie nehmen während eines Anrufs eine Netzwerkverfolgung an, und in den ersten 20 Minuten gibt es keine verlorenen Pakete, doch besteht dann eine Lücke von 1,5 Sekunden Paketen, die dann für den Rest des Anrufs gut sind. Der Durchschnitt wird selbst in einer RTP-Analyse der Wireshark-Ablaufverfolgung <10 % (0,1) Paketverlust betragen. Wie war der Maximale Paketverlust? 1,5 Sekunden in einer 5-Sekunden-Periode waren 30 % (0,3). Ist dies innerhalb des fünf zweiten Stichprobenzeitraums (möglicherweise oder kann innerhalb des Stichprobenzeitraums getrennt werden)?
 
Wenn die Netzwerkmetriken bei Mittelwerten und Max-Werten gut aussehen, dann sehen Sie sich andere Telemetriedaten an: 
- Überprüfen Sie das unzureichende Ereignisverhältnis der CPU, um zu überprüfen, ob die erkannten CPU-Ressourcen nicht ausreichend waren und eine schlechte Qualität verursacht haben. 
- War das Audiogerät im Halbduplexmodus, um Feedback aufgrund von Mikrofonen zu verhindern, die sich in der Nähe der Lautsprecher befinden? 
- Überprüfen Sie das Geräte-AEC-Ereignisverhältnis halber Duplex-AEC. War das Gerät aufgrund von Rauschen oder statischen Mikrofonen aufgrund von USB-Audio-Drop-Outs, die an eine Hub- oder Dockingstation angeschlossen wurden, zu Störgeräuschen oder statischen Ausstöpseln beim Anschließen an einen Hub oder eine Dockingstation:  
- Überprüfen Sie die Geräte-Störungen und Mikrofon-Störungen des Ereignisverhältnisses. Funktionierte das Gerät selbst ordnungsgemäß?  
- Überprüfen Sie die Ereignisverhältnisse des Aufnahme- und Rendergeräts "Not Functioning".


Weitere Informationen zu den in der CQD-Telemetrie verfügbaren Dimensionen und Measures finden Sie unter Verfügbare Dimensionen und Maße [im Anrufqualitätsdashboard.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Überprüfen Sie für Hintergrundgeräusche das Verhältnis für stummgeschaltete Ereignisse, um die Dauer der Stummschaltung der Teilnehmer zu sehen.
 
Erstellen Sie detaillierte Berichte im AQD, und filtern Sie nach Besprechungs-ID, um alle Benutzer und Datenströme in einer Besprechung zu sehen und die Felder hinzuzufügen, die sie interessieren. Ein Benutzer, der das Problem meldet, ist möglicherweise nicht der Benutzer, der das Problem behoben hat. Sie melden lediglich die Erfahrung.
 
Durch die Telemetrie wird das Problem nicht zwangsläufig auf den Ersten Blick errät, aber Sie können besser verstehen, wo Ihre Entscheidungen zu suchen und zu informieren sind. Handelt es sich um Netzwerk-, Geräte-, Treiber- oder Firmwareupdates, die Nutzung oder den Benutzer?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Warum sehe ich bis zu 0,2 % Differenz bei Anruf- und Benutzeranzahl-Werten für Measures und wie kann ich genaueste Mengen erhalten? 
Um Kennzahl- und Benutzeranzahl-Kenndaten zu berechnen, wird für den Aufruf oder die Benutzer-IDs im Datenset ein eindeutiger Zählenwenn-Vorgang ausgeführt. Bei großen Datensätzen liegt der Fehler bei bis zu 0,2 % bei der unterschiedlichen ZählenWENN-Operation. Für die genaueste Lautstärke sollten Sie sich auf Datenstromzähler-Measures verlassen, da diese nicht von diesem eindeutigen Zählenwenn-Vorgang angewiesen sind. Das Filtern zur Verringerung des Datenvolumens kann den Fehler zwar verringern, diese Fehlerquelle jedoch nicht in eindeutigen Aufrufen und bei der Anzahl der Benutzer beseitigen. Weitere Informationen finden Sie unter Verfügbare Dimensionen [und Maße im Anrufqualitätsdashboard,](dimensions-and-measures-available-in-call-quality-dashboard.md) für die Maße betroffen sind.


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Warum unterscheiden sich AQD-daten Skype for Business CQD-Daten von Teams? 


> [!IMPORTANT]
> Ab dem 1. Juli 2020 verwendet das ältere CQD (CQD.lync.com) Daten aus dem neuesten CQD (CQD.Teams.microsoft.com). Die älteren AQD-Daten sind nicht mehr verfügbar, und Sie können Ihre Gebäude- oder Berichtsdaten nicht exportieren. Sie können die CQD.lync.com (über das Skype for Business Admin Center verfügbar) weiterhin verwenden, aber wir werden den Zugriff auf CQD.lync.com bald deaktivieren, daher sollten Sie zum CQD wechseln. Teams.microsoft.com, wenn dies noch nicht geschehen ist.


Wenn Sie versuchen, Daten zwischen dem älteren AQD aus dem Skype for Business-Legacyportal (cqd.lync.com) und dem neuesten CQD aus dem Teams Admin Center (cqd.teams.microsoft.com) zu vergleichen, werden Sie schnell feststellen, dass die Daten nicht übereinstimmen. Der Grund dafür ist, dass das neueste AQD viele weitere Anrufszenarien meldet. Wenn Sie noch Berichte aus dem älteren AQD verwenden, verwenden Sie diesen Artikel als Hilfe bei der Interpretation dieser Berichte: Anrufqualitätsdashboard [für Skype for Business Server.](/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum wird EUII im AQD nicht gefunden?

Diese Administratorrollen können auf das AQD zugreifen, aber sie können EUII (identifizierbare Informationen für Endbenutzer) nicht anzeigen:
- Microsoft 365 Leser für Berichte
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf das AQD zugreifen können (einschließlich EUII), finden Sie unter Zuweisen von Rollen für den Zugriff auf [das AQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden in Skype for Business AQD Informationen angezeigt, wenn ich nur nach Teams gefiltert habe?

Wenn Sie nur Teams in AQD-Berichten filtern (istTeams = 1), filtern  Sie nach allen Anrufen, bei denen der erste Endpunkt Teams. Wenn der *zweite Endpunkt* Skype for Business, werden diese Informationen in Ihrem AQD-Bericht enthalten sein.

CQDv2 und CQDv3 haben immer unterschiedliche Gesamtzahlen, da CQDv3 neue Szenarien hat, die CQDv2 nicht haben wird. Aus diesem Grund können Sie zusammenfassungssummen- oder aggregierte Zahlen ohne Filter vergleichen, die diese erwarteten Unterschiede haben.  

Je nach Kundenszenario enthält das CQDv3 lokale SFB 2019-Anrufe (wenn SFB 2019 mit einem Datenconnector verwendet wird), Skype-Botanrufe (AA, CVI, VDI), Liveereignisse und PSTN-Anrufe. Szenarien/Features, die für Kunden verfügbar sind, deren Daten sich jedoch nicht in CQD V2 befinden.

Es wird beispielsweise erwartet, dass Ihre Kunden 200.000 Audiodatenströme mit 5.000 Fehlern im Zusammenfassungsbericht für AQD V2 sehen. im Vergleich zu 300.000 Audiodatenströmen mit 5.500 Fehlern (von 2019-Anrufen vor Ort, CVI-Anrufen, PSTN-Anrufen usw.) im CQD V3.

Um zu ermitteln, ob unerwartete Unterschiede bestehen, müssen Sie sich verschiedene Aufschlüsselungen der Gesamtdaten anschauen.  Vergleichen Sie den Zweck.  Das Auflisten der Daten nach Benutzer-Agent-Kategoriepaar ist einer der ersten empfohlenen Dinge.  *First Product* und *Second Product* sind auch gute Datenschnitte.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es mehr Einträge geben soll?

Das CQD ist für zusammengefasste Datenabfragen konzipiert und nicht für den Datenexport. Es wird empfohlen, Die Berichte nach Möglichkeit zu verneinen, um zu verhindern, dass das Zeilenlimit von 10.000 Zeilen überschritten wird. Beginnen Sie, indem Sie Ihre KPIs unter Verwendung umfangreicher Dimensionen mit geringerer Kardinalität, z. B. Monat, Jahr, Datum, Region, Land usw., anzeigen. Von dort aus können Sie drilldowns zu zunehmend höheren Kardinalitätsdimensionen führen. Die Helpdesk- und Location-Enhanced-Berichte bieten beide gute Beispiele für diesen Drilldown-Workflow.

## <a name="related-topics"></a>Verwandte Themen

[Verbessern und überwachen Sie die Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwalten der Anruf- und Besprechungsqualität mithilfe des Anrufqualitäts-AQD](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)