---
title: 'Lync Server 2013: standortbasiertes Routing für Konferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing for conferencing
ms:assetid: e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362849(v=OCS.15)
ms:contentKeyID: 56335087
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec3268109b522a96e5593f6e0246ee7b36651c06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="f4ca3-102">Standortbasiertes Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4ca3-102">Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4ca3-103">_**Letztes Änderungsstand des Themas:** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="f4ca3-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="f4ca3-104">Das standortbasierte Routing ermöglicht das Einschränken des Routings von anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Parteien im Anruf.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-104">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="f4ca3-105">Mit dem kumulativen Update 2 von lync Server 2013 können standortbasierte Routing Regeln für lync-Besprechungen (also Konferenzen) erzwungen werden, um eine PSTN-Maut Umgehung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-105">With Cumulative Update 2 of Lync Server 2013, Location-Based Routing rules can be enforced on Lync meetings (i.e. conferences) to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f4ca3-106">Die Anwendung überwacht eine aktive Konferenz und erzwingt standortbasierte Routing Einschränkungen basierend auf dem Speicherort der teilnehmenden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-106">The application monitors an active conference and enforces Location-Based Routing restrictions based on the location of users participating.</span></span> <span data-ttu-id="f4ca3-107">Die standortbasierte Routing Konferenz Anwendung ermöglicht darüber hinaus die Durchsetzung von standortbasierten Routing Einschränkungen auf beratende Übertragungen mit PSTN-Endpunkten.</span><span class="sxs-lookup"><span data-stu-id="f4ca3-107">The Location-Based Routing Conferencing application additionally enables the enforcement of Location-Based Routing restrictions to consultative transfers involving PSTN endpoints.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f4ca3-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f4ca3-108">In This Section</span></span>

  - [<span data-ttu-id="f4ca3-109">Übersicht über das standortbasierte Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4ca3-109">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f4ca3-110">Standortbasiertes Routing und Anrufweiterleitung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4ca3-110">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-and-consultative-call-transfers.md)

  - [<span data-ttu-id="f4ca3-111">Anforderungen für das standortbasierte Routing für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4ca3-111">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-requirements-for-location-based-routing-for-conferencing.md)

  - [<span data-ttu-id="f4ca3-112">Konfiguration des standortbasierten Routings für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4ca3-112">Configuration of Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-configuration-of-location-based-routing-for-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

