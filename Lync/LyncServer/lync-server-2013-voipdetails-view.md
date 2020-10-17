---
title: 'Lync Server 2013: VoIPDetails-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dc01632579c6455c47113f34e181f6598b7c781
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535382"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="82a88-102">VoIPDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82a88-102">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82a88-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="82a88-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="82a88-104">Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="82a88-104">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="82a88-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="82a88-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82a88-106">Die VoIPDetails-Ansicht enthält alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</A> zusätzlich zu den unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="82a88-106">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="82a88-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="82a88-107">Column</span></span></th>
<th><span data-ttu-id="82a88-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="82a88-108">Data Type</span></span></th>
<th><span data-ttu-id="82a88-109">Details</span><span class="sxs-lookup"><span data-stu-id="82a88-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="82a88-110"><strong>Vom Telefon</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-110"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="82a88-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="82a88-112">Telefon-URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="82a88-112">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82a88-113"><strong>Tophone</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-113"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-114">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="82a88-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="82a88-115">Telefon-URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="82a88-115">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82a88-116"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-116"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-117">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="82a88-117">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="82a88-118">URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</span><span class="sxs-lookup"><span data-stu-id="82a88-118">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82a88-119"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-119"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-120">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82a88-120">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82a88-121">URI-Typ des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</span><span class="sxs-lookup"><span data-stu-id="82a88-121">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="82a88-122">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="82a88-122">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82a88-123"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-123"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82a88-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82a88-125">Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="82a88-125">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82a88-126"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-126"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="82a88-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="82a88-128">Telefon-URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</span><span class="sxs-lookup"><span data-stu-id="82a88-128">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82a88-129"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-129"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82a88-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82a88-131">Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="82a88-131">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82a88-132"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-132"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82a88-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82a88-134">Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="82a88-134">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="82a88-135"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-135"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82a88-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82a88-137">Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.</span><span class="sxs-lookup"><span data-stu-id="82a88-137">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="82a88-138"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="82a88-138"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="82a88-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="82a88-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="82a88-140">Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.</span><span class="sxs-lookup"><span data-stu-id="82a88-140">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

