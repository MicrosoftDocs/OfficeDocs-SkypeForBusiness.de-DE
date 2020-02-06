---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Das Stress-und Leistungs Tool für Skype for Business Server 2015 wird während der Kapazitätsplanung und der Leistungsoptimierung in nicht Produktions-oder Testumgebungen verwendet.
ms.openlocfilehash: efc3ed6cc7f24acc5fda7a7ae2ae818df5b43393
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816154"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="343e2-103">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="343e2-103">Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="343e2-104">Das Stress-und Leistungs Tool für Skype for Business Server 2015 wird während der Kapazitätsplanung und der Leistungsoptimierung in nicht Produktions-oder Testumgebungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="343e2-104">The Skype for Business Server 2015 Stress and Performance Tool is used during capacity planning and performance tuning in non-production or test environments.</span></span>
  
<span data-ttu-id="343e2-105">Das Stress-und Leistungs Tool von Skype for Business Server 2015 umfasst Tools, mit denen Sie Ihre Kapazitätsplanung für Skype for Business Server 2015 vereinfachen können.</span><span class="sxs-lookup"><span data-stu-id="343e2-105">The Skype for Business Server 2015 Stress and Performance Tool includes tools that will simplify your capacity planning for Skype for Business Server 2015.</span></span> <span data-ttu-id="343e2-106">Das Stress-und Leistungs Tool von Skype for Business Server 2015 wird Ihnen dabei helfen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="343e2-106">The Skype for Business Server 2015 Stress and Performance Tool will help you to:</span></span>
  
- <span data-ttu-id="343e2-107">Vereinfachung ihrer Hardwareplanung für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="343e2-107">Simplify your hardware planning for Skype for Business Server</span></span>
    
- <span data-ttu-id="343e2-108">Erweitertes Wissen und bewährte Methoden für die Leistungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="343e2-108">Give you increased knowledge and best practices for performance tuning</span></span>
    
- <span data-ttu-id="343e2-109">Messen der Leistung Ihrer Skype for Business Server-Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="343e2-109">Measure the performance of your Skype for Business Server deployments</span></span>
    
<span data-ttu-id="343e2-110">In der Regel verwenden Sie dieses Tool, nachdem Sie das [Planungstool für Skype for Business Server 2015](../../management-tools/planning-tool/planning-tool.md) verwendet haben, um die Topologie zu entwerfen und die Topologie mit dem [Skype for Business Server 2015-Kapazitäts planungsrechner](../../management-tools/capacity-planning-calculator.md)zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="343e2-110">You would typically use this tool after you use the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md) to design the topology, and refining the topology with the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="343e2-111">Dieses Tool wird für Skype for Business Server 2019 nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="343e2-111">This tool will not be updated for Skype for Business Server 2019.</span></span>
  
## <a name="tests"></a><span data-ttu-id="343e2-112">Tests</span><span class="sxs-lookup"><span data-stu-id="343e2-112">Tests</span></span>

<span data-ttu-id="343e2-113">Das Tool "Spannung und Leistung" kann diese Art von Benutzerauslastung simulieren:</span><span class="sxs-lookup"><span data-stu-id="343e2-113">The Stress and Performance Tool can simulate these types of user load:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="343e2-114">Instant Messaging (im) und Anwesenheitsinformationen</span><span class="sxs-lookup"><span data-stu-id="343e2-114">Instant Messaging (IM) and presence</span></span>  <br/> |<span data-ttu-id="343e2-115">Audiokonferenz</span><span class="sxs-lookup"><span data-stu-id="343e2-115">Audio conferencing</span></span>  <br/> |
|<span data-ttu-id="343e2-116">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="343e2-116">Application sharing</span></span>  <br/> |<span data-ttu-id="343e2-117">VoIP (Voice over IP), einschließlich PTSN-Simulation (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="343e2-117">Voice over IP (VoIP), including public switched telephone network (PTSN) simulation</span></span>  <br/> |
|<span data-ttu-id="343e2-118">Web Access-Client Konferenzen</span><span class="sxs-lookup"><span data-stu-id="343e2-118">Web Access Client conferencing</span></span>  <br/> |<span data-ttu-id="343e2-119">Automatische Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="343e2-119">Conference auto attendant</span></span>  <br/> |
|<span data-ttu-id="343e2-120">Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="343e2-120">Response Groups</span></span>  <br/> |<span data-ttu-id="343e2-121">Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="343e2-121">Distribution list expansion</span></span>  <br/> |
|<span data-ttu-id="343e2-122">Adressbuch Download und Adressbuch Abfrage</span><span class="sxs-lookup"><span data-stu-id="343e2-122">Address book download and address book query</span></span>  <br/> |<span data-ttu-id="343e2-123">Erweiterte 911 (E911)-Anrufe und Standortprofil (Wählplan)</span><span class="sxs-lookup"><span data-stu-id="343e2-123">Enhanced 911 (E911) calls and location profile (dial plan)</span></span>  <br/> |
|<span data-ttu-id="343e2-124">MultiView</span><span class="sxs-lookup"><span data-stu-id="343e2-124">MultiView</span></span>  <br/> |<span data-ttu-id="343e2-125">Datenzusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="343e2-125">Data collaboration</span></span>  <br/> |
|<span data-ttu-id="343e2-126">Mobilität</span><span class="sxs-lookup"><span data-stu-id="343e2-126">Mobility</span></span>  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="343e2-127">Im Lieferumfang des Skype for Business Server 2015-Tools für Stress und Leistung enthaltene Anwendungen und Dateien</span><span class="sxs-lookup"><span data-stu-id="343e2-127">Applications and files included with the Skype for Business Server 2015 Stress and Performance Tool</span></span>

<span data-ttu-id="343e2-128">Diese Anwendungen sind Teil des Skype for Business Server Stress and Performance-Tools:</span><span class="sxs-lookup"><span data-stu-id="343e2-128">These applications are a part of the Skype for Business Server Stress and Performance Tool:</span></span>
  
|<span data-ttu-id="343e2-129">**Tool**</span><span class="sxs-lookup"><span data-stu-id="343e2-129">**Tool**</span></span>|<span data-ttu-id="343e2-130">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="343e2-130">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="343e2-131">UserProvisioningTool. exe</span><span class="sxs-lookup"><span data-stu-id="343e2-131">UserProvisioningTool.exe</span></span>  <br/> |<span data-ttu-id="343e2-132">Dieses Tool dient zum Erstellen von Benutzern und Kontakten.</span><span class="sxs-lookup"><span data-stu-id="343e2-132">This tool is used to create users and contacts.</span></span>  <br/> |
|<span data-ttu-id="343e2-133">UserProfileGenerator. exe</span><span class="sxs-lookup"><span data-stu-id="343e2-133">UserProfileGenerator.exe</span></span>  <br/> |<span data-ttu-id="343e2-134">Wird verwendet, um die Eigenschaften der Benutzerauslastung zu konfigurieren, die Sie simulieren.</span><span class="sxs-lookup"><span data-stu-id="343e2-134">Used to configure the characteristics of the user load you're simulating.</span></span>  <br/> |
|<span data-ttu-id="343e2-135">LyncPerfTool. exe</span><span class="sxs-lookup"><span data-stu-id="343e2-135">LyncPerfTool.exe</span></span>  <br/> |<span data-ttu-id="343e2-136">Das Tool, das die Benutzerauslastung simuliert.</span><span class="sxs-lookup"><span data-stu-id="343e2-136">The tool that simulates user load.</span></span>  <br/> |
|<span data-ttu-id="343e2-137">Standard. TMX</span><span class="sxs-lookup"><span data-stu-id="343e2-137">Default.tmx</span></span>  <br/> |<span data-ttu-id="343e2-138">Erforderlich, um das Skype for Business Server 2015-Protokollierungs Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="343e2-138">Required to use the Skype for Business Server 2015 Logging Tool.</span></span>  <br/> |
|<span data-ttu-id="343e2-139">Beispiele für Bereitstellungsskripts</span><span class="sxs-lookup"><span data-stu-id="343e2-139">Provisioning script examples</span></span>  <br/> |<span data-ttu-id="343e2-140">Wird verwendet, um die Topologie für die Ausführung von Auslastungstests basierend auf bestimmten Szenarien zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="343e2-140">Used to configure the topology for running load tests, based on specific scenarios.</span></span> <span data-ttu-id="343e2-141">Sie müssen diese Änderungen wahrscheinlich ändern, damit Sie für ihre jeweilige Umgebung relevant sind.</span><span class="sxs-lookup"><span data-stu-id="343e2-141">You'll likely need to modify them to make them relevant for your particular environment.</span></span>  <br/> |
   
## <a name="topics-in-this-section"></a><span data-ttu-id="343e2-142">Themen in diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="343e2-142">Topics in this section</span></span>

<span data-ttu-id="343e2-143">Wenn Sie weitere Informationen benötigen, sollten Sie die folgenden Artikel lesen:</span><span class="sxs-lookup"><span data-stu-id="343e2-143">You should review the following articles if you need to know more:</span></span>
  
- [<span data-ttu-id="343e2-144">Voraussetzungen und Setup für Skype for Business Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="343e2-144">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>](prerequisites-and-setup.md)
    
- [<span data-ttu-id="343e2-145">Leistungs Szenarien für das Stress-und Leistungs Tool von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="343e2-145">Performance Scenarios for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](scenarios.md)
    
  - [<span data-ttu-id="343e2-146">Bereitstellen der Topologie zum Ausführen der Auslastung in Stress-und Leistungs Szenarien</span><span class="sxs-lookup"><span data-stu-id="343e2-146">Provisioning the topology to run load in Stress and Performance scenarios</span></span>](provisioning-the-topology-to-run-load.md)
    
  - [<span data-ttu-id="343e2-147">Konfigurieren von Richtlinien für das Stress-und Leistungs Tool von Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="343e2-147">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](configuring-policies.md)
    
- [<span data-ttu-id="343e2-148">Verwenden des Skype for Business Server 2015 Stress-und Leistungstools</span><span class="sxs-lookup"><span data-stu-id="343e2-148">Using the Skype for Business Server 2015 Stress and Performance Tool</span></span>](using-the-tool.md)
    
- [<span data-ttu-id="343e2-149">Häufig gestellte Fragen zum Skype for Business Server 2015 Stress-und Leistungs Tool</span><span class="sxs-lookup"><span data-stu-id="343e2-149">FAQ for the Skype for Business Server 2015 Stress and Performance Tool</span></span>](faq.md)
    

