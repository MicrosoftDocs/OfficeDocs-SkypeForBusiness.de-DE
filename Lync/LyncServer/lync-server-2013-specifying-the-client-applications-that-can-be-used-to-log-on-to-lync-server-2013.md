---
title: 'Lync Server 2013: Angeben der Clientanwendungen, die für die Anmeldung bei lync Server 2013 verwendet werden können'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42f1135349c7caab0f8e3fe2e428a1bad59466ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="8842d-102">Angeben der Clientanwendungen, die für die Anmeldung bei lync Server 2013 verwendet werden können</span><span class="sxs-lookup"><span data-stu-id="8842d-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8842d-103">_**Letztes Änderungsdatum des Themas:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="8842d-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="8842d-104">Mit lync Server 2013 können Sie die Version der Clients angeben, die in Ihrer Umgebung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8842d-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="8842d-105">Die Verwendung von clientversionsrichtlinien kann dazu beitragen, die Kosten für die Unterstützung mehrerer Clientversionen zu senken.</span><span class="sxs-lookup"><span data-stu-id="8842d-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="8842d-106">Darüber hinaus kann die Benutzeroberfläche insgesamt verbessert werden, da die verfügbaren Features durch die frühere Version des Clients limitiert werden können, wenn frühere und spätere Versionen von Clients interagieren.</span><span class="sxs-lookup"><span data-stu-id="8842d-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="8842d-107">Es gibt drei Komponenten der Client Versionskontrolle:</span><span class="sxs-lookup"><span data-stu-id="8842d-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="8842d-108">Konfigurationseinstellungen für Clientversionen werden verwendet, um die Client Versionskontrolle entweder global oder für bestimmte Websites zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8842d-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="8842d-109">Client Versionsrichtlinien werden verwendet, um eine Reihe von Regeln Global oder einer bestimmten Website, einem Pool oder einer Gruppe von Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8842d-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="8842d-110">Clientversionsrichtlinien Regeln bilden eine clientversionsrichtlinie und werden verwendet, um die Aktionen zu definieren, die ausgeführt werden sollen, wenn Benutzer versuchen, sich mit bestimmten Clients und Clientversionen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="8842d-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8842d-111">Da anonyme Benutzer keinem Benutzer, Standort oder Dienst zugeordnet sind, unterliegen anonyme Benutzer ausschließlich globalen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="8842d-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8842d-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8842d-112">In This Section</span></span>

  - [<span data-ttu-id="8842d-113">Konfigurationseinstellungen für Client Versionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8842d-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="8842d-114">Client Versionsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8842d-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="8842d-115">Client Versionsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8842d-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8842d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8842d-116">See Also</span></span>


[<span data-ttu-id="8842d-117">Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8842d-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

