---
title: 'Lync Server 2013: Starten des Planungsprozesses'
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
ms.openlocfilehash: d436da8efa7194c2a0a341f4bed7794e532446ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513038"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="4f956-102">Beginnen des Planungsprozesses für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f956-102">Beginning the planning process for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f956-103">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="4f956-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="4f956-104">Während die Planung einer lokalen Unified Communications-Bereitstellung möglicherweise beängstigend wirkt, bietet lync Server zwei wertvolle Tools, die Ihnen helfen:</span><span class="sxs-lookup"><span data-stu-id="4f956-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="4f956-105">Bei **dem Planungs Tool** handelt es sich um einen Assistenten, der eine Reihe von Fragen zu Ihrer Organisation, zu den lync Server Funktionen, die Sie aktivieren möchten, und den Anforderungen an die Kapazitätsplanung stellt.</span><span class="sxs-lookup"><span data-stu-id="4f956-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="4f956-106">Basierend auf Ihren Antworten erstellt das Tool eine empfohlene Bereitstellungstopologie und generiert ein Microsoft Visio-Diagramm dieser Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="4f956-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="4f956-107">Der **Topologie-Generator** ist eine Installationskomponente von lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f956-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="4f956-108">Verwenden Sie den Topologie-Generator, um die geplante Topologie zu erstellen, anzupassen und zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4f956-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="4f956-109">Darüber hinaus überprüft der Topologie-Generator Ihre Topologie, bevor Sie mit den Serverinstallationen beginnen.</span><span class="sxs-lookup"><span data-stu-id="4f956-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="4f956-110">Wenn Sie lync Server auf einzelnen Servern installieren, lesen die Server die veröffentlichte Topologie als Teil des Installationsvorgangs, und das Installationsprogramm stellt den Server wie in der Topologie weitergeleitet bereit.</span><span class="sxs-lookup"><span data-stu-id="4f956-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="4f956-111">Lync Server Planungs Tool</span><span class="sxs-lookup"><span data-stu-id="4f956-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="4f956-112">Das Planungstool verwendet Ihre Antworten auf die Fragen im Tool und generiert eine Topologie basierend auf lync Server Richtlinien und bewährten Methoden.</span><span class="sxs-lookup"><span data-stu-id="4f956-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="4f956-113">Auf Grundlage Ihrer Antworten bietet das Planungstool zudem verschiedene Ansichten einer Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="4f956-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="4f956-114">Es stellt sowohl eine globale Ansicht aller Standorte (einschließlich der zentralen Standorte und Zweigstellen) als auch detaillierte Ansichten der Server und weiterer Komponenten an jedem Standort bereit.</span><span class="sxs-lookup"><span data-stu-id="4f956-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="4f956-115">Durch das Ausführen des Planungstools werden Sie nicht zu einer bestimmten Bereitstellung verpflichtet oder keine Prozesse initiieren.</span><span class="sxs-lookup"><span data-stu-id="4f956-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="4f956-116">Tatsächlich kann das Ausführen des Planungstools noch bevor Sie einen festen Plan im Hinterkopf haben, eine sehr lehrreiche Möglichkeit sein, sich mit den Fragen vertraut zu machen, die Sie in Ihrem Planungsprozess überdenken müssen.</span><span class="sxs-lookup"><span data-stu-id="4f956-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="4f956-117">Sie können das Planungs Tool mehrmals ausführen, Fragen anders beantworten und die Ergebnisse vergleichen.</span><span class="sxs-lookup"><span data-stu-id="4f956-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="4f956-118">Wenn Sie über einen Entwurf verfügen, mit dem Sie überwiegend zufrieden sind, an dem Sie jedoch Änderungen vornehmen müssen, können Sie zum Planungs Tool zurückkehren, den Entwurf laden und die Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4f956-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="4f956-119">Es dauert ungefähr 15 Minuten, bis Sie das Planungs Tool einmal abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="4f956-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="4f956-120">Nachdem Sie zufrieden sind, können Sie das Planungs Tool verwenden, um ein Diagramm Ihrer geplanten Bereitstellung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f956-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="4f956-121">Sie können dieses Diagramm beim Erstellen der Bereitstellung im Topologie-Generator verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f956-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4f956-122">Das in dieser Version von lync Server 2013 enthaltene Planungs Tool ist eine Vorabversion.</span><span class="sxs-lookup"><span data-stu-id="4f956-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="4f956-123">Beachten Sie, dass die Kapazitätsplanungswerte im Planungstool vorläufig sind und nicht für die finale Version unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="4f956-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="4f956-124">Lync Server Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="4f956-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="4f956-125">Nachdem Sie sich für den Bereitstellungsplan entschieden haben, verwenden Sie den Topologie-Generator, um mit der Bereitstellung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="4f956-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="4f956-126">Wenn Sie fertig sind, verwenden Sie den Topologie-Generator, um die Topologie zu überprüfen, und wenn Sie dann übergeben wird, können Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4f956-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="4f956-127">Wenn Sie die Topologie veröffentlichen, stellt lync Server die Topologie in den zentralen Verwaltungsspeicher, der zu diesem Zeitpunkt erstellt wird, wenn er noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4f956-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="4f956-128">Wenn Sie lync Server auf jedem Server in Ihrer Bereitstellung installieren, liest der Server die Topologie aus dem zentralen Verwaltungsspeicher und installiert sich selbst so, dass Sie in ihre Rolle in Ihrer Bereitstellung passt.</span><span class="sxs-lookup"><span data-stu-id="4f956-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="4f956-129">Alternativ können Sie, wenn Sie mit lync Server sehr vertraut sind und eine geringere normative Anleitung benötigen, das Planungs Tool überspringen und die Assistenten im Topologie-Generator für den ersten Entwurf Ihrer Bereitstellung und auch für die Schritte zur Validierung und Veröffentlichung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f956-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="4f956-130">Die Planung und Veröffentlichung einer Topologie mithilfe des Topologie-Generators ist ein erforderlicher Schritt.</span><span class="sxs-lookup"><span data-stu-id="4f956-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="4f956-131">Sie können den Topologie-Generator nicht umgehen und lync Server einzeln auf den Servern in Ihrer Bereitstellung installieren.</span><span class="sxs-lookup"><span data-stu-id="4f956-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="4f956-132">Jeder Server muss die Topologie aus einer validierten, veröffentlichten Topologie im zentralen Verwaltungsspeicher lesen.</span><span class="sxs-lookup"><span data-stu-id="4f956-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="4f956-133">Grundlegende Schritte bei der Planung</span><span class="sxs-lookup"><span data-stu-id="4f956-133">High-Level Planning Process</span></span>

<span data-ttu-id="4f956-134">Wir empfehlen den folgenden allgemeinen Prozess für die Verwendung der Dokumentation und des Planungstools, um Ihre lync Server-Bereitstellung zu planen.</span><span class="sxs-lookup"><span data-stu-id="4f956-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="4f956-135">Wenn Sie mit früheren Versionen von lync Server vertraut sind, lesen Sie [neue Features in lync Server 2013](lync-server-2013-new-features.md) , um sich mit den neuen Features und Anforderungen in lync Server 2013 vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="4f956-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="4f956-136">Lesen Sie die anderen Themen in diesem Abschnitt der Dokumentation: [Grundlagen der Topologie, die Sie vor der Planung von lync Server 2013 kennen müssen](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md), [anfängliche Planungsentscheidungen für lync Server 2013](lync-server-2013-initial-planning-decisions.md)und [Clients für lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4f956-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="4f956-137">Beachten Sie die Planungsentscheidungen, die in [Referenz Topologien in lync Server 2013](lync-server-2013-reference-topologies.md)dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4f956-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="4f956-138">Nachdem Sie sich mit lync Server Features und den Fragen, die beantwortet werden müssen, vertraut gemacht haben, führen Sie das Planungs Tool aus, und zeigen Sie die sich ergebende Topologie und deren Details an.</span><span class="sxs-lookup"><span data-stu-id="4f956-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="4f956-139">Stellen Sie sicher, dass die Topologie den speziellen Anforderungen Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="4f956-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="4f956-140">Wenn es bestimmte Arbeitslasten oder Features gibt, an denen Sie interessiert sind oder die Sie kennen müssen, lesen Sie die entsprechenden Abschnitte der [Planung für lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="4f956-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="4f956-141">Führen Sie das Planungs Tool erneut aus.</span><span class="sxs-lookup"><span data-stu-id="4f956-141">Run the Planning Tool again.</span></span> <span data-ttu-id="4f956-142">Sie können mit der in Schritt 3 erstellten Bereitstellung beginnen und die Ergebnisse ändern, oder Sie beginnen ganz von vorne.</span><span class="sxs-lookup"><span data-stu-id="4f956-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="4f956-143">Führen Sie bei Bedarf das Planungs Tool ein drittes Mal aus, und wiederholen Sie den Vorgang, bis Sie mit der Ausgabe zufrieden sind.</span><span class="sxs-lookup"><span data-stu-id="4f956-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="4f956-144">Wenn Sie den Topologieplan abgeschlossen haben, verwenden Sie das Planungs Tool, um ein Visio-Diagramm Ihrer Topologie zu erstellen und zu drucken.</span><span class="sxs-lookup"><span data-stu-id="4f956-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="4f956-145">Sie können diesen Ausdruck beim Arbeiten mit dem Topologie-Generator verwenden, um Ihre Topologie einzugeben.</span><span class="sxs-lookup"><span data-stu-id="4f956-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="4f956-146">Bevor Sie mit der Bereitstellung beginnen, lesen Sie [Ermitteln der Systemanforderungen für lync Server 2013](lync-server-2013-determining-your-system-requirements.md) und [bestimmen der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) , um sich mit den Voraussetzungen und der erforderlichen Infrastruktur für lync Server vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="4f956-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="4f956-147">Stellen Sie außerdem sicher, dass Sie alle Abschnitte der [Planung für lync Server 2013](lync-server-2013-planning.md) gelesen haben, die für die Arbeitsauslastungen und Features gelten, die Sie bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4f956-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="4f956-148">Migration von früheren Versionen</span><span class="sxs-lookup"><span data-stu-id="4f956-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="4f956-149">Wenn Sie zu lync Server einer früheren Version migrieren, finden Sie in der [Migrations](migration.md) Dokumentation spezifische Anweisungen für die Migration und Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="4f956-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

