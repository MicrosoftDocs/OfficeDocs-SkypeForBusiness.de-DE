---
title: 'Lync Server 2013: Übersicht über den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ac09f5ca7ed67b078b3d5313982cff4af38e835
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="811b9-102">Übersicht über den Director in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="811b9-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="811b9-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="811b9-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="811b9-104">Bei einem Director handelt es sich um einen Server mit lync Server 2013, der Benutzeranforderungen authentifiziert, jedoch keine Benutzerkonten aufweist.</span><span class="sxs-lookup"><span data-stu-id="811b9-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="811b9-105">Optional können Sie einen Director in den folgenden beiden Szenarien bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="811b9-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="811b9-106">Wenn Sie den Zugriff durch externe Benutzer durch die Bereitstellung von Edge-Servern aktivieren, sollten Sie auch einen Director bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="811b9-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="811b9-107">In diesem Szenario authentifiziert der Director die externen Benutzer und übergibt dann den Datenverkehr an interne Server.</span><span class="sxs-lookup"><span data-stu-id="811b9-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="811b9-108">Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlastet Front-End-Pool Server den Aufwand für die Authentifizierung dieser Benutzer.</span><span class="sxs-lookup"><span data-stu-id="811b9-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="811b9-109">Außerdem können interne Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen isoliert werden.</span><span class="sxs-lookup"><span data-stu-id="811b9-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="811b9-110">Wenn das Netzwerk während eines solchen Angriffs mit ungültigem externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.</span><span class="sxs-lookup"><span data-stu-id="811b9-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="811b9-111">Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, können Sie die Authentifizierungsanforderungen rationalisieren und die Leistung verbessern, indem Sie einen Director zu dieser Website hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="811b9-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="811b9-112">In diesem Szenario werden alle Anforderungen zuerst an den Director geleitet, der Sie dann an die richtige Front-End-Pool weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="811b9-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

