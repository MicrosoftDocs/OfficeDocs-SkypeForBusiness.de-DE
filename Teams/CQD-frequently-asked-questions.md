---
title: Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) – Häufig gestellte Fragen (FAQ)
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
description: Lesen Sie häufig gestellte Fragen (FAQ) und Antworten zu Microsoft Teams Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD).
ms.openlocfilehash: f320bab549ee322c1254babd0feb49cc24419215
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823204"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Anrufqualitäts-Dashboard (Call Quality Dashboard, CQD) – Häufig gestellte Fragen (FAQ)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

[Warum kennzeichnet CQD einen Anruf als "Gut", wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Warum sehe ich bis zu 0,2% Unterschiede bei den Anruf- und Benutzeranzahlwerten für Measures und wie erhalte ich die genauesten Volumes? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Warum kann ich EUII im CQD nicht sehen?](#why-cant-i-see-euii-in-cqd)

[Ich versuche, CQD für Nutzungstypberichte zu verwenden, und finde, dass einige der Daten unvollständig sind - warum ist das so?](#im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that)

[Warum werden Skype for Business Informationen in CQD angezeigt, wenn ich nur nach Teams gefiltert habe?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass weitere Einträge vorhanden sein sollten?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

[Warum werden Wi-Fi VPN-Verbindungen anstelle von WLAN als verkabelt angezeigt?](#why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi)

[Ich habe die richtlinienbasierte Aufzeichnung in Teams aktiviert, und jetzt werden Peer-to-Peer-Anrufe als Konferenzen markiert – was ist passiert?](#i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Warum kennzeichnet CQD einen Anruf als "Gut", wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?

Schauen Sie sich die Regeln an, die CQD für die [Datenstromklassifizierung](stream-classification-in-call-quality-dashboard.md) verwendet.
 
Bei Audiodatenströmen kann jeder der fünf Klassifizierer (die für den Durchschnitt basierend auf der Länge des Aufrufs berechnet werden) alle in "guten" Parametern liegen. Dies bedeutet nicht, dass die Benutzer nicht etwas erlebt haben, das zu einem Audioabbruch, statischen Oder Glitch beigetragen hat. 

Um festzustellen, ob es sich um ein Netzwerkproblem handelte, sehen Sie sich das Delta zwischen den Durchschnittswerten für die Sitzung und den maximalen Werten an. Max.-Werte sind die maximal während der Sitzung erkannten und gemeldeten Werte.
 
Hier ist ein Beispiel für die Problembehandlung für diese Situation. Angenommen, Sie nehmen während eines Anrufs eine Netzwerkablaufverfolgung an, und in den ersten 20 Minuten gibt es keine verlorenen Pakete, aber dann haben Sie eine Lücke von 1,5 Sekunden pakete und dann gut für den Rest des Anrufs. Der Durchschnitt wird <10 % (0,1) Paketverlust selbst in einer RtP-Analyse der Wireshark-Ablaufverfolgung betragen. Was war der maximale Paketverlust? 1,5 Sekunden in einem Zeitraum von 5 Sekunden wären 30 % (0,3). Ist dies innerhalb des 5-Sekunden-Samplingzeitraums aufgetreten (oder konnte es über den Sampling-Zeitraum aufgeteilt werden)?
 
Wenn die Netzwerkmetriken in den Mittelwerten und Den maximalen Werten gut aussehen, suchen Sie nach anderen Telemetriedaten: 
- Überprüfen Sie das CPU-ungenügende Ereignisverhältnis, um festzustellen, ob die erkannten verfügbaren CPU-Ressourcen unzureichend waren und zu einer schlechten Qualität geführt haben. 
- War das Audiogerät im Half Duplex-Modus, um Feedback aufgrund von Mikrofonen zu nahe an Lautsprechern zu verhindern? 
- Überprüfen Sie das Halbduplex-AEC-Ereignisverhältnis des Geräts. War ein Glitzern von einem Gerät, z. B. einem Mikrofon, das Rauschen oder statisch verursacht, weil USB-Audio-Abbrüche auftreten, wenn sie an einen Hub oder eine Dockingstation angeschlossen sind?  
- Überprüfen Sie die Ereignisverhältnisse "Gerätefehler" und "Mikrofonfehler". Funktionierte das Gerät selbst ordnungsgemäß?  
- Überprüfen Sie die Ereignisverhältnisse für Aufnahme und Rendern von Geräten, die nicht funktionieren.


Weitere Informationen zu Dimensionen und Kennzahlen, die in der CQD-Telemetrie verfügbar sind, finden Sie [im Anrufqualitätsdashboard](dimensions-and-measures-available-in-call-quality-dashboard.md).

Überprüfen Sie für Hintergrundgeräusche das Verhältnis der Stummschaltungsereignisse, um zu sehen, wie lange die Teilnehmer stumm geschaltet wurden.
 
Erstellen Sie detaillierte Berichte in CQD, und filtern Sie nach der Besprechungs-ID, um alle Benutzer und Datenströme in einer Besprechung anzuzeigen und die felder hinzuzufügen, an der Sie interessiert sind. Ein Benutzer, der das Problem meldet, ist möglicherweise nicht der Benutzer, der das Problem hatte. Sie melden lediglich die Erfahrung.
 
Die Telemetrie wird das Problem nicht unbedingt aufklären, aber sie kann Ihnen helfen, besser zu verstehen, wo Sie Ihre Entscheidungen suchen und informieren müssen. Handelt es sich um Netzwerk-, Geräte-, Treiber- oder Firmwareupdates, -nutzung oder -Benutzer?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Warum sehe ich bis zu 0,2% Unterschiede bei den Anruf- und Benutzeranzahlwerten für Measures und wie erhalte ich die genauesten Volumes? 

Um die Anzahl der Aufrufe und die Anzahl der Benutzer zu berechnen, wird ein eindeutiger Countif-Vorgang für den Aufruf oder die Benutzerbezeichner im Dataset ausgeführt. Bei großen Datensätzen liegt ein Fehler von bis zu 0,2 % vor, der dem eindeutigen Countif-Vorgang zugeordnet ist. Für die genaueste Lautstärke sollten Sie sich auf Datenstromzählermaße verlassen, da diese nicht auf diesem eindeutigen Countif-Vorgang basieren. Das Filtern zur Verringerung des Datenvolumens kann den Fehler verringern, diese Fehlerquelle kann jedoch bei unterschiedlichen Aufrufen und Benutzeranzahlen nicht beseitigt werden. Weitere Informationen finden Sie [unter Dimensionen und Messungen, die im Anrufqualitätsdashboard verfügbar](dimensions-and-measures-available-in-call-quality-dashboard.md) sind, für welche Maßnahmen sie betroffen sind.

  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum kann ich EUII im CQD nicht sehen?

Diese Administratorrollen können auf CQD zugreifen, aber sie können EUII (Endbenutzer-identifizierbare Informationen) nicht anzeigen:

- Microsoft 365 Berichtsleser
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf CQD zugreifen können , einschließlich EUII, finden Sie unter [Zuweisen von Rollen für den Zugriff auf CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd).

### <a name="im-trying-to-use-cqd-for-usage-type-reports-and-find-that-some-of-the-data-is-incomplete----why-is-that"></a>Ich versuche, CQD für Nutzungstypberichte zu verwenden, und finde, dass einige der Daten unvollständig sind - warum ist das so?

Anrufqualitätsverwaltungstools wie CQD, Anrufanalyse, Anrufdatensatz-Graph-API und Echtzeitanalyse basieren auf Diagnosetelemetrie. Die Informationen, die wir in Teams Anrufqualitätsverwaltungstools anzeigen, sind nur so vollständig wie die Telemetriedaten, die wir von Kunden erhalten, die an einem Anruf teilnehmen. Es gibt mehrere Gründe, warum wir möglicherweise keine vollständige Telemetrie erhalten, z. B. Netzwerkausfälle oder [Firewall- oder Proxy-Fehlkonfigurationen](/microsoft-365/enterprise/urls-and-ip-address-ranges). Wir arbeiten weiterhin daran, die Zuverlässigkeit und Resilienz zu verbessern, mit der Teams Clients Telemetrie für den Dienst bereitstellen.

In diesem Sinne unterstützen wir nicht die Verwendung von Tools für das Anrufqualitätsmanagement für die Nutzungsberichterstattung. Sie sind weder für diese Arten von Berichtsszenarien konzipiert noch für diese vorgesehen, und viele Nutzungsstatistiken sind und werden in diesen Tools nicht verfügbar sein. Teams Admin Center bietet eine Reihe von [Nutzungsberichten](teams-analytics-and-reports/teams-reporting-reference.md), und ein [Anwesenheitsbericht über Besprechungen](teams-analytics-and-reports/meeting-attendance-report.md) ist direkt vom Teams-Client verfügbar.

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden Skype for Business Informationen in CQD angezeigt, wenn ich nur nach Teams gefiltert habe?

Wenn Sie nur in CQD-Berichten nach Teams filtern (isTeams = 1), filtern Sie nach allen Aufrufen, bei denen der *erste Endpunkt* Teams ist. Wenn der *zweite Endpunkt* Skype for Business ist, werden diese Informationen in Ihrem CQD-Bericht angezeigt. Abhängig von den Szenarien der Kunden kann das CQD Skype for Business Server 2019-Anrufe enthalten, wenn [der Anrufdatenconnector](/skypeforbusiness/hybrid/plan-call-data-connector) konfiguriert ist. Es kann auch Skype Bot-Anrufe (AA, CVI, VDI), Live-Ereignisse und PSTN-Anrufe enthalten.

Es ist möglich, Skype for Business Informationen aus Ihren Abfragen zu entfernen, indem Sie nach Dimensionen wie der *Kategorie "First User Agent"* und *"Second User Agent Category"* filtern. Sie können auch das *Benutzer-Agent-Kategoriepaar* verwenden, das die erste und zweite Dimension in einem einzigen Filter kombiniert.

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass weitere Einträge vorhanden sein sollten?

CQD ist für zusammengefasste Datenabfragen konzipiert und nicht für den Datenexport vorgesehen. Wir empfehlen, Ihre Berichte nach Möglichkeit neu zu strukturieren, um zu verhindern, dass der Grenzwert von 10.000 Zeilen überschritten wird. Sehen Sie sich zunächst Ihre KPIs mit breiteren, niedrigeren Kardinalitätsdimensionen an, z. B. Monat, Jahr, Datum, Region, Land usw. Von dort aus können Sie einen Drilldown in immer höhere Kardinalitätsdimensionen ausführen. Helpdesk- und Location-Enhanced-Berichte bieten beide gute Beispiele für diesen Drilldownworkflow.

### <a name="why-do-wi-fi-vpn-connections-show-as-wired-instead-of-wi-fi"></a>Warum werden Wi-Fi VPN-Verbindungen anstelle von WLAN als verkabelt angezeigt?

Dieses Verhalten wird erwartet. Der VPN-Anbieter hat einen virtuellen Ethernet-Adapter erstellt, der wie eine kabelgebundene Verbindung behandelt wird. Da die Bezeichnung nicht ordnungsgemäß ist, weiß das Betriebssystem nicht, dass es sich um eine Wi-Fi-Verbindung ist, und meldet sie als verkabelt.

### <a name="i-turned-on-policy-based-recording-in-teams-and-now-peer-to-peer-calls-are-being-marked-as-conferences----what-happened"></a>Ich habe die richtlinienbasierte Aufzeichnung in Teams aktiviert, und jetzt werden Peer-to-Peer-Anrufe als Konferenzen markiert – was ist passiert?

Dieses Verhalten wird erwartet, wenn die richtlinienbasierte Aufzeichnung in Microsoft Teams aktiviert ist. Die richtlinienbasierte Aufzeichnung verwendet einen in Microsoft Azure bereitgestellten Teams Recorder Bot, um Besprechungsinhalte zu Compliancezwecken zu erfassen. Im Anrufqualitätsmanagement ist "Peer-to-Peer" eine Beschreibung des Mediendatenverkehrsflusses und nicht der Interaktion zwischen den Benutzern. Da ein Recorder Bot selbst eine Partei des Anrufs ist, ist der Anruf nicht mehr Peer-to-Peer, sondern ein Anruf mit mehreren Teilnehmern. Anrufe mit mehreren Teilnehmern werden von Microsoft Teams als Konferenzen klassifiziert und werden daher als solche gekennzeichnet, wenn Sie diese Anrufe in CQD und anderen Anrufqualitätstools anzeigen.

## <a name="related-articles"></a>Verwandte Artikel

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitäts-Dashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[CQD-Daten und -Berichte](CQD-data-and-reports.md)

[Verwenden von CQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[In CQD verfügbare Dimensionen und Kennzahlen](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Streamklassifizierung in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von CQD-Daten](CQD-Power-BI-query-templates.md)

[Teams-Problembehandlung](/MicrosoftTeams/troubleshoot/teams)
