---
title: 'Lync Server 2013: Medienansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a760e3113cf12eceaa9f60c829b4d6a4a714ea25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="8d9ea-102">Medienansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8d9ea-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d9ea-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="8d9ea-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="8d9ea-104">In der Medienansicht werden Informationen zu einem in einer Peer-zu-Peer-Sitzung verwendeten Medientyp gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="8d9ea-105">Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="8d9ea-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d9ea-p102">Die Medienansicht sollte nicht zur Berechnung der Mediendauer für eine Sitzung verwendet werden. Diese Ansicht enthält die Signaldetails für den Austausch von Mediendaten in einem Anruf. Der Austausch von Mediendaten erfolgt durch die INVITE-Anforderung; StartTime gibt den Zeitpunkt an, zu dem die INVITE-Anforderung gesendet wurde. Der INVITE-Zeitpunkt gibt nicht notwendigerweise die Medienstartzeit an, da die Medien erst gestartet werden, nachdem die Sitzung angenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="8d9ea-110">Die Medienansicht enthält alle Spalten in der SessionDetails- [Ansicht in lync Server 2013](lync-server-2013-sessiondetails-view.md) zusätzlich die unten aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8d9ea-111">Spalte</span><span class="sxs-lookup"><span data-stu-id="8d9ea-111">Column</span></span></th>
<th><span data-ttu-id="8d9ea-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8d9ea-112">Data Type</span></span></th>
<th><span data-ttu-id="8d9ea-113">Details</span><span class="sxs-lookup"><span data-stu-id="8d9ea-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d9ea-114"><strong>Medien</strong></span><span class="sxs-lookup"><span data-stu-id="8d9ea-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="8d9ea-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8d9ea-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-116">Medientyp.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-116">Media type.</span></span> <span data-ttu-id="8d9ea-117">Weitere Informationen finden Sie <a href="lync-server-2013-medialist-table.md">in der medialist-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8d9ea-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8d9ea-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="8d9ea-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8d9ea-119">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="8d9ea-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-120">Uhrzeit, zu der eine Medienanforderung gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8d9ea-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="8d9ea-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8d9ea-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="8d9ea-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="8d9ea-123">Sitzungsende.</span><span class="sxs-lookup"><span data-stu-id="8d9ea-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

