---
title: 'Lync Server 2013: Inventurbericht über IP-Telefone'
TOCTitle: Inventurbericht über IP-Telefone
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg615027(v=OCS.15)
ms:contentKeyID: 49295045
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Inventurbericht über IP-Telefone in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht für den IP-Telefonbestand enthält Informationen zu den IP-Telefonen, die derzeit in der Organisation verwendet werden. Er umfasst eine detaillierte Liste der IP-Telefone, die während des angegebenen Berichtszeitraums tatsächlich verwendet wurden. Mithilfe dieses Berichts können Administratoren unter anderem Informationen dazu erhalten, ob alte oder veraltete Telefone vorhanden sind, die ausgetauscht werden sollten. Zudem können Administratoren darauf hingewiesen werden, dass in der Organisation teure Telefone existieren, die kaum verwendet werden. Solche Informationen können außerordentlich wertvoll sein, wenn es darum geht, neue Telefone zu kaufen oder vorhandene Telefone neu zu verteilen. (Ein Benutzer, der sein teures Telefon selten nutzt, kann beispielsweise gebeten werden, sein Telefon mit einem Benutzer zu tauschen, der sein Telefon häufiger verwendet.)

Es gilt zu beachten, dass dieser Bericht hinsichtlich der Verwendung als echter Bestandsbericht einigen Einschränkungen unterliegt. Im IP-Telefonbericht werden beispielsweise einfach alle Telefone aufgelistet, für die während des angegebenen Zeitraums Anmeldungen bei Lync Server erfolgt sind (sortiert nach dem Zeitpunkt der letzten Anmeldung). Wenn für ein Telefon während dieses Zeitrausm keine Anmeldung erfolgt ist, wird es nicht im Bestandsbericht aufgeführt. Dies schließt Telefone ein, die vor dem jeweiligen Zeitraum angemeldet wurden und die während des angegebenen Zeitintervalls weiterhin angemeldet waren. Angenommen, Sie möchten den gesamten Telefonbestand für Juli 2012 anzeigen und verschiedene Telefone wurden am 30. Juni 2012 bei Lync Server angemeldet, wobei sie am 1. Juli weiterhin angemeldet waren. Diese Telefone sind im Bestandsbericht für den 1. Juli nicht enthalten.

Weiterhin muss beachtet werden, dass der Bestandsbericht Telefone einschließen kann, die in Ihrer Organisation nicht mehr verwendet werden. Angenommen, eine bestimmte Anzahl Telefone von Fabrikam wurde am 1. Juli 2012 beim System angemeldet. Fünf Tage später hat sich Ihre Organisation dazu entschlossen, diese Fabrikam-Telefone durch ein neueres Modell von Contoso auszutauschen. Die Fabrikam-Telefone werden jedoch weiterhin im "Bestandsbericht" aufgeführt, weil sie im Juli beim System angemeldet wurden.

Darüber hinaus werden im Bericht für den IP-Telefonbestand keine zusammenfassenden Gesamtzahlen für die verschiedenen Telefontypen angegeben. Nehmen wir beispielsweise an, Sie besitzen 105 Telefone vom Typ Polycom CX600. Aus dem Bericht wird nicht ersichtlich, dass Sie 105 solcher Telefone haben. Stattdessen sehen Sie lediglich 105 separate Einträge für das Modell Polycom Cx600. Die einzige Möglichkeit, um herauszufinden, dass für das Modell Polycom Cx600 105 Einträge vorliegen, besteht darin, diese Einträge manuell zu zählen.


> [!WARNING]
> Alternativ dazu können Sie die Daten exportieren und die Zählung in Microsoft Excel oder Windows PowerShell vornehmen.



## Zugreifen auf den Bericht für den IP-Telefonbestand

Der Zugriff auf den Bericht für den IP-Telefonbestand erfolgt über die Startseite der Überwachungsberichte. Wenn Sie auf die Metrik "Benutzer-URI" klicken, können Sie auf den Benutzeraktivitätsbericht für den jeweiligen Benutzer zugreifen. Wenn Sie für einen Peer-zu-Peer-Anruf auf die Metrik "Letzte Aktivität" klicken, gelangen Sie zum Detailbericht über Peer-zu-Peer-Sitzungen. Wenn Sie für eine Konferenz auf dieselbe Metrik klicken, gelangen Sie zum detaillierten Konferenzbericht.

## Optimale Nutzung des Berichts für den IP-Telefonbestand

Wenn Sie nur an Verwendungsinformationen für einen bestimmten Telefontyp interessiert sind (Beispiel: "Wie oft verwenden die Benutzer ein Polycom CX600-Telefon?"), können Sie diese Informationen direkt aus dem Bericht für den IP-Telefonbestand abrufen, indem Sie eine Filterung nach diesem bestimmten Telefontyp ausführen. Wenn Sie jedoch zusammenfassende Informationen für alle Telefone erhalten möchten (wie viele Personen verwenden ein Polycom CX600, wie viele verwenden ein LG-Nortel IP8540 usw.), müssen Sie die Daten exportieren und diese Analyse mithilfe einer anderen Anwendung (z. B. mit Windows PowerShell) ausführen. Nehmen wir beispielsweise an, Sie exportieren die Daten in eine Datei mit durch Komma getrennten Werten (C:\\Data\\IP\_Phone\_Inventory\_Report.csv). In diesem Fall können Sie die folgenden beiden Befehle verwenden, um für alle Ihre Telefone zusammenfassende Daten bereitzustellen:

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

Die zurückgegebenen Daten sehen so ähnlich aus, wie diese:

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

Gleichermaßen erhalten Sie mithilfe dieser beiden Befehle Informationen dazu, welche Telefone zwar beim System angemeldet, aber tatsächlich nie zum Telefonieren genutzt wurden (der Wert der Metrik "Letzte Aktivität" ist leer und gibt somit an, dass es keine letzte Aktivität gab):

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

Dabei werden für alle nicht verwendeten Telefone Daten zurückgegeben, die den Folgenden ähneln:

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Eine andere interessante Verwendungsmöglichkeit des Berichts für den IP-Telefonbestand lautet wie folgt: wenn Sie die MAC-Adresse eines IP-Telefons haben, können Sie den Benutzer ermitteln, der das Telefon zuletzt verwendet hat. Dazu geben Sie einfach die jeweilige Adresse in das Textfeld für die MAC-Adresse ein. Daraufhin gibt der Bericht für den IP-Telefonbestand (unter anderem) die SIP-Adresse des Benutzers zurück, der sich mit diesem Telefon zuletzt angemeldet hat. Alternativ können Sie die SIP-Adresse eines Benutzers eingeben (im Feld "Präfix des Benutzer-URI"), um alle Telefone zu finden, die von diesem Benutzer verwendet wurden.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der IP-Telefonbestand ermöglicht Ihnen beispielsweise das Anzeigen von Telefonen eines bestimmten Herstellers oder sogar einer bestimmten Version dieser Telefone. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht für den IP-Telefonbestand verwenden können.

### Bericht für den IP-Telefonbestand - Filter

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
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 PM</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Hersteller</strong></p></td>
<td><p>Name des Herstellers des IP-Telefons. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hardwareversion</strong></p></td>
<td><p>Versionsnummer des IP-Telefons; mit den Filtern für den Hersteller und die Hardwareversion können Sie einen bestimmten Telefontyp eindeutig identifizieren. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Benutzer-Agent</strong></p></td>
<td><p>ID für die vom IP-Telefon verwendete Software. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>MAC-Adresse</strong></p></td>
<td><p>Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse (Media Access Control) wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</p>
<p>Zum Suchen nach Datensätzen mit einer bestimmten MAC-Adresse geben Sie einfach diese Adresse ein, z. B.:</p>
<p>00-08-5D-16-16-48</p>
<p>Die Adresse muss vollständig eingegeben werden. Ein Teil einer Adresse (z. B. 00-08-5D) gibt keine Daten zurück.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Letzte Aktivität vor (Tage)</strong></p></td>
<td><p>Wählen Sie einen der folgenden Werte:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>10</p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Zuletzt abgemeldet vor (Tage)</strong></p></td>
<td><p>Wählen Sie einen der folgenden Werte:</p>
<ul>
<li><p>[Alle]</p></li>
<li><p>10</p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Präfix des Benutzer-URI</strong></p></td>
<td><p>SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</p></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht für den IP-Telefonbestand angegeben werden.

### Bericht für den IP-Telefonbestand - Metriken

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
<td><p><strong>Hersteller</strong></p></td>
<td><p>Ja</p></td>
<td><p>Name des Herstellers des IP-Telefons.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hardwareversion</strong></p></td>
<td><p>Ja</p></td>
<td><p>Versionsnummer des IP-Telefons.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MAC-Adresse</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Benutzer-URI</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Benutzer-Agent</strong></p></td>
<td><p>Ja</p></td>
<td><p>ID für die vom IP-Telefon verwendete Software.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zuletzt angemeldet um:</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit der letzten Anmeldung des IP-Telefons bei Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zuletzt abgemeldet um:</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit der letzten Abmeldung des IP-Telefons von Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Letzte Aktivität</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit der letzten Verwendung des IP-Telefons.</p></td>
</tr>
</tbody>
</table>

