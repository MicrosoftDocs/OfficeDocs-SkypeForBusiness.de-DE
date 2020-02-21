---
title: 'Lync Server 2013: Verwalten von Reaktionsgruppen-Agentgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 015f2e6b8692dd3ea2ea47dda0510f72202c1ebf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a><span data-ttu-id="d6da1-102">Verwalten von Reaktionsgruppen-Agentgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6da1-102">Managing Response Group agent groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6da1-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d6da1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d6da1-p101">Eine Agentgruppe besteht aus einer Gruppe von Personen, die für die Entgegennahme von Reaktionsgruppenanrufen zuständig sind. Beim Erstellen einer Agentgruppe wählen Sie die Agents aus, die der Gruppe zugewiesen werden. Sie geben an, welche zusätzlichen Gruppeneinstellungen verwendet werden sollen und ob sich ein Agent bei der Gruppe an- und abmelden muss.</span><span class="sxs-lookup"><span data-stu-id="d6da1-p101">An agent group consists of a group of people who are designated to answer calls to a response group. When you create an agent group, you select the agents who are assigned to the group and specify additional group settings, such as the routing method and whether an agent can sign in to and out of the group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6da1-106">Benutzer müssen für Enterprise-VoIP aktiviert sein, bevor Sie Sie zu Agentgruppen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d6da1-106">Users must be enabled for Enterprise Voice before you can add them to agent groups.</span></span> <span data-ttu-id="d6da1-107">Ausführliche Informationen zum Aktivieren eines Benutzers für Enterprise-VoIP finden Sie unter <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d6da1-107">For details about how to enable a user for Enterprise Voice, see <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d6da1-p103">Nur lokale Benutzer können Agents sein. Wenn ein Agent von einer lokalen zu einer Onlinebereitstellung verschoben wird, werden Reaktionsgruppenanrufe nicht an diesen Agent weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d6da1-p103">Only on-premises users can be agents. If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<span data-ttu-id="d6da1-110">Ein Agent, der sich bei der Gruppe an-und abmelden muss, die sich von der Anmeldung an oder von lync Server unterscheidet, wird als *formaler Agent*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d6da1-110">An agent who must sign in and out of the group, which is different from signing in or out of Lync Server, is called a *formal agent*.</span></span> <span data-ttu-id="d6da1-111">Formelle Agents müssen sich bei der Gruppe anmelden, um an die Gruppe weitergeleitete Anrufe empfangen zu können.</span><span class="sxs-lookup"><span data-stu-id="d6da1-111">Formal agents must be signed in to the group before they can receive calls that are routed to the group.</span></span> <span data-ttu-id="d6da1-112">Dies kann für Agents nützlich sein, die Anrufe der Gruppe nur zeitweise annehmen.</span><span class="sxs-lookup"><span data-stu-id="d6da1-112">This can be useful for agents who answer calls from the group on a part-time basis.</span></span> <span data-ttu-id="d6da1-113">Formelle Agents melden sich bei ihren Gruppen an-und abmelden, indem Sie in lync 2013 auf ein Menüelement klicken, um den Windows Internet Explorer-Internet Browser zu öffnen und eine Webseiten Konsole anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d6da1-113">Formal agents sign in and out of their groups by clicking a menu item in Lync 2013 to open the Windows Internet Explorer Internet browser and display a webpage console.</span></span>

<span data-ttu-id="d6da1-114">Ein Agent, der sich nicht an-oder abmeldet, wird als *formloser Agent*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d6da1-114">An agent who does not sign in or out of the group is called an *informal agent*.</span></span> <span data-ttu-id="d6da1-115">Formlose Agents werden bei der Anmeldung bei lync Server automatisch bei der Gruppe angemeldet und können sich nicht von der Gruppe abmelden.</span><span class="sxs-lookup"><span data-stu-id="d6da1-115">Informal agents are automatically signed in to the group when they sign in to Lync Server, and they cannot sign out of the group.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d6da1-p106">Wenn Sie Benutzer als Reaktionsgruppenagents zuweisen, weisen Sie diese darauf hin, dass sie bei aktiviertem Datenschutzmodus nach "RGS-Anwesenheitsmonitor"-Kontakten suchen und sie ihrer Kontaktliste hinzufügen müssen. Agents, deren Datenschutzmodus aktiviert ist, die jedoch "RGS-Anwesenheitsmonitor" nicht in ihre Kontaktliste aufgenommen haben, können keine Anrufe bei der Reaktionsgruppe annehmen. Agents, deren Datenschutzmodus nicht aktiviert ist, sind davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="d6da1-p106">When you assign users as response group agents, inform them that, if they have Privacy mode enabled, they need to search for "RGS Presence Watcher" contacts and add them to their Contacts list. Agents who have Privacy mode enabled, but who do not have "RGS Presence Watcher" in their Contacts list, cannot receive calls to the response group. Agents who do not have Privacy mode enabled are not affected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d6da1-119">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d6da1-119">In This Section</span></span>

  - [<span data-ttu-id="d6da1-120">Erstellen oder Ändern einer Agentengruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6da1-120">Create or modify an agent group in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-agent-group.md)

  - [<span data-ttu-id="d6da1-121">Löschen einer Agentengruppe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6da1-121">Delete an agent group in Lync Server 2013</span></span>](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

