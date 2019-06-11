---
title: 'Lync Server 2013: Erstellen von Workflows für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba7d989d1733645c7055fb64d6b790212e15e16
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="b740b-102">Erstellen von Workflows für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b740b-102">Create Response Group workflows in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b740b-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b740b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b740b-p101">Ein Workflow definiert, wie mit einem Anruf ab dem Läuten des Telefons bis zur Annahme des Anrufs verfahren wird. Der Workflow gibt die Warteschleife zum Halten des Anrufs an und legt die Routingmethode für Sammelanschlüsse oder die Fragen und Antworten für interaktive Reaktionsgruppen fest. Ein Workflow definiert außerdem Einstellungen wie die Willkommensnachricht, Wartemusik, Geschäftszeiten und Feiertage.</span><span class="sxs-lookup"><span data-stu-id="b740b-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="b740b-107">Sie verwenden das Reaktionsgruppen-Konfigurations Tool zum Erstellen von Workflows.</span><span class="sxs-lookup"><span data-stu-id="b740b-107">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="b740b-108">Sie können auf der Seite Reaktionsgruppe der lync Server-Systemsteuerung auf das Tool für die Reaktionsgruppen Konfiguration zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b740b-108">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b740b-109">Vor dem Erstellen eines Workflows müssen Sie zuerst Agent-Gruppen und Warteschleifen erstellen, die vom Workflow verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b740b-109">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b740b-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b740b-110">In This Section</span></span>

  - [<span data-ttu-id="b740b-111">Erstellen oder Ändern eines Sammel Ansuchen-Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b740b-111">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="b740b-112">Entwerfen von Anrufflüssen für interaktive Sprachantwort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b740b-112">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="b740b-113">Erstellen oder Ändern eines interaktiven Workflows in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b740b-113">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="b740b-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b740b-114">Related Sections</span></span>

  - [<span data-ttu-id="b740b-115">Erstellen von Agent-Gruppen für Reaktionsgruppen Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b740b-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="b740b-116">Erstellen von Warteschleifen für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b740b-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

