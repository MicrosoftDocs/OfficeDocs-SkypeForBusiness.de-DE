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
ms.openlocfilehash: bd36fe70d46a190289749a96fbaadb8f6c176251
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457175"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Häufig gestellte Fragen (FAQ) zum Anrufqualitätsdashboard (CQD)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

[Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Warum sehe ich bis zu 0,2 % Differenz bei Anruf- und Benutzeranzahl-Werten für Measures und wie kann ich genaueste Datenmengen erhalten? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Warum wird EUII im CQD nicht gefunden?](#why-cant-i-see-euii-in-cqd)

[Ich versuche, das AQD für Nutzungstypberichte zu verwenden, und finde, dass einige Daten unvollständig sind. Warum ist das der Grund?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Warum werden in Skype for Business AQD Informationen angezeigt, wenn ich nur nach einer Teams habe?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es mehr Einträge geben soll?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Warum werden Wi-Fi VPN-Verbindungen als "Verkabelt" statt als "WLAN" angezeigt?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Ich habe in Teams Richtlinienbasierte Aufzeichnung aktiviert, und jetzt werden Peer-to-Peer-Anrufe als Konferenzen gekennzeichnet – was ist geschehen?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?

Sehen Sie sich die Regeln an, die das AQD für die [Datenstromklassifizierung verwendet](stream-classification-in-call-quality-dashboard.md).
 
Bei Audiodatenströmen kann jede der fünf Klassifizierungen (die basierend auf der Länge des Anrufs für den Mittelwert berechnet werden) innerhalb "guter" Parameter liegen. Es bedeutet nicht, dass bei den Benutzern keine Probleme auft worden sind, die zu einem Audio-Drop-Out, einer statischen oder einer  Störung bei der Audiowiedergabe beigetragen haben. 

Um festzustellen, ob es sich um ein Netzwerkproblem war, sehen Sie sich das Delta zwischen den Durchschnittswerten für die Sitzung und den Max-Werten an. Max-Werte sind die während der Sitzung maximal erkannten und gemeldeten Werte.
 
Hier ist ein Beispiel für die Problembehandlung in dieser Situation. Angenommen, Sie nehmen während eines Anrufs eine Netzwerkverfolgung an, und in den ersten 20 Minuten gibt es keine verlorenen Pakete, doch besteht dann eine Lücke von 1,5 Sekunden Paketen, die dann für den Rest des Anrufs gut sind. Der Durchschnitt wird selbst in einer RTP-Analyse der Wireshark-Ablaufverfolgung <10 % (0,1) Paketverlust betragen. Wie war der Maximale Paketverlust? 1,5 Sekunden in einer 5-Sekunden-Periode waren 30 % (0,3). Ist dies innerhalb des 5-Sekunden-Samplingzeitraums (möglicherweise oder kann über den Stichprobenzeitraum aufgeteilt) erfolgt?
 
Wenn die Netzwerkmetriken bei Mittelwerten und Max-Werten gut aussehen, dann sehen Sie sich andere Telemetriedaten an: 
- Überprüfen Sie das unzureichende Ereignisverhältnis der CPU, um zu überprüfen, ob die erkannten CPU-Ressourcen nicht ausreichend waren und eine schlechte Qualität verursacht haben. 
- War das Audiogerät im Halbduplexmodus, um Feedback aufgrund von Mikrofonen zu nah an den Lautsprechern zu verhindern? 
- Überprüfen Sie das Geräte-AEC-Ereignisverhältnis halber Duplex-AEC. Gab es Lästerungen von einem Gerät wie einem Mikrofon, durch das Rauschen oder statische Rauschen aufgrund von USB-Audio-Drop-Outs, wenn sie an einen Hub oder eine Dockingstation angeschlossen wurden?  
- Überprüfen Sie die Geräte-Störungen und Mikrofon-Störungen des Ereignisverhältnisses. Funktionierte das Gerät selbst ordnungsgemäß?  
- Überprüfen Sie die Ereignisverhältnisse des Aufnahme- und Rendergeräts "Not Functioning".


Weitere Informationen zu den in der CQD-Telemetrie verfügbaren Dimensionen und Measures finden Sie unter Verfügbare Dimensionen und Maße [im Anrufqualitätsdashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).

Überprüfen Sie für Hintergrundgeräusche das Verhältnis für stummgeschaltete Ereignisse, um die Dauer der Stummschaltung der Teilnehmer zu sehen.
 
Erstellen Sie detaillierte Berichte im AQD, und filtern Sie nach Besprechungs-ID, um alle Benutzer und Datenströme in einer Besprechung zu sehen und die Felder hinzuzufügen, die Sie interessieren. Ein Benutzer, der das Problem meldet, ist möglicherweise nicht der Benutzer, der das Problem behoben hat. Sie melden lediglich die Erfahrung.
 
Die Telemetrie wird das Problem nicht zwangsläufig auf sich herausrufen, aber Sie können besser verstehen, wo Sie Ihre Entscheidungen suchen und darüber informieren sollten. Handelt es sich um Netzwerk-, Geräte-, Treiber- oder Firmwareupdates, die Nutzung oder den Benutzer?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Warum sehe ich bis zu 0,2 % Differenz bei Anruf- und Benutzeranzahl-Werten für Measures und wie kann ich genaueste Datenmengen erhalten? 

Um Kennzahl- und Benutzeranzahl-Kenndaten zu berechnen, wird für den Aufruf oder die Benutzer-IDs im Datenset ein eindeutiger Zählenwenn-Vorgang ausgeführt. Bei großen Datenmengen tritt ein Fehler von bis zu 0,2 % auf, der dem eindeutigen ZählenWENN-Vorgang entspricht. Für die genaueste Lautstärke sollten Sie sich auf Datenstromanzahl-Measures verlassen, da diese nicht von diesem eindeutigen Zählenwenn-Vorgang angewiesen sind. Das Filtern zur Verringerung des Datenvolumens kann den Fehler zwar verringern, diese Fehlerquelle jedoch nicht in eindeutigen Aufrufen und bei der Anzahl der Benutzer beseitigen. Weitere Informationen finden [Sie unter Verfügbare Dimensionen und Maße im Anrufqualitätsdashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) , für die Measures betroffen sind.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum wird EUII im CQD nicht gefunden?

Diese Administratorrollen können auf das AQD zugreifen, sie können jedoch nicht EUII (Identifizierbare Informationen für Endbenutzer) anzeigen:

- Microsoft 365 bericht-Leser
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf das AQD zugreifen können –, einschließlich EUII – finden Sie unter Zuweisen von Rollen für [den Zugriff auf das AQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>Ich versuche, das AQD für Nutzungstypberichte zu verwenden, und finde, dass einige Daten unvollständig sind. Warum ist das der Grund?

Anrufqualitätsverwaltungstools wie CQD, Anrufanalyse, Anrufdatensatz-Graph-API und Echtzeitanalyse basieren auf Diagnose telemetrie. Die Informationen, die in Teams Qualitätsverwaltungstools für Anrufe angezeigt werden, sind nur so vollständig wie die Telemetriedaten, die wir von den an einem Anruf teilnehmenden Clients erhalten. Es gibt mehrere Gründe, warum wir möglicherweise keine vollständige Telemetrie erhalten, z. B. Netzwerkausfälle oder Firewall- oder [Proxy-Falschkonfigurationen](/microsoft-365/enterprise/urls-and-ip-address-ranges.md). Wir arbeiten kontinuierlich an der Verbesserung der Zuverlässigkeit und Resilienz, mit der Teams dem Dienst Telemetrie bereitstellen.

In diesem Sinne wird die Verwendung von Tools für die Anrufqualitätsverwaltung für die Verwendungsberichte nicht unterstützt. Sie sind weder für diese Arten von Berichterstellungsszenarien noch für diese vorgesehen, und viele Nutzungsstatistiken sind in diesen Tools nicht verfügbar und stehen auch nicht zur Verfügung. Teams Admin Center bietet eine Reihe [von Verwendungsberichten](teams-analytics-and-reports/teams-reporting-reference.md), und ein Bericht [](teams-analytics-and-reports/meeting-attendance-report.md) zur Teilnahme an Besprechungen steht direkt vom Kunden Teams zur Verfügung.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden in Skype for Business AQD Informationen angezeigt, wenn ich nur nach einer Teams habe?

Wenn Sie nur in Teams AQD-Berichten nach Daten filtern (istTeams = 1), filtern Sie nach allen Anrufen, bei denen der erste Endpunkt  Teams. Wenn der *zweite Endpunkt* Skype for Business, werden diese Informationen in Ihrem AQD-Bericht gezeigt. Je nach Szenario des Kunden kann das Anruf-AQD Skype for Business Server 2019-Anrufe enthalten, wenn der Connector [für Anrufdaten](/skypeforbusiness/hybrid/plan-call-data-connector.md) konfiguriert ist. Dies kann auch Skype Bot-Anrufe (AA, CVI, VDI), Liveereignisse und PSTN-Anrufe umfassen.

Es ist möglich, alle Skype for Business aus Ihren Abfragen zu entfernen, indem Sie nach Dimensionen wie Der erste *Benutzer-Agent-Kategorie* und *zweite Benutzer-Agent-Kategorie filtern*. Sie können auch das *Benutzer-Agent-Kategoriepaar verwenden* , das die Dimensionen "Erster" und "Zweiter" zu einem einzigen Filter kombiniert.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es mehr Einträge geben soll?

Das CQD ist für zusammengefasste Datenabfragen konzipiert und nicht für den Datenexport. Es wird empfohlen, Die Berichte nach Möglichkeit zu verneinen, um zu verhindern, dass das Zeilenlimit von 10.000 Zeilen überschritten wird. Beginnen Sie, indem Sie Ihre KPIs unter Verwendung breiterer Dimensionen mit geringerer Kardinalität, z. B. Monat, Jahr, Datum, Region, Land, und so weiter, anzeigen. Von dort aus können Sie Drilldowns in Dimensionen mit zunehmender Kardinalität führen. Die Helpdesk- und Location-Enhanced-Berichte bieten beide gute Beispiele für diesen Drilldownworkflow.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Warum werden Wi-Fi VPN-Verbindungen als "Verkabelt" statt als "WLAN" angezeigt?

Dies ist ein erwartetes Verhalten. Der VPN-Anbieter hat einen virtuellen Ethernetadapter erstellt, der wie eine Kabelverbindung behandelt wird. Da er nicht ordnungsgemäß beschriftet ist, weiß das Betriebssystem nicht, dass es sich um eine Wi-Fi Verbindung, und meldet ihn als verkabelt.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Ich habe in Teams Richtlinienbasierte Aufzeichnung aktiviert, und jetzt werden Peer-to-Peer-Anrufe als Konferenzen gekennzeichnet – was ist geschehen?

Dies ist ein erwartetes Verhalten, wenn die richtlinienbasierte Aufzeichnung in einem Microsoft Teams. Für die richtlinienbasierte Aufzeichnung wird ein Teams-Recorder-Bot verwendet, der in Microsoft Azure zum Erfassen von Besprechungsinhalten zu Compliancezwecken bereitgestellt wird. Bei der Anrufqualitätsverwaltung ist "Peer-zu-Peer" eine Beschreibung des Fluss des Mediendatenverkehrs, nicht die Interaktion zwischen den Benutzern. Da ein Recorder Bot selbst eine Gesprächsparty ist, ist der Anruf kein Peer-to-Peer mehr, sondern ein Anruf von mehreren Parteien. Anrufe von mehreren Parteien werden nach Microsoft Teams als Konferenzen klassifiziert und daher als solche angezeigt, wenn Sie diese Anrufe im CQD und anderen Tools zur Anrufqualität anzeigen.

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
