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

# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="19d9a-102">Liste der Kompatibilitätstabellen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19d9a-102">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19d9a-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="19d9a-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="19d9a-104">Das Compliance-Datenbankschema für beständigen Chat besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="19d9a-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="19d9a-105">Liste der Kompatibilitätstabellen für Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="19d9a-105">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19d9a-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="19d9a-106">Table</span></span></th>
<th><span data-ttu-id="19d9a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19d9a-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19d9a-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="19d9a-108"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="19d9a-109">Enthält die Genehmigungsereignisse, die noch nicht vom konfigurierten Adapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="19d9a-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="19d9a-110">Diese Tabelle enthält Ereignisse für beständigen Chat, wie Chatnachrichten und Dateidownloads.</span><span class="sxs-lookup"><span data-stu-id="19d9a-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="19d9a-111">(Teilnehmerereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)</span><span class="sxs-lookup"><span data-stu-id="19d9a-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="19d9a-112">(Die Server, von denen die Ereignisse in dieser Tabelle verarbeitet wurden, werden in der tblComplianceFanout-Tabelle aufgelistet.)</span><span class="sxs-lookup"><span data-stu-id="19d9a-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19d9a-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="19d9a-113"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="19d9a-114">Enthält die Server, von denen ein Genehmigungsereignis verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="19d9a-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="19d9a-115">Diese Tabelle steht in engem Zusammenhang mit der tblComplianceData-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="19d9a-115">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19d9a-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="19d9a-116"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="19d9a-117">Enthält aktuelle Teilnehmer pro Chat-Dienst und pro Server.</span><span class="sxs-lookup"><span data-stu-id="19d9a-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="19d9a-118">Sie wird basierend auf Join-und Part-Compliance-Ereignissen verwaltet, die vom beständigen Chat Dienst empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="19d9a-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19d9a-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="19d9a-119"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="19d9a-120">Enthält poolweite Informationen zum Kompatibilitätszustand.</span><span class="sxs-lookup"><span data-stu-id="19d9a-120">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

