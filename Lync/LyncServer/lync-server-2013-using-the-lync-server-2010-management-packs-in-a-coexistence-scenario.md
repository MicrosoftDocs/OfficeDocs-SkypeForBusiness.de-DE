---
title: Verwenden der lync Server 2010-Verwaltungspakete in einem Koexistenz-Szenario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 159aaa55e61068356701abaed3c0a67a60265c75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="821d1-102">Verwenden der lync Server 2010-Verwaltungspakete in einem Koexistenz-Szenario</span><span class="sxs-lookup"><span data-stu-id="821d1-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="821d1-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="821d1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="821d1-104">Viele Kunden nehmen ein Rollout-Programm innerhalb ihrer Unternehmen an, in dem Benutzer schrittweise von Microsoft lync Server 2010 zu lync Server 2013 migriert werden.</span><span class="sxs-lookup"><span data-stu-id="821d1-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="821d1-105">Die Administratoren in diesen Unternehmen kümmern sich um die Überwachung beider lync Server-Versionen, um sicherzustellen, dass alle Endbenutzer die bestmögliche Kommunikationserfahrung erhalten.</span><span class="sxs-lookup"><span data-stu-id="821d1-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="821d1-106">In diesem Szenario unterstützt das lync Server 2013-Management Pack einen parallelen Migrationspfad mit dem lync Server 2010-Management Pack.</span><span class="sxs-lookup"><span data-stu-id="821d1-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="821d1-107">In lync Server 2010 wurden lync Server-Computer über das Topologie-Dokument ermittelt, das mit dem zentralen Verwaltungsspeicher gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="821d1-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="821d1-108">In dieser Konfiguration meldet ein einzelner Computer das vorhanden sein aller anderen lync Server-Computer.</span><span class="sxs-lookup"><span data-stu-id="821d1-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="821d1-109">Die Management Packs für lync Server 2013 verwenden jetzt die Ermittlung auf Computerebene anstelle des zentralen Ermittlungsmechanismus, der in lync Server 2010 verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="821d1-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="821d1-110">Dies bedeutet, dass sich jeder System Center-Agent im wesentlichen selbst erkennt und seine Existenz an System Center Operations Manager meldet.</span><span class="sxs-lookup"><span data-stu-id="821d1-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="821d1-111">Die Verwendung der Ermittlung auf Computerebene vereinfacht die Verwaltung ihrer System Center-Infrastruktur und ermöglicht auch die unterschiedlichen Versionen der lync Server-Verwaltungspakete (beispielsweise Management Packs für lync Server 2010 und Management Packs für lync Server 2013). , um einfacher koexistieren zu können.</span><span class="sxs-lookup"><span data-stu-id="821d1-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="821d1-112">Um diese Migration zu unterstützen, müssen Sie zunächst Ihre vorhandene lync Server 2010-Überwachung aktualisieren, um Lücken in der Berichterstattung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="821d1-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="821d1-113">Wählen Sie dazu einen vorhandenen lync Server 2010-Computer aus, um das zentrale Ermittlungsskript für den lync Server 2010 zu warten, bevor Sie den zentralen Verwaltungsspeicher auf lync Server 2013 aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="821d1-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="821d1-114">Hierbei handelt es sich um einen vierstufigen Prozess:</span><span class="sxs-lookup"><span data-stu-id="821d1-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="821d1-115">Aktualisieren Sie die lync Server 2010-Verwaltungspakete auf Kumulatives Update 7.</span><span class="sxs-lookup"><span data-stu-id="821d1-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="821d1-116">Weisen Sie einen lync Server 2010-Computer an, das zentrale Ermittlungsskript auszuführen.</span><span class="sxs-lookup"><span data-stu-id="821d1-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="821d1-117">Überschreiben Sie den zentralen Ermittlungs Kandidaten im Microsoft lync Server 2010-Management Pack.</span><span class="sxs-lookup"><span data-stu-id="821d1-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="821d1-118">Überprüfen Sie, ob der neue Central Discovery-Kandidat gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="821d1-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="821d1-119">Anweisen eines lync Server 2010-Computers zum Ausführen des zentralen Ermittlungsskripts</span><span class="sxs-lookup"><span data-stu-id="821d1-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="821d1-120">Wenn Sie einen nicht zentralen Verwaltungsspeicher Computer benennen möchten (beispielsweise einen lync Server-Front-End-Server), der die zentrale Ermittlung behandeln soll, müssen Sie den folgenden Registrierungsschlüssel auf dem nicht zentralen Verwaltungsspeicher Server erstellen:</span><span class="sxs-lookup"><span data-stu-id="821d1-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="821d1-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="821d1-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="821d1-122">Sie können diesen Registrierungsschlüssel erstellen, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="821d1-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="821d1-123">Klicken Sie auf **Start** und dann auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="821d1-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="821d1-124">Geben Sie im Dialogfeld **Ausführen** den **Befehl regedit** ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="821d1-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="821d1-125">Erweitern Sie im Registrierungs- **Editor\_HKEY\_lokaler Computer**, erweitern Sie **Software**, erweitern Sie **Microsoft**, und erweitern Sie dann die **Echtzeitkommunikation**.</span><span class="sxs-lookup"><span data-stu-id="821d1-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="821d1-126">Klicken Sie mit der rechten Maustaste auf **Status**, klicken Sie auf **neu**, und klicken Sie dann auf **Taste**.</span><span class="sxs-lookup"><span data-stu-id="821d1-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="821d1-127">Wenn der **Integritäts** Schlüssel nicht vorhanden ist, klicken Sie mit der rechten Maustaste auf **Echtzeitkommunikation**, zeigen Sie auf **neu**, und klicken Sie dann auf **Taste**.</span><span class="sxs-lookup"><span data-stu-id="821d1-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="821d1-128">Wenn Sie den neuen Schlüssel erstellen, geben Sie Gesundheit ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="821d1-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="821d1-129">Nachdem der neue Schlüssel erstellt wurde, geben Sie **CentralDiscoveryCandidate** ein, und drücken Sie dann die EINGABETASTE, um den Schlüssel umzubenennen.</span><span class="sxs-lookup"><span data-stu-id="821d1-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="821d1-130">Es kann den Computer mehrere Stunden dauern, bis diese Änderung abgeholt wird.</span><span class="sxs-lookup"><span data-stu-id="821d1-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="821d1-131">Damit die Änderung sofort wirksam wird, beenden Sie den Integritäts-Agent-Dienst, und starten Sie ihn dann erneut.</span><span class="sxs-lookup"><span data-stu-id="821d1-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="821d1-132">Führen Sie die folgenden Schritte auf dem lync Server 2010-Computer aus, um den Integritäts-Agent-Dienst erneut zu starten:</span><span class="sxs-lookup"><span data-stu-id="821d1-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="821d1-133">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="821d1-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="821d1-134">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="821d1-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="821d1-135">Es wird eine Meldung angezeigt, die besagt, dass "der System Center-Verwaltungsdienst beendet wird", gefolgt von einer zweiten Meldung, die besagt, dass der Dienst angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="821d1-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="821d1-136">Nachdem der Dienst beendet wurde, können Sie ihn erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="821d1-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="821d1-137">Überschreiben des zentralen Ermittlungs Kandidaten im lync Server 2010-Management Pack</span><span class="sxs-lookup"><span data-stu-id="821d1-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="821d1-138">Nachdem Sie einen lync Server 2010-Computer angewiesen haben, auf lync Server 2010-Computern zu berichten, müssen Sie das lync Server 2010-Management Pack auch über diese Änderung informieren.</span><span class="sxs-lookup"><span data-stu-id="821d1-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="821d1-139">Dazu müssen Sie im Management Pack eine Außerkraftsetzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="821d1-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="821d1-140">Dazu können Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="821d1-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="821d1-141">Klicken Sie in der Operations Manager-Konsole auf **Dokumenterstellung**.</span><span class="sxs-lookup"><span data-stu-id="821d1-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="821d1-142">Erweitern Sie auf der Registerkarte Dokumenterstellung den Knoten **Management Pack-Objekte**, klicken Sie auf **Objektermittlungen**, und klicken Sie dann auf **Bereich**.</span><span class="sxs-lookup"><span data-stu-id="821d1-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="821d1-143">Wählen Sie im Dialogfeld **Scope Management Pack-Objekte** das Element mit dem Ziel **ls Discovery Candidate** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="821d1-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="821d1-144">Beachten Sie, dass der ls-Ermittlungs Kandidat nur angezeigt wird, wenn Sie das lync Server 2010-Management Pack installiert haben.</span><span class="sxs-lookup"><span data-stu-id="821d1-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="821d1-145">Klicken Sie in der Operations Manager-Konsole mit der rechten Maustaste auf **ls Discovery Candidate**, zeigen Sie auf **außer Kraft**setzungen, zeigen Sie auf **Objektermittlung außer Kraft setzen**, und klicken Sie dann auf **für alle Objekte der Klasse: ls Discovery Candidate**.</span><span class="sxs-lookup"><span data-stu-id="821d1-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="821d1-146">Aktivieren Sie im Dialogfeld **Eigenschaften außer Kraft setzen** das Kontrollkästchen **außer Kraft setzen** neben dem FQDN des Parameters **Central Discovery WatcherNode**.</span><span class="sxs-lookup"><span data-stu-id="821d1-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="821d1-147">Geben Sie den vollqualifizierten Domänennamen des lync Server 2010-Computers in die Felder **Außerkraftsetzungswert** und **effektiver Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="821d1-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="821d1-148">Aktivieren Sie das Kontrollkästchen **erzwungen** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="821d1-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="821d1-149">Nachdem Sie die Außerkraftsetzung erstellt haben, müssen Sie den Integritätsdienst auf dem Stamm Verwaltungs Server erneut starten.</span><span class="sxs-lookup"><span data-stu-id="821d1-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="821d1-150">Führen Sie den folgenden Vorgang auf dem Stamm Verwaltungs Server aus, um den Integritätsdienst erneut zu starten:</span><span class="sxs-lookup"><span data-stu-id="821d1-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="821d1-151">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Zubehör**, klicken Sie mit der rechten Maustaste auf **Eingabeaufforderung**, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="821d1-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="821d1-152">Geben Sie im Konsolenfenster den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="821d1-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="821d1-153">Es wird eine Meldung angezeigt, die besagt, dass "der System Center-Verwaltungsdienst beendet wird", gefolgt von einer zweiten Meldung, die besagt, dass der Dienst angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="821d1-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="821d1-154">Nachdem der Dienst beendet wurde, können Sie ihn erneut starten, indem Sie den folgenden Befehl eingeben und die EINGABETASTE drücken:</span><span class="sxs-lookup"><span data-stu-id="821d1-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="821d1-155">Überprüfen, ob der neue zentrale Discovery Candidate erkannt wurde</span><span class="sxs-lookup"><span data-stu-id="821d1-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="821d1-156">Der letzte Schritt vor dem Upgrade des zentralen Verwaltungsspeichers besteht darin, sicherzustellen, dass der neue zentrale Discovery-Kandidat vom lync Server 2010-Management Pack erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="821d1-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="821d1-157">Öffnen Sie dazu die Operations Manager-Konsole, und klicken Sie dann auf Überwachung.</span><span class="sxs-lookup"><span data-stu-id="821d1-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="821d1-158">Erweitern Sie auf der Registerkarte Überwachung den **Status Microsoft lync Server 2010**, erweitern Sie **Topologie Discovery**, und klicken Sie dann auf **Ermittlungsstatus Ansicht**.</span><span class="sxs-lookup"><span data-stu-id="821d1-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="821d1-159">Überprüfen Sie, ob eine Zeile in der Anzeige einen **Pfad** enthält, in dem der vollqualifizierte Domänenname des zentralen Ermittlungs Kandidaten aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="821d1-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="821d1-160">Sie sollten auch sicherstellen, dass der Computerzustand als **Fehler**freigemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="821d1-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

