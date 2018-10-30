---
title: 'Lync Server 2013: Grundlegendes zu den Firewallanforderungen für SQL Server'
TOCTitle: Grundlegendes zu den Firewallanforderungen für SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425818(v=OCS.15)
ms:contentKeyID: 49293600
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Grundlegendes zu den Firewallanforderungen für SQL Server mit Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für eine Standard Edition-Bereitstellung werden beim Lync Server 2013-Setup automatisch Firewallausnahmen erstellt. Für Enterprise Edition-Bereitstellungen müssen Sie die Firewallausnahmen jedoch manuell auf dem Microsoft SQL Server-Back-End-Server konfigurieren. Beim TCP/IP-Protokoll kann ein Port nur für eine bestimmte IP-Adresse verwendet werden. Dies bedeutet, dass Sie der Standarddatenbankinstanz für den SQL Server-basierten Server den standardmäßigen TCP-Port 1433 zuweisen können. Für alle weiteren Instanzen müssen Sie mit dem SQL Server-Konfigurations-Manager eindeutige, nicht verwendete Ports zuweisen. In diesem Abschnitt werden folgende Themen behandelt:

  - Anforderungen für eine Firewallausnahme bei Verwendung der Standardinstanz

  - Anforderungen für eine Firewallausnahme für den SQL Server-Browserdienst

  - Anforderungen für statische Überwachungsports bei Verwendung benannter Instanzen

## Anforderungen für eine Firewallausnahme bei Verwendung der Standardinstanz

Wenn Sie bei der Lync Server 2013-Bereitstellung die SQL Server-Standardinstanz für eine beliebige Datenbank verwenden, gelten die folgenden Anforderungen für Firewallregeln, um die Kommunikation zwischen dem Front-End-Pool und der SQL Server-Standardinstanz sicherzustellen.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll</th>
<th>Port</th>
<th>Richtung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Eingehend zu SQL Server</p></td>
</tr>
</tbody>
</table>


## Anforderungen für eine Firewallausnahme für den SQL Server-Browserdienst

Der SQL Server-Browserdienst ermittelt die Datenbankinstanzen und kommuniziert den Port, für dessen Verwendung die Instanz (benannte Instanz oder Standardinstanz) konfiguriert ist.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll</th>
<th>Port</th>
<th>Richtung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


## Anforderungen für statische Überwachungsports bei Verwendung benannter Instanzen

Bei Verwendung benannter Instanzen in der SQL Server-Konfiguration für Datenbanken mit Unterstützung für Lync Server 2013 konfigurieren Sie statische Ports mit dem SQL Server-Konfigurations-Manager. Nachdem die statischen Ports für jede benannte Instanz zugewiesen wurden, erstellen Sie Ausnahmen für jeden statischen Port in der Firewall.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll</th>
<th>Port</th>
<th>Richtung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Als statisch definiert</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


## SQL Server-Dokumentation

Die Microsoft SQL Server 2012-Dokumentation enthält ausführliche Anweisungen zum Konfigurieren des Firewallzugriffs für Datenbanken. Detaillierte Informationen zu Microsoft SQL Server 2012 finden Sie im Thema "Konfigurieren der Windows-Firewall für den SQL Server-Zugriff" unter [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).

