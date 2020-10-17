---
title: 'Lync Server 2013: Client Versions-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8987bc1078dfdfaec8cccdb6625ceb9846ef6a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499172"
---
# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="287db-102">Client Versions-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="287db-102">ClientVersions table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="287db-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="287db-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="287db-p101">Bei der ClientVersions-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste der verschiedenen Clienttypen und -versionen gespeichert wird, die an in der Datenbank aufgezeichneten Sitzungen beteiligt sind. Jeder Datensatz in der Tabelle steht für eine Clientversion.</span><span class="sxs-lookup"><span data-stu-id="287db-p101">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="287db-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="287db-106">Column</span></span></th>
<th><span data-ttu-id="287db-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="287db-107">Data Type</span></span></th>
<th><span data-ttu-id="287db-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="287db-108">Key/Index</span></span></th>
<th><span data-ttu-id="287db-109">Details</span><span class="sxs-lookup"><span data-stu-id="287db-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="287db-110"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="287db-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="287db-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="287db-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="287db-112">Primary</span><span class="sxs-lookup"><span data-stu-id="287db-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="287db-113">Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="287db-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="287db-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="287db-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="287db-115"><strong>nvarchar (256)</strong></span><span class="sxs-lookup"><span data-stu-id="287db-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="287db-116">Versionsname</span><span class="sxs-lookup"><span data-stu-id="287db-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="287db-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="287db-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="287db-118">int</span><span class="sxs-lookup"><span data-stu-id="287db-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="287db-119">Gibt den Typ des Clients an, der in der Sitzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="287db-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="287db-120">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="287db-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="287db-121">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="287db-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

