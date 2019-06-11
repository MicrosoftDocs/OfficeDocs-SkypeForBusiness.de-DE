---
title: 'Lync Server 2013: ClientVersions-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cba578209ca6c22360da73c2317334ecf77da569
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-table-in-lync-server-2013"></a><span data-ttu-id="92ba1-102">ClientVersions-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92ba1-102">ClientVersions table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92ba1-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="92ba1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="92ba1-104">Die ClientVersions-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Clienttypen und-Versionen gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="92ba1-104">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="92ba1-105">Jeder Datensatz in der Tabelle stellt eine Client Version dar.</span><span class="sxs-lookup"><span data-stu-id="92ba1-105">Each record in the table represents one client version.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92ba1-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="92ba1-106">Column</span></span></th>
<th><span data-ttu-id="92ba1-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="92ba1-107">Data Type</span></span></th>
<th><span data-ttu-id="92ba1-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="92ba1-108">Key/Index</span></span></th>
<th><span data-ttu-id="92ba1-109">Details</span><span class="sxs-lookup"><span data-stu-id="92ba1-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92ba1-110"><strong>VersionID</strong></span><span class="sxs-lookup"><span data-stu-id="92ba1-110"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="92ba1-111"><strong>int</strong></span><span class="sxs-lookup"><span data-stu-id="92ba1-111"><strong>int</strong></span></span></p></td>
<td><p><span data-ttu-id="92ba1-112">Primary</span><span class="sxs-lookup"><span data-stu-id="92ba1-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="92ba1-113">Eindeutige Nummer, die diesen Clienttyp und die Version identifiziert.</span><span class="sxs-lookup"><span data-stu-id="92ba1-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92ba1-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="92ba1-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="92ba1-115"><strong>nvarchar(256)</strong></span><span class="sxs-lookup"><span data-stu-id="92ba1-115"><strong>nvarchar(256)</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92ba1-116">Versionsname.</span><span class="sxs-lookup"><span data-stu-id="92ba1-116">Version name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92ba1-117"><strong>Clienttyp</strong></span><span class="sxs-lookup"><span data-stu-id="92ba1-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="92ba1-118">int</span><span class="sxs-lookup"><span data-stu-id="92ba1-118">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="92ba1-119">Gibt den Typ des in der Sitzung verwendeten Clients an.</span><span class="sxs-lookup"><span data-stu-id="92ba1-119">Specifies the type of client used in the session.</span></span> <span data-ttu-id="92ba1-120">Weitere Informationen finden Sie <a href="lync-server-2013-useragentdef-table.md">in der UserAgentDef-Tabelle in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="92ba1-120">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="92ba1-121">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="92ba1-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

