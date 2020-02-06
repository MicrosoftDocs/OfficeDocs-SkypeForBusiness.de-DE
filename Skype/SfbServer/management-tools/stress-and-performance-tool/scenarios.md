---
title: Leistungs Szenarien für das Stress-und Leistungs Tool von Skype for Business Server 2015
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
description: Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, indem Sie das Tool Stress und Leistung verwenden.
ms.openlocfilehash: 343378d0b0d763d8a290e8d1e930a64c5d114bdb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803875"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1d2b9-103">Leistungs Szenarien für das Stress-und Leistungs Tool von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1d2b9-103">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="1d2b9-104">Aufgaben, die Sie ausführen müssen, um Skype for Business Server 2015 für Leistungs-und Auslastungstests zu konfigurieren, indem Sie das Tool Stress und Leistung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-104">Tasks you'll need to do to configure Skype for Business Server 2015 to do performance and load-testing, using the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="1d2b9-105">Zum Ausführen des Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool) muss die Skype for Business Server 2015-Topologie zunächst für für Sie relevante Szenarien konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-105">To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you.</span></span> <span data-ttu-id="1d2b9-106">Wenn Skype for Business Server 2015 nicht konfiguriert ist oder falsch konfiguriert ist, schlägt die Auslastungssimulation höchstwahrscheinlich fehl.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-106">If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail.</span></span> <span data-ttu-id="1d2b9-107">Mit dem Stress-und Leistungstool für Skype for Business Server 2015 stellen wir Beispiele für Skype for Business Server-Verwaltungsshell-Skripts und grundlegende Ressourcendateien als Teil des [Tool Downloads](https://www.microsoft.com/download/details.aspx?id=50367)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-107">With the Skype for Business Server 2015 Stress and Performance Tool, we're providing example Skype for Business Server Management Shell scripts and basic resource files as part of the [tool download](https://www.microsoft.com/download/details.aspx?id=50367).</span></span> <span data-ttu-id="1d2b9-108">Diese können als Ausgangspunkt für die Konfiguration Ihrer Skype for Business Server-Bereitstellung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-108">These can be used as a starting point for configuring your Skype for Business Server deployment.</span></span> <span data-ttu-id="1d2b9-109">In diesem Artikel werden die bereitgestellten Windows PowerShell-Beispiele beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-109">This article describes the Windows PowerShell examples provided.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d2b9-110">In diesem Thema wird Ihnen nicht geholfen, die Konfiguration von Skype for Business Server 2015 im Allgemeinen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-110">This topic won't help you describe how to configure Skype for Business Server 2015 generally, we have other Planning and Deployment topics for that.</span></span> <span data-ttu-id="1d2b9-111">Details zum Arbeiten mit Windows PowerShell in Skype for Business Server 2015 finden Sie in der Dokumentation zur Skype for Business Server-Verwaltungsshell unter Einfügen-Einführung hier.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-111">For details about working with Windows PowerShell in Skype for Business Server 2015, see the Skype for Business Server Management Shell documentation at Insert introduction HERE.</span></span> 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a><span data-ttu-id="1d2b9-112">Informationen zum Ausführen von Skripts für die Verwaltung von Skype for Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="1d2b9-112">About running Skype for Business Server management shell scripts</span></span>

<span data-ttu-id="1d2b9-113">Wir stellen Beispiel-PowerShell-Skripts bereit, mit denen Sie Ihre Auslastungssimulationen vorbereiten können.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-113">We're providing sample PowerShell scripts you can use to prepare for your load simulations.</span></span> <span data-ttu-id="1d2b9-114">Da diese Skripts für die Auslastungssimulation vorgesehen sind, finden Sie Sie einfach und frei zügig.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-114">Because these scripts are intended for load simulation, you'll find them to be simple and permissive.</span></span> <span data-ttu-id="1d2b9-115">, Die möglicherweise nicht für Ihre Produktionsumgebung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-115">That may not be appropriate for your production environment.</span></span> <span data-ttu-id="1d2b9-116">Wir betonen erneut, dass es sich bei diesen Skripts um Beispiele handelt, Sie müssen Sie überprüfen und in vielen Fällen Änderungen vornehmen, die für Ihre Umgebung relevant sind, bevor Sie Sie praktisch nutzen können.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-116">Again we stress that these scripts are samples, you'll need to review them and in many cases make changes relevant to your environment before being able to make practical use of them.</span></span> <span data-ttu-id="1d2b9-117">Wir gehen davon aus, dass Sie mindestens das Wiederherstellungsskript der Antwortdienst Gruppe (RSG) mit Ihrer Topologie ändern müssten (um die Agents anzugeben, die den Agentengruppen zugewiesen sind).</span><span class="sxs-lookup"><span data-stu-id="1d2b9-117">At a minimum, we'd expect you'd need to modify the Response Service Group (RSG) script with your topology in mind (to specify the agents assigned to the agent groups).</span></span> <span data-ttu-id="1d2b9-118">Sie müssen dies aber nicht ausführen, wenn Sie dies nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-118">But you don't have to run that, if you don't need to.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="1d2b9-119">Achten Sie bitte darauf, diese Beispiele zu überprüfen und zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-119">Please take care in reviewing and understanding these samples.</span></span> <span data-ttu-id="1d2b9-120">Skripts überschreiben alle vorhandenen Einstellungen in der Topologie, wenn Sie ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-120">Scripts will overwrite any existing settings in the topology when run.</span></span> 
  
## <a name="stress-and-performance-tool-client-version-names"></a><span data-ttu-id="1d2b9-121">Versionsnamen für Spannungs-und Leistungs Tool-Client</span><span class="sxs-lookup"><span data-stu-id="1d2b9-121">Stress and Performance Tool client version names</span></span>

<span data-ttu-id="1d2b9-122">Möglicherweise müssen Sie die Richtlinie für die Client Versionsüberprüfung konfigurieren, wenn Sie die Einstellungen zuvor von den Standardwerten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-122">You might need to configure the Client Version Check policy if you've previously changed the settings from the default values.</span></span> <span data-ttu-id="1d2b9-123">Wenn Sie sich nicht sicher sind, sehen Sie in der [Dokumentation zur Client Version](https://msdn.microsoft.com/en-us/vsto/jj923060)nach.</span><span class="sxs-lookup"><span data-stu-id="1d2b9-123">If you're unsure about this, check the [Client Version Check documentation](https://msdn.microsoft.com/en-us/vsto/jj923060).</span></span>
  
<span data-ttu-id="1d2b9-124">Das Tool "Spannung und Leistung" verwendet standardmäßig die folgenden Benutzer-Agent-Versionen, wenn Sie mit Skype for Business Server 2015 kommunizieren:</span><span class="sxs-lookup"><span data-stu-id="1d2b9-124">The Stress and Performance Tool uses the following User Agent versions by default when communicating with Skype for Business Server 2015:</span></span>
  
- <span data-ttu-id="1d2b9-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress-und Leistungs Tool)</span><span class="sxs-lookup"><span data-stu-id="1d2b9-125">LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)</span></span>
    
- <span data-ttu-id="1d2b9-126">OCPHONE/. 0.522</span><span class="sxs-lookup"><span data-stu-id="1d2b9-126">OCPHONE/.0.522</span></span>
    
<span data-ttu-id="1d2b9-127">Für den Mobilitäts Client (UCWA) in LyncPerfTool:</span><span class="sxs-lookup"><span data-stu-id="1d2b9-127">For the Mobility (UCWA) client in LyncPerfTool:</span></span>
  
- <span data-ttu-id="1d2b9-128">UCWA-perf-Tool/Webkonferenz</span><span class="sxs-lookup"><span data-stu-id="1d2b9-128">UCWA Perf Tool/Web Conference</span></span>
    
- <span data-ttu-id="1d2b9-129">UCWA perf Tool/Mobil</span><span class="sxs-lookup"><span data-stu-id="1d2b9-129">UCWA Perf Tool/Mobile</span></span>
    

