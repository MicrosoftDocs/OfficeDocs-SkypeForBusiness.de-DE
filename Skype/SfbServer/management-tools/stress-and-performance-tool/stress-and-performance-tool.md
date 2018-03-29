---
title: Skype für Business Server 2015 Stress and Performance-Tool
ms.author: heidip
author: microsoftheidi
ms.date: 4/6/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Die Skype für Business Server 2015 Stress and Performance-Tool wird während der kapazitätsplanung und in einer Umgebung außerhalb der Produktion oder Test Optimieren der Leistung verwendet.
ms.openlocfilehash: 0a0a5b17a6e45b2e8944e0e0dd4b3840fc62e102
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1fa4b-103">Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="1fa4b-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="1fa4b-104">Die Skype für Business Server 2015 Stress and Performance-Tool wird während der kapazitätsplanung und in einer Umgebung außerhalb der Produktion oder Test Optimieren der Leistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="1fa4b-105">Die Skype für Business Server 2015 Stress and Performance-Tool umfasst Tools, mit die die kapazitätsplanung für Skype für Business Server 2015 vereinfacht werden.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="1fa4b-106">Die Skype für Business Server 2015 Stress and Performance-Tool hilft Ihnen beim:</span><span class="sxs-lookup"><span data-stu-id="1fa4b-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="1fa4b-107">Vereinfachen Sie Ihre Hardware Skype für Business Server planen</span><span class="sxs-lookup"><span data-stu-id="1fa4b-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="1fa4b-108">Übergeben Sie erhöht Knowledge und bewährte Methoden für die leistungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="1fa4b-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="1fa4b-109">Messen der Leistung von Ihrer Skype für Business Server-Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="1fa4b-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="1fa4b-110">In der Regel verwenden Sie dieses Tool nach dem Verwenden der [Skype für Business Server 2015 Planungstool](../../management-tools/planning-tool/planning-tool.md) zum Entwerfen der Topologie, und Optimieren der Topologie mit dem [Skype für Business Server 2015 Capacity Planning Rechner](../../management-tools/capacity-planning-calculator.md).</span><span class="sxs-lookup"><span data-stu-id="1fa4b-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 
  
## <a name="tests"></a><span data-ttu-id="1fa4b-111">Tests</span><span class="sxs-lookup"><span data-stu-id="1fa4b-111">Tests</span></span>

<span data-ttu-id="1fa4b-112">Die Stress and Performance-Tool können Sie diese Arten von Benutzerlast simulieren:</span><span class="sxs-lookup"><span data-stu-id="1fa4b-112">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1fa4b-113">Instant Messaging (IM) und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="1fa4b-113">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="1fa4b-114">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="1fa4b-114">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="1fa4b-115">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="1fa4b-115">Application sharing</span></span>  <br/> |<span data-ttu-id="1fa4b-116">Voice over IP (VoIP), einschließlich Telefonfestnetz Simulation (PTSN)</span><span class="sxs-lookup"><span data-stu-id="1fa4b-116">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="1fa4b-117">Access-Client-Webkonferenzen</span><span class="sxs-lookup"><span data-stu-id="1fa4b-117">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="1fa4b-118">Automatische konferenztelefonzentrale</span><span class="sxs-lookup"><span data-stu-id="1fa4b-118">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="1fa4b-119">Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="1fa4b-119">Response Groups</span></span>  <br/> |<span data-ttu-id="1fa4b-120">Die Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="1fa4b-120">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="1fa4b-121">Herunterladen von Adressbüchern und adressbuchabfrage</span><span class="sxs-lookup"><span data-stu-id="1fa4b-121">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="1fa4b-122">Verbesserte 911 (E911)-Anrufe und Standortprofil (Wählplan)</span><span class="sxs-lookup"><span data-stu-id="1fa4b-122">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="1fa4b-123">MultiView</span><span class="sxs-lookup"><span data-stu-id="1fa4b-123">MultiView</span></span>  <br/> |<span data-ttu-id="1fa4b-124">Zusammenarbeit an Daten</span><span class="sxs-lookup"><span data-stu-id="1fa4b-124">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="1fa4b-125">Mobilität</span><span class="sxs-lookup"><span data-stu-id="1fa4b-125">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="1fa4b-126">Anwendungen und für Business Server 2015 Stress and Performance-Tool mit der Skype enthaltene Dateien</span><span class="sxs-lookup"><span data-stu-id="1fa4b-126">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="1fa4b-127">Diese Anwendungen sind Teil der Skype für Business Server Stress and Performance-Tool:</span><span class="sxs-lookup"><span data-stu-id="1fa4b-127">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="1fa4b-128">**Tool**</span><span class="sxs-lookup"><span data-stu-id="1fa4b-128">**Tool**</span></span>|<span data-ttu-id="1fa4b-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="1fa4b-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1fa4b-130">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="1fa4b-130">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="1fa4b-131">Dieses Tool wird verwendet, um Benutzer und Kontakte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-131">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="1fa4b-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="1fa4b-132">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="1fa4b-133">Verwendet, um die Eigenschaften des die Benutzerlast zu konfigurieren, die Sie simulieren sind.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-133">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="1fa4b-134">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="1fa4b-134">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="1fa4b-135">Das Tool, das Benutzerlast simuliert.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-135">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="1fa4b-136">Default.TMX</span><span class="sxs-lookup"><span data-stu-id="1fa4b-136">Default.tmx</span></span>  <br/> |<span data-ttu-id="1fa4b-137">Erforderlich, um die Skype für Business 2015 Protokollierungstool Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-137">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="1fa4b-138">Beispiele für Skripts-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="1fa4b-138">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="1fa4b-139">So konfigurieren Sie die Topologie für die Ausführung von Auslastungstests, basierend auf bestimmten Szenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-139">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="1fa4b-140">Sie müssen wahrscheinlich bearbeitet, damit sie für Ihre speziellen Umgebung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="1fa4b-140">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="1fa4b-141">Die Themen in diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1fa4b-141">Topics in this section</span></span>

<span data-ttu-id="1fa4b-142">Wenn Sie mehr wissen müssen, sollten Sie die folgenden Artikel lesen:</span><span class="sxs-lookup"><span data-stu-id="1fa4b-142">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="1fa4b-143">Erforderliche Komponenten und Setup für die Skype für Business Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="1fa4b-143">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="1fa4b-144">Leistung Szenarien für die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="1fa4b-144">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="1fa4b-145">Bereitstellung der Topologie zum Laden in Stress and Performance Szenarien ausführen</span><span class="sxs-lookup"><span data-stu-id="1fa4b-145">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="1fa4b-146">Konfigurieren von Richtlinien für die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="1fa4b-146">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="1fa4b-147">Verwenden die Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="1fa4b-147">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="1fa4b-148">Häufig gestellte Fragen zu den Skype für Business Server 2015 Stress and Performance-Tool</span><span class="sxs-lookup"><span data-stu-id="1fa4b-148">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

