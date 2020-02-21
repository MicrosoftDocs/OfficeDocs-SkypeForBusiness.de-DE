---
title: 'Lync Server 2013: fehlerlistenbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 010e8314eb7d2cbb33354461bdc2a1eb2c5b2cf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-list-report-in-lync-server-2013"></a>Fehlerlistenbericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-07-02_

Der fehlerlistenbericht enthält Informationen zu den einzelnen Teilnehmern, die an einer fehlgeschlagenen Peer-to-Peer-oder Konferenzsitzung teilgenommen haben. Diese Informationen umfassen den URI des Benutzers, der das Problem auftrat, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.

<div>

## <a name="accessing-the-failure-list-report"></a>Zugriff auf den fehlerlistenbericht

Der Zugriff auf den fehlerlistenbericht erfolgt durch Klicken auf eine der folgenden Metriken im [Bericht über Fehlerverteilung in lync Server 2013](lync-server-2013-failure-distribution-report.md):

  - Häufigste Diagnosegründe (Sitzungen)

  - Häufigste Modalitäten (Sitzungen)

  - Häufigste Pools (Sitzungen)

  - Häufigste Quellen (Sitzungen)

  - Häufigste Komponenten (Sitzungen)

  - Häufigste Absenderbenutzer (Sitzungen)

  - Häufigste Empfängerbenutzer (Sitzungen)

  - Häufigste Absenderbenutzer-Agents (Sitzungen)

Im fehlerlistenbericht können Sie auf den [Detailbericht über Peer-to-Peer-Sitzungen in lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Metrik Sitzungsdetails für eine Peer-to-Peer-Sitzung klicken. Sie können auch auf den Konferenz Detail Bericht zugreifen, indem Sie auf die Konferenz Metrik für eine Konferenz klicken.

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a>Optimale Verwendung des Fehlerlisten Berichts

Im fehlerlistenbericht können Sie einfach eine Beschreibung für jeden Antwortcode oder jede Diagnose-ID anzeigen, indem Sie die Maus über diesen Wert halten. Wenn Sie beispielsweise die Maus über die Diagnose-ID 7025 halten, wird Folgendes in einer QuickInfo angezeigt:

Interner Serverfehler beim Erstellen von Medien für den Benutzer.

Beachten Sie, dass der fehlerlistenbericht keine einfache Möglichkeit bietet, eine Liste aller Benutzer direkt abzurufen, die an mindestens einer fehlgeschlagenen Sitzung teilgenommen haben, und es ist auch nicht möglich, festzustellen, welche Benutzer am häufigsten an einem fehlgeschlagenen Vorgang beteiligt waren. Sitzung. (Für eine Sache hat der fehlerlistenbericht keine Filterfunktionen.) Wenn Sie die Daten jedoch exportieren und dann in eine Datei mit Komma getrennten Werten konvertieren, können Sie Windows PowerShell verwenden, um die Antworten auf Fragen wie diese zu finden. Nehmen Sie beispielsweise an, dass Sie die Daten in a speichern. CSV-Datei namens C\\:\\Data\_Failure List. CSV. Basierend auf den in dieser Datei gespeicherten Daten listet dieser Befehl alle Benutzer auf, die an mindestens einer fehlgeschlagenen Sitzung beteiligt waren:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Dieser Befehl gibt eine Liste zurück, die der folgenden ähnelt:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Mit diesen beiden Befehlen wird die Gesamtzahl der fehlerhaften Sitzungen zurückgemeldet, an denen jeder Benutzer beteiligt war:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Es werden Daten nach dem folgenden Muster zurückgegeben:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a>Filter

Keine. Sie können den fehlerlistenbericht nicht filtern.

</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im fehlerlistenbericht für jeden fehlgeschlagenen Anruf angegeben werden.

### <a name="failure-list-report-metrics"></a>Metriken des Fehlerlisten Berichts

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
<td><p><strong>Gemeldete Zeit</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit, an dem bzw. zu der der Bericht erfasst wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anforderung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Typ der fehlerhaften SIP-Anforderung. Beispielsweise invite oder bye.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Antwortcode, der bei einem Konferenz Fehler gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in der Form eines Headers vom Typ "ms-diagnostics"), die an eine SIP-Nachricht angehängt wird und oft nützliche Informationen für die Fehlerbehebung bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Join Cost time (MS)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeit (in Millisekunden), die der Benutzer benötigt, um an der Konferenz teilzunehmen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Von Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Von Benutzer-Agent</strong></p></td>
<td><p>Nein</p></td>
<td><p>Software, die vom Endpunkt des Benutzers verwendet wird, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers, der aufgerufen wurde.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

