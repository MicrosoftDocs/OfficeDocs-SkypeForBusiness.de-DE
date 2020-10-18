---
title: 'Lync Server 2013: Komponenten und Topologien für lokales Unified Messaging'
description: 'Lync Server 2013: Komponenten und Topologien für lokale Unified Messaging.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for on-premises Unified Messaging
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48183619
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8fe2ca16ec9fbd39e9245fd366e1f7046dd16d42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576821"
---
# <a name="components-and-topologies-for-on-premises-unified-messaging-in-lync-server-2013"></a><span data-ttu-id="10fd5-103">Komponenten und Topologien für lokale Unified Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10fd5-103">Components and topologies for on-premises Unified Messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10fd5-104">_**Letztes Änderungsstand des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="10fd5-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="10fd5-105">In diesem Thema werden die Microsoft Exchange Server 2013 Komponenten beschrieben, die zum Bereitstellen von Exchange Unified Messaging (um) Funktionen für lync Server 2013 Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="10fd5-105">This topic describes the Microsoft Exchange Server 2013 components required to provide Exchange Unified Messaging (UM) features to Lync Server 2013 deployment.</span></span> <span data-ttu-id="10fd5-106">Außerdem werden die unterstützten Topologien für die lokale Exchange um Integration beschrieben.</span><span class="sxs-lookup"><span data-stu-id="10fd5-106">It also describes the supported topologies for on-premises Exchange UM integration.</span></span>

<div>

## <a name="exchange-server-components"></a><span data-ttu-id="10fd5-107">Exchange Server-Komponenten</span><span class="sxs-lookup"><span data-stu-id="10fd5-107">Exchange Server Components</span></span>

<span data-ttu-id="10fd5-108">Um die in den [Features integrierter Unified Messaging und lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) für Enterprise-VoIP-Benutzer in Ihrer Organisation beschriebenen Exchange um Features und Dienste bereitzustellen, müssen Sie einen Microsoft Exchange Postfachserver und Client Zugriffsserver bereitstellen, der Benutzerpostfächer hostet und einen einzelnen Speicherort für e-Mail und Voicemail bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="10fd5-108">To provide the Exchange UM features and services described in [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md) to Enterprise Voice users in your organization, you must deploy an Microsoft Exchange Mailbox server and Client Access server, which hosts user mailboxes and provides a single storage location for email and voice mail.</span></span> <span data-ttu-id="10fd5-109">Exchange um wird auf Exchange-Postfach-und Client Zugriffsservern als Dienst ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="10fd5-109">Exchange UM runs as a service on Exchange Mailbox and Client Access servers.</span></span>

<span data-ttu-id="10fd5-110">Ausführliche Informationen zu Exchange um Komponenten in Microsoft Exchange Server 2007 und Microsoft Exchange Server 2010 finden Sie unter [Deploying on-premises Exchange um to bereitstellen lync Server 2013 Voice Mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="10fd5-110">For details about Exchange UM components in Microsoft Exchange Server 2007 and Microsoft Exchange Server 2010, see [Deploying on-premises Exchange UM to provide Lync Server 2013 voice mail](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="10fd5-111">Unterstützte Topologien</span><span class="sxs-lookup"><span data-stu-id="10fd5-111">Supported Topologies</span></span>

<span data-ttu-id="10fd5-112">Sie können lync Server 2013 und Exchange Unified Messaging (um) in derselben Gesamtstruktur oder in mehreren Gesamtstrukturen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="10fd5-112">You can deploy Lync Server 2013 and Exchange Unified Messaging (UM) in the same forest or multiple forests.</span></span> <span data-ttu-id="10fd5-113">Wenn die Bereitstellung mehrere Gesamtstrukturen umfasst, müssen Sie die Exchange-Integrationsschritte für jede Exchange um Gesamtstruktur ausführen.</span><span class="sxs-lookup"><span data-stu-id="10fd5-113">If the deployment spans multiple forests, you must perform the Exchange integration steps for each Exchange UM forest.</span></span> <span data-ttu-id="10fd5-114">Darüber hinaus müssen Sie jede Microsoft Exchange Gesamtstruktur so konfigurieren, dass Sie der lync Server 2013-Gesamtstruktur und der lync Server 2013-Gesamtstruktur vertraut, um jeder Exchange um Gesamtstruktur zu vertrauen.</span><span class="sxs-lookup"><span data-stu-id="10fd5-114">Furthermore, you must configure each Microsoft Exchange forest to trust the Lync Server 2013 forest and the Lync Server 2013 forest to trust each Exchange UM forest.</span></span> <span data-ttu-id="10fd5-115">Zusätzlich zu dieser Gesamtstrukturvertrauensstellung müssen die Exchange um Einstellungen für alle Benutzer für die Benutzerobjekte in der lync Server 2013 Gesamtstruktur festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="10fd5-115">In addition to this forest trust, the Exchange UM settings for all users must be set on the user objects in the Lync Server 2013 forest.</span></span>

<span data-ttu-id="10fd5-116">Lync Server 2013 unterstützt die folgenden Topologien für die Exchange um Integration:</span><span class="sxs-lookup"><span data-stu-id="10fd5-116">Lync Server 2013 supports the following topologies for Exchange UM integration:</span></span>

  - <span data-ttu-id="10fd5-117">Einzelne Gesamtstruktur</span><span class="sxs-lookup"><span data-stu-id="10fd5-117">Single forest</span></span>

  - <span data-ttu-id="10fd5-118">Einzelne Domäne (also eine einzelne Gesamtstruktur mit einer einzigen Domäne).</span><span class="sxs-lookup"><span data-stu-id="10fd5-118">Single domain (that is, a single forest with a single domain).</span></span> <span data-ttu-id="10fd5-119">Lync Server 2013, Microsoft Exchange und Benutzer befinden sich alle in derselben Domäne.</span><span class="sxs-lookup"><span data-stu-id="10fd5-119">Lync Server 2013, Microsoft Exchange, and users all reside in the same domain.</span></span>

  - <span data-ttu-id="10fd5-120">Mehrere Domänen (also eine Stammdomäne mit einer oder mehreren untergeordneten Domänen).</span><span class="sxs-lookup"><span data-stu-id="10fd5-120">Multiple domain (that is, a root domain with one or more child domains).</span></span> <span data-ttu-id="10fd5-121">Lync Server 2013 und Microsoft Exchange Server werden in verschiedenen Domänen aus der Domäne bereitgestellt, in der Sie Benutzer erstellen.</span><span class="sxs-lookup"><span data-stu-id="10fd5-121">Lync Server 2013, and Microsoft Exchange servers are deployed in different domains from the domain where you create users.</span></span> <span data-ttu-id="10fd5-122">Exchange um Server können in verschiedenen Domänen aus dem lync Server 2013-Pool bereitgestellt werden, den Sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="10fd5-122">Exchange UM servers can be deployed in different domains from the Lync Server 2013 pool they support.</span></span>

  - <span data-ttu-id="10fd5-123">Mehrere Gesamtstrukturen (also Ressourcengesamtstruktur).</span><span class="sxs-lookup"><span data-stu-id="10fd5-123">Multiple forest (that is, resource forest).</span></span> <span data-ttu-id="10fd5-124">Lync Server 2013 wird in einer einzelnen Gesamtstruktur bereitgestellt, und die Benutzer werden dann über mehrere Gesamtstrukturen verteilt.</span><span class="sxs-lookup"><span data-stu-id="10fd5-124">Lync Server 2013 is deployed in a single forest, and then users are distributed across multiple forests.</span></span> <span data-ttu-id="10fd5-125">Die Exchange um Attribute der Benutzer müssen in die lync Server 2013 Gesamtstruktur repliziert werden.</span><span class="sxs-lookup"><span data-stu-id="10fd5-125">The users’ Exchange UM attributes must be replicated over to the Lync Server 2013 forest.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="10fd5-126">Exchange kann in mehreren Gesamtstrukturen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="10fd5-126">Exchange can be deployed in multiple forests.</span></span> <span data-ttu-id="10fd5-127">Jede Exchange-Organisation kann Ihren Benutzern Exchange um bereitstellen, oder Exchange um können in derselben Gesamtstruktur wie lync Server 2013 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="10fd5-127">Each Exchange organization can provide Exchange UM to its users, or Exchange UM can be deployed in the same forest as Lync Server 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

