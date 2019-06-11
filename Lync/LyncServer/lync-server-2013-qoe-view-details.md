---
title: 'Lync Server 2013: Details zur QoE-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoE view details
ms:assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688081(v=OCS.15)
ms:contentKeyID: 49733677
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e223ff2adee63eb8e13304e4df6db519e85014f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-view-details-in-lync-server-2013"></a><span data-ttu-id="3394f-102">Details zur QoE-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3394f-102">QoE view details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3394f-103">_**Letztes Änderungsdatum des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="3394f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="3394f-104">Ansichten decken die am häufigsten verwendeten Szenarien für die Rückgabe von Daten aus der QoE SQL-Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="3394f-104">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="3394f-105">Es wird empfohlen, Ansichten zum Erstellen benutzerdefinierter Berichte zu verwenden, anstatt direkt auf die Datenbanktabellen zuzugreifen. Das liegt daran, dass Ansichten eher die Abwärtskompatibilität mit zukünftigen Versionen aufrecht erhalten.</span><span class="sxs-lookup"><span data-stu-id="3394f-105">It is recommended views used for building custom reports instead of directly accessing the database tables; that’s because views are more likely to maintain backwards compatibility with future releases.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3394f-106">Ansichts Name</span><span class="sxs-lookup"><span data-stu-id="3394f-106">View Name</span></span></th>
<th><span data-ttu-id="3394f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3394f-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3394f-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3394f-108"><a href="lync-server-2013-audiostreamdetail-view.md">AudioStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3394f-109">Speichert Informationen zu jedem Audiostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3394f-109">Stores information about each audio stream in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3394f-110"><a href="lync-server-2013-medialine-view.md">Medienansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3394f-110"><a href="lync-server-2013-medialine-view.md">MediaLine view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3394f-111">Speichert Informationen zu jeder medienzeile in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3394f-111">Stores information about each media line in the database.</span></span> <span data-ttu-id="3394f-112">Eine Audiositzung enthält in der Regel eine Audio-medienzeile.</span><span class="sxs-lookup"><span data-stu-id="3394f-112">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="3394f-113">Eine Audio-und Video (A/V)-Sitzung enthält in der Regel eine Audio-medienzeile und eine Video medienzeile. die Sitzung kann jedoch zwei Video Medien Linien enthalten, wenn ein Konferenzgerät verwendet wird oder wenn die Katalogansicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3394f-113">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3394f-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3394f-114"><a href="lync-server-2013-networkconfigurationsettings-view.md">NetworkConfigurationSettings view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3394f-115">Speichert Informationen zur Netzwerkkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="3394f-115">Stores information about the network configuration.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3394f-116"><a href="lync-server-2013-session-view.md">Sitzungsansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3394f-116"><a href="lync-server-2013-session-view.md">Session view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3394f-117">Speichert Informationen zu Sitzungen mit Datensätzen in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3394f-117">Stores information about sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3394f-118"><a href="lync-server-2013-useragent-view.md">UserAgent-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3394f-118"><a href="lync-server-2013-useragent-view.md">UserAgent view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3394f-119">Speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3394f-119">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3394f-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail-Ansicht in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="3394f-120"><a href="lync-server-2013-videostreamdetail-view.md">VideoStreamDetail view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="3394f-121">Speichert Informationen zu jedem Videostream in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3394f-121">Stores information about each video stream in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

