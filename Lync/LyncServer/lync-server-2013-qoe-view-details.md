---
title: 'Lync Server 2013: QoE-ansichtsdetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f6d2b30654272baf0ce8db712461acb3e4f13a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="9e726-102">QoE-ansichtsdetails in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e726-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e726-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9e726-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9e726-104">Ansichten gibt es für die gebräuchlichsten Szenarien zur Rückgabe von Daten aus der QoE-SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9e726-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="9e726-105">Es wird empfohlen, zum Erstellen von benutzerdefinierten Berichten Ansichten zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen, um auch in zukünftigen Versionen abwärtskompatibel zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="9e726-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e726-106">Ansichtsname</span><span class="sxs-lookup"><span data-stu-id="9e726-106">View Name</span></span></th>
<th><span data-ttu-id="9e726-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e726-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e726-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e726-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9e726-109">Speichert Informationen zu jedem Audiostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9e726-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e726-110"><a href="lync-server-2013-medialine-view.md">Medienansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e726-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9e726-111">Speichert Informationen zu jeder Medienzeile in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9e726-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="9e726-112">Eine Audiositzung enthält für gewöhnlich eine Audiomedienzeile.</span><span class="sxs-lookup"><span data-stu-id="9e726-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="9e726-113">Eine A/V-Sitzung (Audio und Video) enthält meist eine Audiomedienzeile und eine Videomedienzeile, kann jedoch auch zwei Medienzeilen enthalten, wenn ein Konferenzgerät oder eine Galerieansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9e726-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e726-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e726-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9e726-115">Speichert Informationen über die Netzwerkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="9e726-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e726-116"><a href="lync-server-2013-session-view.md">Sitzungsansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e726-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9e726-117">Speichert Informationen über Sitzungen, zu denen in der Datenbank Datensätze vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="9e726-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e726-118"><a href="lync-server-2013-useragent-view.md">UserAgent-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e726-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9e726-119">Speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, zu denen es in der Datenbank Datensätze gibt.</span><span class="sxs-lookup"><span data-stu-id="9e726-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e726-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="9e726-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="9e726-121">Speichert Informationen zu jedem Videostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="9e726-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

