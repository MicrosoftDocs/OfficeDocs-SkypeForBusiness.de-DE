---
title: 'Lync Server 2013: Unterstützung für die Integration gehosteter Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56ba107c9a782acb15ccd8d57f82cf567f2b75e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847702"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="be526-102">Unterstützung für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be526-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be526-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="be526-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="be526-104">Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in Exchange Unified Messaging (um) in einer lokalen Umgebung, in der lync Server 2013 und Exchange um sowohl lokal innerhalb Ihres Unternehmens installiert sind, als auch in Exchange um von einer Dienstanbieter, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="be526-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="be526-105">![Lokale lync Server Exchange um-Bereitstellung] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")</span><span class="sxs-lookup"><span data-stu-id="be526-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="be526-106">Die folgenden Modi werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="be526-106">The following modes are supported:</span></span>

  - <span data-ttu-id="be526-107">**Der lokale Modus**   lync Server 2013 und Exchange um werden auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="be526-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="be526-108">\*\*\*\*   Standortübergreifender Modus lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters wie einem Microsoft Exchange Online-Rechenzentrum gehostet.</span><span class="sxs-lookup"><span data-stu-id="be526-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="be526-109">**Gemischter Modus**   ihre lync Server 2013-Bereitstellung enthält einige Benutzerpostfächer, die sich auf lokalen Servern mit Microsoft Exchange Server innerhalb Ihres Unternehmens und einigen Postfächern befinden, die in einem gehosteten Exchange-Dienst-Rechenzentrum verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="be526-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="be526-110">Der gemischte Modus kann während der Evaluierung und schrittweisen Migration von Benutzern zu Hosted Exchange um als Übergangslösung verwendet werden, oder als dauerhafte Lösung, wenn Sie sich entscheiden, die Exchange um-Dienste einiger Benutzer nach der Migration anderer Personen lokal zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="be526-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="be526-111">Zum Integrieren von lync Server 2013 in gehostete Exchange um müssen Sie einen *freigegebenen SIP-Adressraum* (auch als geteilte *Domäne*bezeichnet) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="be526-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="be526-112">In dieser Konfiguration können sowohl lync Server 2013 als auch der von einem Drittanbieter gehostete Exchange um-Dienstanbieter auf denselben SIP-Domänen Adressraum zugreifen.</span><span class="sxs-lookup"><span data-stu-id="be526-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="be526-113">Ausführliche Informationen finden Sie unter [Hosted Exchange um-Integrationsarchitektur in lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="be526-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

