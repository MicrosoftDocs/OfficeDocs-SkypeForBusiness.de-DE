---
title: 'Lync Server 2013: neue trunk Funktion'
description: 'Lync Server 2013: neue trunk Funktion.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New trunk feature
ms:assetid: 9b398bc8-2760-4218-b1a4-89b9694b1171
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688152(v=OCS.15)
ms:contentKeyID: 49733755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8f923ceada899608cc350bd1343345c12d0996b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541941"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="1a36a-103">Neue trunk Funktion in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a36a-103">New trunk feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a36a-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1a36a-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1a36a-105">In Microsoft lync Server 2013 können mehrere Trunks zwischen einem Vermittlungsserver und einem Gateway definiert werden.</span><span class="sxs-lookup"><span data-stu-id="1a36a-105">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="1a36a-106">Microsoft lync Server 2010 nur für einen einzelnen trunk zwischen einem Vermittlungsserver und einem PSTN-Gateway zulässig.</span><span class="sxs-lookup"><span data-stu-id="1a36a-106">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="1a36a-107">Diese Funktion bietet die Flexibilität, zusätzliche Trunks zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1a36a-107">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="1a36a-108">Ein trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver FQDN und einem Überwachungs Port und einem PSTN-Gateway-FQDN und dem Überwachungs Port.</span><span class="sxs-lookup"><span data-stu-id="1a36a-108">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="1a36a-109">Diese neue Funktion ermöglicht eine einfache trunk Definition für Ausfallsicherheit (wobei mehrere Vermittlungsserver zum Weiterleiten von Anrufen an das gleiche PSTN-Gateway verwendet werden können), für die PBX-Interoperabilität, bei der mehrere Trunks mit unterschiedlichen zugeordneten Richtlinien zwischen und IP-Nebenstellenanlage und einem Vermittlungsserver verwendet werden können, und für SIP-Trunk Konfigurationen, bei denen Vermittlungsserver an unterschiedliche</span><span class="sxs-lookup"><span data-stu-id="1a36a-109">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="1a36a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a36a-110">See Also</span></span>


[<span data-ttu-id="1a36a-111">Neue Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a36a-111">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

