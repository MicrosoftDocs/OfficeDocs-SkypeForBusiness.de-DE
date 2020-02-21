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
ms.openlocfilehash: 322b700b807f8654e96572a3c040ddd7fe0d1e5f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a>Liste der Kompatibilitätstabellen für den Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Das Compliance-Datenbankschema für beständigen Chat besteht aus den folgenden Tabellen.

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a>Liste der Kompatibilitätstabellen für Persistent Chat Server


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
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in lync Server 2013</a></p></td>
<td><p>Enthält die Genehmigungsereignisse, die noch nicht vom konfigurierten Adapter verarbeitet wurden.</p>
<p>Diese Tabelle enthält Ereignisse für beständigen Chat, wie Chatnachrichten und Dateidownloads. (Teilnehmerereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)</p>
<p>(Die Server, von denen die Ereignisse in dieser Tabelle verarbeitet wurden, werden in der tblComplianceFanout-Tabelle aufgelistet.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in lync Server 2013</a></p></td>
<td><p>Enthält die Server, von denen ein Genehmigungsereignis verarbeitet wurde. Diese Tabelle steht in engem Zusammenhang mit der tblComplianceData-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in lync Server 2013</a></p></td>
<td><p>Enthält aktuelle Teilnehmer pro Chat-Dienst und pro Server. Sie wird basierend auf Join-und Part-Compliance-Ereignissen verwaltet, die vom beständigen Chat Dienst empfangen werden.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in lync Server 2013</a></p></td>
<td><p>Enthält poolweite Informationen zum Kompatibilitätszustand.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

