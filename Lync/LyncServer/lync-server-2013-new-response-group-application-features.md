---
title: 'Lync Server 2013: Neue Funktionen der Reaktionsgruppenanwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33dd01cf7516f950e58dbc90ee09b06901bccf74
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826150"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="13f6a-102">Neue Funktionen der Reaktionsgruppenanwendung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13f6a-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13f6a-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="13f6a-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="13f6a-104">Mit der reaktionsgruppenanwendung können Sie eingehende Anrufe an bestimmte Personen zu speziellen Zwecken wie Kundendienst, internem Helpdesk oder allgemeinen Telefonsupport für eine Abteilung weiterleiten und in die Warteschlange einreihen.</span><span class="sxs-lookup"><span data-stu-id="13f6a-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="13f6a-105">Die folgenden Features der reaktionsgruppenanwendung sind in lync Server 2013 neu:</span><span class="sxs-lookup"><span data-stu-id="13f6a-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="13f6a-106">**Manager-Rolle**</span><span class="sxs-lookup"><span data-stu-id="13f6a-106">**Manager role**</span></span>
    
    <span data-ttu-id="13f6a-107">Lync Server 2013 führt eine neue Rolle des Antwortgruppen-Managers ein.</span><span class="sxs-lookup"><span data-stu-id="13f6a-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="13f6a-108">Nun gibt es zwei Verwaltungsrollen für Antwortgruppen: Antwortgruppen-Manager und Antwortgruppen Administrator.</span><span class="sxs-lookup"><span data-stu-id="13f6a-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="13f6a-109">Während Reaktionsgruppen Administratoren weiterhin ein beliebiges Element für eine Reaktionsgruppe konfigurieren können, können Manager nur bestimmte Elemente nur für Antwortgruppen konfigurieren, die Sie besitzen.</span><span class="sxs-lookup"><span data-stu-id="13f6a-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="13f6a-110">Diese Verbesserungen im Verwaltungsmodell nutzen die Skalierbarkeit der Reaktionsgruppe, insbesondere bei umfangreichen Bereitstellungsszenarien.</span><span class="sxs-lookup"><span data-stu-id="13f6a-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="13f6a-111">**Hohe Verfügbarkeit**</span><span class="sxs-lookup"><span data-stu-id="13f6a-111">**High availability**</span></span>
    
    <span data-ttu-id="13f6a-112">Die Unterstützung für die Reaktionsgruppe in Form einer SQL Server-Spiegelung ist als Teil der allgemeinen Konfiguration und Bereitstellung von Hochverfügbarkeits Funktionen für lync Server 2013 aktiviert.</span><span class="sxs-lookup"><span data-stu-id="13f6a-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="13f6a-113">Wenn Sie für eine höhere Verfügbarkeit konfigurieren und die Verbindung mit dem primären Back-End-Server verlieren, ist die Funktion der Reaktionsgruppe nicht von der Nutzung des gespiegelten Back-End-Servers betroffen.</span><span class="sxs-lookup"><span data-stu-id="13f6a-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="13f6a-114">Die Unterstützung für die SQL Server-Spiegelung für die reaktionsgruppenanwendung kann nicht einzeln aktiviert oder außerhalb der gesamten lync Server 2013-Konfiguration mit höherer Verfügbarkeit konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="13f6a-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="13f6a-115">**Notfallwiederherstellung**</span><span class="sxs-lookup"><span data-stu-id="13f6a-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="13f6a-116">Die Unterstützung für die Disaster Recovery für die reaktionsgruppenanwendung wird im Rahmen der Konfiguration und Bereitstellung der gekoppelten Front-End-Pools aktiviert, die Teil der gesamten lync Server 2013-Konfiguration für die Disaster Recovery sind.</span><span class="sxs-lookup"><span data-stu-id="13f6a-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="13f6a-117">Darüber hinaus unterstützen Cmdlets für das Importieren und Exportieren von Reaktionsgruppen den Failoverprozess für den Sicherungspool und den Failback-Prozess im primären Pool oder in einem neuen Pool.</span><span class="sxs-lookup"><span data-stu-id="13f6a-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="13f6a-118">Wenn ein Ausfall im primären Pool auftritt, können Reaktionsgruppen für den Sicherungspool Failover durchgeführt werden, und bei einem Ausfall ist der primäre Pool oder ein neuer Pool wieder fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="13f6a-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13f6a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13f6a-119">See Also</span></span>


[<span data-ttu-id="13f6a-120">Planen von Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13f6a-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

