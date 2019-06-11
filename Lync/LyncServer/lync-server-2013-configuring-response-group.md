---
title: 'Lync Server 2013: Konfigurieren von Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4d12d1ee21cfa5e480dea52a0de9f89b250715c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="78d80-102">Konfigurieren von Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78d80-103">_**Letztes Änderungsdatum des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="78d80-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="78d80-104">Reaktionsgruppe ist ein Enterprise-VoIP-Feature, mit dem eingehende Anrufe an Personengruppen, so genannte *Agenten*, weitergeleitet und in die Warteschlange gestellt werden, beispielsweise ein Helpdesk oder ein Kundendienst Desk.</span><span class="sxs-lookup"><span data-stu-id="78d80-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="78d80-105">Die Komponenten, die von der Reaktionsgruppe benötigt werden, werden beim Bereitstellen von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="78d80-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="78d80-106">Um die Reaktionsgruppe für Benutzer verfügbar zu machen, müssen Sie Agentengruppen, dann Warteschlangen und dann Workflows konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="78d80-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="78d80-107">Darüber hinaus kann ein Antwortgruppen Administrator die Konfiguration eines vorhandenen Workflows an einen Reaktionsgruppen-Manager delegieren, der dann den Workflow und die zugehörigen Agentengruppen und-Warteschlangen ändern und neu konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="78d80-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="78d80-108">Dieser Abschnitt führt Sie durch die Konfiguration der lync Server 2013-Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="78d80-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="78d80-109">Es wird davon ausgegangen, dass Sie die Planungsabschnitte in Bezug auf die Reaktionsgruppe bereits gelesen haben und einen Enterprise Edition-Server oder einen Standard Edition-Server mit Enterprise-VoIP bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="78d80-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="78d80-110">Details zum Erstellen einer Reaktionsgruppe mithilfe der lync Server-Verwaltungsshell, einschließlich eines Beispielskripts, finden Sie unter "Erstellen Ihrer ersten Reaktionsgruppe mithilfe der lync Server-Verwaltungsshell <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>" unter.</span><span class="sxs-lookup"><span data-stu-id="78d80-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="78d80-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="78d80-111">In This Section</span></span>

  - [<span data-ttu-id="78d80-112">Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="78d80-113">Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="78d80-114">Übersicht über Szenarios zur Erstellung von Workflows in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="78d80-115">Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="78d80-116">Erstellen von Warteschleifen für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="78d80-117">Optional Definieren der Geschäftszeiten der Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="78d80-118">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="78d80-119">Erstellen von Workflows für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="78d80-120">Optional Überprüfen der Bereitstellung von Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="78d80-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78d80-121">See Also</span></span>


[<span data-ttu-id="78d80-122">Planen der Anruf Verwaltungsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="78d80-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

