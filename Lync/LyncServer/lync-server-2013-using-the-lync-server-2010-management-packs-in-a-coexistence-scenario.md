---
title: Verwenden der lync Server 2010 Management Packs in einem Szenario für die Koexistenz
description: Verwenden der lync Server 2010 Management Packs in einem Szenario für die Koexistenz.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5f6e76f49b74badd0f40d115101abb38aa35172
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556065"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="535ba-103">Verwenden der lync Server 2010 Management Packs in einem Szenario für die Koexistenz</span><span class="sxs-lookup"><span data-stu-id="535ba-103">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="535ba-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="535ba-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="535ba-105">Viele Kunden nehmen ein Einführungsprogramm innerhalb ihrer Unternehmen an, in dem Benutzer schrittweise von Microsoft lync Server 2010 zu lync Server 2013 migriert werden.</span><span class="sxs-lookup"><span data-stu-id="535ba-105">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="535ba-106">Die Administratoren dieser Unternehmen kümmern sich um die Überwachung beider Versionen von lync Server, um sicherzustellen, dass alle Ihre Endbenutzer die bestmögliche Kommunikationserfahrung erhalten.</span><span class="sxs-lookup"><span data-stu-id="535ba-106">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="535ba-107">In diesem Szenario unterstützt das lync Server 2013 Management Pack einen Side-by-Side-Migrationspfad mit dem lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="535ba-107">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="535ba-108">In der lync Server 2010 wurden lync Server Computer über das im zentralen Verwaltungsspeicher gespeicherte Topologie-Dokument ermittelt.</span><span class="sxs-lookup"><span data-stu-id="535ba-108">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="535ba-109">In dieser Konfiguration würde ein einzelner Computer das vorhanden sein aller anderen lync Server Computer melden.</span><span class="sxs-lookup"><span data-stu-id="535ba-109">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="535ba-110">Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in lync Server 2010 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="535ba-110">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="535ba-111">Das bedeutet, dass sich jeder System Center-Agent im Prinzip selbst ermittelt und sein Vorhandensein dem System Center Operations Manager berichtet.</span><span class="sxs-lookup"><span data-stu-id="535ba-111">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="535ba-112">Das Verwenden der Ermittlung auf Computerebene vereinfacht die Verwaltung ihrer System Center-Infrastruktur und ermöglicht außerdem eine einfachere Koexistenz verschiedener Versionen der lync Server Management Packs (beispielsweise von Management Packs für lync Server 2010 und Management Packs für lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="535ba-112">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="535ba-113">Zur Unterstützung dieser Migration müssen Sie zunächst die vorhandene lync Server 2010 Überwachung aktualisieren, um Lücken bei der Berichterstattung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="535ba-113">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="535ba-114">Wählen Sie dazu einen vorhandenen lync Server 2010 Computer aus, um das zentrale Ermittlungsskript für die lync Server 2010 zu warten, bevor Sie den zentralen Verwaltungsspeicher auf lync Server 2013 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="535ba-114">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="535ba-115">Dies ist ein Prozess in vier Schritten:</span><span class="sxs-lookup"><span data-stu-id="535ba-115">This is a four-step process:</span></span>

1.  <span data-ttu-id="535ba-116">Aktualisieren Sie die lync Server 2010 Management Packs auf das kumulative Update 7.</span><span class="sxs-lookup"><span data-stu-id="535ba-116">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="535ba-117">Weisen Sie einen lync Server 2010 Computer an, das zentrale Ermittlungsskript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="535ba-117">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="535ba-118">Überschreiben Sie den zentralen Discovery Candidate im Microsoft lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="535ba-118">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="535ba-119">Stellen Sie sicher, dass der neue zentrale Ermittlungskandidat ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="535ba-119">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="535ba-120">Anweisen eines Lync Server 2010-Computer zum Ausführen eines zentralen Ermittlungsskripts</span><span class="sxs-lookup"><span data-stu-id="535ba-120">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="535ba-121">Wenn Sie einen nicht-zentralen Verwaltungsspeicher Computer (beispielsweise einen lync Server-Front-End-Server) für die zentrale Ermittlung benennen möchten, müssen Sie den folgenden Registrierungsschlüssel auf dem nicht-zentralen Verwaltungsspeicher Server erstellen:</span><span class="sxs-lookup"><span data-stu-id="535ba-121">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="535ba-122">HKLM \\ Software \\ Microsoft \\ Real-Time Communications \\ Health \\ CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="535ba-122">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="535ba-123">Sie können diesen Registrierungsschlüssel erstellen, indem Sie das folgende Verfahren durchführen:</span><span class="sxs-lookup"><span data-stu-id="535ba-123">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="535ba-124">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="535ba-124">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="535ba-125">Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="535ba-125">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="535ba-126">Erweitern Sie im Registrierungs- **Editor \_ HKEY lokaler \_ Computer**, erweitern Sie **Software**, erweitern Sie **Microsoft**, und erweitern Sie dann **Echtzeitkommunikation**.</span><span class="sxs-lookup"><span data-stu-id="535ba-126">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="535ba-p105">Klicken Sie mit der rechten Maustaste auf **Status**, klicken Sie dann auf **Neu**, und klicken Sie anschließend auf **Schlüssel**. Wenn der Schlüssel **Status** nicht vorhanden ist, klicken Sie mit der rechten Maustaste auf **Real-Time Communications**, zeigen auf **Neu**, und klicken Sie dann auf **Schlüssel**. Wenn der neue Schlüssel erstellt wurde, geben Sie "Status" ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="535ba-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="535ba-130">Geben Sie **CentralDiscoveryCandidate** ein, nachdem der neue Schlüssel erstellt wurde, und drücken Sie die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="535ba-130">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="535ba-131">Es kann einige Stunden dauern, bis diese Änderung vom Computer übernommen wurde.</span><span class="sxs-lookup"><span data-stu-id="535ba-131">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="535ba-132">Damit die Änderungen sofort wirksam werden, sollte der Health Agent-Dienst beendet und dann erneut gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="535ba-132">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="535ba-133">Führen Sie auf dem lync Server 2010 Computer das folgende Verfahren aus, um den Integritäts-Agent-Dienst neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="535ba-133">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="535ba-134">Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="535ba-134">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="535ba-135">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="535ba-135">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="535ba-p107">Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="535ba-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="535ba-138">Außer Kraft setzen des zentralen Ermittlungskandidaten im Lync Server 2010 Management Pack</span><span class="sxs-lookup"><span data-stu-id="535ba-138">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="535ba-139">Nachdem Sie einen lync Server 2010 Computer angewiesen haben, auf lync Server 2010 Computern zu berichten, müssen Sie das lync Server 2010 Management Pack auch über diese Änderung informieren.</span><span class="sxs-lookup"><span data-stu-id="535ba-139">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="535ba-140">Dafür müssen Sie im Management Pack eine Außerkraftsetzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="535ba-140">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="535ba-141">Führen Sie dafür die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="535ba-141">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="535ba-142">Klicken Sie in der Operations Manager-Konsole auf **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="535ba-142">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="535ba-143">Erweitern Sie in der Registerkarte "Konfiguration" die Option **Management Pack-Objekte**, klicken Sie auf **Objektermittlungen** und anschließend auf **Bereiche**.</span><span class="sxs-lookup"><span data-stu-id="535ba-143">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="535ba-144">Wählen Sie im Dialogfeld **Management Pack-Objekte in Bereiche einteilen** das Element mit dem Ziel-**LS-Ermittlungskandidat** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="535ba-144">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="535ba-145">Beachten Sie, dass ls Discovery Candidate nur angezeigt wird, wenn Sie das lync Server 2010 Management Pack installiert haben.</span><span class="sxs-lookup"><span data-stu-id="535ba-145">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="535ba-146">Klicken Sie mit der rechten Maustaste in der Operations Manager-Konsole auf **LS-Ermittlungskandidat**, zeigen Sie auf **Außerkraftsetzungen**, zeigen Sie auf **Objektermittlung außer Kraft setzen**, und klicken Sie anschließend auf **Für alle Objekte der Klasse: LS-Ermittlungskandidat**.</span><span class="sxs-lookup"><span data-stu-id="535ba-146">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="535ba-147">Aktivieren Sie im Dialogfeld **Außerkraftsetzungseigenschaften** das Kontrollkästchen **Außerkraftsetzung** neben dem Parameter **Central Discovery WatcherNode Fqdn**.</span><span class="sxs-lookup"><span data-stu-id="535ba-147">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="535ba-148">Geben Sie den vollqualifizierten Domänennamen des lync Server 2010 Computers in die Felder **Außerkraftsetzungswert** und **effektiver Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="535ba-148">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="535ba-149">Aktivieren Sie das Kontrollkästchen **Erzwungen**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="535ba-149">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="535ba-p111">Nachdem die Außerkraftsetzung erstellt wurde, müssen Sie den Integritätsdienst auf dem Stammverwaltungsserver neu starten. Führen Sie die folgenden Schritte auf dem Stammverwaltungsserver aus, um den Integritätsdienst neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="535ba-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="535ba-152">Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="535ba-152">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="535ba-153">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="535ba-153">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="535ba-p112">Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="535ba-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="535ba-156">So wird sichergestellt, dass der neue zentrale Ermittlungskandidat ermittelt wurde</span><span class="sxs-lookup"><span data-stu-id="535ba-156">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="535ba-157">Der letzte Schritt vor dem Upgrade des zentralen Verwaltungsspeichers besteht darin, sicherzustellen, dass der neue zentrale Ermittlungs Kandidat vom lync Server 2010 Management Pack erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="535ba-157">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="535ba-158">Öffnen Sie dafür die Operations Manager-Konsole, und klicken Sie auf "Überwachung".</span><span class="sxs-lookup"><span data-stu-id="535ba-158">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="535ba-159">Erweitern Sie in der Registerkarte "Überwachung" die Option **Microsoft Lync Server 2010 Health**, erweitern Sie dann **Topologieerkennung**, und klicken Sie dann auf **Ansicht Ermittlungsstatus**.</span><span class="sxs-lookup"><span data-stu-id="535ba-159">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="535ba-160">Stellen Sie sicher, dass eine Zeile in der Anzeige über einen **Pfad** verfügt, der den vollqualifizierten Domänennamen des zentralen Ermittlungskandidaten auflistet.</span><span class="sxs-lookup"><span data-stu-id="535ba-160">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="535ba-161">Es sollte auch sichergestellt werden, dass als Computerstatus **Fehlerfrei** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="535ba-161">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

