---
title: 'Lync Server 2013: Konfigurieren der Reaktionsgruppe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda955072f42989e6323ea6422d8b25736cf8c32
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="02bf1-102">Konfigurieren der Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02bf1-103">_**Letztes Änderungsstand des Themas:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="02bf1-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="02bf1-104">Reaktionsgruppe ist eine Enterprise-VoIP-Funktion, mit der eingehende Anrufe an Personengruppen weitergeleitet und in die Warteschlange gestellt werden, die als *Agents*bezeichnet werden, wie beispielsweise ein Helpdesk oder ein Kundendienst Desk.</span><span class="sxs-lookup"><span data-stu-id="02bf1-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="02bf1-105">Die erforderlichen Komponenten für Reaktionsgruppen werden bei der Bereitstellung von Enterprise-VoIP automatisch auf dem Front-End-Server oder Standard Edition-Server installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="02bf1-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="02bf1-106">Zur Bereitstellung der Reaktionsgruppenfunktion für Benutzer müssen Sie Agentgruppen, dann Warteschleifen und anschließend Workflows konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="02bf1-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="02bf1-107">Darüber hinaus kann ein Reaktionsgruppen Administrator die Konfiguration eines vorhandenen Workflows an einen Reaktionsgruppen Manager delegieren, der dann den Workflow und die zugehörigen Agentgruppen und Warteschlangen ändern und neu konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="02bf1-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="02bf1-108">Dieser Abschnitt führt Sie durch die Konfiguration von lync Server 2013 Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="02bf1-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="02bf1-109">Es wird davon ausgegangen, dass Sie die Planungsabschnitte im Zusammenhang mit der Reaktionsgruppe bereits gelesen haben und ein Enterprise Edition-Server oder ein Standard Edition-Server mit Enterprise-VoIP bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="02bf1-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="02bf1-110">Ausführliche Informationen zum Erstellen einer Reaktionsgruppe mithilfe von lync Server-Verwaltungsshell, einschließlich eines Beispielskripts, finden Sie unter "Erstellen der ersten Reaktionsgruppe mit lync Server-Verwaltungsshell <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>" unter.</span><span class="sxs-lookup"><span data-stu-id="02bf1-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02bf1-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="02bf1-111">In This Section</span></span>

  - [<span data-ttu-id="02bf1-112">Berechtigungen und Voraussetzungen für die Reaktionsgruppen Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="02bf1-113">Bereitstellungsprozess für die Reaktionsgruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="02bf1-114">Übersicht über Szenarien zur Erstellung von Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="02bf1-115">Erstellen von Gruppen für Reaktionsgruppen-Agents lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="02bf1-116">Erstellen von Warteschlangen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="02bf1-117">Optional Definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="02bf1-118">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="02bf1-119">Erstellen von Workflows für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="02bf1-120">Optional Überprüfen der Bereitstellung von Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02bf1-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02bf1-121">See Also</span></span>


[<span data-ttu-id="02bf1-122">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02bf1-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

