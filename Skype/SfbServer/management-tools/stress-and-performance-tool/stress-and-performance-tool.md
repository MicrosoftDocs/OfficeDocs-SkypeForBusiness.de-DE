---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Die Skype für Business Server 2015 Stress and Performance-Tool wird während der kapazitätsplanung und in einer Umgebung außerhalb der Produktion oder Test Optimieren der Leistung verwendet.
ms.openlocfilehash: 7705e92c8389e0377e805bd7d8e09aee454d9160
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904573"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e8312-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e8312-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="e8312-104">Die Skype für Business Server 2015 Stress and Performance-Tool wird während der kapazitätsplanung und in einer Umgebung außerhalb der Produktion oder Test Optimieren der Leistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8312-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="e8312-105">Die Skype für Business Server 2015 Stress and Performance-Tool umfasst Tools, mit die die kapazitätsplanung für Skype für Business Server 2015 vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="e8312-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="e8312-106">Die Skype für Business Server 2015 Stress and Performance-Tool hilft Ihnen beim:</span><span class="sxs-lookup"><span data-stu-id="e8312-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="e8312-107">Vereinfachen Sie Ihre Hardware Skype für Business Server planen</span><span class="sxs-lookup"><span data-stu-id="e8312-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="e8312-108">Übergeben Sie erhöht Knowledge und bewährte Methoden für die leistungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="e8312-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="e8312-109">Messen der Leistung von Ihrer Skype für Business Server-Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="e8312-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="e8312-110">In der Regel verwenden Sie dieses Tool nach dem Verwenden der [Skype für Business Server 2015 Planungstool](../../management-tools/planning-tool/planning-tool.md) zum Entwerfen der Topologie, und Optimieren der Topologie mit dem [Skype für Business Server 2015 Capacity Planning Rechner](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="e8312-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="e8312-111">Dieses Tool wird für Skype für Business Server 2019 nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8312-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="e8312-112">Tests</span><span class="sxs-lookup"><span data-stu-id="e8312-112">Tests</span></span>

<span data-ttu-id="e8312-113">Die Stress and Performance-Tool können Sie diese Arten von Benutzerlast simulieren:</span><span class="sxs-lookup"><span data-stu-id="e8312-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e8312-114">Instant Messaging (IM) und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="e8312-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="e8312-115">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="e8312-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="e8312-116">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="e8312-116">Application sharing</span></span>  <br/> |<span data-ttu-id="e8312-117">Voice over IP (VoIP), einschließlich Telefonfestnetz Simulation (PTSN)</span><span class="sxs-lookup"><span data-stu-id="e8312-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="e8312-118">Access-Client-Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="e8312-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="e8312-119">Automatische konferenztelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="e8312-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="e8312-120">Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="e8312-120">Response Groups</span></span>  <br/> |<span data-ttu-id="e8312-121">Die Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="e8312-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="e8312-122">Herunterladen von Adressbüchern und adressbuchabfrage</span><span class="sxs-lookup"><span data-stu-id="e8312-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="e8312-123">Verbesserte 911 (E911)-Anrufe und Standortprofil (Wählplan)</span><span class="sxs-lookup"><span data-stu-id="e8312-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="e8312-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="e8312-124">MultiView</span></span>  <br/> |<span data-ttu-id="e8312-125">Datenzusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="e8312-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="e8312-126">Mobilität</span><span class="sxs-lookup"><span data-stu-id="e8312-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e8312-127">Anwendungen und für Business Server 2015 Stress and Performance-Tool mit der Skype enthaltene Dateien</span><span class="sxs-lookup"><span data-stu-id="e8312-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="e8312-128">Diese Anwendungen sind Teil der Skype für Business Server Stress and Performance-Tool:</span><span class="sxs-lookup"><span data-stu-id="e8312-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="e8312-129">**Werkzeug**</span><span class="sxs-lookup"><span data-stu-id="e8312-129">**Tool**</span></span>|<span data-ttu-id="e8312-130">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e8312-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8312-131">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="e8312-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="e8312-132">Dieses Tool wird verwendet, um Benutzer und Kontakte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8312-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="e8312-133">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="e8312-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="e8312-134">Verwendet, um die Eigenschaften des die Benutzerlast zu konfigurieren, die Sie simulieren sind.</span><span class="sxs-lookup"><span data-stu-id="e8312-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="e8312-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="e8312-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="e8312-136">Das Tool, das Benutzerlast simuliert.</span><span class="sxs-lookup"><span data-stu-id="e8312-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="e8312-137">Default.TMX</span><span class="sxs-lookup"><span data-stu-id="e8312-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="e8312-138">Erforderlich, um die Skype für Business 2015 Protokollierungstool Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8312-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="e8312-139">Beispiele für Skripts-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="e8312-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="e8312-140">So konfigurieren Sie die Topologie für die Ausführung von Auslastungstests, basierend auf bestimmten Szenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8312-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="e8312-141">Sie müssen wahrscheinlich bearbeitet, damit sie für Ihre speziellen Umgebung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="e8312-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="e8312-142">Die Themen in diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e8312-142">Topics in this section</span></span>

<span data-ttu-id="e8312-143">Wenn Sie mehr wissen müssen, sollten Sie die folgenden Artikel lesen:</span><span class="sxs-lookup"><span data-stu-id="e8312-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="e8312-144">Voraussetzungen und Setup für Skype for Business Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="e8312-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="e8312-145">Leistung Szenarien für die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="e8312-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="e8312-146">Bereitstellung der Topologie zum Laden in Stress and Performance Szenarien ausführen</span><span class="sxs-lookup"><span data-stu-id="e8312-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="e8312-147">Konfigurieren von Richtlinien für die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="e8312-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="e8312-148">Verwenden die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="e8312-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="e8312-149">Häufig gestellte Fragen zu den Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="e8312-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

