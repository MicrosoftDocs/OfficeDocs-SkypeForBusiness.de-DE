---
title: 'Lync Server 2013: Bericht über Benutzeraktivität'
TOCTitle: Bericht über Benutzeraktivität
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558638(v=OCS.15)
ms:contentKeyID: 49293723
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über Benutzeraktivität in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht über Benutzeraktivität stellt eine detaillierte Liste der Peer-zu-Peer- und Konferenzsitzungen bereit, die von Benutzern in einem bestimmten Zeitraum durchgeführt werden. Anders als bei vielen der Überwachungsberichte ist im Bericht über Benutzeraktivität jeder Anruf mit einzelnen Benutzern verknüpft. Für Peer-zu-Peer-Sitzungen ist im Bericht beispielsweise der SIP-URI der Person angegeben, die den Anruf initiiert hat (der Absenderbenutzer), und der Person, die angerufen wurde (der Empfängerbenutzer). Wenn Sie die Informationen zu einer Konferenz erweitern, sehen Sie eine Liste aller Konferenzteilnehmer einschließlich der Rolle, die die bei dieser Konferenz hatten.

Der Bericht über Benutzeraktivität wird auch als "Helpdesk"-Bericht bezeichnet. Der Grund ist, dass der Bericht häufig vom Helpdeskpersonal verwendet wird, um Sitzungsinformationen für einen bestimmten Benutzer abzurufen. Sie können den Bericht nach Anrufen filtern, die von einem bestimmten Benutzer entgegengenommen oder initiiert wurden, indem Sie einfach den SIP-URI dieses Benutzers in das Feld **Präfix des Benutzer-URI** eingeben.

Wenn Sie beispielsweise **ken** in das Feld für den URI eingeben, findet der Bericht über Benutzeraktivität den Benutzer mit dem URI " **Ken**.Myer@litwareinc.com". Er findet aber auch die folgenden Benutzer:

  - **ken**azi@litwareinc.com

  - **ken**burg@litwareinc.com

  - **Ken**.Sanchez@litwareinc.com

  - **Ken**nedy@litwareinc.com

Um sicherzustellen, dass nur Informationen für Ken Myer zurückgegeben werden, geben Sie entweder dessen vollständigen URI (Ken.Myer@litwareinc.com) oder ausreichende Bestandteile des URI in das Suchfeld ein, um ihn von anderen Benutzern in Ihrem Unternehmen zu unterscheiden. Ein Beispiel:

Ken.my

## So greifen Sie auf den Bericht über Benutzeraktivität zu

Auf den Bericht über Benutzeraktivität können Sie von der Homepage für Überwachungsberichte aus zugreifen. Sie können auf den Bericht über Benutzeraktivität auch zugreifen, indem Sie im [Inventurbericht über IP-Telefone in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) auf die Metrik **Benutzer-URI** klicken. Wenn Sie im Bericht über Benutzeraktivität auf den Konferenz-URI (für eine Konferenz) klicken, gelangen Sie zum Konferenzdetailbericht. Entsprechend wird der [Detailbericht über Peer-zu-Peer-Sitzungen in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) aufgerufen, wenn Sie auf die Metrik **Detail** eines Peer-zu-Peer-Anrufs klicken.

## Optimales Verwenden des Berichts über Benutzeraktivität

Der Bericht über Benutzeraktivität enthält zwar viele nützliche Informationen, diese sind aber mitunter nicht leicht zu finden. Der Bericht über Benutzeraktivität enthält beispielsweise alle Benutzeraktivitäten, die in dem angegebenen Zeitraum in Ihrer Organisation stattgefunden haben. Im Bericht sind also auch Informationen darüber verborgen, welche Benutzer tatsächlich Microsoft Lync Server 2013 auf irgendeine Weise verwendet haben.


> [!WARNING]
> Technisch gesehen ist es möglich, dass eine Benutzeraktivität nicht aufgezeichnet wird: In Lync Server wird versucht, Informationen zu allen Telefonaten aufzuzeichnen. Dennoch kann es passieren, dass ein Anruf durchgeführt wird, ohne dass Informationen zum Anruf in die Datenbank geschrieben werden. Lync Server ist so konzipiert, dass Sie einen äußerst genauen, aber nicht unbedingt perfekten Einblick in die Verwendung von Lync Server 2013 erhalten. (Die Tatsache, dass es keine Garantie dafür gibt, dass 100 % aller Anrufe aufgezeichnet werden, ist der Grund dafür, dass die Lync Server-Überwachung nicht als Fakturierungssystem verwendet werden sollte.)<BR>Zweitens können in einem Überwachungsbericht nur maximal 1.000 Datensätze angezeigt werden. Je nach Umfang der Benutzeraktivität und des Zeitraums, den Sie auswählen, werden bei der Abfrage möglicherweise nicht alle Daten zurückgegeben, die tatsächlich in der Datenbank gespeichert sind.



  - Welche Benutzter haben das System in diesem Zeitraum tatsächlich verwendet?

  - Welcher der Benutzer war in diesem Zeitraum am aktivsten?

  - Sind die Benutzer, die die meisten Telefonate durchführen, auch die Benutzer, die am häufigsten an Chatsitzungen teilnehmen?

Wenn Sie Antworten auf Fragen wie diese benötigen, können Sie die von den Überwachungsberichten abgerufenen Daten nach einem Excel-Arbeitsblatt exportieren. Sie können dieses Arbeitsblatt und/oder eine CSV-Datei dann verwenden, um die Daten zu analysieren. Angenommen, Sie haben Berichtsdaten nach Excel und dann in eine CSV-Datei exportiert. An dieser Stelle können Sie die Daten aus der CSV-Datei mit einem ähnlichen Befehl wie den folgenden in Windows PowerShell importieren:

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

Nachdem die Daten importiert wurden, können Sie einfache Windows PowerShell-Befehle verwenden, um Antworten auf Ihre Fragen zu erhalten. Mit dem folgenden Befehl wird beispielsweise eine Liste von eindeutigen Benutzern zurückgegeben, die in mindestens einer Sitzung als "Absenderbenutzer" fungiert haben:

    $x | Group-Object "From user" | Select Name | Sort-Object Name

Anders ausgedrückt:

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

Mit diesem Befehl werden eindeutige Benutzer aufgelistet (basierend auf der Gesamtanzahl der Sitzungen, an denen sie teilgenommen haben:

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Der Befehl gibt ähnliche Daten wie die folgenden zurück:

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

Dieser Befehl beschränkt die gemeldeten Sitzungen auf diejenigen mit Audio als Modalität ein:

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Wenn Sie mit der Maus auf eine beliebige Diagnose-ID im Bericht zeigen, erscheint eine QuickInfo mit einer Beschreibung der ID.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Benutzeraktivität können Sie beispielsweise die zurückgegebenen Daten nach Kriterien wie dem Aktivitätstyp (Peer-zu-Peer-Sitzung oder Konferenzsitzung) oder nach der SIP-Adresse (zum Anzeigen der Aktivitäten eines Benutzers) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzeraktivität verwenden können.

### Bericht über Benutzeraktivität - Filter

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
<p>7/17/2012 1:00 PM</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 AM. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/17/2012 1:00 PM</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 AM. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Peer-zu-Peer</p></li>
<li><p>Konferenz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalität</strong></p></td>
<td><p>Die für Sie verfügbare Modalität ist je nach ausgewähltem Aktivitätstyp unterschiedlich. Wenn der Aktivitätstyp Peer-zu-Peer ist, können Sie Chat, Dateiübertragung, Anwendungsfreigabe, Sprache oder Video als Modalität auswählen.</p>
<p>Wenn der Aktivitätstyp Konferenz ist, können Sie Chat-Telefonkonferenz, Webkonferenz, Anwendungsfreigabe, Sprach-/Videokonferenz oder Telefoniekonferenz auswählen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sitzungskategorie</strong></p></td>
<td><p>Gibt an, ob die betreffende Aktivität erfolgreich war oder nicht. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Erfolg</p></li>
<li><p>Erwarteter Fehler</p></li>
<li><p>Unerwarteter Fehler</p></li>
</ul>
<p>Ein &quot;erwarteter Fehler&quot; ist ein Fehler, der erwartungsgemäß auftritt. Hat beispielsweise ein Benutzer seinen Status auf &quot;Nicht stören&quot; gesetzt, ist zu erwarten, dass alle Anrufe an diesen Benutzer fehlschlagen. Ein &quot;unerwarteter Fehler&quot; ist ein Fehler, der in einem ansonsten scheinbar fehlerfreien System auftritt. Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet. In diesem Fall würde der Fehler als &quot;unerwartet&quot; gekennzeichnet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Präfix des Benutzer-URI</strong></p></td>
<td><p>SIP-Adresse für den Benutzer. Um nur die Datensätze des Benutzers Ken Myer anzuzeigen, geben Sie die SIP-Adresse von Ken Myer ein, z. B.:</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


## Metriken für Peer-zu-Peer-Sitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Peer-zu-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.

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
<td><p><strong>Detail</strong></p></td>
<td><p>Nein</p></td>
<td><p>Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Peer-to-Peer-Sitzungsbericht für die ausgewählte Sitzung an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Von Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der die Peer-zu-Peer-Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der der Peer-zu-Peer-Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalitäten</strong></p></td>
<td><p>Ja</p></td>
<td><p>In der Sitzung verwendete Kommunikationsart, z. B. Instant Messaging, Audio oder Dateiübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Einladung</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Peer-zu-Peer-Sitzungseinladung gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Antwortzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der eingeladene Benutzer die Sitzungseinladung annahm.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Peer-zu-Peer-Sitzung endete.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


## Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.

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
<td><p><strong>Konferenz-URI</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Konferenzbericht für die ausgewählte Sitzung an. Erweitern Sie dieses Element, damit der der Bericht Informationen zu den Konferenzteilnehmern anzeigt. Ausführliche Informationen finden Sie im Abschnitt &quot;Metriken für Konferenzteilnehmer&quot; weiter unten in diesem Thema.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisator</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Ja</p></td>
<td><p>Name des in der Konferenz verwendeten Edgesservers (sofern vorhanden).</p></td>
</tr>
<tr class="even">
<td><p><strong>Beginn</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</p></td>
</tr>
</tbody>
</table>


## Metriken für Konferenzteilnehmer

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für jeden Teilnehmer einer Konferenz enthaltenen Informationen aufgeführt.

### Metriken für Konferenzteilnehmer

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
<td><p><strong>Rolle</strong></p></td>
<td><p>Nein</p></td>
<td><p>Konferenzrolle (z. B. Referent) des Benutzers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Teilnehmer</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers</p></td>
</tr>
<tr class="odd">
<td><p><strong>Verbindung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Art der Netzwerkverbindung, z. B. &quot;From Internal&quot; für interne Verbindungen oder &quot;From PSTN&quot; für Einwahlbenutzer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zeitpunkt des Beitritts</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Benutzer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zeitpunkt der Beendigung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Benutzer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>

