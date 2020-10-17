---
title: 'Lync Server 2013: Configure Enhanced 9-1-1'
description: 'Lync Server 2013: Configure Enhanced 9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc7a2a9ed10e7f29f53a4dfff6dff926ded18d38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553331"
---
# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a><span data-ttu-id="16059-103">Konfigurieren von Enhanced 9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16059-103">Configure Enhanced 9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16059-104">_**Letztes Änderungsstand des Themas:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="16059-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="16059-p101">9-1-1 (erweitert) (E9-1-1) ist eine Benachrichtigungsfunktion für Notfallsituationen, bei dem die Telefonnummer des Anrufers einem physischen Standort in Form einer Adresse zugeordnet wird. Anhand dieser Informationen kann die Rettungsleitstelle umgehend Rettungskräfte an die Unglücksstelle senden.</span><span class="sxs-lookup"><span data-stu-id="16059-p101">Enhanced 9-1-1 (E9-1-1) is an emergency notification feature that associates the calling party’s telephone number with a civic or a street address. Using this information, the Public Safety Answering Point (PSAP) can immediately dispatch emergency services to the caller in distress.</span></span>

<span data-ttu-id="16059-107">Zur Unterstützung von E9-1-1 müssen lync Server 2013 einen Standort einem Client ordnungsgemäß zuordnen können und sicherstellen, dass diese Informationen zum Weiterleiten des Notrufs an den nächstgelegenen Rettungsleitstelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16059-107">To support E9-1-1, Lync Server 2013 must be able to correctly associate a location with a client and to make sure that this information is used to route the emergency call to the nearest PSAP.</span></span>

<span data-ttu-id="16059-108">Ausführliche Informationen zur Planung einer E9-1-1-Bereitstellung finden Sie unter [Planning for Emergency Services (E9-1-1) in lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="16059-108">For details about planning for an E9-1-1 deployment, see [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="16059-109">Lync Server 2013 unterstützt nur E9-1-1 in den Vereinigten Staaten.</span><span class="sxs-lookup"><span data-stu-id="16059-109">Lync Server 2013 only supports E9-1-1 within the United States.</span></span> <span data-ttu-id="16059-110">Für die Bereitstellung von E9-1-1 müssen Sie eine SIP-Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter konfigurieren oder ein Elin-Gateway (Emergency Location Identification Number) für einen PSTN-basierten E9-1-1-Dienstanbieter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="16059-110">To deploy E9-1-1, you need to configure a SIP connection to a qualified E9-1-1 service provider, or deploy an emergency location identification number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider.</span></span> <span data-ttu-id="16059-111">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) und Vermittlungsserver in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="16059-111">For details, see <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</A>.</span></span> <span data-ttu-id="16059-112">Ausführliche Informationen zum Konfigurieren von trunk Verbindungen finden Sie unter <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="16059-112">For details about configuring trunk connections, see <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">Configure a trunk with media bypass in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16059-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="16059-113">In This Section</span></span>

  - [<span data-ttu-id="16059-114">Konfigurieren einer E9-1-1-VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16059-114">Configure an E9-1-1 voice route in Lync Server 2013</span></span>](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [<span data-ttu-id="16059-115">Erstellen von ortungsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16059-115">Create location policies in Lync Server 2013</span></span>](lync-server-2013-create-location-policies.md)

  - [<span data-ttu-id="16059-116">Konfigurieren von Website Informationen für E9-1-1 in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16059-116">Configure site information for E9-1-1 in Lync Server 2013</span></span>](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [<span data-ttu-id="16059-117">Konfigurieren der Standortdatenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16059-117">Configure the location database in Lync Server 2013</span></span>](lync-server-2013-configure-the-location-database.md)

  - [<span data-ttu-id="16059-118">Konfigurieren der erweiterten E9-1-1-Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16059-118">Configure advanced E9-1-1 features in Lync Server 2013</span></span>](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

