---
title: 'Lync Server 2013: unterstützte Server Zusammenstellung für Edge-Komponenten'
description: 'Lync Server 2013: unterstützte Server Zusammenstellung für Edge-Komponenten.'
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
ms.openlocfilehash: 7bf253e5210e077ca62b3d00f7f130d54d8392a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556361"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="a7bbf-103">Unterstützte Server Zusammenstellungen für Edge-Komponenten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7bbf-103">Supported server collocation for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7bbf-104">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a7bbf-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a7bbf-105">Der Zugriffs-Edgedienst-, Webkonferenz-Edgedienst-, A/V-Edgedienst-und XMPP-Proxy Dienst befinden sich auf den Edge-Servern.</span><span class="sxs-lookup"><span data-stu-id="a7bbf-105">The Access Edge service, Web Conferencing Edge service, A/V Edge service and XMPP Proxy service are collocated on the Edge Servers.</span></span> <span data-ttu-id="a7bbf-106">Die folgenden Server bieten für den Zugriff durch externe Benutzer erforderliche Funktionen und müssen als dedizierte Server bereitgestellt werden:</span><span class="sxs-lookup"><span data-stu-id="a7bbf-106">The following servers provide functions needed for external user access and must be deployed as dedicated servers:</span></span>

  - <span data-ttu-id="a7bbf-107">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="a7bbf-107">Edge Server</span></span>

  - <span data-ttu-id="a7bbf-108">Director (optional)</span><span class="sxs-lookup"><span data-stu-id="a7bbf-108">Director (Optional)</span></span>

  - <span data-ttu-id="a7bbf-109">Reverseproxy</span><span class="sxs-lookup"><span data-stu-id="a7bbf-109">Reverse proxy</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a7bbf-110">Der Reverseproxy muss nicht nur für lync Server 2013 reserviert werden.</span><span class="sxs-lookup"><span data-stu-id="a7bbf-110">The reverse proxy does not need to be dedicated to serving only Lync Server 2013.</span></span> <span data-ttu-id="a7bbf-111">Beispielsweise können Sie Dienste zum Veröffentlichen der lync Server-Webdienste bereitstellen und gleichzeitig eine veröffentlichte Website für eine andere Website bereitstellen, die keinen Einfluss auf lync Server hat.</span><span class="sxs-lookup"><span data-stu-id="a7bbf-111">For example, you can provide services to publish the Lync Server Web services, and concurrently provide a published Web site for another Web site that has no bearing on Lync Server at all.</span></span> <span data-ttu-id="a7bbf-112">Wenn Sie bereits einen Reverseproxy im Umkreisnetzwerk haben, um andere Dienste zu unterstützen, können Sie ihn für lync Server 2013 verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7bbf-112">If you already have a reverse proxy server in the perimeter network to support other services, you can use it for Lync Server 2013.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

