---
title: 'Lync Server 2013: Fehlerlistenbericht'
TOCTitle: Fehlerlistenbericht
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615446(v=OCS.15)
ms:contentKeyID: 49295172
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Fehlerlistenbericht in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Fehlerlistenbericht enthält ausführliche Informationen über die einzelnen Teilnehmer, die an einer fehlerhaften Peer-zu-Peer-Sitzung oder Konferenzsitzung beteiligt waren. Diese Informationen umfassen den URI des Benutzers, bei dem das Problem aufgetreten ist, sowie den SIP-Antwortcode und die Diagnose-ID, die dem Fehler zugeordnet sind.

## Zugriff auf den Fehlerlistenbericht

Der Zugriff auf den Fehlerlistenbericht ist durch Klicken auf eine der folgenden Metriken [Bericht über Fehlerverteilung in Lync Server 2013](lync-server-2013-failure-distribution-report.md) möglich:

  - Wichtigste Diagnosegründe (Sitzungen)

  - Wichtigste Modalitäten (Sitzungen)

  - Wichtigste Pools (Sitzungen)

  - Wichtigste Quellen (Sitzungen)

  - Wichtigste Komponenten (Sitzungen)

  - Wichtigste "Von Benutzer" (Sitzungen)

  - Wichtigste "An Benutzer" (Sitzungen)

  - Wichtigste "Von Benutzeragenten" (Sitzungen)

Über den Fehlerlistenbericht können Sie auf den [Detailbericht über Peer-zu-Peer-Sitzungen in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) zugreifen, indem Sie auf die Sitzungsdetailmetrik für eine Peer-zu-Peer-Sitzung klicken. Sie können ebenfalls auf den detaillierten Konferenzbericht zugreifen, indem Sie auf die Konferenzmetrik für eine Konferenz klicken.

## Bestmögliche Verwendung des Fehlerlistenberichts

Im Fehlerlistenbericht können Sie eine Beschreibung für jeden Antwortcode bzw. jede Diagnose-ID sehen, indem Sie einfach den Mauszeiger über diesen Wert halten. Wenn Sie zum Beispiel Ihre Maus über die Diagnose-ID 7025 halten, wird in einer QuickInfo folgender Text angezeigt:

Interner Serverfehler erstellt Medien für Benutzer.

Dabei muss beachtet werden, dass der Fehlerlistenbericht weder eine einfache Methode zum direkten Abrufen einer Liste aller Benutzer, die an einer fehlerhaften Sitzung beteiligt waren, noch eine Methode zur Ermittlung der Benutzer, die am häufigsten an einer fehlerhaften Sitzung beteiligt waren, darstellt. (Der Fehlerlistenbericht verfügt zunächst einmal nicht über Filterfunktionen.) Wenn Sie jedoch die Daten exportieren und in eine CSV-Datei umwanden, können Sie Windows PowerShell verwenden, um Antworten auf Fragen wie diese zu finden. Zum Beispiel können Sie die Daten in einer CSV-Datei mit dem Namen "C:\\Data\\Failure\_List.csv" speichern. Auf Basis der in dieser Datei gespeicherten Daten können mithilfe dieses Befehls alle Benutzer aufgelistet werden, die an mindestens einer fehlerhaften Sitzung beteiligt waren:

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

Die Ausgabe für den Befehl ist eine Liste, die der folgenden Liste ähnelt:

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

Diese beiden Befehle melden die Gesamtzahl der fehlerhaften Sitzungen zurück, an denen Benutzer beteiligt waren:

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

## Filter

Keine. Sie können den Fehlerlistenbericht nicht filtern.

## Metriken

In der folgenden Tabelle sind die im Fehlerlistenbericht enthaltenen Informationen für jeden fehlerhaften Anruf aufgeführt.

### Metriken des Fehlerlistenberichts

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
<td><p><strong>Gemeldeter Zeitpunkt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Datum und Uhrzeit der Aufzeichnung des Berichts.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anforderung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Typ der fehlerhaften SIP-Anforderung. Beispiel: INVITE oder BYE.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Antwortcode</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Antwortcode, der bei einem Konferenzfehler gesendet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Diagnose-ID</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eindeutige ID (in Form eines Headers vom Typ &quot;ms-diagnostics&quot;), die einer SIP-Nachricht angefügt ist, die häufig nützliche Informationen für die Problembehandlung von Fehlern bereitstellt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Beitrittszeitraum (ms)</strong></p></td>
<td><p>Nein</p></td>
<td><p>Zeitraum (in Millisekunden), der erforderlich ist, damit der Benutzer der Konferenz beitreten kann.</p></td>
</tr>
<tr class="even">
<td><p><strong>Von Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Von Benutzer-Agent</strong></p></td>
<td><p>Nein</p></td>
<td><p>Software, die vom Endpunkt des Benutzers, der den Anruf initiiert hat, verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>An Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>SIP-Adresse des Benutzers, der angerufen wurde.</p></td>
</tr>
</tbody>
</table>

