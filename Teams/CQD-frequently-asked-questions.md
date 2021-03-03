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
description: Lesen Sie häufig gestellte Fragen (FAQ) und Antworten zum Microsoft Teams Call Quality Dashboard (CQD).
ms.openlocfilehash: f622d197900faf632d94d659dae0a5b6eeaee2db
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110258"
---
# <a name="call-quality-dashboard-cqd-frequently-asked-questions-faq"></a>Anrufqualitätsdashboard (CQD) Häufig gestellte Fragen (FAQ)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

[Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?](#why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience)

[Warum sehe ich bei den Measures bis zu 0,2 % Differenz bei der Anruf- und Benutzeranzahl und wie kann ich die genaueste Lautstärke erhalten? ](#why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes)

[Warum unterscheiden sich CQD-Daten aus Skype for Business von CQD-Daten in Teams? ](#why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams)

[Warum wird EUII im CQD nicht sehen?](#why-cant-i-see-euii-in-cqd)

[Warum werden Skype for Business-Informationen im AQD angezeigt, wenn ich nur nach Teams gefiltert habe?](#why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only)

[Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es weitere Einträge geben soll?](#why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries)

### <a name="why-does-cqd-mark-a-call-as-good-if-one-or-more-meeting-participants-had-a-poor-experience"></a>Warum wird ein Anruf vom CQD als "Gut" bezeichnet, wenn ein oder mehrere Besprechungsteilnehmer eine schlechte Erfahrung hatten?

Sehen Sie sich die Regeln an, die das AQD für die [Datenstromklassifizierung verwendet.](stream-classification-in-call-quality-dashboard.md)
 
Für Audiodatenströme kann sich jede der fünf Klassifizierungen, die basierend auf der Länge des Aufrufs für den Mittelwert berechnet werden, innerhalb der "guten" Parameter befinden. Dies bedeutet nicht, dass bei den Benutzern etwas nicht zu einem Audio-Drop- oder statischen Audiosignal oder einer Panne beigetragen hat. 

Um festzustellen, ob es sich um ein Netzwerkproblem ging, sehen Sie sich das Delta zwischen den Durchschnittswerten für die Sitzung und den Maximalwerten an. Maximalwerte sind die während der Sitzung maximal erkannten und gemeldeten Werte.
 
Hier ist ein Beispiel für die Problembehandlung. Angenommen, Sie nehmen während eines Anrufs eine Netzwerkverfolgung an, und in den ersten 20 Minuten gibt es keine verlorenen Pakete, aber dann besteht eine Lücke von 1,5 Sekunden Paketen, die dann für den Rest des Anrufs gut sind. Der Durchschnitt beträgt <Paketverlust von 10 % (0,1) selbst bei einer RTP-Analyse der Wireshark-Ablaufverfolgung. Wie war der Maximale Paketverlust? 1,5 Sekunden in einem Zeitraum von 5 Sekunden waren 30 % (0,3). Ist dies innerhalb des fünf sekunden zeitraums der Stichprobe (möglicherweise oder kann sie über den Samplingzeitraum aufgeteilt werden)?
 
Wenn Die Netzwerkmetriken in den Mittelwerten und den Maximalwerten gut aussehen, dann suchen Sie nach anderen Telemetriedaten: 
- Überprüfen Sie das unzureichende Ereignisverhältnis der CPU, um zu überprüfen, ob die erkannten verfügbaren CPU-Ressourcen nicht ausreichend waren und eine schlechte Qualität verursacht haben. 
- War das Audiogerät im Halbduplexmodus, um Feedback aufgrund von Mikrofonen zu verhindern, die sich in der Nähe von Lautsprechern befinden? 
- Überprüfen Sie das Geräte-Halbduplex-AEC-Ereignisverhältnis. War die Gerätelärmung oder das Mikrofon aufgrund von USB-Audio-Drop-Outs, die an eine Hub- oder Dockingstation angeschlossen wurden, ein Rauschen oder statisches Geräusch:  
- Überprüfen Sie die Ereignisverhältnisse zwischen Geräte-Störungen und Mikrofon.. Funktionierte das Gerät selbst ordnungsgemäß?  
- Überprüfen Sie die Ereignisverhältnisse für Aufnahme und Rendergerät ohne Funktion.


Weitere Informationen zu den in der Telemetrie von AQD verfügbaren Dimensionen und Measures finden Sie im [Anrufqualitätsdashboard](dimensions-and-measures-available-in-call-quality-dashboard.md)unter "Abmessungen und Maße".

Überprüfen Sie für Hintergrundgeräusche das Verhältnis der Stummschaltung, um die Dauer der Stummschaltung der Teilnehmer zu sehen.
 
Erstellen Sie detaillierte Berichte im CQD, filtern Sie nach Besprechungs-ID, um alle Benutzer und Datenströme in einer Besprechung zu betrachten und die Felder hinzuzufügen, die Sie interessieren. Ein Benutzer, der das Problem meldet, ist möglicherweise nicht der Benutzer, der das Problem hatte. Sie melden lediglich die Erfahrung.
 
Die Telemetrie führt das Problem nicht unbedingt auf, aber sie hilft Ihnen, besser zu verstehen, wo Sie Ihre Entscheidungen suchen und darüber informieren sollten. Handelt es sich um Netzwerk-, Geräte-, Treiber- oder Firmwareupdates, die Nutzung oder den Benutzer?

### <a name="why-do-i-see-up-to-02-difference-in-call-and-user-count-values-on-measures-and-how-to-get-most-accurate-volumes"></a>Warum sehe ich bei den Measures bis zu 0,2 % Differenz bei der Anruf- und Benutzeranzahl und wie kann ich die genaueste Lautstärke erhalten? 
Um Kennzahl- und Kennzahl für Benutzer zu berechnen, wird ein eindeutiger Zählenwennvorgang für den Aufruf oder die Benutzerbezeichner im Datenset ausgeführt. Bei großen Datenmengen tritt ein Fehler von bis zu 0,2 % auf, der dem eindeutigen Zählenwenn-Vorgang innewohnt. Um die genaueste Lautstärke zu erhalten, sollten Sie sich auf Datenstromzähler als Maße verlassen, da diese nicht von diesem eindeutigen Zählenwenn-Vorgang beruhen. Das Filtern zur Verringerung des Datenvolumens kann den Fehler zwar verringern, diese Fehlerquelle jedoch nicht in eindeutigen Aufrufen und Benutzerzahlen beseitigen. Informationen zu [den im Anrufqualitätsdashboard](dimensions-and-measures-available-in-call-quality-dashboard.md) verfügbaren Dimensionen und Maßen, für die Maße betroffen sind


### <a name="why-is-cqd-data-from-skype-for-business-different-than-cqd-data-from-teams"></a>Warum unterscheiden sich CQD-Daten aus Skype for Business von CQD-Daten in Teams? 


> [!IMPORTANT]
> Ab dem 1. Juli 2020 verwendet das ältere AQD (CQD.lync.com) Daten aus dem neuesten AQD. Teams.microsoft.com). Die älteren AQD-Daten sind nicht mehr verfügbar, und Sie können ihre Gebäude- oder Berichtsdaten nicht exportieren. Sie können das CQD.lync.com (über das Skype for Business Admin Center verfügbar) weiterhin verwenden, aber wir werden den Zugriff auf CQD.lync.com bald deaktivieren, daher sollten Sie zum AQD wechseln. Teams.microsoft.com, wenn dies noch nicht geschehen ist.


Wenn Sie versuchen, Daten zwischen dem älteren AQD aus dem älteren Skype for Business-Legacyportal (cqd.lync.com) und dem neuesten AQD aus dem Teams Admin Center (cqd.teams.microsoft.com) zu vergleichen, werden Sie schnell feststellen, dass die Daten nicht übereinstimmen. Der Grund dafür ist, dass das neueste AQD viele weitere Anrufszenarien meldet. Wenn Sie noch Berichte aus dem älteren AQD verwenden, verwenden Sie diesen Artikel als Hilfe bei der Interpretation dieser Berichte: Anrufqualitätsdashboard [für Skype for Business Server.](https://docs.microsoft.com/skypeforbusiness/management-tools/call-quality-dashboard/call-quality-dashboard)


  
### <a name="why-cant-i-see-euii-in-cqd"></a>Warum wird EUII im CQD nicht sehen?

Diese Administratorrollen können auf das AQD zugreifen, sie können jedoch nicht EUII (identifizierbare Informationen für Endbenutzer) anzeigen:
- Microsoft 365 Reports Reader
- Supportfachmann für die Teams-Kommunikation

Weitere Informationen zu Rollen, die auf das AQD zugreifen können – einschließlich EUII – finden Sie unter "Zuweisen von Rollen für den Zugriff [auf das AQD".](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>Warum werden Skype for Business-Informationen im AQD angezeigt, wenn ich nur nach Teams gefiltert habe?

Wenn Sie nur in AQD-Berichten (isTeams = 1) nach Teams  filtern, filtern Sie nach allen Anrufen, bei denen der erste Endpunkt "Teams" ist. Wenn der *zweite Endpunkt* Skype for Business ist, werden diese Informationen in Ihrem AQD-Bericht gezeigt.

CQDv2 und CQDv3 haben immer unterschiedliche Gesamtanzahlen, da CQDv3 neue Szenarien hat, die CQDv2 nicht hat. Aus diesem Grund hat ein Vergleich der Zusammenfassungssummen- oder aggregierten Gesamtwerte ohne Filter diese erwarteten Unterschiede.  

Je nach Szenario des Kunden umfasst das CQDv3 lokale SFB 2019-Anrufe (wenn SFB 2019 mit einem Datenconnector verwendet wird), Skype-Bot-Anrufe (AA, CVI, VDI), Liveereignisse und PSTN-Anrufe. Szenarien/Features, die für Kunden verfügbar sind, deren Daten sich jedoch nicht im CQD V2 befinden.

Es wird z. B. erwartet, dass Ihre Kunden 200.000 Audiodatenströme mit 5.000 Fehlern im Zusammenfassungsbericht zu CQD V2 sehen. im Vergleich zu 300.000 Audiodatenströmen mit 5.500 Fehlern (von 2019-Anrufen vor Ort, CVI-Anrufen, #A0 usw.) in AQD V3.

Um festzustellen, ob unerwartete Unterschiede bestehen, müssen Sie verschiedene Aufschlüsselungen der Gesamtdaten überprüfen.  Vergleichen Sie den Zweck.  Das Auflisten der Daten nach Benutzer-Agent-Kategoriepaar ist eine der ersten Empfohlenen.  *First Product* und *Second Product* sind ebenfalls gute Datenschnitte.  

### <a name="why-do-my-custom-reports-only-return-a-maximum-of-10000-rows-when-i-know-there-should-be-more-entries"></a>Warum geben meine benutzerdefinierten Berichte nur maximal 10.000 Zeilen zurück, wenn ich weiß, dass es weitere Einträge geben soll?

Das CQD ist für zusammengefasste Datenabfragen konzipiert und nicht für den Datenexport. Es wird empfohlen, Ihre Berichte möglichst zu verdingen, um zu verhindern, dass das Limit von 10.000 Zeilen überschritten wird. Sehen Sie sich zunächst die KPIs mithilfe umfangreicherer Dimensionen mit niedrigerer Kardinalität an, z. B. "Monat", "Jahr", "Datum", "Region", "Land" usw. Von dort aus können Sie drilldowns zu zunehmend höheren Kardinalitätsdimensionen führen. Die Helpdesk- und Location-Enhanced bieten beide gute Beispiele für diesen Drilldownworkflow.

## <a name="related-topics"></a>Verwandte Themen

[Verbessern und Überwachen der Anrufqualität für Teams](monitor-call-quality-qos.md)

[Was ist CQD?](CQD-what-is-call-quality-dashboard.md)

[Einrichten des Anrufqualitätsdashboards (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Hochladen von Mandanten- und Gebäudedaten](CQD-upload-tenant-building-data.md)

[Daten und Berichte zum AQD](CQD-data-and-reports.md)

[Verwenden des AQD zum Verwalten der Anruf- und Besprechungsqualität](quality-of-experience-review-guide.md)

[Im AQD verfügbare Dimensionen und Measures](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Stream Classification in CQD](stream-classification-in-call-quality-dashboard.md)

[Verwenden von Power BI zum Analysieren von AQD-Daten](CQD-Power-BI-query-templates.md)

[Teams-Problembehandlung](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
