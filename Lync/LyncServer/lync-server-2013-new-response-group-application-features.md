---
title: 'Lync Server 2013: neue Reaktionsgruppenanwendung-Features'
description: 'Lync Server 2013: neue Reaktionsgruppenanwendung-Features.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 191d3867758da427ade3470e78abfd417f6f00de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541961"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="aa686-103">Neue Reaktionsgruppenanwendung Features in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa686-103">New Response Group application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa686-104">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="aa686-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="aa686-105">Mithilfe der Reaktionsgruppenanwendung können Sie eingehende Anrufe an benannte Personen mit speziellen Aufgabenbereichen weiterleiten – z. B. an den Kundendienst, ein internes Helpdesk oder die allgemeine Telefonunterstützung für eine Abteilung – oder den Anruf in der Warteschleife platzieren.</span><span class="sxs-lookup"><span data-stu-id="aa686-105">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="aa686-106">Die folgenden Reaktionsgruppenanwendung Features sind in lync Server 2013 neu:</span><span class="sxs-lookup"><span data-stu-id="aa686-106">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="aa686-107">**Manager-Rolle**</span><span class="sxs-lookup"><span data-stu-id="aa686-107">**Manager role**</span></span>
    
    <span data-ttu-id="aa686-108">Lync Server 2013 stellt eine neue Rolle für Reaktionsgruppen-Manager vor.</span><span class="sxs-lookup"><span data-stu-id="aa686-108">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="aa686-109">Nun gibt es zwei Verwaltungsrollen für Reaktionsgruppen: Reaktionsgruppen-Manager und Reaktionsgruppen Administrator.</span><span class="sxs-lookup"><span data-stu-id="aa686-109">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="aa686-110">Während Reaktionsgruppen Administratoren immer noch ein beliebiges Element für eine beliebige Reaktionsgruppe konfigurieren können, können Manager nur bestimmte Elemente konfigurieren, nur für Ihre eigenen Reaktionsgruppen.</span><span class="sxs-lookup"><span data-stu-id="aa686-110">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="aa686-111">Dies stellt – insbesondere mit Blick auf umfangreiche Bereitstellungsszenarien – eine Verbesserung im Verwaltungsmodell bezüglich der Skalierbarkeit von Reaktionsgruppen dar.</span><span class="sxs-lookup"><span data-stu-id="aa686-111">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="aa686-112">**Hochverfügbarkeit**</span><span class="sxs-lookup"><span data-stu-id="aa686-112">**High availability**</span></span>
    
    <span data-ttu-id="aa686-113">Die Unterstützung für hohe Verfügbarkeit für den Reaktionsgruppenanwendung in Form von SQL Server Spiegelung wird als Teil der Gesamtkonfiguration und der Bereitstellung der hohen Verfügbarkeit für lync Server 2013 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa686-113">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="aa686-114">Wenn Sie Ihre Konfiguration auf hohe Verfügbarkeit auslegen und es zu einer Unterbrechung der Verbindung zum primären Back-End-Server kommt, ist die Reaktionsgruppenfunktion davon nicht beeinträchtigt, weil auf einen gespiegelten Back-End-Server zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="aa686-114">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="aa686-115">Unterstützung für SQL Server Spiegelung für das Reaktionsgruppenanwendung kann nicht einzeln aktiviert oder konfiguriert werden, außerhalb der gesamten lync Server 2013 Konfiguration für hohe Verfügbarkeit.</span><span class="sxs-lookup"><span data-stu-id="aa686-115">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="aa686-116">**Notfallwiederherstellung**</span><span class="sxs-lookup"><span data-stu-id="aa686-116">**Disaster recovery**</span></span>
    
    <span data-ttu-id="aa686-117">Die Unterstützung für die Notfallwiederherstellung für den Reaktionsgruppenanwendung wird als Teil der Konfiguration und Bereitstellung der gekoppelten Front-End-Pools aktiviert, die Teil der gesamten lync Server 2013 Notfall Wiederherstellungskonfiguration sind.</span><span class="sxs-lookup"><span data-stu-id="aa686-117">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="aa686-118">Darüber hinaus unterstützen die Cmdlets der Reaktionsgruppe den Failoverprozess zum Sicherungspool sowie den Failbackprozess zum primären oder zu einem neuen Pool.</span><span class="sxs-lookup"><span data-stu-id="aa686-118">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="aa686-119">Bei einem Ausfall des primären Pools kann für die Reaktionsgruppen ein Failover zum Sicherungspool durchgeführt werden, und nach der Wiederherstellung kann ein Failback zum primären oder zu einem neuen Pool durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="aa686-119">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aa686-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa686-120">See Also</span></span>


[<span data-ttu-id="aa686-121">Planen von Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa686-121">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

