---
title: Verbinden einer Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c76e70278d709b52388c22714db85f9bae4610d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="f0005-102">Verbinden einer Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="f0005-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0005-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f0005-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f0005-104">Jede Survivable Branch Appliance (SBA) ist mit einem Front-End-Pool verbunden, der als Backup-Registrar für die SBA fungiert.</span><span class="sxs-lookup"><span data-stu-id="f0005-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="f0005-105">Wenn der Front-End-Pool zu lync Server 2013 migriert wird, muss die SBA vom lync Server 2010-Front-End-Pool nicht zugeordnet werden, während der Pool aktualisiert wird, nachdem der Pool zu lync Server 2013 migriert wurde, kann die SBA erneut mit dem aktualisierten Front-End-Pool verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="f0005-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="f0005-106">Dies umfasst das Löschen des SBA aus der Legacy lync Server 2010-Topologie im Topologie-Generator und das anschließende Hinzufügen der SBA zur lync Server 2013-Topologie.</span><span class="sxs-lookup"><span data-stu-id="f0005-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="f0005-107">Benutzer, die auf dem Legacy-lync Server 2010 SBA verwaltet werden, müssen zuerst in einen anderen Front-End-Pool verschoben werden, bevor Sie die SBA aus der Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="f0005-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="f0005-108">Sobald die SBA zur lync Server 2013-Topologie hinzugefügt wurde, können diese Benutzer wieder in die SBA verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="f0005-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="f0005-109">Nachfolgend werden die folgenden Schritte zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="f0005-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="f0005-110">Verschieben Sie Branch-Benutzer, die sich auf der Legacy-SBA lync Server 2010 befinden, in einen anderen Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="f0005-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="f0005-111">Entfernen Sie SBA aus der Legacy lync Server 2010-Topologie, um den vorhandenen Front-End-Pool als Sicherungs Registrierungsstelle zu trennen.</span><span class="sxs-lookup"><span data-stu-id="f0005-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="f0005-112">Fügen Sie SBA zur lync Server 2013-Topologie hinzu, und konfigurieren Sie diesen neuen Front-End-Pool als Sicherungs Registrierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="f0005-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="f0005-113">Verschieben Sie die Benutzer der Verzweigung in den neuen lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="f0005-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="f0005-114">**Hinzufügen der lync Server 2010 SBA-Verzweigungs Website zu Ihrer Topologie**</span><span class="sxs-lookup"><span data-stu-id="f0005-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="f0005-115">Öffnen Sie den **Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="f0005-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="f0005-116">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Verzweigungs Websites**, und klicken Sie dann auf **neue Verzweigungs Website**.</span><span class="sxs-lookup"><span data-stu-id="f0005-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="f0005-117">Klicken Sie im Dialogfeld **neue Verzweigungs Website definieren** auf **Name**, und geben Sie dann den Namen der Verzweigungs Website ein.</span><span class="sxs-lookup"><span data-stu-id="f0005-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="f0005-118">Optional Klicken Sie auf **Beschreibung**, und geben Sie eine aussagekräftige Beschreibung für die Verzweigungs Website ein.</span><span class="sxs-lookup"><span data-stu-id="f0005-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="f0005-119">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f0005-119">Click **Next**.</span></span>

6.  <span data-ttu-id="f0005-120">Optional Führen Sie im nächsten Dialogfeld **neue Verzweigungs Website definieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f0005-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="f0005-121">Klicken Sie auf **Stadt**, und geben Sie dann den Namen des Orts ein, in dem sich die Zweigstelle befindet.</span><span class="sxs-lookup"><span data-stu-id="f0005-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="f0005-122">Klicken Sie auf **Bundesland/Region**, und geben Sie dann den Namen des Bundeslands oder der Region ein, in dem sich die Verzweigungs Website befindet.</span><span class="sxs-lookup"><span data-stu-id="f0005-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="f0005-123">Klicken Sie auf **Landesvorwahl**, und geben Sie dann den zweistelligen anrufcode für das Land/die Region ein, in dem sich die Zweigstelle befindet.</span><span class="sxs-lookup"><span data-stu-id="f0005-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="f0005-124">Klicken Sie auf **weiter**, und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f0005-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="f0005-125">Wenn Sie eine überlebensfähige lync 2010-Branch-Appliance oder einen Server auf dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird.</span><span class="sxs-lookup"><span data-stu-id="f0005-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="f0005-126">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f0005-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="f0005-127">So ordnen Sie den Legacy-lync Server 2010 SBA dem lync Server 2013-Front-End-Pool zu:</span><span class="sxs-lookup"><span data-stu-id="f0005-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="f0005-128">Erweitern Sie die erstellte Verzweigungs Website.</span><span class="sxs-lookup"><span data-stu-id="f0005-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="f0005-129">Klicken Sie mit der rechten Maustaste auf **lync Server 2010** , und klicken Sie dann auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="f0005-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="f0005-130">Klicken Sie auf **Survivable Branch Appliance...**</span><span class="sxs-lookup"><span data-stu-id="f0005-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="f0005-131">Folgen Sie den Anweisungen im Assistenten, der geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f0005-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="f0005-132">Informationen zu Assistenten Elementen finden Sie unter Definieren einer überlebensfähigen [Verzweigungs Einheit oder eines Servers in lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="f0005-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0005-133">Eine Survivable Branch-Appliance von lync Server 2010 kann nur einem lync Server 2010-Überwachungsspeicher zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f0005-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="f0005-134">Wenn Sie keine Survivable Branch-Appliance oder einen Server an dieser Website verwenden, deaktivieren Sie das Kontrollkästchen **neuen Überlebenden Assistenten öffnen, wenn dieser Assistent geschlossen** wird, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f0005-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="f0005-135">Wiederholen Sie die vorherigen Schritte für jede Verzweigungs Website, die Sie der Topologie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0005-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

