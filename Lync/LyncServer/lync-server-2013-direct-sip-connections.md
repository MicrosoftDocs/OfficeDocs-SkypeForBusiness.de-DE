---
title: 'Lync Server 2013: direkte SIP-Verbindungen'
description: 'Lync Server 2013: direkte SIP-Verbindungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebc42cd26472bbb19c7ef886a9449ab453b90680
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559671"
---
# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="3bb5a-103">Direkte SIP-Verbindungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bb5a-103">Direct SIP connections in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3bb5a-104">_**Letztes Änderungsstand des Themas:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="3bb5a-104">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="3bb5a-105">Sie können *direkte SIP-Verbindungen* verwenden, um lync Server mit einem der folgenden zu verbinden:</span><span class="sxs-lookup"><span data-stu-id="3bb5a-105">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="3bb5a-106">Eine IP-Nebenstellenanlage (Ausführliche Informationen finden Sie unter [Direct SIP-Bereitstellungsoptionen in lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="3bb5a-106">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="3bb5a-107">Ein PSTN-Gateway (Weitere Informationen finden Sie unter [PSTN-Gateway-Bereitstellungsoptionen in lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="3bb5a-107">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="3bb5a-108">Um eine direkte SIP-Verbindung zu implementieren, führen Sie im wesentlichen dieselben Bereitstellungsschritte aus wie bei der Implementierung eines SIP-Trunks.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="3bb5a-109">In beiden Fällen implementieren Sie die Verbindung mithilfe der externen Schnittstelle eines Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="3bb5a-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="3bb5a-110">Der einzige Unterschied besteht darin, dass Sie SIP-Trunks mit einer externen Entität wie einem ITSP-Gateway verbinden und direkte SIP-Verbindungen mit einer internen Entität in Ihrem lokalen Netzwerk verbinden, beispielsweise mit einer IP-Nebenstellenanlage oder einem PSTN-Gateway (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="3bb5a-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3bb5a-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="3bb5a-111">In This Section</span></span>

  - [<span data-ttu-id="3bb5a-112">Direkte SIP-Bereitstellungsoptionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bb5a-112">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="3bb5a-113">Bereitstellungsoptionen für PSTN-Gateways in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3bb5a-113">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

