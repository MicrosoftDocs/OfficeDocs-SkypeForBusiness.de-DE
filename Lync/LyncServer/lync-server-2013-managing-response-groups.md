---
title: 'Lync Server 2013: Verwalten von Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00736a94cc383a362a3f952519acc603c5beefab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507192"
---
# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="12e4d-102">Verwalten von Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e4d-102">Managing response groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12e4d-103">_**Letztes Änderungsstand des Themas:** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="12e4d-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="12e4d-104">Reaktionsgruppen sind eine Anrufverwaltungsfunktion, mit der Sie Anrufe für einen bestimmten Bereich (z. B. ein Helpdesk) in der Warteschleife platzieren und anschließend an eine zuständige Personengruppe namens *Agents* weiterleiten können.</span><span class="sxs-lookup"><span data-stu-id="12e4d-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="12e4d-105">Um die Reaktionsgruppen zu verwalten, konfigurieren Sie Agentgruppen, Warteschlangen und Workflows. Diese legen fest, wie ein Anruf vom Zeitpunkt der Tätigung bis hin zur Beantwortung durch einen Agent verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="12e4d-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="12e4d-106">Wenn Sie mehr als 300 Workflows in einem einzelnen Pool in ihrer Reaktionsgruppen Bereitstellung haben, ist es besser, lync Server-Verwaltungsshell-Cmdlets zum Erstellen der Workflows zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="12e4d-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="12e4d-107">Wenn Sie das Reaktionsgruppen-Konfigurationstool zum Erstellen von Workflows für einen Pool mit mehr als 300 Workflows verwenden, wird für das Laden der Webseite sehr viel Zeit benötigt.</span><span class="sxs-lookup"><span data-stu-id="12e4d-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="12e4d-108">Die Anzahl der Agents, die indirekt Workflows über die Warteschlangen zugeordnet sind, wirkt sich auch proportional auf das Laden von Seiten aus.</span><span class="sxs-lookup"><span data-stu-id="12e4d-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="12e4d-109">Die Themen in diesem Abschnitt bieten schrittweise Anleitungen für Aufgaben, die Sie ausführen können, um die Reaktionsgruppenanwendung in Ihrer Bereitstellung anzupassen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="12e4d-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="12e4d-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="12e4d-110">In This Section</span></span>

  - [<span data-ttu-id="12e4d-111">Verwalten von Reaktionsgruppen-Agentgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e4d-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="12e4d-112">Verwalten von Warteschlangen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e4d-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="12e4d-113">Verwalten von Workflows für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e4d-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="12e4d-114">Verwalten von Reaktionsgruppeneinstellungen auf Anwendungsebene in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e4d-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="12e4d-115">Verschieben von Reaktionsgruppen in einen neuen Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12e4d-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="12e4d-116">Verwalten von Reaktionsgruppen in lync Server 2013 während eines Notfalls</span><span class="sxs-lookup"><span data-stu-id="12e4d-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

