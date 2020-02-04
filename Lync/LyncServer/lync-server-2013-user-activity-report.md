---
title: 'Lync Server 2013: Benutzer Aktivitätsbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 583c647ac3cdab290f1833539abbbd033ea89410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a>Bericht zur Benutzeraktivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-02-27_

Der Bericht über Benutzeraktivität stellt eine detaillierte Liste der Peer-to-Peer- und Konferenzsitzungen bereit, die von Benutzern in einem bestimmten Zeitraum durchgeführt werden. Anders als bei vielen der Überwachungsberichte ist im Bericht über Benutzeraktivität jeder Anruf mit einzelnen Benutzern verknüpft. Für Peer-to-Peer-Sitzungen ist im Bericht beispielsweise der SIP-URI der Person angegeben, die den Anruf initiiert hat (der Absenderbenutzer), und der Person, die angerufen wurde (der Empfängerbenutzer). Wenn Sie die Informationen zu einer Konferenz erweitern, sehen Sie eine Liste aller Konferenzteilnehmer einschließlich der Rolle, die die bei dieser Konferenz hatten.

Der Bericht über Benutzeraktivität wird auch als „Helpdesk“-Bericht bezeichnet. Der Grund ist, dass der Bericht häufig vom Helpdesk-Personal verwendet wird, um Sitzungsinformationen für einen bestimmten Benutzer abzurufen. Sie können den Bericht nach Anrufen filtern, die von einem bestimmten Benutzer entgegengenommen oder initiiert wurden, indem Sie einfach den SIP-URI dieses Benutzers in das Feld „Präfix des Benutzer-URI“ eingeben.

Wenn Sie dies tun, gibt der Benutzer Aktivitätsbericht Informationen für jeden Benutzer zurück, dessen SIP-URI mit der angegebenen Zeichenfolge beginnt. Wenn Sie beispielsweise **Klaus** in das Feld für den URI eingeben, findet der Bericht über Benutzeraktivität **Klaus**.Buzov@litwareinc.com. Er findet aber auch die folgenden Benutzer:

  - **Klaus**kohler@litwareinc.com

  - **Klaus**schulz@litwareinc.com

  - **Klaus**.Kiefer@litwareinc.com

  - **Klaus**gasper@litwareinc.com

Um sicherzustellen, dass nur Informationen für Ken Myer zurückgegeben werden, geben Sie entweder dessen vollständigen URI (Ken.Myer@litwareinc.com) oder ausreichende Bestandteile des URI in das Suchfeld ein, um ihn von anderen Benutzern in Ihrem Unternehmen zu unterscheiden. Ein Beispiel:

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>So greifen Sie auf den Bericht über Benutzeraktivität zu

Auf den Bericht über Benutzeraktivität können Sie von der Startseite für Überwachungsberichte aus zugreifen. Sie können auch den Benutzer Aktivitätsbericht erreichen, indem Sie [im Bericht IP Phone Inventory in lync Server 2013](lync-server-2013-ip-phone-inventory-report.md)auf die Benutzer-URI-Metrik klicken. Wenn Sie im Bericht über Benutzeraktivität auf den Konferenz-URI (für eine Konferenz) klicken, gelangen Sie zum Konferenzdetailbericht. Auf ähnliche Weise wird durch Klicken auf die Detail Metrik für einen Peer-to-Peer-Anruf der [Peer-to-Peer-Sitzungs Detailbericht in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md)aufgerufen.

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>Optimales Verwenden des Berichts über Benutzeraktivität

Obwohl im Berichtbenutzer Aktivität viele gute Informationen vorhanden sind, können diese Informationen manchmal schwierig zu finden sein. So werden beispielsweise alle Benutzeraktivitäten, die während eines bestimmten Zeitraums in Ihrer Organisation stattfinden, in den Bericht zur Benutzeraktivität aufgenommen. Das bedeutet, dass im Bericht begraben Informationen darüber enthalten sind, welche Benutzer tatsächlich Microsoft lync Server 2013 in irgendeiner Weise verwendet haben.

<div>


> [!WARNING]  
> Technisch gesehen ist es möglich, dass einige Benutzeraktivitäten nicht aufgezeichnet werden: während lync Server versucht, Informationen zu allen Telefon anrufen zu speichern, ist es möglich, dass ein Anruf getätigt wurde, ohne dass die Informationen zu diesem Anruf in die Datenbank geschrieben wurden. Lync Server ist so konzipiert, dass es eine äußerst genaue, aber nicht unbedingt perfekte Darstellung der Verwendung von lync Server 2013 bietet. (Die Tatsache, dass es keine Garantie dafür gibt, dass 100% aller Anrufe aufgezeichnet werden, erklärt, warum die lync Server-Überwachung nicht als Abrechnungssystem verwendet werden sollte.)<BR>Zweitens kann ein Überwachungsberichts Bericht höchstens 1.000 Datensätze anzeigen. Je nach Umfang der Benutzeraktivität und des Zeitraums, den Sie auswählen, werden bei der Abfrage möglicherweise nicht alle Daten zurückgegeben, die tatsächlich in der Datenbank gespeichert sind.



</div>

  - Welche Benutzter haben das System in diesem Zeitraum tatsächlich verwendet?

  - Welcher der Benutzer war in diesem Zeitraum am aktivsten?

  - Sind die Benutzer, die die meisten Telefonate durchführen, auch die Benutzer, die am häufigsten an Chatsitzungen teilnehmen?

Wenn Sie Antworten auf Fragen wie diese benötigen, können Sie die von den Überwachungsberichten abgerufenen Daten in ein Excel-Arbeitsblatt exportieren. Sie können dieses Arbeitsblatt und/oder eine CSV-Datei dann verwenden, um die Daten zu analysieren. Angenommen, Sie haben Berichtsdaten nach Excel und dann in eine CSV-Datei exportiert. Zu diesem Zeitpunkt können Sie die Daten aus dem Importieren. CSV-Datei in Windows PowerShell mithilfe eines Befehls ähnlich der folgenden:

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

Nachdem die Daten importiert wurden, können Sie mithilfe von einfachen Windows PowerShell-Befehlen Ihre Fragen beantworten. Mit dem folgenden Befehl wird beispielsweise eine Liste von eindeutigen Benutzern zurückgegeben, die in mindestens einer Sitzung als „Absenderbenutzer“ fungiert haben:

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

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Mit dem Bericht über Benutzeraktivität können Sie beispielsweise die zurückgegebenen Daten nach Kriterien wie dem Aktivitätstyp (Peer-to-Peer-Sitzung oder Konferenzsitzung) oder nach der SIP-Adresse (zum Anzeigen der Aktivitäten eines Benutzers) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Anrufe nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzeraktivität verwenden können.

### <a name="user-activity-report-filters"></a>Bericht über Benutzeraktivität - Filter

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
<p>7/17/12012 1:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/12012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/17/12012 1:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/17/12012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/13/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aktivitätstyp</strong></p></td>
<td><p>Aktivitätstyp. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>Peer-to-Peer</p></li>
<li><p>Konferenz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalität</strong></p></td>
<td><p>Die für Sie verfügbare Modalität ist je nach ausgewähltem Aktivitätstyp unterschiedlich. Wenn es sich bei dem Aktivitätstyp um Peer-to-Peer handelt, können Sie im auswählen. Dateiübertragung; Anwendungsfreigabe; Stimme oder Video als Modalität.</p>
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
<p>Bei &quot;einem erwarteten&quot; Fehler handelt es sich um einen Fehler, der erwartet wird. Wenn ein Benutzer beispielsweise seinen Status auf "nicht stören" festgelegt hat, erwarten Sie, dass ein Anruf an diesen Benutzer fehlschlägt. Bei &quot;einem unerwarteten Fehler&quot; handelt es sich um einen Fehler, der in einem ansonsten fehlerhaften System auftreten kann. Beispielsweise sollte ein Anruf nicht abgebrochen werden, während der Anrufer sich in der Warteschleife befindet. In diesem Fall würde der Fehler als „unerwartet“ gekennzeichnet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Präfix des Benutzer-URI</strong></p></td>
<td><p>SIP-Adresse für den Benutzer. Um nur die Datensätze des Benutzers Ken Myer anzuzeigen, geben Sie die SIP-Adresse von Ken Myer ein, z. B.:</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Peer-to-Peer-Sitzungen (d. h. Sitzungen mit nur zwei Teilnehmern) enthaltenen Informationen aufgeführt.

### <a name="metrics-for-peer-to-peer-sessions"></a>Metriken für Peer-to-Peer-Sitzungen

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
<td><p><strong>Absenderbenutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der die Peer-to-Peer-Sitzung initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der der Peer-to-Peer-Sitzung beigetreten ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalitäten</strong></p></td>
<td><p>Ja</p></td>
<td><p>In der Sitzung verwendete Kommunikationsart, z. B. Instant Messaging, Audio oder Dateiübertragung.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Einladungszeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die ursprüngliche Peer-to-Peer-Sitzungseinladung gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Antwortzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Das Datum und die Uhrzeit &quot;,&quot; zu dem der Benutzer die Sitzungseinladung angenommen hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Peer-to-Peer-Sitzung endete.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für Konferenzsitzungen (d. h. Sitzungen mit mindestens drei Teilnehmern) enthaltenen Informationen aufgeführt.

### <a name="metrics-for-conferencing-sessions"></a>Metriken für Konferenzsitzungen

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
<td><p>Eindeutige ID für die Konferenz. Wenn Sie auf dieses Element klicken, zeigt der Bericht den detaillierten Konferenzbericht für die ausgewählte Sitzung an. Erweitern Sie dieses Element, damit der der Bericht Informationen zu den Konferenzteilnehmern anzeigt. Ausführliche Informationen finden Sie im &quot;Abschnitt Metriken für Konferenz&quot; Teilnehmer weiter unten in diesem Thema.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisator</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der die Sitzung organisiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Ja</p></td>
<td><p>Name des in der Konferenz verwendeten Edgeservers (sofern vorhanden).</p></td>
</tr>
<tr class="even">
<td><p><strong>Startzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der Konferenz begann.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endzeitpunkt</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der die Konferenz endete.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>Metriken für Konferenzteilnehmer

In der folgenden Tabelle sind die im Bericht über Benutzeraktivität für jeden Teilnehmer einer Konferenz enthaltenen Informationen aufgeführt.

### <a name="metrics-for-conference-participants"></a>Metriken für Konferenzteilnehmer

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
<td><p>Netzwerkverbindungstyp. Beispielsweise &quot;aus Internal&quot; für interne Verbindung oder &quot;aus PSTN&quot; für Einwahlbenutzer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Beitrittszeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Benutzer der Konferenz beigetreten ist.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beendigungszeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Benutzer die Konferenz verlassen hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ „ms-diagnostics“), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt. Diagnostics-Header sind optional (SIP-Sitzungen ohne diese Header sind möglich) und Diagnose-IDs werden nur für Sitzungen berichtet, bei denen Probleme aufgetreten sind.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

