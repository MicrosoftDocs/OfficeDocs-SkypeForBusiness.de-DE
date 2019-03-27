---
title: Leistung Szenarien für die Skype für Business Server 2015 Stress and Performance-Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Aufgaben, die Sie Schritte zum Konfigurieren von Skype für Business Server 2015 erforderlichen zu Leistung und Auslastungstests, führen Sie den Stress and Performance-Tool verwenden.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874591"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="ff4f4-103">Leistung Szenarien für die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="ff4f4-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="ff4f4-104">Aufgaben, die Sie Schritte zum Konfigurieren von Skype für Business Server 2015 erforderlichen zu Leistung und Auslastungstests, führen Sie den Stress and Performance-Tool verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="ff4f4-105">Um die Skype für Business Server 2015 Stress and Performance-Tool (LyncPerfTool) ausgeführt werden soll, muss die Skype für Business Server 2015 Topologie zunächst für Szenarien, die für Sie relevant konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="ff4f4-106">Skype für Business Server 2015 ist nicht konfiguriert oder falsch konfiguriert ist, ist die Load Simulation sehr wahrscheinlich ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="ff4f4-107">Mit der Skype für Business Server 2015 Stress and Performance-Tool sind wir Beispiel Skype als Teil der [herunterladen Tools](https://www.microsoft.com/download/details.aspx?id=50367)für Business Server-Verwaltungsshell-Skripts und grundlegende Ressourcendateien bereit.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="ff4f4-108">Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype für Business Server-Bereitstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="ff4f4-109">In diesem Artikel werden die Windows PowerShell-Beispiele zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff4f4-110">In diesem Thema kann damit nicht im Allgemeinen Skype für Business Server 2015 konfigurieren beschrieben, haben wir für die anderen Themen Planning and Deployment.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="ff4f4-111">Ausführliche Informationen zum Arbeiten mit Windows PowerShell in Skype für Business Server 2015 finden Sie unter der Skype für Business Server Management Shell-Dokumentation unter Einführung hier einfügen.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="ff4f4-112">Zum Ausführen von Skype für Business Server Management Shell-Skripts</span><span class="sxs-lookup"><span data-stu-id="ff4f4-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="ff4f4-113">Wir sind PowerShell-Skriptbeispiele bereit, die Sie zur Vorbereitung Ihrer Load Simulationen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="ff4f4-114">Da diese Skripts für Load Simulation vorgesehen sind, finden Sie diese einfach und permissive sein.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="ff4f4-115">Die kann nicht für die produktionsumgebung geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="ff4f4-116">Belasten es erneut, dass diese Skripts sind Beispiele können, müssen Sie zu prüfen, und in vielen Fällen zu ändern, damit Sie die von ihnen praktische nutzen für Ihre Umgebung relevant.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="ff4f4-117">Mindestens würden wir erwarten, dass Sie das Skript Antwort Service Group (RSG) mit Ihrer Topologie berücksichtigen (an die Agents, agentgruppen zugewiesen) ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="ff4f4-118">Sie müssen aber nicht ausgeführt, die bei Bedarf nicht.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ff4f4-119">Bitte achten Sie in die Überprüfung und Grundlegendes zu in diesen Beispielen.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="ff4f4-120">Skripts überschreibt eine vorhandene Einstellung in der Topologie, die beim Ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="ff4f4-121">Stress and Performance-Tool-Client-Version-Namen</span><span class="sxs-lookup"><span data-stu-id="ff4f4-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="ff4f4-122">Sie müssen möglicherweise die Clientversionsüberprüfung Richtlinie zu konfigurieren, sollten Sie zuvor die Einstellungen die Standardwerte geändert haben.</span><span class="sxs-lookup"><span data-stu-id="ff4f4-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="ff4f4-123">Wenn Sie dies nicht sicher sind, überprüfen Sie die [Dokumentation Clientversionsüberprüfung](https://msdn.microsoft.com/en-us/vsto/jj923060).</span><span class="sxs-lookup"><span data-stu-id="ff4f4-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="ff4f4-124">Die Stress and Performance-Tool verwendet die folgenden Benutzer-Agent-Versionen werden standardmäßig bei der Kommunikation mit Skype für Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="ff4f4-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="ff4f4-125">LSPT/15.0.0.0 (Skype für Business Server 2015 Stress and Performance-Tool)</span><span class="sxs-lookup"><span data-stu-id="ff4f4-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="ff4f4-126">OCPHONE/.0.522</span><span class="sxs-lookup"><span data-stu-id="ff4f4-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="ff4f4-127">Für die Mobilität (UCWA)-Client in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="ff4f4-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="ff4f4-128">UCWA Perf Tool/Webkonferenz</span><span class="sxs-lookup"><span data-stu-id="ff4f4-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="ff4f4-129">UCWA Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="ff4f4-129">UCWA Perf Tool/Mobile</span></span>
    

