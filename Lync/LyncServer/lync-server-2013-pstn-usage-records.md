---
title: 'Lync Server 2013: PSTN-Verwendungsdaten Sätze'
description: 'Lync Server 2013: PSTN-Verwendungsdaten Sätze.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f8ff428dc2fa5cf8cf0f10e37f0f79c38d70d70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565581"
---
# <a name="pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="d5242-103">PSTN-Verwendungsdaten Sätze in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5242-103">PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5242-104">_**Letztes Änderungsstand des Themas:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="d5242-104">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="d5242-p101">Die Planung von PSTN-Verwendungsdatensätzen besteht hauptsächlich darin, alle Anrufberechtigungen aufzulisten, die aktuell in Ihrer Organisation vorhanden sind, vom Firmenchef bis hin zu Personen mit befristeten Arbeitsverträgen, Beratern und Zeitarbeitern. Dieses Verfahren bietet außerdem die Gelegenheit, vorhandene Berechtigungen neu zu überprüfen und sie zu überarbeiten. Sie können PSTN-Verwendungsdatensätze ausschließlich für Berechtigungen erstellen, die sich auf Ihre vorgesehenen Enterprise-VoIP-Benutzer beziehen. Langfristig besteht eine bessere Lösung möglicherweise darin, PSTN-Verwendungsdatensätze einfach für alle Berechtigungen zu erstellen, und zwar unabhängig davon, ob einige davon derzeit nicht für die Gruppe der Benutzer gelten, für die Enterprise-VoIP aktiviert werden soll. Wenn Anrufberechtigungen geändert oder neue Benutzer mit abweichenden Abrufberechtigungen hinzugefügt werden, haben Sie die erforderlichen PSTN-Verwendungsdatensätze bereits erstellt.</span><span class="sxs-lookup"><span data-stu-id="d5242-p101">Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.</span></span>

<span data-ttu-id="d5242-109">Die folgende Tabelle stellt eine typische PSTN-Verwendungstabelle dar.</span><span class="sxs-lookup"><span data-stu-id="d5242-109">The following table shows a typical PSTN usage table.</span></span>

### <a name="pstn-usage-records"></a><span data-ttu-id="d5242-110">PSTN-Verwendungsdatensätze</span><span class="sxs-lookup"><span data-stu-id="d5242-110">PSTN Usage Records</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5242-111">Telefonattribut</span><span class="sxs-lookup"><span data-stu-id="d5242-111">Phone attribute</span></span></th>
<th><span data-ttu-id="d5242-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5242-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5242-113">Lokal</span><span class="sxs-lookup"><span data-stu-id="d5242-113">Local</span></span></p></td>
<td><p><span data-ttu-id="d5242-114">Ortsgespräche</span><span class="sxs-lookup"><span data-stu-id="d5242-114">Local calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5242-115">Long-Distance</span><span class="sxs-lookup"><span data-stu-id="d5242-115">Long-Distance</span></span></p></td>
<td><p><span data-ttu-id="d5242-116">Ferngespräche</span><span class="sxs-lookup"><span data-stu-id="d5242-116">Long distance calls</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5242-117">International</span><span class="sxs-lookup"><span data-stu-id="d5242-117">International</span></span></p></td>
<td><p><span data-ttu-id="d5242-118">Auslandsgespräche</span><span class="sxs-lookup"><span data-stu-id="d5242-118">International calls</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5242-119">Delhi</span><span class="sxs-lookup"><span data-stu-id="d5242-119">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d5242-120">Vollzeitmitarbeiter in Delhi</span><span class="sxs-lookup"><span data-stu-id="d5242-120">Delhi full-time employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5242-121">Redmond</span><span class="sxs-lookup"><span data-stu-id="d5242-121">Redmond</span></span></p></td>
<td><p><span data-ttu-id="d5242-122">Vollzeitmitarbeiter in Redmond</span><span class="sxs-lookup"><span data-stu-id="d5242-122">Redmond full-time employees</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5242-123">RedmondTemps</span><span class="sxs-lookup"><span data-stu-id="d5242-123">RedmondTemps</span></span></p></td>
<td><p><span data-ttu-id="d5242-124">Zeitarbeiter in Redmond</span><span class="sxs-lookup"><span data-stu-id="d5242-124">Redmond temporary employees</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5242-125">Zürich</span><span class="sxs-lookup"><span data-stu-id="d5242-125">Zurich</span></span></p></td>
<td><p><span data-ttu-id="d5242-126">Vollzeitmitarbeiter in Zürich</span><span class="sxs-lookup"><span data-stu-id="d5242-126">Zurich full-time employees</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5242-p102">PSTN-Verwendungsdatensätze alleine führen keine Aktionen aus. Um sie verwenden zu können, müssen Sie sie mit Folgendem verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="d5242-p102">By themselves, PSTN usage records do not do anything. For them to work, you must associate them with the following:</span></span>

  - <span data-ttu-id="d5242-129">VoIP-Richtlinien, die Benutzern zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="d5242-129">Voice policies, which are assigned to users.</span></span>

  - <span data-ttu-id="d5242-130">Routen, die Rufnummern zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="d5242-130">Routes, which are assigned to phone numbers.</span></span>

<span data-ttu-id="d5242-131">Ausführliche Informationen zu VoIP-Richtlinien und-Routen finden Sie unter [VoIP-Richtlinien in lync Server 2013](lync-server-2013-voice-policies.md) und [VoIP-Routen in lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="d5242-131">For details about voice policies and routes, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md) and [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span> <span data-ttu-id="d5242-132">Ausführliche Informationen zum Erstellen und Konfigurieren dieser Informationen finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="d5242-132">For details about how to create and configure them, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

