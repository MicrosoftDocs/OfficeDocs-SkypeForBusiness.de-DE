---
title: Leistungs Szenarien für das Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, verwenden Sie das Tool für Stress und Leistung.
ms.openlocfilehash: 5531627ab7d5072d32dfcf60fed41eac47f5373f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983850"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="b5c88-103">Leistungs Szenarien für das Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="b5c88-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="b5c88-104">Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, verwenden Sie das Tool für Stress und Leistung.</span><span class="sxs-lookup"><span data-stu-id="b5c88-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="b5c88-105">Damit Sie das Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) ausführen können, muss die Skype for Business Server 2015 Topologie zunächst für die für Sie relevanten Szenarien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b5c88-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="b5c88-106">Wenn Skype for Business Server 2015 nicht konfiguriert ist oder nicht ordnungsgemäß konfiguriert ist, kann es sein, dass die Auslastungssimulation sehr wahrscheinlich fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="b5c88-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="b5c88-107">Mit dem Skype for Business Server 2015 Stress and Performance-Tool werden Beispiel-Skype for Business Server-Verwaltungsshell-Skripts und grundlegende Ressourcendateien als Teil des [Tool Downloads](https://www.microsoft.com/download/details.aspx?id=50367)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b5c88-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="b5c88-108">Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype for Business Server-Bereitstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5c88-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="b5c88-109">In diesem Artikel werden die bereitgestellten Windows PowerShell Beispiele beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5c88-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5c88-110">In diesem Thema wird nicht beschrieben, wie Sie Skype for Business Server 2015 im allgemeinen konfigurieren, sondern auch andere Planungs-und Bereitstellungsthemen.</span><span class="sxs-lookup"><span data-stu-id="b5c88-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="b5c88-111">Ausführliche Informationen zum Arbeiten mit Windows PowerShell in Skype for Business Server 2015 finden Sie in der Dokumentation zur Skype for Business Server Management Shell unter INSERT Introduction here.</span><span class="sxs-lookup"><span data-stu-id="b5c88-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="b5c88-112">Informationen zum Durchführen von Skype for Business Server-Verwaltungsshell-Skripts</span><span class="sxs-lookup"><span data-stu-id="b5c88-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="b5c88-113">Wir stellen Beispiel-PowerShell-Skripts bereit, mit denen Sie Ihre Auslastungssimulationen vorbereiten können.</span><span class="sxs-lookup"><span data-stu-id="b5c88-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="b5c88-114">Da diese Skripts für die Lastsimulation vorgesehen sind, finden Sie diese einfach und frei zügig.</span><span class="sxs-lookup"><span data-stu-id="b5c88-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="b5c88-115">Dies ist möglicherweise nicht für Ihre Produktionsumgebung geeignet.</span><span class="sxs-lookup"><span data-stu-id="b5c88-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="b5c88-116">Wir betonen erneut, dass es sich bei diesen Skripts um Beispiele handelt, Sie müssen diese überprüfen und in vielen Fällen Änderungen vornehmen, die für Ihre Umgebung relevant sind, bevor Sie Sie praktisch nutzen können.</span><span class="sxs-lookup"><span data-stu-id="b5c88-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="b5c88-117">Es wird davon ausgegangen, dass Sie das Wiederherstellungsskript für die Reaktions Dienstgruppe (RSG) mit der Topologie im Hinterkopf ändern müssen (um die Agents anzugeben, die den Agentgruppen zugewiesen sind).</span><span class="sxs-lookup"><span data-stu-id="b5c88-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="b5c88-118">Sie müssen dies jedoch nicht ausführen, wenn Sie dies nicht tun müssen.</span><span class="sxs-lookup"><span data-stu-id="b5c88-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b5c88-119">Achten Sie darauf, diese Beispiele zu überprüfen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="b5c88-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="b5c88-120">Bei der Ausführung werden in Skripts alle vorhandenen Einstellungen in der Topologie überschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5c88-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="b5c88-121">Client Versionsnamen für Stress und Leistungs Tool</span><span class="sxs-lookup"><span data-stu-id="b5c88-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="b5c88-122">Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie zuvor die Einstellungen von den Standardwerten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="b5c88-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="b5c88-123">Wenn Sie sich nicht sicher sind, überprüfen Sie die [Dokumentation zur Client Versionsüberprüfung](https://msdn.microsoft.com/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="b5c88-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/vsto/jj923060).</span></span>
  
<span data-ttu-id="b5c88-124">Das Tool Stress and Performance verwendet bei der Kommunikation mit Skype for Business Server 2015 standardmäßig die folgenden Versionen des Benutzer-Agents:</span><span class="sxs-lookup"><span data-stu-id="b5c88-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="b5c88-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span><span class="sxs-lookup"><span data-stu-id="b5c88-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="b5c88-126">OCPHONE/. 0.522</span><span class="sxs-lookup"><span data-stu-id="b5c88-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="b5c88-127">Für den Mobility-Client (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="b5c88-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="b5c88-128">UCWA perf-Tool/Webkonferenz</span><span class="sxs-lookup"><span data-stu-id="b5c88-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="b5c88-129">UCWA perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="b5c88-129">UCWA Perf Tool/Mobile</span></span>
    

