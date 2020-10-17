---
title: 'Lync Server 2013: neue trunk Funktion'
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
ms.openlocfilehash: 0feda45fd6c035209783d173da3a85dec3876e50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505282"
---
# <a name="new-trunk-feature-in-lync-server-2013"></a><span data-ttu-id="30e3d-102">Neue trunk Funktion in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30e3d-102">New trunk feature in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30e3d-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="30e3d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="30e3d-104">In Microsoft lync Server 2013 können mehrere Trunks zwischen einem Vermittlungsserver und einem Gateway definiert werden.</span><span class="sxs-lookup"><span data-stu-id="30e3d-104">In Microsoft Lync Server 2013, multiple trunks between a Mediation Server and a gateway can be defined.</span></span> <span data-ttu-id="30e3d-105">Microsoft lync Server 2010 nur für einen einzelnen trunk zwischen einem Vermittlungsserver und einem PSTN-Gateway zulässig.</span><span class="sxs-lookup"><span data-stu-id="30e3d-105">Microsoft Lync Server 2010 only allowed for a single trunk between a Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="30e3d-106">Diese Funktion bietet die Flexibilität, zusätzliche Trunks zu definieren.</span><span class="sxs-lookup"><span data-stu-id="30e3d-106">This feature provides the flexibility to define additional trunks.</span></span> <span data-ttu-id="30e3d-107">Ein trunk ist eine logische Zuordnung zwischen einem Vermittlungsserver FQDN und einem Überwachungs Port und einem PSTN-Gateway-FQDN und dem Überwachungs Port.</span><span class="sxs-lookup"><span data-stu-id="30e3d-107">A trunk is a logical association between a Mediation Server FQDN and listening port and a PSTN gateway FQDN and listening port.</span></span> <span data-ttu-id="30e3d-108">Diese neue Funktion ermöglicht eine einfache trunk Definition für Ausfallsicherheit (wobei mehrere Vermittlungsserver zum Weiterleiten von Anrufen an das gleiche PSTN-Gateway verwendet werden können), für die PBX-Interoperabilität, bei der mehrere Trunks mit unterschiedlichen zugeordneten Richtlinien zwischen und IP-Nebenstellenanlage und einem Vermittlungsserver verwendet werden können, und für SIP-Trunk Konfigurationen, bei denen Vermittlungsserver an unterschiedliche</span><span class="sxs-lookup"><span data-stu-id="30e3d-108">This new capability allows for easy trunk definition for resiliency (where multiple Mediation Servers can be used to route calls to the same PSTN Gateway), for PBX interoperability, where multiple trunks with different associated policies can be used between and IP-PBX and a Mediation Server, and for SIP trunk configurations where Mediation Servers at different sites have SIP trunks to the carrier referenced by the same carrier FQDN.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="30e3d-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30e3d-109">See Also</span></span>


[<span data-ttu-id="30e3d-110">Neue Enterprise-VoIP-Funktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30e3d-110">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

