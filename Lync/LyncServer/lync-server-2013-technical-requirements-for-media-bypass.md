---
title: 'Lync Server 2013: technische Anforderungen für die medienumgehung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b962905870287ef6765ecb6e7ee9b3e321ac6a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="59c5d-102">Technische Anforderungen für die medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c5d-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59c5d-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="59c5d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="59c5d-104">Für jeden Anruf im PSTN bestimmt der Vermittlungsserver, ob Medien aus dem lync-Endpunkt des Ursprungs direkt an einen Vermittlungsserver Peer gesendet werden können, ohne das Vermittlungsserver zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="59c5d-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="59c5d-105">Der Peer kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) bei einem Anbieter von Internettelefoniediensten sein, der zu der Leitung zwischen dem Vermittlungsserver gehört, bei dem der Anruf weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="59c5d-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="59c5d-106">Die Medienumgehung kann implementiert werden, wenn die folgenden Voraussetzungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="59c5d-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="59c5d-107">Ein Vermittlungsserver Peer muss die erforderlichen Funktionen für die medienumgehung unterstützen, wobei es sich dabei um die Möglichkeit handelt, mehrere gegabelte Antworten zu verarbeiten ("frühe Dialoge" genannt).</span><span class="sxs-lookup"><span data-stu-id="59c5d-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="59c5d-108">Wenden Sie sich an den Hersteller Ihres Gateways oder Ihrer Nebenstellenanlage oder an Ihr ITSP, um den Wert für die maximale Anzahl von frühzeitigen Dialogen zu erhalten, die das Gateway, die Nebenstellenanlage oder der SBC annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="59c5d-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="59c5d-109">Der Vermittlungsserver Peer muss den Mediendatenverkehr direkt von lync-Endpunkten akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="59c5d-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="59c5d-110">Viele internettelefoniediensten ermöglichen, dass Ihr SBC nur Datenverkehr aus dem Vermittlungsserver empfängt.</span><span class="sxs-lookup"><span data-stu-id="59c5d-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="59c5d-111">Wenden Sie sich an Ihren ITSP, um zu ermitteln, ob der SBC Mediendatenverkehr direkt von lync-Endpunkten akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="59c5d-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="59c5d-112">Lync-Clients und ein Vermittlungsserver Peer müssen gut verbunden sein, was bedeutet, dass Sie sich entweder in derselben netzwerkregion oder an Netzwerkstandorten befinden, die über WAN-Verbindungen, die keine Bandbreiteneinschränkungen aufweisen, eine Verbindung mit der Region herstellen.</span><span class="sxs-lookup"><span data-stu-id="59c5d-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="59c5d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59c5d-113">See Also</span></span>


[<span data-ttu-id="59c5d-114">Medien Umgehungs Modi in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c5d-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="59c5d-115">Medienumgehung und Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="59c5d-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

