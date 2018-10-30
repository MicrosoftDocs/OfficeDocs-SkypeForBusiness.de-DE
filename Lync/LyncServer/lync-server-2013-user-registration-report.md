---
title: 'Lync Server 2013: Bericht über Benutzerregistrierung'
TOCTitle: Bericht über Benutzerregistrierung
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558614(v=OCS.15)
ms:contentKeyID: 49293272
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bericht über Benutzerregistrierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Der Bericht über Benutzerregistrierung bietet eine Übersicht über die Anmeldeaktivität von Benutzern, hauptsächlich über die Anzahl der Benutzer, die sich in einem angegebenen Zeitraum (stündlich, täglich, wöchentlich oder monatlich) bei Microsoft Lync Server 2013 angemeldet haben. Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält. Er enthält keine Informationen dazu, *welche* Personen sich angemeldet haben. Überwachungsberichte bieten keine Informationen dazu, welche bestimmten Benutzer Lync Server 2013 verwenden (oder nicht verwenden). Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.

Bei der Bereitstellung von Informationen zu Benutzeranmeldungen werden vom Bericht über Benutzerregistrierung zwei erhebliche Unterschiede hervorgehoben. Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen. Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Fierwall Ihrer Organisation anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind). Bei externen Anmeldungen handelt es sich um Benutzer, die sich außerhalb der Firewall über einen Edgeserver anmelden (ein Benutzer, der sich in einem Internetcafé anmeldet gilt beispielsweise als externe Anmeldung). Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.

Der Bericht über Benutzerregistrierung enthält zudem Informationen darüber, wie viele *aktive* Benutzer in einem bestimmten Zeitraum anwesend waren. Bei einem aktiven Benutzer handelt es sich um einen Benutzer, der an einer Chatsitzung oder an einerLync-Besprechung teilgenommen hat, einen Telefonanruf getätigt oder empfangen hat, oder Lync Server während dieses Zeitraums anderweitig genutzt hat. Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht tatsächlich genutzt haben.

## Zugreifen auf den Bericht über Benutzerregistrierung

Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.

## Optimale Nutzung des Berichts über Benutzerregistrierung

Nach der Bereitstellung von Lync Server wird häufig folgende Frage gestellt: Woher weiß ich, ob meine Benutzer diese neue Technologie tatsächlich nutzen? Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung dieser Frage helfen. Sie müssen zwei Schritte ausführen, um festzustellen, ob Benutzer Lync Server verwenden oder nicht. Rufen Sie zunächst den Wert der Metrik "Eindeutige angemeldete Benutzer" im Bericht über Benutzerregistrierung ab. Anhand dieses Werts erfahren Sie, wie viele einzelne Benutzer sich an Lync Server angemeldet haben.

Im Vergleich dazu zeigt die Metrik "Anmeldungen insgesamt", wie viele Anmeldungen an Lync Server insgesamt stattfanden. Angenommen, Ken Myer hat sich an einem Tag fünf Mal an Lync Server angemeldet. In diesem Fall zählt Ken Myer als fünf separate Anmeldesitzungen für die Metrik "Anmeldungen insgesamt", aber nur als ein angemeldeter Benutzer für die Metrik "Eindeutige angemeldete Benutzer". Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an. Ein Benutzer kann sich beispielsweise auf seinem Desktopcomputer oder Laptop anmelden oder über ein IP-Telefon verfügen, das automatisch an Lync Server angemeldet wird. In diesem Beispiel ist ein eindeutiger Benutzer mit drei Anmeldungen vorhanden.

Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>User</th>
<th>Anmeldezeitpunkt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 08:45:00</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 08:46:00</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>07.07.2012 09:17:00</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>07.07.2012 09:22:00</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>07.07.2012 09:31:00</p></td>
</tr>
</tbody>
</table>


Insgesamt fanden fünf Anmeldungen statt, es sind jedoch nur zwei eindeutige angemeldete Benutzer vorhanden: Ken Myer (der sich dreimal angemeldet hat) und Pilar Ackerman (die sich zweimal angemeldet hat). Darin besteht der Unterschied zwischen Anmeldungen und eindeutigen angemeldeten Benutzern.

Neben der Anzahl an eindeutige Anmeldungen muss Ihnen auch die Gesamtanzahl der Benutzer bekannt sein, die für Lync Server aktiviert sind. Dieser Wert kann durch Öffnen der Verwaltungsshell für Lync Server 2013 und Ausführen des folgenden Windows PowerShell-Befehls abgerufen werden:

    (Get-CsUser).Count

Wenn der vorhergehende Befehl den Wert 1.236 und die Metrik "Eindeutige angemeldete Benutzer" den Wert of 667, deutet dies darauf hin, dass etwas mehr über die Hälfte Ihrer Benutzer, die für Lync aktiviert sind, sich tatsächlich jeden Tag am System anmelden (667 geteilt durch 1.236 ergibt etwa 54 %).


> [!WARNING]
> Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben. Bereits am System angemeldete Benutzer werden nicht erfasst. Wenn die Metrik "Eindeutige angemeldete Benutzer" 667&nbsp;Anmeldungen anzeigt und insgesamt 1.236&nbsp;Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer am System anmeldet. Angenommen jedoch, 300&nbsp;Benutzer waren bereits am System angemeldet, als Sie begonnen haben, die Anmeldedaten zu überprüfen. In diesem Fall wären tatsächlich bereits fast 1.000&nbsp;Benutzer und damit beinahe 80&nbsp;% Ihrer Benutzer an Lync Server angemeldet gewesen.



Vergleichen Sie auch den Wert "Eindeutige angemeldete Benutzer" mit dem Wert der Metrik "Eindeutige aktive Benutzer". Die Metrik "Eindeutige aktive Benutzer" gibt an, wie viele aktive Benutzer Lync Server tatsächlich verwendet haben, indem sie z. B. einen Telefonanruf getätigt haben, einer Lync-Besprechung beigetreten sind oder an einer Chatsitzung teilgenommen haben. Diese Informationen sind nützlich, da Microsoft Lync 2013 so konfiguriert werden kann, dass es immer automatisch gestartet wird, wenn ein Benutzer Windows startet. Daher wird u. U. jeden Tag eine höhere Anzahl von Benutzern automatisch an Lync angemeldet, wenn sie sich an Windows anmelden, die Lync Server während dieses Zeitraum aber tatsächlich nicht benutzen.

Die Metrik "Eindeutige aktive Benutzer" stellt auch in einer Organisation aussagekräftigere Daten zur Verfügung, in der sich Benutzer in der Regel am Ende des Tages nicht von Windows abmelden. Stattdessen sperren sie einfach einfach ihre Computer, und Windows und Lync werden weiter ausgeführt. In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben. Die Metrik "Eindeutige aktive Benutzer" gibt jedoch an, ob Benutzer Lync oder einen anderen Lync Server-Client aktiv nutzen.

## Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Bericht über Benutzerregistrierung Daten für alle Ihre Registrierungsstellenpool und Edgeserver anzeigen oder nur für einen einzelnen Pool. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.

### Filter im Bericht über Benutzerregistrierung

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
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.12</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>07.07.12</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>03.07.12</p>
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
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall &quot;Täglich&quot; mit dem Startdatum &quot;07.07.2012&quot; und dem Enddatum &quot;28.09.2012&quot; ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2011 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool oder <strong>[Alle]</strong> auswählen, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
</tbody>
</table>


## Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind.

### Metriken im Bericht über Benutzerregistrierung

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
<td><p>Gibt das Zeitintervall an, das Sie auf der Symbolleiste für Filter ausgewählt haben. Sie können auf ein einzelnes Zeitintervall klicken, um Details zu diesem Intervall abzurufen. Wenn Sie beispielsweise das Intervall &quot;Täglich&quot; verwenden und auf &quot;07.07.2012&quot; klicken, sehen Sie die nach Stunden aufgeschlüsselten Benutzerregistrierungsaktivitäten an diesem Tag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anmeldungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der erfolgreichen Anmeldesitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interne Anmeldungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anmeldungen im internen Netzwerk.</p></td>
</tr>
<tr class="even">
<td><p><strong>Externe Anmeldungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anmeldungen von außerhalb des internen Netzwerks über den Edgeserver.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Eindeutige angemeldete Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die mindestens eine Anmeldesitzung hatten. Ein Benutzer, der mehrere Anmeldesitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Anmeldesitzung ausgeführt hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eindeutige aktive Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die an einer Peer-zu-Peer- oder Konferenzsitzung teilgenommen haben. Ein Benutzer, der mehrere Sitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Sitzung ausgeführt hat.</p></td>
</tr>
</tbody>
</table>

