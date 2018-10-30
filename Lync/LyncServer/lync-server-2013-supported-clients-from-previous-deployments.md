---
title: 'Lync Server 2013: Unterstützte Clients aus vorherigen Bereitstellungen'
TOCTitle: Unterstützte Clients aus vorherigen Bereitstellungen
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398499(v=OCS.15)
ms:contentKeyID: 49294288
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Clients aus vorherigen Bereitstellungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In einem Koexistenzszenario können Lync Server 2013-Clients mit Clients älterer Versionen von Lync Server und Office Communications Server interagieren. Anders als bei bisherigen Versionen unterstützt Lync Server 2010 die neuen Lync 2013-Clients. Dies ermöglicht es Organisationen, die ein Upgrade von Lync Server 2010 durchführen, neue Clients unabhängig von Lync Server-Upgrades einzuführen.

## Unterstützte Kombinationen von Server und Client

In der folgenden Tabelle ist aufgeführt, welche Kombinationen von Client- und Serverversionen unterstützt werden. Lync Server 2013 unterstützt zwei ältere Clientversionen, und Lync Server 2010 unterstützt den neuen Lync 2013-Client.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010-Vermittlung</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010-Gruppenchat</p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>Unterstützt1</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010-Teilnehmer</p></td>
<td><p>Nicht unterstützt2</p></td>
<td><p>Unterstützt</p></td>
<td><p>Nicht unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperabel3</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2-Vermittlung</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Nicht unterstützt</p></td>
<td><p>Unterstützt</p></td>
<td><p>Unterstützt</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010 war die Gruppenchatfunktionalität über den Gruppenchatserver verfügbar, eine eine vertrauenswürdige Anwendung eines Drittanbieters für Lync Server 2010. Lync 2013-Clients sind nicht mit Lync Server 2010-Gruppenchat kompatibel.

2Lync Web App 2013 bietet jetzt eine umfassende Besprechungsfunktionalität mit Computeraudio- und Videofunktionen, die als Ersatz für Lync 2010-Teilnehmer gilt.

3Die Anwesenheits- und Chatfeatures in Office Communicator 2007 R2 sind mit Lync Server 2013 kompatibel, nicht jedoch die Konferenzfeatures. Während der Migration von Office Communications Server 2007 R2 eignet sich Office Communicator 2007 R2 für Anwesenheits- und Chatinteroperabilität, Benutzer sollten jedoch Lync Web App 2013 verwenden, um an Lync Server 2013-Besprechungen teilzunehmen.


> [!NOTE]
> Nähere Informationen darüber, wie Lync Server 2013-Clients mit Clients aus älteren Versionen von Lync Server und Office Communications Server koexistieren und interagieren können, finden Sie unter <A href="lync-server-2013-client-interoperability-in-lync-2013.md">Clientinteroperabilität in Lync 2013</A> in der Planungsdokumentation.


