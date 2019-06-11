---
title: 'Lync Server 2013: Medienansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="9c00e-102">Medienansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c00e-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c00e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9c00e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9c00e-104">In der Medienansicht werden Informationen zu einem Medientyp gespeichert, der in einer Peer-to-Peer-Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c00e-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="9c00e-105">Eine Sitzung wird von mehreren Datensätzen in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c00e-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="9c00e-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="9c00e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9c00e-107">Die Medienansicht sollte nicht verwendet werden, um die Mediendauer einer Sitzung zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="9c00e-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="9c00e-108">Diese Ansicht enthält die Signalisierungs Details von Medienaustausch in einer Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9c00e-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="9c00e-109">Der Medienaustausch erfolgt über die Einladungs Anfrage, und Startzeit gibt an, wie lange die Einladung gesendet wurde. Die Einladungs Zeit bedeutet nicht unbedingt die Startzeit des Mediums, da Medien erst nach Annahme der Sitzung gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="9c00e-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="9c00e-110">Die Medienansicht enthält alle Spalten in der SessionDetails- [Ansicht in lync Server 2013](lync-server-2013-sessiondetails-view.md) sowie die nachstehend aufgeführten.</span><span class="sxs-lookup"><span data-stu-id="9c00e-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c00e-111">Spalte</span><span class="sxs-lookup"><span data-stu-id="9c00e-111">Column</span></span></th>
<th><span data-ttu-id="9c00e-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9c00e-112">Data Type</span></span></th>
<th><span data-ttu-id="9c00e-113">Details</span><span class="sxs-lookup"><span data-stu-id="9c00e-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c00e-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="9c00e-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="9c00e-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c00e-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9c00e-116">Medientyp.</span><span class="sxs-lookup"><span data-stu-id="9c00e-116">Media type.</span></span> <span data-ttu-id="9c00e-117">Weitere Informationen finden Sie <a href="lync-server-2013-medialist-table.md">in der Tabelle medialist in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="9c00e-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c00e-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c00e-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c00e-119">datetime</span><span class="sxs-lookup"><span data-stu-id="9c00e-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c00e-120">Zeit, zu der eine Medienanfrage gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="9c00e-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c00e-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9c00e-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9c00e-122">datetime</span><span class="sxs-lookup"><span data-stu-id="9c00e-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="9c00e-123">Endzeit der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="9c00e-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

