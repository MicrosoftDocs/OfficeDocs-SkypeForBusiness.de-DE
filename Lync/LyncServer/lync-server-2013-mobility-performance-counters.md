---
title: 'Lync Server 2013: Mobilitäts Leistungsindikatoren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c0759ccd6a9203dfac87f0ec55f555d49d19ccc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Mobilitäts Leistungsindikatoren in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

In den folgenden Tabellen sind die Namen und Beschreibungen der Leistungsindikatoren aufgeführt, die Sie zum Überwachen von Servern mit der Unified Communications Web-API (UCWA) und dem lync Server 2013 MCX-Mobilitätsdienst verwenden können.

Der Kategoriename für die Leistungsindikatoren in der UCWA-Tabelle ist **LS:WEB – UCWA**.

Der Kategoriename für die Leistungsindikatoren in der Mcx-Mobilitätsdiensttabelle ist **LS:WEB - Mobile Communication Service**.

<div>

## <a name="performance-counters-for-ucwa"></a>Leistungsindikatoren für UCWA


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Leistungsindikator</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anzahl aktiver Anwendungen</p></td>
<td><p>Die aktuelle Anzahl von Anwendungen.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der aktiven Anwendungsfreigabemodalitäten</p></td>
<td><p>Die aktuelle Anzahl der Anwendungsfreigabemodalitäten.</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der aktiven Audiomodalitäten</p></td>
<td><p>Die aktuelle Anzahl der Audiomodalitäten.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der aktiven Datenzusammenarbeitsmodalitäten</p></td>
<td><p>Die aktuelle Anzahl der Datenzusammenarbeitsmodalitäten.</p></td>
</tr>
<tr class="odd">
<td><p>Wartezeit bei Active Directory-HD-Fotoabruf (ms)</p></td>
<td><p>Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Active Directory an.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der aktiven Messaging-Modalitäten</p></td>
<td><p>Die aktuelle Anzahl der Messaging-Modalitäten.</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der aktiven Panoramavideomodalitäten</p></td>
<td><p>Die aktuelle Anzahl der Panoramavideomodalitäten.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl aktiver ausstehender GET-Anforderungen</p></td>
<td><p>Die Anzahl der derzeit aktiven ausstehenden GET-Anforderungen; lange gehaltene Verbindungen mit dem Server.</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl aktiver Sitzungen</p></td>
<td><p>Die aktuelle Gesamtzahl der Endpunkte, die in UCWA pro Anwendung registriert sind.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl aktiver Benutzerinstanzen</p></td>
<td><p>Die aktuelle Anzahl von Benutzerinstanzen.</p></td>
</tr>
<tr class="odd">
<td><p>Aktive Benutzerinstanzen ohne Anwendung</p></td>
<td><p>Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der aktiven Videomodalitäten</p></td>
<td><p>Die aktuelle Anzahl der Videomodalitäten.</p></td>
</tr>
<tr class="odd">
<td><p>Empfangene Anwendungserstellungsanforderungen/Sekunde</p></td>
<td><p>Die Rate der empfangenen Anwendungserstellungsanforderungen pro Sekunde.</p></td>
</tr>
<tr class="even">
<td><p>AS-MCU-Teilnahmefehler</p></td>
<td><p>Die Anzahl der AS-MCU-Teilnahmefehler.</p></td>
</tr>
<tr class="odd">
<td><p>Audio-Video-MCU-Teilnahmefehler</p></td>
<td><p>Die Anzahl der Audio-Video-MCU-Teilnahmefehler.</p></td>
</tr>
<tr class="even">
<td><p>Durchschnittliche Anwendungsstartzeit (ms)</p></td>
<td><p>Die durchschnittliche Anwendungsstartzeit in Millisekunden.</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Sitzungsdauer (ms)</p></td>
<td><p>Die durchschnittliche Dauer einer Sitzung in Millisekunden.</p></td>
</tr>
<tr class="even">
<td><p>Daten-MCU-Teilnahmefehler</p></td>
<td><p>Die Anzahl der Daten-MCU-Teilnahmefehler.</p></td>
</tr>
<tr class="odd">
<td><p>Wartezeit bei Exchange-Kontaktsuche (ms)</p></td>
<td><p>Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) bei der Suche eines Kontakts in Exchange an.</p></td>
</tr>
<tr class="even">
<td><p>Wartezeit bei Exchange-HD-Fotoabruf (ms)</p></td>
<td><p>Dieser Leistungsindikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange an.</p></td>
</tr>
<tr class="odd">
<td><p>HTTP-4xx-Antworten/Sekunde</p></td>
<td><p>Die Rate der Antworten mit dem HTTP-Code 4xx pro Sekunde.</p></td>
</tr>
<tr class="even">
<td><p>HTTP-5xx-Antworten/Sekunde</p></td>
<td><p>Die Rate der Antworten mit dem HTTP-Code 5xx pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Chat-MCU-Teilnahmefehler</p></td>
<td><p>Die Anzahl der Chat-MCU-Teilnahmefehler.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Fehlern beim Abruf von Fotos aus Active Directory</p></td>
<td><p>Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory.</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl von Fehlern bei Kontaktsuche</p></td>
<td><p>Die Gesamtzahl von Fehlern bei der Kontaktsuche in Exchange.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl von Deserialisierungsfehlern</p></td>
<td><p>Die Gesamtzahl der Deserialisierungsfehler.</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der HD-fotofehler erhalten</p></td>
<td><p>Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange.</p></td>
</tr>
<tr class="even">
<td><p>Über Maximum an Abonnements pro Anwendung</p></td>
<td><p>Die Anzahl der Abonnementanforderungen über der maximal pro Anwendung erlaubten Anzahl.</p></td>
</tr>
<tr class="odd">
<td><p>Über Maximum an Abonnements pro Batch</p></td>
<td><p>Die Anzahl der Abonnementanforderungen über der maximal pro Batch erlaubten Anzahl.</p></td>
</tr>
<tr class="even">
<td><p>Fehler beim Abonnieren der Anwesenheit</p></td>
<td><p>Die Anzahl der Fehler beim Abonnieren der Anwesenheit.</p></td>
</tr>
<tr class="odd">
<td><p>Fehler beim Registrieren von Endpunkten</p></td>
<td><p>Die Anzahl der Fehler beim Registrieren von Endpunkten.</p></td>
</tr>
<tr class="even">
<td><p>Empfangene Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der empfangenen Anforderungen pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Erfolgreiche Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der erfolgreichen Anforderungen pro Sekunde (HTTP-Antwortcodes 2xx/3xx).</p></td>
</tr>
<tr class="even">
<td><p>Erfolgreiche Anwendungserstellungsanforderungen/Sekunde</p></td>
<td><p>Die Rate der erfolgreichen Anwendungserstellungsanforderungen pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der GET-Anforderungen mit Timeout</p></td>
<td><p>Die Anzahl der ausstehenden GET-Anforderungen, bei denen das Zeitlimit überschritten wurde.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der empfangenen Anwendungserstellungsanforderungen</p></td>
<td><p>Die Gesamtzahl der Anwendungserstellungsanforderungen, die seit dem Start des Diensts empfangen wurden.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der HTTP-4xx-Antworten</p></td>
<td><p>Die Gesamtzahl der HTTP-Antworten vom Typ 4xx.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der HTTP-5xx-Antworten</p></td>
<td><p>Die Gesamtzahl der HTTP-Antworten vom Typ 5xx.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</p></td>
<td><p>Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der erfolgreichen Anforderungen</p></td>
<td><p>Die Gesamtzahl der erfolgreichen Anforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der initiierten Sitzungen</p></td>
<td><p>Die Gesamtzahl der Sitzungen, die seit dem Start des Diensts initiiert wurden.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts beendet wurden</p></td>
<td><p>Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der gedrosselten Anwendungen</p></td>
<td><p>Die Anzahl der gedrosselten Anwendungen.</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Leistungsindikatoren für den Mcx-Mobilitätsdienst

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Leistungsindikator</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Durchschnittliche Sitzungsdauer in Millisekunden</p></td>
<td><p>Die durchschnittliche Dauer einer Sitzung in Millisekunden.</p></td>
</tr>
<tr class="even">
<td><p>Aktuelle Pushbenachrichtigungsabonnements</p></td>
<td><p>Die aktuelle Anzahl von Pushbenachrichtigungsabonnements. Diese Anzahl in Verbindung mit „Anzahl derzeit aktiver Sitzungen“ stellt eine Teilmenge der derzeit aktiven Sitzungen dar, die für Windows Mobile- oder iPhone-Geräte registriert sind.</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl derzeit aktiver Netzwerkumfragen mit Timeout</p></td>
<td><p>Die Anzahl von Netzwerkumfragen, bei denen ein Timeout aufgetreten ist.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl derzeit aktiver Umfragen</p></td>
<td><p>Die Anzahl von derzeit aktiven Umfragen (lange gehaltene Verbindungen mit dem Server).</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl derzeit aktiver Sitzungen</p></td>
<td><p>Die derzeitige Anzahl der im Mobilitätsdienst registrierten Endpunkte.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements</p></td>
<td><p>Die Anzahl derzeit aktiver Sitzungen mit aktiven Anwesenheitsabonnements.</p></td>
</tr>
<tr class="odd">
<td><p>Gescheiterte Pushbenachrichtigungsanforderungen/Sekunde</p></td>
<td><p>Die Anzahl der gescheiterten Pushbenachrichtigungsanforderungen pro Sekunde.</p></td>
</tr>
<tr class="even">
<td><p>Erfolgreiche Pushbenachrichtigungsanforderungen/Sekunde</p></td>
<td><p>Die Anzahl der erfolgreichen Pushbenachrichtigungsanforderungen pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Gedrosselte Pushbenachrichtigungsanforderungen/Sekunde</p></td>
<td><p>Die Anzahl der gedrosselten Pushbenachrichtigungsanforderungen pro Sekunde.</p></td>
</tr>
<tr class="even">
<td><p>Pushbenachrichtigungsanforderungen/Sekunde</p></td>
<td><p>Die Anzahl der gesendeten Pushbenachrichtigungsanforderungen pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Gescheiterte Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der gescheiterten Anforderungen pro Sekunde.</p></td>
</tr>
<tr class="even">
<td><p>Empfangene Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der empfangenen Anforderungen pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Abgelehnte Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der abgelehnten Anforderungen pro Sekunde.</p></td>
</tr>
<tr class="even">
<td><p>Erfolgreiche Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der erfolgreichen Anforderungen pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Erfolgreiche Anforderungen zur Sitzungsinitiierung/Sekunde</p></td>
<td><p>Die Anzahl der erfolgreichen Anforderungen zur Standortermittlung pro Sekunde. Anforderungen zum Initiieren einer Sitzung beanspruchen die meisten CPU-Ressourcen auf dem Server. Maximal wird eine Last von 12 Anforderungen/Sekunde unterstützt. Die Aufrechterhaltbarkeit hängt von anderen Lasten auf dem Server ab. Das Initiieren einer Sitzung bedeutet normalerweise, dass ein Benutzer angemeldet wird, der für einen längeren Zeitraum abgemeldet war.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der abgelehnten eingehenden Sprachanrufe</p></td>
<td><p>Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der gescheiterten eingehenden Sprachanrufe</p></td>
<td><p>Die Gesamtzahl der gescheiterten eingehenden Sprachanrufe.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der gescheiterten ausgehenden Sprachanrufe</p></td>
<td><p>Die Gesamtzahl der gescheiterten ausgehenden Sprachanrufe.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der vom Benutzer beendeten Sitzungen</p></td>
<td><p>Die Gesamtzahl der vom Benutzer beendeten Sitzungen.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der Pushbenachrichtigungsanforderungen</p></td>
<td><p>Die Gesamtzahl der Pushbenachrichtigungsanforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl gescheiterter Pushbenachrichtigungsanforderungen</p></td>
<td><p>Die Gesamtzahl der gescheiterten Pushbenachrichtigungsanforderungen.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl erfolgreicher Pushbenachrichtigungsanforderungen</p></td>
<td><p>Die Gesamtzahl der erfolgreichen Pushbenachrichtigungsanforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl gedrosselter Pushbenachrichtigungsanforderungen</p></td>
<td><p>Die Gesamtzahl der gedrosselten Pushbenachrichtigungsanforderungen.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der gescheiterten Anforderungen</p></td>
<td><p>Die Gesamtzahl der gescheiterten Anforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der über den Befehlskanal empfangenen Anforderungen</p></td>
<td><p>Die Gesamtzahl der über den Befehlskanal empfangenen Anforderungen.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der abgelehnten Anforderungen</p></td>
<td><p>Die Gesamtzahl der abgelehnten Anforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der erfolgreichen Anforderungen</p></td>
<td><p>Die Gesamtzahl der an den Mobilitätsdienst gerichteten Anforderungen, die erfolgreich waren.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der initiierten Sitzungen</p></td>
<td><p>Die Gesamtzahl der Sitzungen, die seit dem Start des Mobilitätsdiensts initiiert wurden.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der Sitzungen, die aufgrund eines Leerlauftimeouts des Benutzers beendet wurden</p></td>
<td><p>Die Gesamtzahl der Sitzungen, die beendet wurden, da das Leerlauftimeout des Benutzers erreicht wurde.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der erfolgreichen eingehenden Sprachanrufe</p></td>
<td><p>Die Gesamtzahl der erfolgreichen eingehenden Sprachanrufe.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe</p></td>
<td><p>Die Gesamtzahl der erfolgreichen ausgehenden Sprachanrufe.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

