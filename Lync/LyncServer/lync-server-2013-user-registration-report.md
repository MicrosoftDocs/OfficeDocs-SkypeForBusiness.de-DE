---
title: 'Lync Server 2013: Bericht über Benutzerregistrierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77edf04decc6aee7bb0cd292c1b5b0b38139a164
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Bericht über Benutzerregistrierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

Der Bericht über Benutzerregistrierung bietet eine Übersicht über die Benutzeranmelde Aktivität, vor allem Informationen zur Anzahl der Benutzer, die sich in einem bestimmten Zeitraum bei Microsoft lync Server 2013 angemeldet haben (stündlich, täglich, wöchentlich, monatlich). Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält. Er enthält keine Informationen dazu, *welche* Personen sich angemeldet haben. Überwachungsberichte bieten keine Informationen darüber, welche bestimmten Benutzer lync Server 2013 verwenden (und welche nicht). Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.

Bei der Bereitstellung von Informationen zu Benutzeranmeldungen werden vom Bericht über Benutzerregistrierung zwei erhebliche Unterschiede hervorgehoben. Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen. Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Fierwall Ihrer Organisation anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind). Externe Anmeldungen stellen Benutzer dar, die sich über eine Edgeserver von außerhalb der Firewall angemeldet haben (beispielsweise zählt ein Benutzer, der sich bei einem Internet Café angemeldet hat, als externe Anmeldung). Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.

Der Bericht über Benutzerregistrierung enthält zudem Informationen darüber, wie viele *aktive* Benutzer in einem bestimmten Zeitraum anwesend waren. Ein aktiver Benutzer ist ein Benutzer, der an einer Chatsitzung teilgenommen, an einer lync-Besprechung teilgenommen, einen Telefonanruf getätigt oder empfangen oder anderweitig lync Server in diesem Zeitraum verwendet hat. Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht tatsächlich genutzt haben.

<div>

## <a name="accessing-the-user-registration-report"></a>Zugreifen auf den Bericht über Benutzerregistrierung

Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Optimale Nutzung des Berichts über Benutzerregistrierung

Nachdem Sie lync Server einer häufig gestellten Frage bereitgestellt haben, lautet diese Vorgehensweise: Woher weiß ich, ob meine Benutzer diese neue Technologie tatsächlich verwenden? Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung dieser Frage helfen. Um festzustellen, ob Benutzer lync Server verwenden, müssen Sie zwei Dinge tun. Rufen Sie zunächst den Wert der Metrik "Eindeutige angemeldete Benutzer" im Bericht über Benutzerregistrierung ab. Dieser Wert gibt an, wie viele unterschiedliche Personen bei lync Server angemeldet sind.

Im Vergleich dazu zeigt die Metrik "Gesamt Anmeldungen" an, wie viele Personen insgesamt bei lync Server angemeldet sind. Nehmen wir beispielsweise an, dass Ken Myers an einem einzigen Tag an lync Server fünf verschiedenen Zeiten angemeldet ist. In diesem Fall zählt Ken Myer als fünf separate Anmeldesitzungen für die Metrik "Anmeldungen insgesamt", aber nur als ein angemeldeter Benutzer für die Metrik "Eindeutige angemeldete Benutzer". Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an. Beispielsweise kann sich ein Benutzer mit seinem Desktopcomputer, seinem Laptop Computer, anmelden, und er kann ein IP-Telefon haben, das sich automatisch bei lync Server anmeldet. In diesem Beispiel ist ein eindeutiger Benutzer mit drei Anmeldungen vorhanden.

Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzer</th>
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

Sie müssen nicht nur die Anzahl der eindeutigen Anmeldungen kennen, sondern auch die Gesamtzahl der Benutzer, die für lync Server aktiviert wurden. Dieser Wert kann abgerufen werden, indem Sie die lync Server 2013-Verwaltungsshell öffnen und den folgenden Windows PowerShell-Befehl ausführen:

    (Get-CsUser).Count

Wenn der obige Befehl den Wert 1.236 zurückgibt und die Metrik für eindeutige Anmeldebenutzer einen durchschnittlichen Wert von 667 zurückgibt, deutet dies darauf hin, dass sich etwas mehr als die Hälfte der Benutzer für lync tatsächlich am System anmelden (d. 667 dividiert durch 1.236). , was ungefähr 54% beträgt.

<div>


> [!WARNING]  
> Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben. Bereits am System angemeldete Benutzer werden nicht erfasst. Wenn die Metrik "Eindeutige angemeldete Benutzer" 667 Anmeldungen anzeigt und insgesamt 1.236 Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer am System anmeldet. Angenommen jedoch, 300 Benutzer waren bereits am System angemeldet, als Sie begonnen haben, die Anmeldedaten zu überprüfen. Das bedeutet, dass Sie tatsächlich fast 1.000 Benutzer bei lync Server angemeldet hatten, was dazu führen würde, dass näher an 80% ihrer Benutzer angemeldet waren.



</div>

Vergleichen Sie auch den Wert "Eindeutige angemeldete Benutzer" mit dem Wert der Metrik "Eindeutige aktive Benutzer". Die Metrik "Unique Active Users" gibt an, wie viele eindeutige Benutzer lync Server tatsächlich verwendet haben: Sie haben einen Anruf getätigt, sich einer lync-Besprechung angeschlossen oder an einer Chatsitzung teilgenommen. Dies sind nützliche Informationen, da Microsoft lync 2013 so konfiguriert werden können, dass Sie bei jedem Start von Windows automatisch gestartet werden. Aus diesem Grund haben Sie möglicherweise eine große Anzahl von Benutzern, die sich automatisch bei lync anmelden, wenn Sie sich jeden Tag bei Windows anmelden, aber in diesem Zeitraum niemals tatsächlich lync Server verwenden.

Die Metrik "Unique Active Users" bietet auch aussagekräftigere Daten in einer Organisation, in der Benutzer normalerweise nicht am Ende des Tages Windows abmelden. Stattdessen Sperren Sie einfach Ihre Computer und lassen Windows und lync auf dem laufenden. In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben. Eindeutige aktive Benutzer erfahren jedoch, ob Benutzer lync oder einen anderen lync Server-Client aktiv verwenden.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie mit dem Bericht über Benutzerregistrierung Daten für alle Registrierungsstellen Pools und Edgeserver anzeigen oder Daten für einen einzelnen Pool anzeigen. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.

### <a name="user-registration-report-filters"></a>Filter im Bericht über Benutzerregistrierung

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
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Beispiel: Wenn Sie das Intervall "Täglich" mit dem Startdatum 07.07.2012 und dem Enddatum 28.02.2012 ausgewählt haben, werden Daten für die Tage 07.08.2012 12:00 Uhr bis 07.09.2012 12:00 Uhr angezeigt (d. h. Daten für insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungsstellenpools oder Edgeservers. Sie können einen einzelnen Pool oder <strong>[Alle]</strong> auswählen, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind.

### <a name="user-registration-report-metrics"></a>Metriken im Bericht über Benutzerregistrierung

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
<td><p>Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das tägliche Intervall verwenden und auf 07.07.2012 klicken, wird eine stündliche Übersicht der Benutzerregistrierungsaktivität für dieses Datum angezeigt.</p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

