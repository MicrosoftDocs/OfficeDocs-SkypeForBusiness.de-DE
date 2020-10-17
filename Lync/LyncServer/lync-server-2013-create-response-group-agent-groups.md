---
title: 'Lync Server 2013: Gruppen von Reaktionsgruppen-Agents erstellen'
description: 'Lync Server 2013: Erstellen von Gruppen für Reaktionsgruppen-Agents.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9420ee5f6fbd4b995c8542b848ef30f53e46fc4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548691"
---
# <a name="create-response-group-agent-groups-lync-server-2013"></a><span data-ttu-id="ce7a5-103">Erstellen von Gruppen für Reaktionsgruppen-Agents lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7a5-103">Create Response Group agent groups Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce7a5-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ce7a5-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ce7a5-105">Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Außerdem geben Sie zusätzliche Gruppeneinstellungen (beispielsweise die Routingmethode) an und legen fest, ob sich ein Agent bei der Gruppe an- und abmelden muss.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-105">When you create an agent group, you select the agents that are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<span data-ttu-id="ce7a5-106">Ein Agent, der sich bei der Gruppe an-und abmelden muss, die sich von der Anmeldung an oder von lync Server unterscheidet, wird als *formaler Agent*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-106">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="ce7a5-107">Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-107">Formal agents must be signed in to the group before they can receive calls routed to the group.</span></span> <span data-ttu-id="ce7a5-108">Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-108">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="ce7a5-109">Formelle Agents melden sich bei ihren Gruppen an-und abmelden, indem Sie in lync 2013 auf ein Menüelement klicken, um den Windows Internet Explorer-Internet Browser zu öffnen und eine Webseiten Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-109">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="ce7a5-110">Ein Agent, der sich nicht an-oder abmeldet, wird als *formloser Agent*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-110">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="ce7a5-111">Formlose Agents werden bei der Anmeldung bei lync Server automatisch bei der Gruppe angemeldet und können sich nicht von der Gruppe abmelden.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-111">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce7a5-p103">Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ce7a5-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ce7a5-114">In This Section</span></span>

[<span data-ttu-id="ce7a5-115">Erstellen oder Ändern einer Agentengruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce7a5-115">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

