---
title: 'Lync Server 2013: Unterstützte Serverkollokation für Edgekomponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc12e442be98ba1fd962634460200ce749aca3d6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="e08e6-102">Unterstützte Serverkollokation für Edgekomponenten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e08e6-102">Supported server collocation for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e08e6-103">_**Letztes Änderungsdatum des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e08e6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e08e6-104">Der Zugriffs-Edgedienst, der Webkonferenz-Edgedienst, der A/V-Edgedienst und der XMPP-Proxy Dienst sind auf den Edgeserver verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e08e6-104">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="e08e6-105">Die folgenden Server stellen Funktionen bereit, die für den Zugriff durch externe Benutzer erforderlich sind, und müssen als dedizierte Server bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="e08e6-105">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="e08e6-106">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="e08e6-106">Edge Server</span></span>

  - <span data-ttu-id="e08e6-107">Director (optional)</span><span class="sxs-lookup"><span data-stu-id="e08e6-107">Director (Optional)</span></span>

  - <span data-ttu-id="e08e6-108">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="e08e6-108">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e08e6-109">Der Reverse-Proxy muss nicht nur für die Bereitstellung von lync Server 2013 dediziert sein.</span><span class="sxs-lookup"><span data-stu-id="e08e6-109">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="e08e6-110">So können Sie beispielsweise Dienste bereitstellen, um die lync Server-Webdienste zu veröffentlichen, und gleichzeitig eine veröffentlichte Website für eine andere Website bereitstellen, die überhaupt keine Auswirkungen auf lync Server hat.</span><span class="sxs-lookup"><span data-stu-id="e08e6-110">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="e08e6-111">Wenn Sie bereits über einen Reverse Proxy-Server im Umkreisnetzwerk verfügen, um andere Dienste zu unterstützen, können Sie ihn für lync Server 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="e08e6-111">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

