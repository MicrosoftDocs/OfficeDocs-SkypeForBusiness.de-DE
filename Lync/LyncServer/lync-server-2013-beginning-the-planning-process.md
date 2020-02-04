---
title: 'Lync Server 2013: Beginnen des Planungsprozesses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="03dad-102">Beginnen des Planungsprozesses für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03dad-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03dad-103">_**Letztes Änderungsdatum des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="03dad-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="03dad-104">Bei der Planung einer lokalen Unified Communications-Bereitstellung mag Einschüchterungen auftreten, lync Server bietet zwei nützliche Tools, die Ihnen helfen können:</span><span class="sxs-lookup"><span data-stu-id="03dad-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="03dad-105">**Das Planungs Tool** ist ein Assistent, der eine Reihe von Fragen zu Ihrer Organisation, zu den lync-Server Features, die Sie aktivieren möchten, und Ihren Anforderungen an die Kapazitätsplanung stellt.</span><span class="sxs-lookup"><span data-stu-id="03dad-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="03dad-106">Anschließend erstellt Sie eine empfohlene Bereitstellungstopologie auf der Grundlage ihrer Antworten und erstellt ein Microsoft Visio-Diagramm dieser Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="03dad-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="03dad-107">Der **Topologie-Generator** ist eine Installationskomponente von lync Server.</span><span class="sxs-lookup"><span data-stu-id="03dad-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="03dad-108">Sie verwenden den Topologie-Generator zum Erstellen, anpassen und Veröffentlichen Ihrer geplanten Topologie.</span><span class="sxs-lookup"><span data-stu-id="03dad-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="03dad-109">Darüber hinaus wird Ihre Topologie überprüft, bevor Sie mit Server Installationen beginnen.</span><span class="sxs-lookup"><span data-stu-id="03dad-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="03dad-110">Wenn Sie lync Server auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server in der Topologie bereit.</span><span class="sxs-lookup"><span data-stu-id="03dad-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="03dad-111">Lync Server-Planungs Tool</span><span class="sxs-lookup"><span data-stu-id="03dad-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="03dad-112">Das Planungstool nimmt Ihre Antworten auf die Fragen im Tool auf und generiert eine Topologie basierend auf den Richtlinien und bewährten Methoden von lync Server.</span><span class="sxs-lookup"><span data-stu-id="03dad-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="03dad-113">Darüber hinaus werden auf Grundlage ihrer Antworten mehrere Ansichten einer Bereitstellung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="03dad-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="03dad-114">Sie zeigt sowohl eine globale Ansicht aller Ihrer Websites (also sowohl zentrale Websites als auch Zweigstellenstandorte) sowie detaillierte Ansichten mit den Servern und anderen Komponenten an den einzelnen Standorten.</span><span class="sxs-lookup"><span data-stu-id="03dad-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="03dad-115">Durch Ausführen des Planungstools werden Sie nicht zu einer bestimmten Bereitstellung oder zum Initiieren von Prozessen verpflichtet.</span><span class="sxs-lookup"><span data-stu-id="03dad-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="03dad-116">Das Ausführen des Planungstools, bevor Sie einen festen Plan haben, kann in der Tat eine sehr lehrreiche Möglichkeit sein, die Art der Fragen zu verstehen, die Sie in Ihrem Planungsprozess berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="03dad-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="03dad-117">Sie können das Planungs Tool mehrmals ausführen, Fragen anders beantworten und die Ergebnisse vergleichen.</span><span class="sxs-lookup"><span data-stu-id="03dad-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="03dad-118">Wenn Sie über ein Design verfügen, mit dem Sie überwiegend zufrieden sind, aber Änderungen vornehmen müssen, können Sie zum Planungs Tool zurückkehren, das Design laden und die Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="03dad-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="03dad-119">Es dauert etwa 15 Minuten, bis das Planungs Tool einmal abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="03dad-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="03dad-120">Nachdem Sie zufrieden sind, können Sie das Planungs Tool verwenden, um ein Diagramm Ihrer geplanten Bereitstellung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="03dad-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="03dad-121">Sie können dieses Diagramm verwenden, während Sie die Bereitstellung im Topologie-Generator erstellen.</span><span class="sxs-lookup"><span data-stu-id="03dad-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03dad-122">Das in dieser Version von lync Server 2013 enthaltene Planungs Tool ist eine Vorabversion.</span><span class="sxs-lookup"><span data-stu-id="03dad-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="03dad-123">Beachten Sie, dass die Kapazitätsplanungswerte im Planungstool vorläufig sind und nicht für die finale Version unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="03dad-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="03dad-124">Lync Server Topology Builder</span><span class="sxs-lookup"><span data-stu-id="03dad-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="03dad-125">Nachdem Sie sich für Ihren Bereitstellungsplan entschieden haben, verwenden Sie den Topologie-Generator, um mit der Bereitstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="03dad-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="03dad-126">Wenn Sie den Vorgang beenden, verwenden Sie den Topologie-Generator, um die Topologie zu überprüfen, und wenn Sie erfolgreich ist, können Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="03dad-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="03dad-127">Wenn Sie die Topologie veröffentlichen, platziert lync Server die Topologie in den zentralen Verwaltungsspeicher, der zu diesem Zeitpunkt erstellt wird, wenn er noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="03dad-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="03dad-128">Wenn Sie lync Server auf jedem Server in Ihrer Bereitstellung installieren, liest der Server die Topologie aus dem zentralen Verwaltungsspeicher und installiert sich selbst, damit er in ihre Rolle in Ihrer Bereitstellung passt.</span><span class="sxs-lookup"><span data-stu-id="03dad-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="03dad-129">Wenn Sie mit lync Server sehr vertraut sind und eine geringere normative Anleitung benötigen, können Sie das Planungs Tool überspringen und die Assistenten im Topologie-Generator verwenden, um den anfänglichen Entwurf Ihrer Bereitstellung und auch die Schritte für die Validierung und Veröffentlichung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="03dad-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="03dad-130">Die Verwendung des Topologie-Generators zum Planen und Veröffentlichen einer Topologie ist ein erforderlicher Schritt.</span><span class="sxs-lookup"><span data-stu-id="03dad-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="03dad-131">Sie können den Topologie-Generator nicht umgehen und lync Server auf den Servern in Ihrer Bereitstellung einzeln installieren.</span><span class="sxs-lookup"><span data-stu-id="03dad-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="03dad-132">Jeder Server muss die Topologie aus einer validierten, veröffentlichten Topologie im zentralen Verwaltungsspeicher lesen.</span><span class="sxs-lookup"><span data-stu-id="03dad-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="03dad-133">Planungsprozess auf oberster Ebene</span><span class="sxs-lookup"><span data-stu-id="03dad-133">High-Level Planning Process</span></span>

<span data-ttu-id="03dad-134">Wir empfehlen die folgenden allgemeinen Verfahren für die Verwendung der Dokumentation und des Planungstools zum Planen Ihrer lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="03dad-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="03dad-135">Wenn Sie mit früheren Versionen von lync Server vertraut sind, lesen Sie [neue Features in lync Server 2013](lync-server-2013-new-features.md) , um sich mit den neuen Features und Anforderungen in lync Server 2013 vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="03dad-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="03dad-136">Lesen Sie die anderen Themen in diesem Abschnitt der Dokumentation: [Topologie-Grundlagen, die Sie kennen müssen, bevor Sie lync Server 2013 planen](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md), [erste Planungsentscheidungen für lync Server 2013](lync-server-2013-initial-planning-decisions.md)und [Clients für lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="03dad-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="03dad-137">Beachten Sie die Planungsentscheidungen, die in [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md)dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="03dad-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="03dad-138">Nachdem Sie sich nun mit den lync Server-Features und den Arten von Fragen vertraut gemacht haben, die beantwortet werden müssen, führen Sie das Planungs Tool aus, und zeigen Sie die resultierende Topologie und deren Details an.</span><span class="sxs-lookup"><span data-stu-id="03dad-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="03dad-139">Stellen Sie sicher, dass die Topologie den eindeutigen Anforderungen für Ihre Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="03dad-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="03dad-140">Wenn es bestimmte Arbeitsauslastungen oder Features gibt, an denen Sie interessiert sind oder die Sie kennen müssen, lesen Sie die entsprechenden Abschnitte der [Planung für lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="03dad-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="03dad-141">Führen Sie das Planungs Tool erneut aus.</span><span class="sxs-lookup"><span data-stu-id="03dad-141">Run the Planning Tool again.</span></span> <span data-ttu-id="03dad-142">Sie können mit der Bereitstellung beginnen, die Sie in Schritt 3 erstellt haben, und die Ergebnisse ändern oder von vorn beginnen.</span><span class="sxs-lookup"><span data-stu-id="03dad-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="03dad-143">Führen Sie bei Bedarf das Planungs Tool ein drittes Mal aus, und wiederholen Sie den Vorgang, bis Sie mit der Ausgabe zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="03dad-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="03dad-144">Wenn Sie den Topologieplan abgeschlossen haben, verwenden Sie das Planungs Tool zum Erstellen und Drucken eines Visio-Diagramms Ihrer Topologie.</span><span class="sxs-lookup"><span data-stu-id="03dad-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="03dad-145">Sie können diesen Ausdruck während der Arbeit mit dem Topologie-Generator verwenden, um Ihre Topologie einzugeben.</span><span class="sxs-lookup"><span data-stu-id="03dad-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="03dad-146">Bevor Sie mit der Bereitstellung beginnen, lesen Sie [Ermitteln der Systemanforderungen für lync Server 2013](lync-server-2013-determining-your-system-requirements.md) und [Ermitteln der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) , um sich mit den Voraussetzungen und der erforderlichen Infrastruktur für lync Server vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="03dad-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="03dad-147">Stellen Sie außerdem sicher, dass Sie alle Abschnitte der [Planning für lync Server 2013](lync-server-2013-planning.md) gelesen haben, die für die Arbeitslasten und Features gelten, die Sie bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="03dad-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="03dad-148">Migrieren von vorherigen Versionen</span><span class="sxs-lookup"><span data-stu-id="03dad-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="03dad-149">Wenn Sie von einer früheren Version zu lync Server migrieren, finden Sie in der [Migrations](migration.md) Dokumentation spezifische Anweisungen für Ihre Migration und Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="03dad-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

