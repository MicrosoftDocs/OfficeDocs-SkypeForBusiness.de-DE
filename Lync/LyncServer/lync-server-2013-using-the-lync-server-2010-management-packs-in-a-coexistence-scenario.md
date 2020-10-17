---
title: Verwenden der lync Server 2010 Management Packs in einem Szenario für die Koexistenz
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
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529922"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="1c385-102">Verwenden der lync Server 2010 Management Packs in einem Szenario für die Koexistenz</span><span class="sxs-lookup"><span data-stu-id="1c385-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c385-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1c385-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1c385-104">Viele Kunden nehmen ein Einführungsprogramm innerhalb ihrer Unternehmen an, in dem Benutzer schrittweise von Microsoft lync Server 2010 zu lync Server 2013 migriert werden.</span><span class="sxs-lookup"><span data-stu-id="1c385-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="1c385-105">Die Administratoren dieser Unternehmen kümmern sich um die Überwachung beider Versionen von lync Server, um sicherzustellen, dass alle Ihre Endbenutzer die bestmögliche Kommunikationserfahrung erhalten.</span><span class="sxs-lookup"><span data-stu-id="1c385-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="1c385-106">In diesem Szenario unterstützt das lync Server 2013 Management Pack einen Side-by-Side-Migrationspfad mit dem lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="1c385-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="1c385-107">In der lync Server 2010 wurden lync Server Computer über das im zentralen Verwaltungsspeicher gespeicherte Topologie-Dokument ermittelt.</span><span class="sxs-lookup"><span data-stu-id="1c385-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="1c385-108">In dieser Konfiguration würde ein einzelner Computer das vorhanden sein aller anderen lync Server Computer melden.</span><span class="sxs-lookup"><span data-stu-id="1c385-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="1c385-109">Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in lync Server 2010 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="1c385-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="1c385-110">Das bedeutet, dass sich jeder System Center-Agent im Prinzip selbst ermittelt und sein Vorhandensein dem System Center Operations Manager berichtet.</span><span class="sxs-lookup"><span data-stu-id="1c385-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="1c385-111">Das Verwenden der Ermittlung auf Computerebene vereinfacht die Verwaltung ihrer System Center-Infrastruktur und ermöglicht außerdem eine einfachere Koexistenz verschiedener Versionen der lync Server Management Packs (beispielsweise von Management Packs für lync Server 2010 und Management Packs für lync Server 2013).</span><span class="sxs-lookup"><span data-stu-id="1c385-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="1c385-112">Zur Unterstützung dieser Migration müssen Sie zunächst die vorhandene lync Server 2010 Überwachung aktualisieren, um Lücken bei der Berichterstattung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="1c385-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="1c385-113">Wählen Sie dazu einen vorhandenen lync Server 2010 Computer aus, um das zentrale Ermittlungsskript für die lync Server 2010 zu warten, bevor Sie den zentralen Verwaltungsspeicher auf lync Server 2013 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1c385-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="1c385-114">Dies ist ein Prozess in vier Schritten:</span><span class="sxs-lookup"><span data-stu-id="1c385-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="1c385-115">Aktualisieren Sie die lync Server 2010 Management Packs auf das kumulative Update 7.</span><span class="sxs-lookup"><span data-stu-id="1c385-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="1c385-116">Weisen Sie einen lync Server 2010 Computer an, das zentrale Ermittlungsskript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1c385-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="1c385-117">Überschreiben Sie den zentralen Discovery Candidate im Microsoft lync Server 2010 Management Pack.</span><span class="sxs-lookup"><span data-stu-id="1c385-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="1c385-118">Stellen Sie sicher, dass der neue zentrale Ermittlungskandidat ermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1c385-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="1c385-119">Anweisen eines Lync Server 2010-Computer zum Ausführen eines zentralen Ermittlungsskripts</span><span class="sxs-lookup"><span data-stu-id="1c385-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="1c385-120">Wenn Sie einen nicht-zentralen Verwaltungsspeicher Computer (beispielsweise einen lync Server-Front-End-Server) für die zentrale Ermittlung benennen möchten, müssen Sie den folgenden Registrierungsschlüssel auf dem nicht-zentralen Verwaltungsspeicher Server erstellen:</span><span class="sxs-lookup"><span data-stu-id="1c385-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="1c385-121">HKLM \\ Software \\ Microsoft \\ Real-Time Communications \\ Health \\ CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="1c385-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="1c385-122">Sie können diesen Registrierungsschlüssel erstellen, indem Sie das folgende Verfahren durchführen:</span><span class="sxs-lookup"><span data-stu-id="1c385-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="1c385-123">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1c385-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="1c385-124">Geben Sie im Dialogfeld **Ausführen** den Befehl **reged** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="1c385-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="1c385-125">Erweitern Sie im Registrierungs- **Editor \_ HKEY lokaler \_ Computer**, erweitern Sie **Software**, erweitern Sie **Microsoft**, und erweitern Sie dann **Echtzeitkommunikation**.</span><span class="sxs-lookup"><span data-stu-id="1c385-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="1c385-p105">Klicken Sie mit der rechten Maustaste auf **Status**, klicken Sie dann auf **Neu**, und klicken Sie anschließend auf **Schlüssel**. Wenn der Schlüssel **Status** nicht vorhanden ist, klicken Sie mit der rechten Maustaste auf **Real-Time Communications**, zeigen auf **Neu**, und klicken Sie dann auf **Schlüssel**. Wenn der neue Schlüssel erstellt wurde, geben Sie "Status" ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="1c385-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="1c385-129">Geben Sie **CentralDiscoveryCandidate** ein, nachdem der neue Schlüssel erstellt wurde, und drücken Sie die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="1c385-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="1c385-130">Es kann einige Stunden dauern, bis diese Änderung vom Computer übernommen wurde.</span><span class="sxs-lookup"><span data-stu-id="1c385-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="1c385-131">Damit die Änderungen sofort wirksam werden, sollte der Health Agent-Dienst beendet und dann erneut gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="1c385-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="1c385-132">Führen Sie auf dem lync Server 2010 Computer das folgende Verfahren aus, um den Integritäts-Agent-Dienst neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="1c385-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="1c385-133">Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1c385-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="1c385-134">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1c385-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="1c385-p107">Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="1c385-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="1c385-137">Außer Kraft setzen des zentralen Ermittlungskandidaten im Lync Server 2010 Management Pack</span><span class="sxs-lookup"><span data-stu-id="1c385-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="1c385-138">Nachdem Sie einen lync Server 2010 Computer angewiesen haben, auf lync Server 2010 Computern zu berichten, müssen Sie das lync Server 2010 Management Pack auch über diese Änderung informieren.</span><span class="sxs-lookup"><span data-stu-id="1c385-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="1c385-139">Dafür müssen Sie im Management Pack eine Außerkraftsetzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c385-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="1c385-140">Führen Sie dafür die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="1c385-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="1c385-141">Klicken Sie in der Operations Manager-Konsole auf **Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1c385-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="1c385-142">Erweitern Sie in der Registerkarte "Konfiguration" die Option **Management Pack-Objekte**, klicken Sie auf **Objektermittlungen** und anschließend auf **Bereiche**.</span><span class="sxs-lookup"><span data-stu-id="1c385-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="1c385-143">Wählen Sie im Dialogfeld **Management Pack-Objekte in Bereiche einteilen** das Element mit dem Ziel-**LS-Ermittlungskandidat** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c385-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="1c385-144">Beachten Sie, dass ls Discovery Candidate nur angezeigt wird, wenn Sie das lync Server 2010 Management Pack installiert haben.</span><span class="sxs-lookup"><span data-stu-id="1c385-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="1c385-145">Klicken Sie mit der rechten Maustaste in der Operations Manager-Konsole auf **LS-Ermittlungskandidat**, zeigen Sie auf **Außerkraftsetzungen**, zeigen Sie auf **Objektermittlung außer Kraft setzen**, und klicken Sie anschließend auf **Für alle Objekte der Klasse: LS-Ermittlungskandidat**.</span><span class="sxs-lookup"><span data-stu-id="1c385-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="1c385-146">Aktivieren Sie im Dialogfeld **Außerkraftsetzungseigenschaften** das Kontrollkästchen **Außerkraftsetzung** neben dem Parameter **Central Discovery WatcherNode Fqdn**.</span><span class="sxs-lookup"><span data-stu-id="1c385-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="1c385-147">Geben Sie den vollqualifizierten Domänennamen des lync Server 2010 Computers in die Felder **Außerkraftsetzungswert** und **effektiver Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="1c385-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="1c385-148">Aktivieren Sie das Kontrollkästchen **Erzwungen**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c385-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="1c385-p111">Nachdem die Außerkraftsetzung erstellt wurde, müssen Sie den Integritätsdienst auf dem Stammverwaltungsserver neu starten. Führen Sie die folgenden Schritte auf dem Stammverwaltungsserver aus, um den Integritätsdienst neu zu starten:</span><span class="sxs-lookup"><span data-stu-id="1c385-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="1c385-151">Klicken Sie nacheinander auf **Start**, **Alle Programme** und **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **Als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1c385-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="1c385-152">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="1c385-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="1c385-p112">Es wird eine Meldung mit dem Text "Der System Center-Verwaltungsdienst wird beendet" gefolgt von einer zweiten Meldung angezeigt, in der mitgeteilt wird, dass der Dienst beendet wurde. Nachdem der Dienst gestoppt wurde, können Sie diesen erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="1c385-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="1c385-155">So wird sichergestellt, dass der neue zentrale Ermittlungskandidat ermittelt wurde</span><span class="sxs-lookup"><span data-stu-id="1c385-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="1c385-156">Der letzte Schritt vor dem Upgrade des zentralen Verwaltungsspeichers besteht darin, sicherzustellen, dass der neue zentrale Ermittlungs Kandidat vom lync Server 2010 Management Pack erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="1c385-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="1c385-157">Öffnen Sie dafür die Operations Manager-Konsole, und klicken Sie auf "Überwachung".</span><span class="sxs-lookup"><span data-stu-id="1c385-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="1c385-158">Erweitern Sie in der Registerkarte "Überwachung" die Option **Microsoft Lync Server 2010 Health**, erweitern Sie dann **Topologieerkennung**, und klicken Sie dann auf **Ansicht Ermittlungsstatus**.</span><span class="sxs-lookup"><span data-stu-id="1c385-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="1c385-159">Stellen Sie sicher, dass eine Zeile in der Anzeige über einen **Pfad** verfügt, der den vollqualifizierten Domänennamen des zentralen Ermittlungskandidaten auflistet.</span><span class="sxs-lookup"><span data-stu-id="1c385-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="1c385-160">Es sollte auch sichergestellt werden, dass als Computerstatus **Fehlerfrei** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1c385-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

