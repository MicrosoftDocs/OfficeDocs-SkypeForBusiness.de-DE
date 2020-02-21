---
title: 'Lync Server 2013: Überlegungen zur Interoperabilität für Videokonferenzen'
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
ms.openlocfilehash: 6157b9dc8867b2f458eafb6f0343fd43a19af537
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="1708f-102">Überlegungen zur Interoperabilität für Videokonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1708f-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1708f-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1708f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1708f-104">In diesem Abschnitt wird die Benutzererfahrung während der Koexistenzphase der Migration beschrieben, wenn Interoperabilität zwischen Legacyclients und einem lync Server 2013 Pool oder lync Server 2013 Clients und einem Legacy Pool besteht.</span><span class="sxs-lookup"><span data-stu-id="1708f-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="1708f-105">Lync Server 2013 Pools</span><span class="sxs-lookup"><span data-stu-id="1708f-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="1708f-106">Benutzer erleben das folgende Verhalten, wenn ein Legacyclient in einem lync Server 2013-Pool verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1708f-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="1708f-107">Bei Gesprächen mit zwei Teilnehmern ist die Videoauflösung mit der im Legacypool identisch.</span><span class="sxs-lookup"><span data-stu-id="1708f-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="1708f-p101">Bei Konferenzen mit mehreren Teilnehmern entsprechen Videoauflösung und Videokonferenzfeatures denen im Legacypool. Profilfotoansicht und hohe Auflösung sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1708f-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="1708f-110">Legacypools</span><span class="sxs-lookup"><span data-stu-id="1708f-110">Legacy Pools</span></span>

<span data-ttu-id="1708f-111">Benutzer erleben das folgende Verhalten, wenn ein lync Server 2013-Client in einem Legacy Pool verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="1708f-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="1708f-112">Für Anrufe mit zwei Teilnehmern können lync Server 2013-Clients wie folgt neue Features verwenden:</span><span class="sxs-lookup"><span data-stu-id="1708f-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="1708f-113">H. 264 ist verfügbar, wenn beide Teilnehmer lync Server 2013 Clients verwenden.</span><span class="sxs-lookup"><span data-stu-id="1708f-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="1708f-114">Der lync Server 2013-Client verwendet den Standardwert für TotalReceiveVideoBitRateKb, da der Legacy Server diese Informationen nicht mit in-Band-Übermittlung sendet.</span><span class="sxs-lookup"><span data-stu-id="1708f-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="1708f-115">Bei Konferenzen mit mehreren Teilnehmern entsprechen Videoauflösung und Videokonferenzfeatures denen eines Legacyclients im Legacypool.</span><span class="sxs-lookup"><span data-stu-id="1708f-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1708f-116">Wenn ein Legacy Server einen lync Server 2013-Client hostet, ist es möglich, die Bandbreiten für Videokonferenzen so zu konfigurieren, dass alle Benutzer im Pool nur Video mit niedriger Auflösung empfangen, aber hochauflösende Videos senden.</span><span class="sxs-lookup"><span data-stu-id="1708f-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="1708f-117">Ein Beispiel hierfür ist, wenn MaxVideoRateAllowed auf cif-250K in der Medienkonfiguration festgelegt ist und VideoBitRateKb in der konferenzrichtlinie auf 2000 Kbit/s festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1708f-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="1708f-118">Der Nettoeffekt in dieser Situation ist, dass eine hohe Auflösung für Benutzer im Pool nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="1708f-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="1708f-119">Da MaxVideoRateAllowed nicht mehr für lync Server 2013-Clients verwendet wird, kann es nicht verhindern, dass lync Server 2013 Clients hochauflösende Videos anfordern.</span><span class="sxs-lookup"><span data-stu-id="1708f-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="1708f-120">Legen Sie stattdessen VideoBitRateKb in der konferenzrichtlinie für alle Benutzer im Pool auf denselben Wert fest wie MaxVideoRateAllowed (CIF ist auf 250 KBit/s festgelegt, oder VGA ist auf 600 KBit/s festgelegt, oder HD ist auf 1500 kBit/s festgelegt).</span><span class="sxs-lookup"><span data-stu-id="1708f-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

