---
title: 'Lync Server 2013: Zusammenfassender Bericht über Medienqualität'
TOCTitle: Zusammenfassender Bericht über Medienqualität
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615012(v=OCS.15)
ms:contentKeyID: 49294686
ms.date: 06/29/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusammenfassender Bericht über Medienqualität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-06-29_

Der "Zusammenfassende Bericht über Medienqualität" ist möglicherweise die beste Option zum Analysieren der Anrufqualität in Ihrer Organisation: In diesem Bericht werden detailliert die QoE-Anrufmetriken (Quality of Experience, QoE) in den folgenden Kategorien aufgeführt:

  - UC-Peer-zu-Peer-Anrufe (z. B. ein Microsoft Lync 2013 zu Microsoft Lync 2013-Anruf)

  - UC-Konferenzsitzungen

  - PSTN-Konferenzsitzungen

  - PSTN-Anrufe: Medienumgehung

  - PSTN-Anrufe (keine Umgehung): UC-Abschnitt

  - PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt

  - Andere Anruftypen

Beim ersten Öffnen des Berichts wird eine Zusammenfassung zu den einzelnen Kategorien angezeigt. Sie können ohne den Bericht verlassen zu müssen, jede Kategorie erweitern, um die Unterkategorien, wie z. B. die von Office Communicator 2007 R2 zu Lync 2013 getätigten Anrufe, anzuzeigen. Diese Unterkategorien können Sie anschließend erweitern, um Details zu jedem in diesen Unterkategorien getätigten Anruf anzuzeigen.

In Microsoft Lync Server 2013 werden die Daten im "Zusammenfassenden Bericht über Medienqualität" erneut in drei Anruftypen aufgeteilt: Audioanrufe, Videoanrufe und Anwendungsfreigabeanrufe. Für jeden Anruftyp gibt es im Bericht einen eigenen Bereich und eigenen benutzerdefinierten Satz von Anrufmetriken.

Im "Zusammenfassenden Bericht über Medienqualität" können Sie Filter anwenden, mit denen Sie die Anrufqualität zwischen verkabelten und drahtlosen Anrufen, internen und externen Anrufen sowie VPN- und Nicht-VPN-Anrufen vergleichen können.

## Zugreifen auf den "Zusammenfassenden Bericht über Medienqualität"

Auf den "Zusammenfassenden Bericht über Medienqualität" kann auf der Startseite "Überwachungsberichte" zugegriffen werden. Sie können Detailinformationen bis zum [Anruflistenbericht in Lync Server 2013](lync-server-2013-call-list-report.md) anzeigen, indem Sie auf eine der folgenden Metriken klicken:

  - Anrufvolumen

  - Prozentsatz der Anrufe schlechter Qualität

Auf den "Zusammenfassenden Bericht über Medienqualität" können Sie auch zugreifen, indem Sie auf eine beliebige der folgenden Audioanrufmetriken klicken:

  - Roundtrip (ms)

  - Beeinträchtigung (MOS)

  - Paketverlust

  - Jitter (ms)

  - Ausblendungsverhältnis der Reparatur

  - Streckungsverhältnis der Reparatur

  - Komprimierungsverhältnis der Reparatur

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Bespielsweise können Sie im zusammenfassenden Bericht über Medienqualität die zurückgegebenen Daten nach Zugriffstyp (d. h. interner oder externer Zugriff) oder nach Netzwerkverbindung (Kabel- oder Funkverbindung) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über Medienqualität verwenden können.

### Filter im Zusammenfassenden Bericht über Medienqualität

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Von</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 PM</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>3/7/12</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 PM</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>3/7/12</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Intern</p></li>
<li><p>Extern</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Netzwerktyp</strong></p></td>
<td><p>Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Verkabelt</p></li>
<li><p>Funk</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>VPN</p></li>
<li><p>Nicht-VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Zusammenfassenden Bericht über Medienqualität angegeben werden.

### Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Audioanrufe

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Anruftyp/Endpunkttyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</p>
<ul>
<li><p>UC-Peer-zu-Peer-Anrufe</p></li>
<li><p>UC-Konferenzsitzungen</p></li>
<li><p>PSTN-Konferenzsitzungen</p></li>
<li><p>PSTN-Anrufe: Medienumgehung</p></li>
<li><p>PSTN-Anrufe (keine Umgehung): UC-Abschnitt</p></li>
<li><p>PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</p></li>
<li><p>Andere Anruftypen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe pro Anruftyp.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen (Funkanruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufvolumen (VPN-Anruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen (externer Anruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roundtrip (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Zeit (in Millisekunden), die ein RTP-Paket (Real-time Transport Protocol) benötigt, um zu einem anderen Endpunkt und wieder zurück zu gelangen. Eine Roundtripzeit von 100 ms oder weniger gilt als akzeptable Qualität.</p>
<p>Hohe Roundtripwerte können durch internationale Anrufweiterleitung, eine falsche Routingkonfiguration oder einen überlasteten Medienserver verursacht werden. Sie führen zu Problemen bei bidirektionalen Echtzeit-Audiounterhaltungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Beeinträchtigung (MOS)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Beeinträchtigung der Qualität, die gemäß Mean Opinion Score (MOS) während eines Anrufs auftrat. Die Beeinträchtigungswerte liegen zwischen 0,0 (schlecht) und 5,0 (gut). Ein Wert von 0,5 oder besser gilt als akzeptable Beeinträchtigung. Früher wurden Mean Opinion Scores berechnet, indem man Benutzer die Qualität eines Telefongesprächs auf einer Skala von 1 bis 5 bewerten ließ. Lync Server ermittelt anhand mehrerer Algorithmen, wie die Benutzer einen Anruf bewertet hätten.</p>
<p>Hohe Beeinträchtigungswerte können durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver oder Endpunkt verursacht werden. Eine hohe Beeinträchtigung führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Paketverlust</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Rate an RTP-Paketverlusten. Zu Paketverlusten kommt es, wenn RTP-Pakete (RTP ist ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen. Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Jitter (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das &quot;Zittern&quot; der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ausblendungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen ausgeblendeten Audiosamples und der Gesamtzahl der Samples. (Ausgeblendete Audiosamples sind ein Verfahren zum &quot;Glätten&quot; der &quot;holprigen&quot; Übertragung, die normalerweise von verworfenen Netzwerkpaketen verursacht wird.) Ein hoher Wert gibt an, dass wegen Paketverlusten oder Jitters Verlustausblendung in großem Umfang angewendet wurde und führt zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Streckungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen gestreckten Audiosamples und der Gesamtzahl der Samples. (Gestrecktes Audio ist ein Verfahren zum Dehnen von Audiodaten, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplestreckung in hohem Umfang aufgetreten ist und führt zu roboterhafter oder verzerrter Sprachqualität.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Komprimierungsverhältnis der Reparatur</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das durchschnittliche Verhältnis zwischen komprimierten Audiosamples und der Gesamtzahl der Samples. (Komprimiertes Audio sind Audiodaten, die komprimiert wurden, um die Gesprächsqualität aufrechtzuerhalten, wenn ein verworfenes Netzwerkpaket festgestellt wurde.) Ein hoher Wert gibt an, dass wegen Jitters Samplekomprimierung in hohem Umfang angewendet wurde und führt zu zu schneller Sprachwiedergabe oder zu verzerrter Sprachqualität.</p></td>
</tr>
</tbody>
</table>


### Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Videoanrufe

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Anruftyp/Endpunkttyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</p>
<ul>
<li><p>UC-Peer-zu-Peer-Anrufe</p></li>
<li><p>UC-Konferenzsitzungen</p></li>
<li><p>PSTN-Konferenzsitzungen</p></li>
<li><p>PSTN-Anrufe: Medienumgehung</p></li>
<li><p>PSTN-Anrufe (keine Umgehung): UC-Abschnitt</p></li>
<li><p>PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</p></li>
<li><p>Andere Anruftypen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe pro Anruftyp.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen (Funkanruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufvolumen (VPN-Anruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen (externer Anruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Durchschnittliche Bitrate (KBit/s)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Video-Bitrate (in Kilobit pro Sekunde).</p></td>
</tr>
<tr class="even">
<td><p><strong>Niedrige Bitrate %</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz aller Anrufe, bei denen die Bitrate niedrig war.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Verlust ausgehender Pakete</strong></p></td>
<td><p>Nein</p></td>
<td><p>RTP-Paketverluste (Real-Time Transport Protocol) bei ausgehenden Paketen. (Zu Paketverlusten kommt es, wenn RTP-Pakete (ein Protokoll für die Übertragung von Audio und Video über das Internet) ihr Ziel nicht erreichen.) Hohe Verlustraten werden allgemein durch Überlastung, zu geringe Bandbreite, Funknetzüberlastung oder -interferenzen oder durch einen überlasteten Medienserver verursacht. Paketverluste führen in der Regel zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eingefrorene Frames %</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz der &quot;eingefrorenen&quot; Frames. In einem eingefrorenen Frame wird das Video nicht fortgesetzt, während der Audioteil des Anrufs weitergeht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Durchschnittliche ausgehende Framerate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Framerate für ausgehende Übertragungen während des Anrufs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnittliche eingehende Framerate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche Framerate für eingehende Übertragungen während des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Niedrige eingehende Framerate %</strong></p></td>
<td><p>Nein</p></td>
<td><p>Prozentsatz aller Anrufe, bei denen die Bitrate für eingehende Videodaten niedrig war.</p></td>
</tr>
<tr class="even">
<td><p><strong>Clientintegrität %</strong></p></td>
<td><p></p></td>
<td><p>Zeigt die relative Integrität des Clientgeräts während des Anrufs an.</p></td>
</tr>
</tbody>
</table>


### Metriken im "Zusammenfassenden Bericht über Medienqualität": Zusammenfassung der Anwendungsfreigabeanrufe

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Anruftyp/Endpunkttyp</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, zeigt der Bericht Details zu den auf diesem Typ basierenden Anrufen. Es gibt folgende Anruftypen:</p>
<ul>
<li><p>UC-Peer-zu-Peer-Anrufe</p></li>
<li><p>UC-Konferenzsitzungen</p></li>
<li><p>PSTN-Konferenzsitzungen</p></li>
<li><p>PSTN-Anrufe: Medienumgehung</p></li>
<li><p>PSTN-Anrufe (keine Umgehung): UC-Abschnitt</p></li>
<li><p>PSTN-Anrufe (keine Umgehung): Gateway-Abschnitt</p></li>
<li><p>Andere Anruftypen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe pro Anruftyp.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, die als Anrufe schlechter Qualität klassifiziert werden. Dies sind Anrufe, bei denen für mindestens eine der gemessenen Metriken der zulässige Wert überschritten wurde (z. B. ein Anruf mit übermäßigem Jitter).</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen (Funkanruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine Funkverbindung verwendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufvolumen (VPN-Anruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine VPN-Verbindung verwendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufvolumen (externer Anruf)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anrufe, für die eine externe Verbindung verwendet wurde (d. h. eine Verbindung außerhalb des internen Netzwerks).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Jitter (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der durchschnittliche Jitter, der zwischen dem Eintreffen von RTP-Paketen ermittelt wurde. (Jitter ist ein Maß für das &quot;Zittern&quot; der Übertragung während eines Anrufs.) Hohe Jitterwerte werden in der Regel durch Überlastung oder einen überlasteten Medienserver verursacht und führen zu verzerrter oder unterbrochener Sprachübertragung.</p></td>
</tr>
<tr class="even">
<td><p><strong>Durchschnitt relativ unidirektional</strong></p></td>
<td><p>Nein</p></td>
<td><p>Durchschnittliche relative unidirektionale Verzögerung zwischen zwei Medienendpunkten. Dies ist ein Single-Hop-Latenzmaß.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Durchschnittliche Latenz der RDP-Kachelverarbeitung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die durchschnittliche Latenz der RDP-Kachelverarbeitung im AS-Konferenzserver über die Dauer der Anzeigesitzung. Diese Metrik deckt die Netzwerklatenz nicht ab. Ein hoher Durchschnitt zeigt eine längere Verzögerung bei der Anzeige an. Ein überlasteter Konferenzserver zeigt gegebenenfalls höhere durchschnittliche Verzögerungen an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Insgesamt schlechte Kacheln %</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gesamtprozentsatz schlechter RDP-Kacheln.</p></td>
</tr>
</tbody>
</table>

