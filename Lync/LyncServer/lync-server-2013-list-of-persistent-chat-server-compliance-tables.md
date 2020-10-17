---
title: 'Lync Server 2013: Liste der Kompatibilitätstabellen für den Server für beständigen Chat'
description: 'Lync Server 2013: Liste der Kompatibilitätstabellen für den Server für beständigen Chat.'
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
ms.openlocfilehash: 47cb28a0ca4180327c2adc48d80e9e41171a7bfc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550071"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-lync-server-2013"></a><span data-ttu-id="0453f-103">Liste der Kompatibilitätstabellen für den Server für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0453f-103">List of Persistent Chat Server compliance tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0453f-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0453f-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0453f-105">Das Compliance-Datenbankschema für beständigen Chat besteht aus den folgenden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="0453f-105">The Persistent Chat compliance database schema consists of the following tables.</span></span>

<div>

## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="0453f-106">Liste der Kompatibilitätstabellen für Persistent Chat Server</span><span class="sxs-lookup"><span data-stu-id="0453f-106">List of Persistent Chat Server Compliance Tables</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0453f-107">Tabelle</span><span class="sxs-lookup"><span data-stu-id="0453f-107">Table</span></span></th>
<th><span data-ttu-id="0453f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0453f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0453f-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0453f-109"><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0453f-110">Enthält die Genehmigungsereignisse, die noch nicht vom konfigurierten Adapter verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="0453f-110">Contains the compliance events that have not yet been processed by the configured adapter.</span></span></p>
<p><span data-ttu-id="0453f-111">Diese Tabelle enthält Ereignisse für beständigen Chat, wie Chatnachrichten und Dateidownloads.</span><span class="sxs-lookup"><span data-stu-id="0453f-111">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="0453f-112">(Teilnehmerereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)</span><span class="sxs-lookup"><span data-stu-id="0453f-112">(Participant events are tracked by the tblComplianceParticipant table.)</span></span></p>
<p><span data-ttu-id="0453f-113">(Die Server, von denen die Ereignisse in dieser Tabelle verarbeitet wurden, werden in der tblComplianceFanout-Tabelle aufgelistet.)</span><span class="sxs-lookup"><span data-stu-id="0453f-113">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0453f-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0453f-114"><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0453f-115">Enthält die Server, von denen ein Genehmigungsereignis verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="0453f-115">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="0453f-116">Diese Tabelle steht in engem Zusammenhang mit der tblComplianceData-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0453f-116">This table is tightly coupled with the tblComplianceData table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0453f-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0453f-117"><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0453f-118">Enthält aktuelle Teilnehmer pro Chat-Dienst und pro Server.</span><span class="sxs-lookup"><span data-stu-id="0453f-118">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="0453f-119">Sie wird basierend auf Join-und Part-Compliance-Ereignissen verwaltet, die vom beständigen Chat Dienst empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="0453f-119">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0453f-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0453f-120"><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0453f-121">Enthält poolweite Informationen zum Kompatibilitätszustand.</span><span class="sxs-lookup"><span data-stu-id="0453f-121">Contains pool-wide compliance state information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

