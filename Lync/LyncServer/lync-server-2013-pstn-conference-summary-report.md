---
title: 'Lync Server 2013: Zusammenfassender Bericht über PSTN-Konferenzen'
TOCTitle: Zusammenfassender Bericht über PSTN-Konferenzen
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615014(v=OCS.15)
ms:contentKeyID: 49294707
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusammenfassender Bericht über PSTN-Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Eine PSTN-Konferenz ist in Microsoft Lync Server 2013 eine beliebige Konferenz, in der sich mindestens ein Teilnehmer bei der Audioübertragung mithilfe eines PSTN-Telefons (Public Switched Telephone Network, Telefonfestnetz) einwählt. (PSTN-Telefone können Festnetztelefone, Mobiltelefone oder beliebige andere Telefone sein, die nicht die VoIP-Funktion \[Voice over IP\] nutzen.) Obwohl diese als PSTN-Konferenzen in den Überwachungsberichten bezeichnet werden, sind diese Konferenzen eventuell besser bekannt als Einwahlkonferenzen.

Der "Zusammenfassende Bericht über PSTN-Konferenzen" liefert Informationen zu allen in Ihrer Organisation durchgeführten PSTN-Konferenzen (das sind alle Konferenzen mit mindestens einem Einwahlbenutzer). Der Bericht enthält Informationen zur Gesamtanzahl der PSTN-Konferenzen, der Gesamtanzahl der Teilnehmer an diesen Konferenzen und vielleicht als wichtigste Information, die Gesamtanzahl der Einwahlbenutzer (Metrik der PSTN-Teilnehmer insgesamt).

## Zugreifen auf den "Zusammenfassenden Bericht über PSTN-Konferenzen"

Auf der Startseite "Überwachungsberichte" können Sie auf den "Zusammenfassenden Bericht über PSTN-Konferenzen" zugreifen. Dieser Bericht ist nicht mit anderen Berichten verknüpft. Beachten Sie, dass Sie keine ausführlichen Anrufinformationen für eine PSTN-Konferenz abrufen können. Als teilweise Erklärung hierfür kann angeführt werden, dass die einzelnen Endpunkte für die Übertragung dieser Informationen verantwortlich sind. PSTN-Telefone können keine ausführlichen Anrufinformationen nachverfolgen oder übertragen.

## Optimale Nutzung des "Zusammenfassenden Berichts über PSTN-Konferenzen"

Vergleichen Sie den Wert der Metriken der PSTN-Konferenzen insgesamt mit dem im [Zusammenfassender Konferenzbericht in Lync Server 2013](lync-server-2013-conference-summary-report.md) aufgeführten Wert der Metriken der PSTN-Konferenzen, um den Prozentsatz Ihrer Konferenzen, die Einwahlbenutzer enthalten, zu ermitteln.

Wenn nicht die von Ihnen erwartete Anzahl an PSTN-Konferenzen angezeigt wird, müssen Sie beachten, dass die Funktion zum Organisieren einer Konferenz, die Einwahlbenutzer zulässt, von der Konferenzrichtlinie abhängt, die einem Benutzern zugewiesen ist. Wenn eine geringe Anzahl Ihrer Benutzer berechtigt ist, PSTN-Konferenzen durchzuführen, werden nur wenige PSTN-Konferenzen angezeigt. Sie können schnell überprüfen, mit welcher Konferenzrichtlinie (falls vorhanden) die Benutzer PSTN-Konferenzen planen können, indem Sie den folgenden Befehl über die Lync Server-Verwaltungsshell ausführen:

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Bericht über PSTN-Konferenz festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über PSTN-Konferenz verwenden können.

### Filter im Zusammenfassenden Bericht über PSTN-Konferenz

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
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p><strong>Stündlich</strong> (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p><strong>Täglich</strong> (maximal 31 Tage können angezeigt werden)</p></li>
<li><p><strong>Wöchentlich</strong> (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p><strong>Monatlich</strong> (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall <strong>Täglich</strong> mit dem Startdatum 7/8/2012 und dem Enddatum 28/9/2012 ausgewählt haben, werden Daten für die Tage 7/8/2012 12:00 Uhr bis 7/9/2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Bericht über PSTN-Konferenz angegeben werden.

### Metriken im Zusammenfassenden Bericht über PSTN-Konferenz

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
<td><p><strong>Stündlich</strong></p>
<p><strong>Täglich</strong></p>
<p><strong>Wöchentlich</strong></p>
<p><strong>Monatlich</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall &quot;Täglich&quot; verwenden und auf 7/7/2012 klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN-Konferenzen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, die Zugriff per Einwahl erlaubten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Teilnehmer insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Personen, die an Konferenzen mit Einwahlzugriff teilnahmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gesamtdauer der A/V-Konferenzen in Minuten</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtdauer von Konferenzen mit Audio oder Video.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gesamtdauer (in Minuten), die Teilnehmer in der A/V-Konferenz verbleiben</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtdauer, die Teilnehmer in Konferenzen mit Audio bzw. Video verbrachten. Beispiel: Angenommen, ein Teilnehmer hat 5 Minuten in einer A/V-Konferenz verbracht und ein zweiter Benutzer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN-Teilnehmer insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die sich in Konferenzen einwählten, die Zugriff per Einwahl erlaubten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PSTN-Teilnehmerminuten insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtdauer, die Einwahlbenutzer in Konferenzen verbrachten. Beispiel: Angenommen, ein Einwahlteilnehmer hat 5 Minuten in einer Konferenz verbracht und ein zweiter Teilnehmer war 3 Minuten in der gleichen Konferenz. Dann ergibt dies eine Gesamtdauer von 8 Minuten.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eindeutige Konferenzorganisatoren</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die mindestens eine Konferenz mit Einwahlzugriff organisiert haben. Benutzer, die mehr als eine Konferenz organisiert haben, zählen als ein eindeutiger Organisator, genauso wie Benutzer, die nur eine einzige Konferenz organisiert haben.</p></td>
</tr>
</tbody>
</table>

