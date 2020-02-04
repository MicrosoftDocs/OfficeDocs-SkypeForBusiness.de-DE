---
title: 'Lync Server 2013: Liste der Kompatibilitätstabellen für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server compliance tables
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215878(v=OCS.15)
ms:contentKeyID: 48706007
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c4f6e9622e839e2f1fd719b8e2d7ba95286247e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Das Compliance-Datenbankschema für beständige Chats besteht aus den folgenden Tabellen.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste der Kompatibilitätstabellen für beständigen Chat Server


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></p></td>
<td><p>Enthält die Konformitätsereignisse, die vom konfigurierten Adapter noch nicht verarbeitet wurden.</p>
<p>Diese Tabelle enthält dauerhafte Chat bezogene Ereignisse wie Chatnachrichten und Dateidownloads. (Teilnehmer-Ereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)</p>
<p>(Die Server, die die Ereignisse in dieser Tabelle verarbeitet haben, werden in der tblComplianceFanout-Tabelle aufgelistet.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></p></td>
<td><p>Enthält die Server, die ein Compliance-Ereignis verarbeitet haben. Diese Tabelle ist eng mit der tblComplianceData-Tabelle gekoppelt.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></p></td>
<td><p>Enthält aktuelle Teilnehmer pro Chatdienst und pro Server. Sie wird auf der Grundlage von Join-und Part-Konformitäts Ereignissen verwaltet, die vom beständigen Chat Dienst empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></p></td>
<td><p>Enthält Informationen zum Kompatibilitätszustand des Pools.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

