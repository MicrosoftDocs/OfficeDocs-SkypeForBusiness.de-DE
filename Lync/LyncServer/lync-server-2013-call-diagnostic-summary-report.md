---
title: 'Lync Server 2013: Zusammenfassender Anrufdiagnosebericht'
TOCTitle: Zusammenfassender Anrufdiagnosebericht
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615016(v=OCS.15)
ms:contentKeyID: 49294744
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusammenfassender Anrufdiagnosebericht in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der zusammenfassende Anrufdiagnosebericht bietet eine Gesamtübersicht zu fehlgeschlagenen Peer-zu-Peer- und Konferenzsitzungen. Der Bericht zeigt die Gesamtfehlerrate für beide Sitzungstypen und detaillierte Fehlerinformationen nach Sitzungsmodalitätstyp:

  - Sofortnachrichten

  - Anwendungsfreigabe

  - Dateiübertragung

  - Audio

  - Video

## Zugriff auf den zusammenfassenden Anrufdiagnosebericht

Der Zugriff auf den zusammenfassenden Anrufdiagnosebericht erfolgt auf der Startseite für Überwachungsberichte. Über den zusammenfassenden Anrufdiagnosebericht können Sie auf den [Diagnosebericht über Peer-zu-Peer-Aktivität in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) zugreifen, indem Sie unter dem Abschnitt zu den Peer-zu-Peer-Sitzungen des Berichts auf die Maße für die Fehlerrate klicken. Sie können außerdem auf den [Diagnosebericht über die Konferenz in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) zugreifen, indem Sie auf eines der folgenden Konferenzmaße klicken:

  - Sitzungsfehlerrate insgesamt

  - Fehlerrate für Konferenzzustandsobjekt

  - MCU-Fehlerrate

## Optimale Verwendung des zusammenfassenden Anrufdiagnoseberichts

Der zusammenfassende Anrufdiagnosebericht enthält Diagramme, in denen die Fehlerraten für verschiedene Modalitäten verglichen werden, die in Microsoft Lync Server 2013 verwendet werden. Die Spalten dieser Diagramme sind Hotlinks. Wenn Sie z. B. auf die Spalte für Sofortnachrichten für Peer-zu-Peer-Sitzungen klicken, wird eine Instanz mit Detailinformationen des [Diagnosebericht über Peer-zu-Peer-Aktivität in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) angezeigt. Der Bericht bietet zusätzliche Einzelheiten zu allen im zusammenfassenden Anrufdiagnosebericht enthaltenen Instant Messaging-Sitzungen.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Anrufdiagnosebericht nach Kriterien wie dem Registrierungspool oder den in der Sitzung verwendeten Edgeserver filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Anrufdiagnosebericht verwenden können.

### Filter im Zusammenfassenden Anrufdiagnosebericht

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
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrar-Pools oder Edgeservers. Sie können einen einzelnen Pool auswählen, oder auf <strong>[Alle]</strong> klicken, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
</tbody>
</table>


## Metriken für Peer-zu-Peer-Sitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Peer-zu-Peer-Sitzungen (d. h. für Sitzungen mit nur zwei Teilnehmern) angegeben werden.

### Metriken für Peer-zu-Peer-Sitzungen

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
<td><p><strong>Sitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Peer-zu-Peer-Sitzungen, die stattgefunden haben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fehlerrate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Peer-zu-Peer-Sitzungen, bei denen ein Fehler aufgetreten ist. Wenn Sie auf dieses Element klicken, wird der Diagnosebericht über Peer-zu-Peer-Aktivitäten angezeigt, der detailliertere Angaben zu den fehlgeschlagenen Peer-zu-Peer-Sitzungen enthält.</p></td>
</tr>
</tbody>
</table>


## Metriken für Konferenzsitzungen

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Anrufdiagnosebericht für Konferenzsitzungen (d. h. für Sitzungen mit mindestens drei Teilnehmern) angegeben werden.

### Metriken für Konferenzsitzungen

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
<td><p><strong>Konferenzen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzen, die stattgefunden haben.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzsitzungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Konferenzsitzungen, die durchgeführt wurden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungsfehlerrate insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Konferenzzustandsobjekt-Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Anzahl der auf Konferenzzustandsobjekten basierenden Sitzungen, bei denen Fehler aufgetreten sind.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fehlerrate für Konferenzzustandsobjekt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der auf Konferenzzustandsobjekten basierenden Konferenzsitzungen, bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU-Sitzungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU-Fehlerrate</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Prozentsatz der auf Konferenzservern basierenden Konferenzen (früher als MCU-Konferenzen bezeichnet [Multipoint Control Unit]), bei denen ein Fehler aufgetreten ist.</p></td>
</tr>
</tbody>
</table>

