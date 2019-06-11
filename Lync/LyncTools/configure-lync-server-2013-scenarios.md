---
title: Konfigurieren von lync Server 2013-Szenarien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93ad7a3be8b69c956b1cca0f1d1554a5fa288f17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="1537f-102">Konfigurieren von lync Server 2013-Szenarien</span><span class="sxs-lookup"><span data-stu-id="1537f-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1537f-103">_**Letztes Änderungsdatum des Themas:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="1537f-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="1537f-104">Zum Ausführen des lync Server 2013-Stress-und-Leistungstools (LyncPerfTool) muss die lync Server 2013-Topologie zunächst für die Szenarios konfiguriert werden, die ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1537f-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="1537f-105">Wenn lync Server 2013 nicht konfiguriert ist oder falsch konfiguriert ist, schlägt die Auslastungssimulation in den meisten Fällen fehl.</span><span class="sxs-lookup"><span data-stu-id="1537f-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="1537f-106">Mit dem lync Server 2013-Stress-und-Leistungs Tool haben wir Beispielskripts zur lync Server-Verwaltungsshell und grundlegende Ressourcendateien bereitgestellt, die als Ausgangspunkt für die Konfiguration von lync Server 2013 verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1537f-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="1537f-107">In diesem Thema werden die bereitgestellten Windows PowerShell-Beispiele beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1537f-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="1537f-108">Beachten Sie, dass es nicht das Ziel dieses Themas ist, die Konfiguration von lync Server 2013 im Allgemeinen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="1537f-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="1537f-109">Details zum Arbeiten mit Windows PowerShell in lync Server 2013 finden Sie in der Dokumentation zur lync Server-Verwaltungsshell <https://technet.microsoft.com/en-us/library/gg398474.aspx>unter.</span><span class="sxs-lookup"><span data-stu-id="1537f-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/en-us/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="1537f-110">Informationen zum Ausführen von lync Server-Verwaltungsshell-Skripts</span><span class="sxs-lookup"><span data-stu-id="1537f-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="1537f-111">Wir haben Beispielskripts für die lync Server-Verwaltungsshell bereitgestellt, die möglicherweise zur Vorbereitung der Auslastungssimulation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1537f-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="1537f-112">Da die Skripts für die Auslastungssimulation vorgesehen sind, sind Sie einfach und frei zügig und daher möglicherweise nicht für die Produktion geeignet.</span><span class="sxs-lookup"><span data-stu-id="1537f-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="1537f-113">Alle Skripts sind Beispiele und müssen überprüft und in einigen Fällen geändert werden, um Ihre Topologie wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="1537f-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="1537f-114">Wir gehen davon aus, dass das Szenario des Reaktionsgruppendiensts (RGS) mindestens geändert werden muss, um die Agents anzugeben, die den Agentengruppen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="1537f-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="1537f-115">Sie haben jedoch die Möglichkeit, diese Last nicht zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="1537f-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="1537f-116">Achten Sie darauf, die bereitgestellten Beispiele zu überprüfen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="1537f-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="1537f-117">In Skripts werden alle vorhandenen Einstellungen in der Topologie überschrieben.</span><span class="sxs-lookup"><span data-stu-id="1537f-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1537f-118">Ausführliche Informationen zur Verwendung von Windows PowerShell und der lync Server-Verwaltungsshell finden Sie im Windows PowerShell-Blog zu <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>lync Server 2013 unter.</span><span class="sxs-lookup"><span data-stu-id="1537f-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="1537f-119">Client Version-Moniker für Spannungs-und Leistungs Tool</span><span class="sxs-lookup"><span data-stu-id="1537f-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="1537f-120">Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie die Einstellungen von den Standardwerten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="1537f-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="1537f-121">Ausführliche Informationen finden Sie unter "Konfigurieren unterstützter Clientversionen <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>" unter.</span><span class="sxs-lookup"><span data-stu-id="1537f-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="1537f-122">Das Stress-und Leistungs Tool von lync Server 2013 verwendet die folgenden Benutzer-Agent-Versionen standardmäßig bei der Kommunikation mit lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="1537f-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="1537f-123">LSPT/15.0.0.0 (lync Server 2013 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="1537f-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="1537f-124">OCPHONE/. 0.522</span><span class="sxs-lookup"><span data-stu-id="1537f-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="1537f-125">Diese sind für den Mobilitäts Client (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="1537f-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="1537f-126">Ucwa-perf-Tool/Webkonferenz</span><span class="sxs-lookup"><span data-stu-id="1537f-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="1537f-127">Ucwa perf Tool/Mobil</span><span class="sxs-lookup"><span data-stu-id="1537f-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

