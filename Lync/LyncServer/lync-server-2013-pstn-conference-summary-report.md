---
title: 'Lync Server 2013: zusammenfassender PSTN-Konferenzbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b531d0e8d7d4fe5de6d1598cf557096ebff8a90
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Zusammenfassender PSTN-Konferenzbericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

In Microsoft lync Server 2013 handelt es sich bei einer PSTN-Konferenz um eine Konferenz, bei der sich mindestens ein Teilnehmer über ein PSTN-Telefon (Public Switched Telephone Network) an den Audioteil anwählt. (Ein PSTN-Telefon ist ein "Festnetz", ein Mobiltelefon oder ein beliebiges anderes Telefon, das nicht von Voice over IP Gebrauch macht.) Obwohl Sie in den Überwachungsberichten als PSTN-Konferenzen bezeichnet werden, werden diese Konferenzen möglicherweise häufiger als Einwahlkonferenzen bezeichnet.

Der "Zusammenfassende Bericht über PSTN-Konferenzen" liefert Informationen zu allen in Ihrer Organisation durchgeführten PSTN-Konferenzen (das sind alle Konferenzen mit mindestens einem Einwahlbenutzer). Der Bericht enthält Informationen zur Gesamtanzahl der PSTN-Konferenzen, der Gesamtanzahl der Teilnehmer an diesen Konferenzen und vielleicht als wichtigste Information, die Gesamtanzahl der Einwahlbenutzer (Metrik der PSTN-Teilnehmer insgesamt).

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>Zugreifen auf den "Zusammenfassenden Bericht über PSTN-Konferenzen"

Auf der Startseite "Überwachungsberichte" können Sie auf den "Zusammenfassenden Bericht über PSTN-Konferenzen" zugreifen. Dieser Bericht ist nicht mit anderen Berichten verknüpft. Beachten Sie, dass Sie keine ausführlichen Anrufinformationen für eine PSTN-Konferenz abrufen können. Als teilweise Erklärung hierfür kann angeführt werden, dass die einzelnen Endpunkte für die Übertragung dieser Informationen verantwortlich sind. PSTN-Telefone können keine ausführlichen Anrufinformationen nachverfolgen oder übertragen.

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Optimale Nutzung des "Zusammenfassenden Berichts über PSTN-Konferenzen"

Um den Prozentsatz aller ihrer Konferenzen zu ermitteln, die Einwahlbenutzer einschließen, vergleichen Sie den Wert der Gesamt Metrik für PSTN-Konferenzen mit der Metrik "Gesamt Konferenzen" [im zusammenfassenden Konferenzbericht in lync Server 2013](lync-server-2013-conference-summary-report.md).

Wenn nicht die von Ihnen erwartete Anzahl an PSTN-Konferenzen angezeigt wird, müssen Sie beachten, dass die Funktion zum Organisieren einer Konferenz, die Einwahlbenutzer zulässt, von der Konferenzrichtlinie abhängt, die einem Benutzern zugewiesen ist. Wenn eine geringe Anzahl Ihrer Benutzer berechtigt ist, PSTN-Konferenzen durchzuführen, werden nur wenige PSTN-Konferenzen angezeigt. Sie können schnell überprüfen, mit welcher Konferenzrichtlinie (falls vorhanden) die Benutzer PSTN-Konferenzen planen können, indem Sie den folgenden Befehl über die Lync Server-Verwaltungsshell ausführen:

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Dadurch werden Daten zurückgegeben, die den Folgenden ähneln:

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

Es werden Daten nach dem folgenden Muster zurückgegeben:

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Zusammenfassenden Bericht über PSTN-Konferenz festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Konferenzen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Zusammenfassenden Bericht über PSTN-Konferenz verwenden können.

### <a name="pstn-conference-summary-report-filters"></a>Filter im Zusammenfassenden Bericht über PSTN-Konferenz

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
<td><p><strong>From</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ziel</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p>Monatlich (maximal 12 Monate werden angezeigt)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall Täglich mit dem Startdatum 07.08.2012 und dem Enddatum 28.09.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Zusammenfassenden Bericht über PSTN-Konferenz angegeben werden.

### <a name="pstn-conference-summary-report-metrics"></a>Metriken im Zusammenfassenden Bericht über PSTN-Konferenz

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
<td><p>Gibt das ausgewählte Zeitintervall an. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall "Täglich" verwenden und auf 07.07.2012 klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.</p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

