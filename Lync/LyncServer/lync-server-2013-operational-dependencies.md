---
title: 'Lync Server 2013: Betriebs Abhängigkeiten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Operational dependencies
ms:assetid: 450b6be2-7fb3-47d7-8b0b-c05faa331e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720559(v=OCS.15)
ms:contentKeyID: 63969597
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26e7de821dee778d4b0b1e9aa105669635abaf6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755809"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="operational-dependencies-in-lync-server-2013"></a>Betriebs Abhängigkeiten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-05-15_

Die in diesem Dokument beschriebene Referenzarchitektur wird Ihnen dabei helfen sicherzustellen, dass Sie über eine lync Server 2013-Bereitstellung verfügen, die nicht nur auf die Anforderungen der Organisation skaliert, sondern nach den bewährten Microsoft-Methoden entworfen wurde. Es kann sein, dass die lync Server 2013-Implementierung ein dynamischer Dienst ist und wie jeder andere Dienst im Unternehmen weiterhin Überwachungs-und proaktives Management erfordert, um dem Unternehmen ein hohes Maß an Serviceverfügbarkeit und Servicequalität zu gewährleisten.

Da lync Server 2013 in der täglichen Geschäftstätigkeit des Unternehmens tief verwurzelt ist, ist es wichtig, dass der Dienst durch ein genaues und greifbares Service Level-Management verwaltet wird. Die lync-Systemarchitektur kann komplex und sehr integriert werden, und um ein effektives Service Level-Management zu gewährleisten und SLAs für lync Server 2013 festzulegen, wird es entscheidend, die Abhängigkeiten des Systems auf anderen Plattformen und Servern zu verstehen. Ebenso wichtig ist, zu beachten, welche Unternehmensdienste wie Sprach-und UC-integrierte Anwendungen von lync abhängig werden.

Lync Server 2013 muss eingerichtet werden, wobei alle genannten Abhängigkeiten berücksichtigt werden. Die Dienstzuordnung ermöglicht es Ihnen, eine SLA zwischen lync und dem abhängigen Dienst zu formulieren und einen Ausgangspunkt für die SLA-Aushandlung bereitzustellen.

In der folgenden Tabelle sind die typischen Abhängigkeitsdienste für eine lync-Infrastruktur aufgeführt. Jede dieser Technologien sollte eine eigene proaktive Überwachung aufweisen.

### <a name="typical-dependency-services"></a>Typische Abhängigkeitsdienste

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Abhängigkeitsdienst</th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Betriebssysteme</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Server Hardware</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Active Directory</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Infrastruktur öffentlicher Schlüssel</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Domain Naming Service</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Datenbankdienste</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Speicherdienste</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>System Verwaltung – Überwachung und Verteilung</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Security Services – Antivirus</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Netzwerkinfrastruktur – Internet</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Netzwerkinfrastruktur – intern (LAN/WAN)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Telefonie-Infrastruktur – IP-PBX und Gateways</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Cloud-Dienste</p></td>
<td></td>
</tr>
</tbody>
</table>


Es wird davon ausgegangen, dass die Organisation in der Lage ist, grundlegende Service Level-Verwaltungsfunktionen wie Change-, Incident-und Release-Management gemäß dem MOF-Verfahren zu entwickeln. Die lync-Lösung sollte von diesen Funktionen übernommen werden und den gleichen operativen Verwaltungsprozessen unterworfen werden.

Aufbauend auf den obigen Informationen haben wir jetzt ein größeres Verständnis darüber, was sich auf den lync-Dienst im Unternehmen auswirken kann. Um die Verfügbarkeit und Qualität von lync Server 2013 zu gewährleisten, müssen die folgenden Überwachungstools mit der Bereitstellung der Referenzarchitektur einhergehen:

### <a name="monitoring-tools"></a>Überwachungstools

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Komponente</th>
<th>Beschreibung</th>
<th>Anwendbare Website</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013-Überwachungs Server</p></td>
<td><p>Stellen Sie mindestens eine lync Server 2013 Monitoring Server-Rolle pro zentralen Standort bereit, und konfigurieren Sie das QoE-Berichterstattungs Paket (Quality of Experience).</p>
<p>Weitere Informationen finden Sie in der Dokumentation zur lync Server 2013-Bereitstellung:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Bereitstellen der Überwachung in lync Server 2013</a></p></td>
<td><p>Zentrale Websites</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Binden Sie die einzelnen Pools an die nächstgelegene Instanz der Monitoring Server-Rolle.</p></td>
<td><p>Zentrale Websites</p>
<p>Zweigstellen</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012 mit importiertem Microsoft lync Server 2013 Management Pack (MP).</p>
<p>Das Management Pack implementiert herkömmliches Ereignisprotokoll und Leistungsindikator basierte Instrumentation sowie die Aktivierung der neu verfügbaren Instrumentation in lync Server 2013.</p></td>
<td><p>Zentrale Websites</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Stellen Sie sicher, dass die zentrale Ermittlung zur Erkennung von Rollen und Komponenten, die überwacht werden müssen, automatisch auf Grundlage eines zentralen Ermittlungsskripts abgeschlossen wird, das das in der zentralen Verwaltungsdatenbank veröffentlichte Topologie-Dokument liest.</p></td>
<td><p>Zentraler Standort</p>
<p>Verzweigungs Website</p>
<p>Edge-Website</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Bereitstellen von System Center Operations Manager 2007-Agents für alle bereitgestellten Server mit lync Server</p></td>
<td><p>Zentraler Standort</p>
<p>Verzweigungs Website</p>
<p>Edge-Website</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Stellen Sie sicher, dass priorisierte Benachrichtigungen für Benachrichtigungen konfiguriert sind:</p>
<p>Benachrichtigungen mit höherer Priorität</p>
<p>Warnungen mittlerer Priorität</p>
<p>Andere Benachrichtigungen.</p></td>
<td><p>Zentraler Standort</p>
<p>Verzweigungs Website</p>
<p>Edge-Website</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Konfigurieren Sie die Port Überwachung für Ihre Bereitstellung.</p></td>
<td><p>Zentraler Standort</p>
<p>Verzweigungs Website</p>
<p>Edge-Website</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Konfigurieren der URL-Überwachung für Ihre Bereitstellung</p></td>
<td><p>Zentraler Standort</p></td>
</tr>
<tr class="odd">
<td><p>Integration von lync und System Center Operations Manager</p></td>
<td><p>Bereitstellen von Anruf Zuverlässigkeit und Medienqualität MonitoringCall Zuverlässigkeit und Überwachung der Medienqualität verwenden Sie den Monitoring Server-Computer als Watcher-Knoten, um die Anruf Zuverlässigkeit und Medienqualität von lync Server zu überwachen. Beide Features Abfragen die Monitoring Server-Datenbanken, um die Analyse durchführen zu können.</p></td>
<td><p>Zentraler Standort</p>
<p>Verzweigungs Website</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Stellen Sie sicher, dass die Warnungsschwellenwerte für Medienqualität genau konfiguriert sind. In der folgenden Tabelle ist die maximale Anzahl von Netzwerk Mittelwerten nach Codec angegeben. In der Produktion sollten diese Bewertungen für einen festgelegten Zeitraum überwacht werden, und es müssen akzeptable Schwellenwerte basierend auf den organisationsspezifischen NMOS-Ergebnissen festgelegt werden.</p></td>
<td><p>Zentraler Standort</p>
<p>Verzweigungs Website</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013, synthetischer Transaktionsmonitor</p></td>
<td><p>Bereitstellen eines dedizierten lync-Servers als synthetischer Transaktionsmonitor</p>
<p>Synthetische Transaktionen sind lync Server 2013 Windows PowerShell-Cmdlets, die vom Management Pack automatisch in einem vordefinierten Intervall ausgelöst werden. Diese werden auf einem synthetischen Transaktions Überwachungsknoten ausgeführt, bei dem es sich um einen vom Administrator benannten Server handelt, der für die Ermittlung und Ausführung von STS für jeden Pool verantwortlich ist.</p>
<p>Es wird nicht empfohlen, einen vorhandenen Microsoft lync Server 2013-Server als synthetischer Transaktions Überwachungsknoten zu verwenden. Dies liegt an den Anforderungen an die CPU/Arbeitsspeichernutzung für die Ausführung von STS. Verwenden Sie einen neuen Server Computer (oder einen virtuellen Server) für den synthetischen Transaktions Überwachungsknoten.</p></td>
<td><p>Zentraler Standort</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Bereitstellen des Überwachungs Knotens für synthetische Transaktionen</p>
<p>Verweisen Sie auf das MonitoringCS_withSCOM. docx-Dokument in der UCTAP Connect-Dokumentation.</p></td>
<td><p>Zentraler Standort</p></td>
</tr>
</tbody>
</table>


### <a name="maximum-network-mos-scores-per-codec"></a>Maximale Anzahl von Netzwerk-Mos-Bewertungen Pro Codec

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Szenario</th>
<th>Codec</th>
<th>Max NMOS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC-UC-Anruf</p></td>
<td><p>RTAudio WB</p></td>
<td><p>4,10</p></td>
</tr>
<tr class="even">
<td><p>UC-UC-Anruf</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Telefonkonferenz</p></td>
<td><p>Siren</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>UC – PSTN-Anruf</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>UC – PSTN-Anruf</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Über die vorherigen proaktiven Überwachungsaktivitäten hinaus sollten Wartungsaufgaben für zentral-, Edge-und Verzweigungs Standorte regelmäßig täglich, wöchentlich und monatlich ausgeführt werden, wie im lync RA-Betriebshandbuch definiert.

</div>

<span> </span>

</div>

</div>

</div>

