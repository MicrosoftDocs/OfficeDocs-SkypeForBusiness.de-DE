---
title: 'Lync Server 2013: Interoperabilitäts Überlegungen für Videokonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8cdfa88cf6d6f58478ff3c6b44210545e24a765
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="a24ce-102">Interoperabilitäts Überlegungen für Videokonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a24ce-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a24ce-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a24ce-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a24ce-104">In diesem Abschnitt werden die Benutzererfahrung während der Koexistenzphase der Migration beschrieben, wenn es Interoperabilität zwischen Legacyclients und einem lync Server 2013-Pool oder lync Server 2013-Clients und einem Legacy Pool gibt.</span><span class="sxs-lookup"><span data-stu-id="a24ce-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="a24ce-105">Lync Server 2013-Pools</span><span class="sxs-lookup"><span data-stu-id="a24ce-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="a24ce-106">Benutzer erleben das folgende Verhalten, wenn ein Legacyclient in einem lync Server 2013-Pool verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="a24ce-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="a24ce-107">Bei Anrufen mit zwei Teilnehmern ist die Videoauflösung identisch mit der des Legacy Pools.</span><span class="sxs-lookup"><span data-stu-id="a24ce-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="a24ce-108">Für Konferenzen mit mehreren Teilnehmern sind Videoauflösung und Videokonferenz Features identisch mit dem Legacy Pool.</span><span class="sxs-lookup"><span data-stu-id="a24ce-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="a24ce-109">Eine Katalogansicht und eine höhere Auflösung sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a24ce-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="a24ce-110">Legacy Pools</span><span class="sxs-lookup"><span data-stu-id="a24ce-110">Legacy Pools</span></span>

<span data-ttu-id="a24ce-111">Benutzer erleben das folgende Verhalten, wenn ein lync Server 2013-Client in einem Legacy Pool verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="a24ce-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="a24ce-112">Bei Anrufen mit zwei Teilnehmern können lync Server 2013-Clients neue Features wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="a24ce-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="a24ce-113">H. 264 steht zur Verfügung, wenn beide Teilnehmer lync Server 2013-Clients verwenden.</span><span class="sxs-lookup"><span data-stu-id="a24ce-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="a24ce-114">Der lync Server 2013-Client verwendet den Standardwert für TotalReceiveVideoBitRateKb, da diese Informationen vom Legacy Server nicht an die in-Band-Bereitstellung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a24ce-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="a24ce-115">Für Konferenzen mit mehreren Teilnehmern sind Videoauflösungen und Videokonferenz Features identisch mit den Erfahrungen eines Legacyclients im Legacy Pool.</span><span class="sxs-lookup"><span data-stu-id="a24ce-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a24ce-116">Wenn ein Legacy Server einen lync Server 2013-Client hostet, ist es möglich, die Bandbreite für Videokonferenzen so zu konfigurieren, dass alle Benutzer im Pool nur Videos mit niedriger Auflösung empfangen, aber Video mit hoher Auflösung senden.</span><span class="sxs-lookup"><span data-stu-id="a24ce-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="a24ce-117">Ein Beispiel hierfür ist, wenn MaxVideoRateAllowed in der Medienkonfiguration auf cif-250K und VideoBitRateKb auf 2000 Kbit/s in Konferenzrichtlinien eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="a24ce-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="a24ce-118">Der Nettoeffekt in dieser Situation ist, dass eine höhere Auflösung für Benutzer im Pool nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="a24ce-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="a24ce-119">Da MaxVideoRateAllowed nicht mehr für lync Server 2013-Clients verwendet wird, kann es nicht verhindern, dass lync Server 2013-Clients ein Video mit hoher Auflösung anfordern.</span><span class="sxs-lookup"><span data-stu-id="a24ce-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="a24ce-120">Setzen Sie stattdessen VideoBitRateKb in der konferenzrichtlinie für alle Benutzer im Pool auf den gleichen Wert wie MaxVideoRateAllowed (das heißt, CIF ist auf 250 KBit/s festgesetzt, oder VGA ist auf 600 KBit/s festgesetzt, oder HD ist auf 1500 kBit/s festgesetzt).</span><span class="sxs-lookup"><span data-stu-id="a24ce-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

