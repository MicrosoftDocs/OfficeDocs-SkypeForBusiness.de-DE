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
ms.openlocfilehash: 1e506fbbe204b7248396c25c3728556c61681cbf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526572"
---
# <a name="operational-dependencies-in-lync-server-2013"></a>Betriebs Abhängigkeiten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-05-15_

Die in diesem Dokument beschriebene Referenzarchitektur hilft sicherzustellen, dass Sie über eine lync Server 2013-Bereitstellung verfügen, die nicht nur auf die Anforderungen der Organisation skaliert, sondern gemäß den bewährten Methoden von Microsoft entworfen wurde. Es kann sein, dass die lync Server 2013 Implementierung ein dynamischer Dienst ist und wie jeder andere Dienst im Unternehmen weiterhin eine Überwachung und proaktive Verwaltung benötigt, um dem Unternehmen hohe Serviceverfügbarkeit und Servicequalität zu gewährleisten.

Da lync Server 2013 im täglichen Geschäft der Organisation tief verwurzelt ist, ist es wichtig, dass der Dienst durch eine präzise und greifbare Service Level-Verwaltung verwaltet wird. Die lync-Systemarchitektur kann komplex und sehr integriert werden, um ein effektives Service Level-Management beizubehalten und SLAs für lync Server 2013 einzurichten, um die Abhängigkeiten des Systems von anderen Plattformen und Servern zu verstehen. Ebenso wichtig ist es, festzustellen, welche Unternehmensdienste wie VoIP-und UC-integrierte Anwendungen von lync abhängig werden.

Lync Server 2013 muss festgestellt werden, wobei alle genannten Abhängigkeiten berücksichtigt werden. Mit der Service Map können Sie eine SLA zwischen lync und dem dazugehörigen Dienst formulieren und einen Ausgangspunkt für die SLA-Aushandlung bieten.

In der folgenden Tabelle sind die typischen Abhängigkeitsdienste für eine lync-Infrastruktur aufgeführt. Jede dieser Technologien sollte über eine eigene proaktive Überwachung verfügen.

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
<td><p>Öffentliche Schlüsselinfrastruktur</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Domänen Benennungsdienst</p></td>
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
<td><p>Sicherheitsdienste – Antivirus</p></td>
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


Es wird davon ausgegangen, dass die Organisation operativ ausgereift ist, indem Sie grundlegende Service Level-Verwaltungsfunktionen wie Change, Incident and Release Management gemäß der vorgeschriebenen MOF-Funktion ausüben. Die lync-Lösung sollte von diesen Funktionen übernommen werden und den gleichen betrieblichen Verwaltungsprozessen unterworfen werden.

Aufbauend auf den oben gewonnenen Informationen haben wir nun ein besseres Verständnis dafür, was sich auf den lync-Dienst im Unternehmen auswirken kann. Um die Verfügbarkeit und Qualität von lync Server 2013 Diensten sicherzustellen, müssen die folgenden Überwachungstools mit der Bereitstellung der Referenzarchitektur einhergehen:

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
<th>Zutreffende Website</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 Monitoring Server</p></td>
<td><p>Stellen Sie mindestens eine lync Server 2013 Monitoring Server-Rolle pro zentraler Standort bereit, und konfigurieren Sie das QoE-Berichtspaket (Quality of Experience).</p>
<p>Weitere Informationen finden Sie in der Dokumentation zur lync Server 2013-Bereitstellung:</p>
<p><a href="lync-server-2013-deploying-monitoring.md">Bereitstellen der Überwachung in lync Server 2013</a></p></td>
<td><p>Zentrale Standorte</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Binden Sie jeden Pool an die nächstgelegene Instanz der Monitoring Server Rolle.</p></td>
<td><p>Zentrale Standorte</p>
<p>Zweigstellenstandorte</p></td>
</tr>
<tr class="odd">
<td><p>System Center Operations Manager 2012</p></td>
<td><p>System Center Operations Manager 2012, in dem das Microsoft lync Server 2013 Management Pack (MP) importiert wurde.</p>
<p>Das Management Pack implementiert herkömmliches Ereignisprotokoll und Leistungsindikator basierte Instrumentation wird verwendet und ermöglicht die neu verfügbare Instrumentation in lync Server 2013.</p></td>
<td><p>Zentrale Standorte</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Stellen Sie sicher, dass die zentrale Ermittlung der zu überwachenden Rollen und Komponenten automatisch basierend auf einem zentralen Ermittlungsskript ausgeführt wird, das das in der zentralen Verwaltungsdatenbank veröffentlichte Topologie-Dokument liest.</p></td>
<td><p>Zentraler Standort</p>
<p>Zweigstellenstandort</p>
<p>Edge-Website</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Bereitstellen von System Center Operations Manager 2007-Agents auf allen bereitgestellten Servern mit lync Server.</p></td>
<td><p>Zentraler Standort</p>
<p>Zweigstellenstandort</p>
<p>Edge-Website</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Stellen Sie sicher, dass priorisierte Warnungen für die Benachrichtigung konfiguriert sind:</p>
<p>Warnungen mit hoher Priorität</p>
<p>Warnungen mittlerer Priorität</p>
<p>Andere Warnungen.</p></td>
<td><p>Zentraler Standort</p>
<p>Zweigstellenstandort</p>
<p>Edge-Website</p></td>
</tr>
<tr class="odd">
<td></td>
<td><p>Konfigurieren Sie die Port Überwachung für Ihre Bereitstellung.</p></td>
<td><p>Zentraler Standort</p>
<p>Zweigstellenstandort</p>
<p>Edge-Website</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Konfigurieren der URL-Überwachung für Ihre Bereitstellung</p></td>
<td><p>Zentraler Standort</p></td>
</tr>
<tr class="odd">
<td><p>Integration von lync und System Center Operations Manager</p></td>
<td><p>Bereitstellen der Anruf Zuverlässigkeit und Medienqualität MonitoringCall Zuverlässigkeit und Medien Qualitätsüberwachung verwenden Sie den Monitoring Server Computer als Monitor Knoten, um die Anruf Zuverlässigkeit und Medienqualität von lync Server zu überwachen. Beide Funktionen Abfrage der Monitoring Server Datenbanken zu tun Analyse.</p></td>
<td><p>Zentraler Standort</p>
<p>Zweigstellenstandort</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Stellen Sie sicher, dass die Warnschwellen für Medienqualität genau konfiguriert sind. In der folgenden Tabelle werden die maximalen Netzwerk mittleren Meinungs Bewertungen nach Codec angegeben. In der Produktion sollten diese Ergebnisse für einen festgelegten Zeitraum überwacht werden, und es müssen akzeptable Schwellenwerte basierend auf den jeweiligen NMOS-Ergebnissen der Organisation festgelegt werden.</p></td>
<td><p>Zentraler Standort</p>
<p>Zweigstellenstandort</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013er synthetischer Transaktionsmonitor</p></td>
<td><p>Stellen Sie eine dedizierte lync Server als synthetischen Transaktionsmonitor bereit.</p>
<p>Synthetische Transaktionen sind lync Server 2013 Windows PowerShell-Cmdlets, die vom Management Pack automatisch in einem vordefinierten Intervall ausgelöst werden. Diese werden auf einem Knoten mit synthetischen Transaktions Monitoren ausgeführt, der ein vom Administrator festgelegter Server ist, der für die Ermittlung und Ausführung von STS für jeden Pool zuständig ist.</p>
<p>Es wird nicht empfohlen, einen vorhandenen Microsoft lync Server 2013 Server als synthetischen Transaktionsmonitor Knoten zu verwenden. Dies ist auf die hohen Anforderungen an die CPU/Arbeitsspeichernutzung für die Ausführung von STS zurückzuführen. Verwenden Sie für den Knoten synthetischer Transaktionsmonitor einen neuen Server Computer (oder einen virtuellen Server).</p></td>
<td><p>Zentraler Standort</p></td>
</tr>
<tr class="even">
<td></td>
<td><p>Bereitstellen des Monitor Knotens für synthetische Transaktionen</p>
<p>Lesen Sie das MonitoringCS_withSCOM.docx Dokument in der UCTAP Connect-Dokumentation.</p></td>
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
<td><p>4.10</p></td>
</tr>
<tr class="even">
<td><p>UC-UC-Anruf</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>Konferenzanruf</p></td>
<td><p>Sirene</p></td>
<td><p>3,72</p></td>
</tr>
<tr class="even">
<td><p>UC-PSTN-Anruf</p></td>
<td><p>RTAudio NB</p></td>
<td><p>2,95</p></td>
</tr>
<tr class="odd">
<td><p>UC-PSTN-Anruf</p></td>
<td><p>G-711</p></td>
<td><p>3,61</p></td>
</tr>
</tbody>
</table>


Neben den vorherigen proaktiven Überwachungsaktivitäten sollten Wartungsaufgaben für zentrale, Edge-und Zweigstellenstandorte auf einer wiederkehrenden täglichen, wöchentlichen und monatlichen Basis gemäß der Definition im lync RA-Betriebshandbuch ausgeführt werden.

</div>

<span> </span>

</div>

</div>

</div>

