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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Lesen Sie häufig gestellte Fragen (FAQ) und Antworten Microsoft Teams anrufqualitätsdashboard (CQD).
ms.openlocfilehash: 4d0d0bbbc35ac130755e61075408e9de80f1c09c
ms.sourcegitcommit: d976e49943aedd511bd6a80b02afeac4a6453406
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2021
ms.locfileid: "61362542"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ) zum Anrufqualitätsdashboard (CQD)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

[Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Warum sehe ich bis zu 0,2 % Differenz bei Anruf- und Benutzeranzahl-Werten für Measures und wie kann ich genaueste Datenmengen erhalten? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Warum wird EUII im CQD nicht gefunden?](#why-cant-i-see-euii-in-cqd)

[Warum werden in Skype for Business AQD Informationen angezeigt, wenn ich nur nach einer Teams habe?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es mehr Einträge geben soll?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Warum werden Wi-Fi VPN-Verbindungen als "Verkabelt" statt als "WLAN" angezeigt?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Ich habe in Teams Richtlinienbasierte Aufzeichnung aktiviert, und jetzt werden Peer-to-Peer-Anrufe als Konferenzen gekennzeichnet – was ist geschehen?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?

Sehen Sie sich die Regeln an, die das AQD für die [Datenstromklassifizierung verwendet.](stream-classification-in-call-quality-dashboard.md)
 
Für Audiodatenströme kann jede der fünf Klassifizierungen, die basierend auf der Länge des Anrufs für den Mittelwert berechnet werden, innerhalb "guter" Parameter liegen. Es bedeutet nicht, dass bei den Benutzern keine Probleme auft worden sind, die zu einem Audio-Drop-Out, einer statischen oder einer Störung bei der Audiowiedergabe beigetragen haben. 

Um festzustellen, ob es sich um ein Netzwerkproblem war, sehen Sie sich das Delta zwischen den Durchschnittswerten für die Sitzung und den Max-Werten an. Max-Werte sind die während der Sitzung maximal erkannten und gemeldeten Werte.
 
Hier ist ein Beispiel für die Problembehandlung in dieser Situation. Angenommen, Sie nehmen während eines Anrufs eine Netzwerkverfolgung an, und in den ersten 20 Minuten gibt es keine verlorenen Pakete, doch besteht dann eine Lücke von 1,5 Sekunden Paketen, die dann für den Rest des Anrufs gut sind. Der Durchschnitt wird selbst in einer RTP-Analyse der Wireshark-Ablaufverfolgung <10 % (0,1) Paketverlust betragen. Wie war der Maximale Paketverlust? 1,5 Sekunden in einer 5-Sekunden-Periode waren 30 % (0,3). Ist dies innerhalb des 5-Sekunden-Samplingzeitraums (möglicherweise oder kann über den Stichprobenzeitraum aufgeteilt) erfolgt?
 
Wenn die Netzwerkmetriken bei Mittelwerten und Max-Werten gut aussehen, dann sehen Sie sich andere Telemetriedaten an: 
- Überprüfen Sie das unzureichende Ereignisverhältnis der CPU, um zu überprüfen, ob die erkannten CPU-Ressourcen nicht ausreichend waren und eine schlechte Qualität verursacht haben. 
- War das Audiogerät im Halbduplexmodus, um Feedback aufgrund von Mikrofonen zu verhindern, die sich in der Nähe der Lautsprecher befinden? 
- Überprüfen Sie das Geräte-AEC-Ereignisverhältnis halber Duplex-AEC. War die Geräte-Kopplung oder das Mikrofon aufgrund von USB-Audio-Drop-Outs, die an eine Hub- oder Dockingstation angeschlossen wurden, ein Rauschen oder ein statisches Mikrofon?  
- Überprüfen Sie die Geräte-Störungen und Mikrofon-Störungen des Ereignisverhältnisses. Funktionierte das Gerät selbst ordnungsgemäß?  
- Überprüfen Sie die Ereignisverhältnisse des Aufnahme- und Rendergeräts "Not Functioning".


Weitere Informationen zu den in der CQD-Telemetrie verfügbaren Dimensionen und Measures finden Sie unter Verfügbare Dimensionen und Maße [im Anrufqualitätsdashboard.](dimensions-and-measures-available-in-call-quality-dashboard.md)

Überprüfen Sie für Hintergrundgeräusche das Verhältnis für stummgeschaltete Ereignisse, um die Dauer der Stummschaltung der Teilnehmer zu sehen.
 
Erstellen Sie detaillierte Berichte im AQD, und filtern Sie nach Besprechungs-ID, um alle Benutzer und Datenströme in einer Besprechung zu betrachten und die Felder hinzuzufügen, die Sie interessieren. Ein Benutzer, der das Problem meldet, ist möglicherweise nicht der Benutzer, der das Problem behoben hat. Sie melden lediglich die Erfahrung.
 
Durch die Telemetrie wird das Problem nicht zwangsläufig behoben, aber Sie können besser verstehen, wo Ihre Entscheidungen zu suchen und zu informieren sind. Handelt es sich um Netzwerk-, Geräte-, Treiber- oder Firmwareupdates, die Nutzung oder den Benutzer?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Warum sehe ich bis zu 0,2 % Differenz bei Anruf- und Benutzeranzahl-Werten für Measures und wie kann ich genaueste Datenmengen erhalten? 

Um Kennzahl- und Benutzeranzahl-Kenndaten zu berechnen, wird für den Aufruf oder die Benutzer-IDs im Datenset ein eindeutiger Zählenwenn-Vorgang ausgeführt. Bei großen Datensätzen liegt der Fehler bei bis zu 0,2 % bei dem eindeutigen ZählenWENN-Vorgang. Für die genaueste Lautstärke sollten Sie sich auf Datenstromzähler-Measures verlassen, da diese nicht von diesem eindeutigen Zählenwenn-Vorgang angewiesen sind. Das Filtern zur Verringerung des Datenvolumens kann den Fehler zwar verringern, diese Fehlerquelle jedoch nicht in eindeutigen Aufrufen und bei der Anzahl der Benutzer beseitigen. Weitere Informationen finden [Sie unter Verfügbare Dimensionen und Maße im Anrufqualitätsdashboard,](dimensions-and-measures-available-in-call-quality-dashboard.md) für die Maße betroffen sind.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum wird EUII im CQD nicht gefunden?

Diese Administratorrollen können auf das AQD zugreifen, sie können jedoch nicht EUII (Identifizierbare Informationen für Endbenutzer) anzeigen:

- Microsoft 365 bericht-Leser
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf das AQD zugreifen können (einschließlich EUII), finden Sie unter Zuweisen von Rollen für den Zugriff auf [das AQD.](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden in Skype for Business AQD Informationen angezeigt, wenn ich nur nach Teams gefiltert habe?

Wenn Sie nur in Teams AQD-Berichten nach Nachrichten filtern (istTeams = 1), filtern Sie nach allen Anrufen, bei denen der erste Endpunkt Teams.  Wenn der *zweite Endpunkt* Skype for Business, werden diese Informationen in Ihrem AQD-Bericht enthalten sein.

CQDv2 und CQDv3 haben immer unterschiedliche Gesamtanzahlen, da CQDv3 neue Szenarien hat, die CQDv2 nicht haben wird. Aus diesem Grund können sie diese erwarteten Unterschiede zwischen Zusammenfassungssumme und aggregierten Zahlen ohne Filter haben.  

Je nach Kundenszenario enthält das CQDv3 lokale SFB 2019-Anrufe (wenn SFB 2019 mit einem Datenconnector verwendet wird), Skype-Bot-Anrufe (AA, CVI, VDI), Liveereignisse und PSTN-Anrufe. Szenarien/Features, die für Die Kunden zur Verfügung stehen, deren Daten sich jedoch nicht in CQD V2 befinden.

Es wird beispielsweise erwartet, dass Ihre Kunden 200.000 Audiodatenströme mit 5.000 Fehlern im Zusammenfassungsbericht für AQD V2 im Vergleich zu 300.000 Audiodatenströmen mit 5.500 Fehlern (aus 2019-Präm-Anrufen, CVI-Anrufen, PSTN-Anrufen und so weiter) im CQD V3 sehen.

Um zu ermitteln, ob unerwartete Unterschiede bestehen, müssen Sie sich verschiedene Aufschlüsselungen der Gesamtdaten anschauen.  Vergleichen Sie den Zweck.  Das Auflisten der Daten nach Benutzer-Agent-Kategoriepaar ist einer der ersten empfohlenen Dinge.  *First Product* und *Second Product* sind auch gute Datenschnitte.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es mehr Einträge geben soll?

Das CQD ist für zusammengefasste Datenabfragen konzipiert und nicht für den Datenexport. Es wird empfohlen, Die Berichte nach Möglichkeit zu verneinen, um zu verhindern, dass das Zeilenlimit von 10.000 Zeilen überschritten wird. Beginnen Sie, indem Sie Ihre KPIs unter Verwendung breiterer Dimensionen mit geringerer Kardinalität, z. B. Monat, Jahr, Datum, Region, Land, und so weiter, anzeigen. Von dort aus können Sie Drilldowns in Dimensionen mit zunehmender Kardinalität führen. Die Helpdesk- und Location-Enhanced-Berichte bieten beide gute Beispiele für diesen Drilldown-Workflow.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Warum werden Wi-Fi VPN-Verbindungen als "Verkabelt" statt als "WLAN" angezeigt?

Dies ist ein erwartetes Verhalten. Der VPN-Anbieter hat einen virtuellen Ethernetadapter erstellt, der wie eine Kabelverbindung behandelt wird. Da sie nicht ordnungsgemäß beschriftet ist, weiß das Betriebssystem nicht, dass es sich um eine Wi-Fi Verbindung, und meldet sie als verkabelt.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Ich habe in Teams Richtlinienbasierte Aufzeichnung aktiviert, und jetzt werden Peer-to-Peer-Anrufe als Konferenzen gekennzeichnet – was ist geschehen?

Dies ist ein erwartetes Verhalten, wenn die richtlinienbasierte Aufzeichnung in einem Microsoft Teams. Für die richtlinienbasierte Aufzeichnung wird ein Teams Recorder Bot verwendet, der in Microsoft Azure zum Erfassen von Besprechungsinhalten zu Compliancezwecken bereitgestellt wird. Da ein Recorder Bot selbst eine Gesprächsparty ist, ist der Anruf kein Peer-to-Peer mehr, sondern ein Anruf von mehreren Parteien. Anrufe von mehreren Parteien werden nach Microsoft Teams als Konferenzen klassifiziert und daher als solche angezeigt, wenn Sie diese Anrufe im AQD und anderen Tools zur Anrufqualität anzeigen.

## <a name="related-articles"></a>Verwandte Artikel

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
