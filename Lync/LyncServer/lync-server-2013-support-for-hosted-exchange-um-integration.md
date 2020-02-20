---
title: Lync Server 2013 Unterstützung für gehostete Exchange um Integration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 714b10cfc10e101439670eda6ff3810be06b8599
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a><span data-ttu-id="99a3b-102">Unterstützung für gehostete Exchange um Integration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99a3b-102">Support for hosted Exchange UM integration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99a3b-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="99a3b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="99a3b-104">Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in Exchange Unified Messaging (um) in einer lokalen Umgebung, in der lync Server 2013 und Exchange um sowohl lokal in Ihrem Unternehmen installiert sind, als auch in mit Exchange um Hosted by a Dienstanbieter, wie im folgenden Diagramm dargestellt.</span><span class="sxs-lookup"><span data-stu-id="99a3b-104">The Lync Server 2013 ExUM Routing application supports integration with Exchange Unified Messaging (UM) in an on-premises environment, where Lync Server 2013 and Exchange UM are both installed locally within your enterprise, or in with Exchange UM hosted by a service provider, as shown in the following diagram.</span></span>

<span data-ttu-id="99a3b-105">![Lokale lync Server Exchange um-Bereitstellung](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")</span><span class="sxs-lookup"><span data-stu-id="99a3b-105">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="99a3b-106">Die folgenden Modi werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="99a3b-106">The following modes are supported:</span></span>

  - <span data-ttu-id="99a3b-107">\*\*\*\*   Der lokale Modus lync Server 2013 und Exchange um werden auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="99a3b-107">**On-premises Mode**   Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="99a3b-108">**Standortübergreifender Modus**   lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters gehostet, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="99a3b-108">**Cross-premises Mode**   Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="99a3b-109">**Gemischter Modus**   bei ihrer lync Server 2013-Bereitstellung befinden sich einige Benutzerpostfächer auf lokalen Servern, auf denen Exchange Server in Ihrem Unternehmen ausgeführt wird, sowie einige Postfächer, die in einem gehosteten Exchange-Dienst Datencenter verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="99a3b-109">**Mixed Mode**   Your Lync Server 2013 deployment has some user mailboxes homed on local servers running Microsoft Exchange Server within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="99a3b-110">Der gemischte Modus kann als Übergangslösung bei der Evaluierung und schrittweisen Migration von Benutzern zu gehosteten Exchange um oder als dauerhafte Lösung verwendet werden, wenn Sie sich dafür entscheiden, einige Benutzer Exchange um Dienste lokal zu halten, nachdem Sie andere Personen migriert haben.</span><span class="sxs-lookup"><span data-stu-id="99a3b-110">Mixed mode can be used as a transitional solution during evaluation and stepwise migration of users to hosted Exchange UM, or as a permanent solution if you opt to keep some users’ Exchange UM services on-premises after migrating others.</span></span>

    
    </div>

<span data-ttu-id="99a3b-111">Um lync Server 2013 mit gehosteten Exchange um zu integrieren, müssen Sie einen *freigegebenen SIP-Adressraum* konfigurieren (auch als *geteilte Domäne*bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="99a3b-111">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space* (also called a *split domain*).</span></span> <span data-ttu-id="99a3b-112">In dieser Konfiguration können sowohl lync Server 2013 als auch der von einem Drittanbieter gehostete Exchange um-Dienstanbieter auf denselben Adressraum für die SIP-Domäne zugreifen.</span><span class="sxs-lookup"><span data-stu-id="99a3b-112">In this configuration, both Lync Server 2013 and the third-party hosted Exchange UM service provider can access the same SIP domain address space.</span></span> <span data-ttu-id="99a3b-113">Ausführliche Informationen finden Sie unter [Hosted Exchange um Integration Architecture in lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="99a3b-113">For details, see [Hosted Exchange UM integration architecture in Lync Server 2013](lync-server-2013-hosted-exchange-um-integration-architecture.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

