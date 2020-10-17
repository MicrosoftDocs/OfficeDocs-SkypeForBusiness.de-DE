---
title: 'Lync Server 2013: UserAgent-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb9e70635fc4c54448f6fe3f549d3d6853612070
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530122"
---
# <a name="useragent-view-in-lync-server-2013"></a><span data-ttu-id="8c45e-102">UserAgent-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c45e-102">UserAgent view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c45e-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8c45e-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8c45e-104">Die UserAgent-Ansicht speichert Informationen über die Benutzeragenten, die an Sitzungen teilgenommen haben und die über Datensätze in der Datenbank verfügen.</span><span class="sxs-lookup"><span data-stu-id="8c45e-104">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="8c45e-105">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8c45e-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c45e-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="8c45e-106">Column</span></span></th>
<th><span data-ttu-id="8c45e-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="8c45e-107">Data Type</span></span></th>
<th><span data-ttu-id="8c45e-108">Details</span><span class="sxs-lookup"><span data-stu-id="8c45e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c45e-109">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="8c45e-109">UserAgentKey</span></span></p></td>
<td><p><span data-ttu-id="8c45e-110">int</span><span class="sxs-lookup"><span data-stu-id="8c45e-110">int</span></span></p></td>
<td><p><span data-ttu-id="8c45e-111">Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8c45e-111">Unique number identifying this user agent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c45e-112">UserAgent</span><span class="sxs-lookup"><span data-stu-id="8c45e-112">UserAgent</span></span></p></td>
<td><p><span data-ttu-id="8c45e-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="8c45e-113">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="8c45e-114">Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="8c45e-114">User agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c45e-115">UAType</span><span class="sxs-lookup"><span data-stu-id="8c45e-115">UAType</span></span></p></td>
<td><p><span data-ttu-id="8c45e-116">smallint</span><span class="sxs-lookup"><span data-stu-id="8c45e-116">smallint</span></span></p></td>
<td><p><span data-ttu-id="8c45e-117">Benutzeragententyp.</span><span class="sxs-lookup"><span data-stu-id="8c45e-117">Type of user agent.</span></span> <span data-ttu-id="8c45e-118">Weitere Informationen finden Sie <a href="lync-server-2013-useragent-table.md">in der UserAgent-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="8c45e-118">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c45e-119">UACategory</span><span class="sxs-lookup"><span data-stu-id="8c45e-119">UACategory</span></span></p></td>
<td><p><span data-ttu-id="8c45e-120">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="8c45e-120">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="8c45e-p103">Die Kategorie, der der Benutzer-Agent angehört. Beispielsweise weist der Benutzer-Agent Conferencing_Attendant_1.0 eine UACategory von CAA auf.</span><span class="sxs-lookup"><span data-stu-id="8c45e-p103">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

