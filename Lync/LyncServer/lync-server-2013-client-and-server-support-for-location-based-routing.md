---
title: 'Lync Server 2013: Client- und Serverunterstützung für standortbasiertes Routing'
TOCTitle: Client- und Serverunterstützung für standortbasiertes Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994024(v=OCS.15)
ms:contentKeyID: 52056307
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Client- und Serverunterstützung für standortbasiertes Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Standortbasiertes Routing wird von Lync Server erzwungen. Lync Server kann die Netzwerkstandorte erkennen, von denen Benutzer Verbindungen aus dem Unternehmensnetzwerk herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, werden deren Positionen als unbekannt angesehen.

## Unterstützung für Lync Server

Standortbasiertes Routing erfordert, dass Lync Server 2013 CU1 auf allen Front-End-Pools und Standard Edition-Servern bereitgestellt ist, die zu einer bestimmten Topologie gehören. Ist Lync Server 2013 CU1 auf einigen Lync-Komponenten in der Topologie nicht installiert, können Beschränkungen des standortbasierten Routings nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination aus Serverrolle und -version angegeben, die für standortbasiertes Routing unterstützt wird.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Poolversion</th>
<th>Vermittlungsserverversion</th>
<th>Unterstützt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 Cumulative Update, Februar 2013</p></td>
<td><p>Lync Server 2013 Cumulative Update, Februar 2013</p></td>
<td><p>ja</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 Cumulative Update, Februar 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Cumulative Update, Februar 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 Cumulative Update, Februar 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>Beliebig</p></td>
<td><p>nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>Beliebig</p></td>
<td><p>nein</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Beliebig</p></td>
<td><p>nein</p></td>
</tr>
</tbody>
</table>


## Unterstützung des Lync-Clients

In der folgenden Tabelle sind die Clients gekennzeichnet, die standortbasiertes Routing unterstützen.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Clienttyp</th>
<th>Unterstützt</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>ja</p></td>
<td><p>Einschließlich Lync 2013 Cumulative Update, Februar 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>nein</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Vermittlung</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync für Windows 8</p></td>
<td><p>nein</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>nein</p></td>
<td><p>VoIP muss für Lync Mobile 2013-Clients deaktiviert sein, wenn sie von Benutzern verwendet werden, für die standortbasiertes Routing aktiviert ist.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
</tbody>
</table>

  


> [!NOTE]
> Wenn Sie VoIP für Lync Mobile 2013-Clients deaktivieren möchten, weisen Sie eine Mobilitätsrichtlinie zu, in der für alle Benutzer, für die standortbasiertes Routing aktiviert ist, die Einstellung "IP-Audio/Video aktivieren" deaktiviert wird. Ausführlichere Informationen zu Mobilitätsrichtlinien finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



## Siehe auch

#### Weitere Ressourcen

[Planung des standortbasierten Routings in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

