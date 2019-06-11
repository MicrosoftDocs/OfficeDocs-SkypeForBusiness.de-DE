---
title: 'Lync Server 2013: Übersicht über Szenarios zur Erstellung von Workflows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc785392c50ea0ea1babe79ca5d30b455844ecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a><span data-ttu-id="e1c65-102">Übersicht über Szenarios zur Erstellung von Workflows in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1c65-102">Overview of workflow creation scenarios in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1c65-103">_**Letztes Änderungsdatum des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="e1c65-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="e1c65-104">Beim Erstellen von Workflows stehen zwei mögliche Szenarien zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e1c65-104">When you create workflows, there are two possible scenarios:</span></span>

  - <span data-ttu-id="e1c65-105">**Der Administrator erstellt und konfiguriert den Workflow**: Das Mitglied der Rolle „CsResponseGroupAdministrator“ (oder einer gleichwertigen Rolle) erstellt und aktiviert den Workflow und alle Elemente im Workflow, z. B. die Agentgruppen, Warteschleifen, Feiertage und Geschäftszeiten, Wartemusik usw.</span><span class="sxs-lookup"><span data-stu-id="e1c65-105">**The Administrator creates and configures the workflow** — The CsResponseGroupAdministrator role member (or equivalent) creates and activates the workflow and all elements in the workflow, such as the agent groups, queues, holiday and business hours, music on hold, and so on.</span></span>

  - <span data-ttu-id="e1c65-p101">**Der Administrator erstellt den Workflow und der Manager konfiguriert die Optionen**: Das Mitglied der Rolle „CsResponseGroupAdministrator“ (oder einer gleichwertigen Rolle) definiert den primären SIP-URI und den Anzeigenamen, weist Mitglieder der Rolle „CsResponseGroupManager“ zu, wählt eine Warteschleife aus und aktiviert den Workflow. Das CsResponseGroupManager-Mitglied kann sich dann anmelden und die Konfiguration des Workflows bearbeiten, indem es Agentgruppen erstellt und die Gruppe ebenfalls der Warteschleife zuweist und die Telefonnummer, Feiertage und Geschäftszeiten, Wartemusik usw. konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e1c65-p101">**The Administrator creates the workflow and the Manager configures options** — The CsResponseGroupAdministrator role member (or equivalent) defines the primary SIP URI, Display Name, assigns a member or members of the CsResponseGroupManager role, and selects a queue and activates the workflow. The CsResponseGroupManager can then log on and edit the configuration of the workflow by creating agent groups and also assigns the group to the queue, configuring the telephone number, holiday and business hours, music on hold, and so on.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e1c65-p102">Wenn Sie einen verwalteten Workflow erstellen möchten, müssen Sie den Workflow als aktiv erstellen. Nach dem Speichern eines aktiven, verwalteten Workflows können Sie den Workflow ändern und deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e1c65-p102">When you want to create a managed workflow, you need to create the workflow as active. After you save an active, managed workflow, you can then modify and deactivate the workflow.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

