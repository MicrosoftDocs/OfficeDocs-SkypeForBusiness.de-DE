---
title: 'Lync Server 2013: Leistungsindikatoren für die Mobilität'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility performance counters
ms:assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690046(v=OCS.15)
ms:contentKeyID: 48185441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56454e4ea4fa1498dc73056d5b5f01193b007352
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-performance-counters-in-lync-server-2013"></a>Mobilitäts Leistungsindikatoren in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

In den folgenden Tabellen sind die Namen und Beschreibungen der Leistungsindikatoren aufgeführt, die Sie zum Überwachen von Servern mit dem Unified Communications Web API (UCWA) und dem lync Server 2013 MCX-Mobilitätsdienst verwenden können.

Der Kategorienamen für die Leistungsindikatoren in der UCWA-Tabelle lautet **ls: "UCWA**".

Der Kategoriename für die Leistungsindikatoren in der MCX-Mobilitätsdienst Tabelle lautet **ls: mobiler Kommunikationsdienst**.

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
<td><p>Die aktuelle Anzahl von Anwendungen</p></td>
</tr>
<tr class="even">
<td><p>Anzahl aktiver Modality für die Anwendungsfreigabe</p></td>
<td><p>Die aktuelle Anzahl von Modalitäten für die Anwendungsfreigabe</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl aktiver audiomodaler Daten</p></td>
<td><p>Die aktuelle Anzahl an audiomodalen Daten</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der aktiven Daten Zusammenarbeits Modalitäten</p></td>
<td><p>Die aktuelle Anzahl der Daten Zusammenarbeits Modalitäten</p></td>
</tr>
<tr class="odd">
<td><p>Wartezeit für Active Directory Photo get (MS)</p></td>
<td><p>Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Active Directory an.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl aktiver Messaging-Modalitäten</p></td>
<td><p>Die aktuelle Anzahl von Messaging Modalitäten</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl aktiver Panorama-Video Modalitäten</p></td>
<td><p>Die aktuelle Anzahl der Panorama Video Modalitäten</p></td>
</tr>
<tr class="even">
<td><p>Aktive ausstehende Get-Anzahl</p></td>
<td><p>Die Anzahl der derzeit aktiven ausstehenden Gets; lange gehaltene Verbindungen mit dem Server</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl aktiver Sitzungen</p></td>
<td><p>Die aktuelle Anzahl von Endpunkten, die in UCWA pro Anwendung und Gesamtzahl registriert sind.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der aktiven Benutzerinstanzen</p></td>
<td><p>Die aktuelle Anzahl von Benutzerinstanzen</p></td>
</tr>
<tr class="odd">
<td><p>Aktive Benutzerinstanzen ohne Anwendung</p></td>
<td><p>Die aktuelle Anzahl von Benutzerinstanzen ohne Anwendung</p></td>
</tr>
<tr class="even">
<td><p>Anzahl aktiver Video Modalitäten</p></td>
<td><p>Die aktuelle Anzahl von Video Modalitäten</p></td>
</tr>
<tr class="odd">
<td><p>Empfangene Anwendungs Erstellungsanforderungen/Sekunde</p></td>
<td><p>Die Anzahl der empfangenen Anwendungs Erstellungsanforderungen pro Sekunde.</p></td>
</tr>
<tr class="even">
<td><p>Als MCU-Join-Fehler</p></td>
<td><p>Die Anzahl der AS-MCU-Join-Fehler</p></td>
</tr>
<tr class="odd">
<td><p>AV-MCU-Join-Fehler</p></td>
<td><p>Die Anzahl der AV MCU Join-Fehler</p></td>
</tr>
<tr class="even">
<td><p>Durchschnittliche Anwendungsstartzeit (MS)</p></td>
<td><p>Die durchschnittliche Startzeit der Anwendung in Millisekunden</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Lebensdauer für Sitzung (MS)</p></td>
<td><p>Die durchschnittliche Dauer einer Sitzung in Millisekunden.</p></td>
</tr>
<tr class="even">
<td><p>Daten-MCU-Join-Fehler</p></td>
<td><p>Anzahl der Daten-MCU-Join-Fehler</p></td>
</tr>
<tr class="odd">
<td><p>Wartezeit für die Exchange-Kontakt Suche (MS)</p></td>
<td><p>Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Suchen von Kontakten in Exchange an.</p></td>
</tr>
<tr class="even">
<td><p>Wartezeit für Exchange HD Photo get (MS)</p></td>
<td><p>Dieser Indikator zeigt die durchschnittliche Zeit (in Millisekunden) zum Abrufen eines Fotos aus Exchange an.</p></td>
</tr>
<tr class="odd">
<td><p>HTTP-4xx-Antworten/Sekunde</p></td>
<td><p>Die pro Sekunde Rate von Antworten mit http-4xx-Code</p></td>
</tr>
<tr class="even">
<td><p>HTTP-5xx-Antworten/Sekunde</p></td>
<td><p>Die pro Sekunde Rate von Antworten mit http-5xx-Code</p></td>
</tr>
<tr class="odd">
<td><p>Fehler im MCU-Join</p></td>
<td><p>Anzahl der im MCU-Join-Fehler</p></td>
</tr>
<tr class="even">
<td><p>Anzahl Active Directory Fehler beim Abrufen von Fotos</p></td>
<td><p>Die Gesamtzahl der Fehler beim Abrufen von Fotos aus Active Directory</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der Fehler bei der Kontakt Suche</p></td>
<td><p>Die Gesamtzahl der Fehler beim Durchsuchen von Kontakten in Exchange</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der deserialisierungs Fehler</p></td>
<td><p>Die Gesamtzahl der deserialisierungs Fehler</p></td>
</tr>
<tr class="odd">
<td><p>Anzahl der Fehler bei HD Photo Get</p></td>
<td><p>Die Gesamtzahl der Fehler beim Abrufen von HD-Fotos aus Exchange</p></td>
</tr>
<tr class="even">
<td><p>Über die maximalen Abonnements pro Anwendung</p></td>
<td><p>Die Anzahl der Abonnementanforderungen über den maximal zulässigen pro Anwendung</p></td>
</tr>
<tr class="odd">
<td><p>Über die maximalen Abonnements pro Batch</p></td>
<td><p>Die Anzahl der Abonnementanforderungen über den maximal zulässigen pro Batch</p></td>
</tr>
<tr class="even">
<td><p>Fehler bei Anwesenheitsabonnements</p></td>
<td><p>Die Anzahl der Fehler beim Abonnieren der Anwesenheitsinformationen</p></td>
</tr>
<tr class="odd">
<td><p>Registrieren von Endpunkt Fehlern</p></td>
<td><p>Die Anzahl der Fehler beim Registrieren von Endpunkten</p></td>
</tr>
<tr class="even">
<td><p>Empfangene Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der empfangenen Anforderungen pro Sekunde.</p></td>
</tr>
<tr class="odd">
<td><p>Erfolgreiche Anforderungen/Sekunde</p></td>
<td><p>Die Anzahl der erfolgreichen Anforderungen pro Sekunde (http-2xx/3xx-Antwortcodes)</p></td>
</tr>
<tr class="even">
<td><p>Erfolgreiche Erstellung von Anwendungsanforderungen/Sekunde</p></td>
<td><p>Die Anzahl der erfolgreichen Anwendungs Erstellungsanforderungen pro Sekunde</p></td>
</tr>
<tr class="odd">
<td><p>Timeout für ausstehende Get-Anzahl</p></td>
<td><p>Die Anzahl der ausstehenden ruft dieses Timeout ab.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der empfangenen Anwendungs Erstellungsanforderungen</p></td>
<td><p>Die Gesamtzahl der seit dem Start des Diensts empfangenen Anwendungs Erstellungsanforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>Gesamtzahl der http-4xx-Antworten</p></td>
<td><p>Die Gesamtzahl der http-4xx-Antworten</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der http-5xx-Antworten</p></td>
<td><p>Die Gesamtzahl der http-5xx-Antworten</p></td>
</tr>
<tr class="odd">
<td><p>Insgesamt empfangene Anforderungen im Befehlskanal</p></td>
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
<td><p>Insgesamt gedrosselte Anwendungen</p></td>
<td><p>Die Anzahl der gedrosselten Anwendungen</p></td>
</tr>
</tbody>
</table>


</div>

<div id="sectionSection1" class="section">

### <a name="performance-counters-for-mcx-mobility-service"></a>Leistungsindikatoren für den MCX-Mobilitätsdienst

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
<td><p>Die aktuelle Anzahl von Pushbenachrichtigungsabonnements. Diese Nummer steht in Verbindung mit der Anzahl der derzeit aktiven Sitzungen für die Teilmenge der derzeit aktiven Sitzungen, die für Windows Mobile-oder iPhone-Geräte registriert sind.</p></td>
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

