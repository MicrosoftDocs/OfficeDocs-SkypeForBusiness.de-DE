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

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="b24ba-102">Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b24ba-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b24ba-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b24ba-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b24ba-104">Das Compliance-Datenbankschema für beständige Chats besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b24ba-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="b24ba-105">Liste der Kompatibilitätstabellen für beständigen Chat Server</span><span class="sxs-lookup"><span data-stu-id="b24ba-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b24ba-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="b24ba-106">Table</span></span></th>
<th><span data-ttu-id="b24ba-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b24ba-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b24ba-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b24ba-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b24ba-109">Enthält die Konformitätsereignisse, die vom konfigurierten Adapter noch nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="b24ba-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="b24ba-110">Diese Tabelle enthält dauerhafte Chat bezogene Ereignisse wie Chatnachrichten und Dateidownloads.</span><span class="sxs-lookup"><span data-stu-id="b24ba-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="b24ba-111">(Teilnehmer-Ereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)</span><span class="sxs-lookup"><span data-stu-id="b24ba-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="b24ba-112">(Die Server, die die Ereignisse in dieser Tabelle verarbeitet haben, werden in der tblComplianceFanout-Tabelle aufgelistet.)</span><span class="sxs-lookup"><span data-stu-id="b24ba-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b24ba-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b24ba-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b24ba-114">Enthält die Server, die ein Compliance-Ereignis verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="b24ba-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="b24ba-115">Diese Tabelle ist eng mit der tblComplianceData-Tabelle gekoppelt.</span><span class="sxs-lookup"><span data-stu-id="b24ba-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b24ba-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b24ba-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b24ba-117">Enthält aktuelle Teilnehmer pro Chatdienst und pro Server.</span><span class="sxs-lookup"><span data-stu-id="b24ba-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="b24ba-118">Sie wird auf der Grundlage von Join-und Part-Konformitäts Ereignissen verwaltet, die vom beständigen Chat Dienst empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="b24ba-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b24ba-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="b24ba-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="b24ba-120">Enthält Informationen zum Kompatibilitätszustand des Pools.</span><span class="sxs-lookup"><span data-stu-id="b24ba-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

