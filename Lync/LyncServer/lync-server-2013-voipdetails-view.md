---
title: 'Lync Server 2013: VoIPDetails-Ansicht'
description: 'Lync Server 2013: VoIPDetails-Ansicht.'
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
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566201"
---
# <a name="voipdetails-view-in-lync-server-2013"></a><span data-ttu-id="6f042-103">VoIPDetails-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f042-103">VoIPDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f042-104">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="6f042-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="6f042-105">Die VoIPDetails-Ansicht speichert Informationen zu Peer-zu-Peer-Sitzungen, an denen mindestens ein VoIP-Benutzer teilnimmt.</span><span class="sxs-lookup"><span data-stu-id="6f042-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="6f042-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6f042-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f042-107">Die VoIPDetails-Ansicht enthält alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</A> zusätzlich zu den unten aufgeführten Spalten.</span><span class="sxs-lookup"><span data-stu-id="6f042-107">The VoIPDetails view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f042-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="6f042-108">Column</span></span></th>
<th><span data-ttu-id="6f042-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="6f042-109">Data Type</span></span></th>
<th><span data-ttu-id="6f042-110">Details</span><span class="sxs-lookup"><span data-stu-id="6f042-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f042-111"><strong>Vom Telefon</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-111"><strong>FromPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6f042-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6f042-113">Telefon-URI des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6f042-113">Phone URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f042-114"><strong>Tophone</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-114"><strong>ToPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6f042-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6f042-116">Telefon-URI des Benutzers, der der Sitzung beigetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6f042-116">Phone URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f042-117"><strong>DisconnectedByUri</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-117"><strong>DisconnectedByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6f042-118">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6f042-119">URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</span><span class="sxs-lookup"><span data-stu-id="6f042-119">URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f042-120"><strong>DisconnectedByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-120"><strong>DisconnectedByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6f042-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6f042-122">URI-Typ des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</span><span class="sxs-lookup"><span data-stu-id="6f042-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="6f042-123">Weitere Informationen finden Sie <a href="lync-server-2013-uritypes-table.md">in der UriTypes-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="6f042-123">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f042-124"><strong>DisconnectedByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-124"><strong>DisconnectedByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6f042-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6f042-126">Mandant des Benutzers, der die Sitzung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="6f042-126">Tenant of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f042-127"><strong>DisconnectedByPhone</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-127"><strong>DisconnectedByPhone</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="6f042-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="6f042-129">Telefon-URI des Benutzers, der die Verbindung zur Sitzung unterbrochen hat.</span><span class="sxs-lookup"><span data-stu-id="6f042-129">Phone URI of the user who disconnected the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f042-130"><strong>FromMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-130"><strong>FromMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6f042-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6f042-132">Vom Benutzer, der die Sitzung gestartet hat, verwendeter Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="6f042-132">Mediation Server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f042-133"><strong>ToMediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-133"><strong>ToMediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6f042-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6f042-135">Vom Benutzer, der der Sitzung beigetreten ist, verwendeter Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="6f042-135">Mediation Server used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f042-136"><strong>FromGateway</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-136"><strong>FromGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6f042-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6f042-138">Vom Benutzer, der die Sitzung gestartet hat, verwendetes Gateway.</span><span class="sxs-lookup"><span data-stu-id="6f042-138">Gateway used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f042-139"><strong>Togateway</strong></span><span class="sxs-lookup"><span data-stu-id="6f042-139"><strong>ToGateway</strong></span></span></p></td>
<td><p><span data-ttu-id="6f042-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="6f042-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="6f042-141">Vom Benutzer, der der Sitzung beigetreten ist, verwendetes Gateway.</span><span class="sxs-lookup"><span data-stu-id="6f042-141">Gateway used by the user who joined the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

