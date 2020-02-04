---
title: 'Lync Server 2013: Anhang B: Verwalten einer Survivable Branch Appliance'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix B: Managing a Survivable Branch Appliance'
ms:assetid: 2ec9d505-6d39-491c-9524-8cf36866b855
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425797(v=OCS.15)
ms:contentKeyID: 48183773
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b16d4c55197785a6df12ad2031dbd2e624501ebd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="8c3ca-102">Anhang B: Verwalten einer Survivable Branch Appliance in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c3ca-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c3ca-103">_**Letztes Änderungsdatum des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="8c3ca-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="8c3ca-104">In diesem Thema werden die Verfahren zum Verwalten einer Survivable Branch-Appliance beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="8c3ca-105">Insbesondere wird beschrieben, wie eine überlebensfähige Branch Appliance ersetzt und umbenannt wird und wie der lync Server 2013-Front-End-Pool geändert wird, dem die Survivable Branch-Appliance zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="8c3ca-106">So ersetzen Sie eine Survivable Branch-Appliance</span><span class="sxs-lookup"><span data-stu-id="8c3ca-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="8c3ca-107">Beenden Sie alle lync Server 2013-Dienste auf der Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="8c3ca-108">(Weitere Informationen finden Sie in der Vendor-Dokumentation für Survivable Branch Appliances.)</span><span class="sxs-lookup"><span data-stu-id="8c3ca-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="8c3ca-109">Empfohlen Entfernen Sie die Survivable Branch-Appliance aus der Domäne.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="8c3ca-110">Führen Sie die folgenden Schritte aus, um das Computerobjekt Survivable Branch Appliance in den Active Directory-Domänendiensten zu löschen:</span><span class="sxs-lookup"><span data-stu-id="8c3ca-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="8c3ca-111">Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Unternehmensadministratoren" an.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="8c3ca-112">Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="8c3ca-113">Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance-Objekt, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="8c3ca-114">Fügen Sie das Computerobjekt der Survivable Branch Appliance erneut hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="8c3ca-115">(Weitere Informationen finden Sie unter [Hinzufügen einer Survivable Branch-Appliance zu Active Directory in lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span><span class="sxs-lookup"><span data-stu-id="8c3ca-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="8c3ca-116">Warten Sie, bis die Active Directory-Replikation durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="8c3ca-117">Öffnen Sie die lync Server-Verwaltungsshell, und geben Sie **enable-CSTopology**ein.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="8c3ca-118">Verbinden Sie die neue Survivable Branch-Appliance mit dem Netzwerk, und führen Sie die Schritte unter [Bereitstelleneiner überlebensfähigen Branch-Appliance oder eines Servers mit lync Server 2013-Central-Websiteaufgaben](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) aus, und [Stellen Sie eine Survivable Branch-Appliance oder einen Server mit lync Server 2013-Branch Site-Aufgabe bereit](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ca-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="8c3ca-119">So benennen Sie eine Survivable Branch-Appliance um</span><span class="sxs-lookup"><span data-stu-id="8c3ca-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="8c3ca-120">Verschieben von Benutzern auf die zentrale Website</span><span class="sxs-lookup"><span data-stu-id="8c3ca-120">Move users to the central site.</span></span> <span data-ttu-id="8c3ca-121">Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ca-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="8c3ca-122">Beenden Sie alle lync Server 2013-Dienste auf der Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="8c3ca-123">(Weitere Informationen finden Sie in der Vendor-Dokumentation für Survivable Branch Appliances.)</span><span class="sxs-lookup"><span data-stu-id="8c3ca-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="8c3ca-124">Führen Sie die folgenden Schritte aus, um die Survivable Branch-Appliance aus der Topologie zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="8c3ca-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="8c3ca-125">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="8c3ca-126">Erweitern Sie in der Konsolenstruktur **Verzweigungs Websites**, klicken Sie auf die Survivable Branch-Appliance, und klicken Sie dann im Bereich "Aktion" auf **Löschen** .</span><span class="sxs-lookup"><span data-stu-id="8c3ca-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="8c3ca-127">Entfernen Sie die Survivable Branch-Appliance aus der Domäne.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="8c3ca-128">Führen Sie die folgenden Schritte aus, um das Computerobjekt Survivable Branch Appliance in Active Directory zu löschen:</span><span class="sxs-lookup"><span data-stu-id="8c3ca-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="8c3ca-129">Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Unternehmensadministratoren" an.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="8c3ca-130">Klicken Sie auf **Start**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **Active Directory-Benutzer und-Computer**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="8c3ca-131">Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance-Objekt, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="8c3ca-132">Wiederherstellen der Überlebenden Branch-Appliance auf die Werkseinstellungen</span><span class="sxs-lookup"><span data-stu-id="8c3ca-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="8c3ca-133">(Weitere Informationen finden Sie in der Vendor-Dokumentation für Survivable Branch Appliances.)</span><span class="sxs-lookup"><span data-stu-id="8c3ca-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="8c3ca-134">Führen Sie die Schritte unter [Bereitstelleneiner überlebensfähigen Zweigstelle oder eines Servers mit lync Server 2013 – zentrale Websiteaufgaben](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) aus, und [Stellen Sie eine Survivable Branch Appliance oder einen Server mit lync Server 2013-Branch Site Task bereit](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ca-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="8c3ca-135">Verschieben Sie Benutzer in die umbenannte Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="8c3ca-136">Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ca-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="8c3ca-137">So ändern Sie den lync Server-Front-End-Pool, dem die Survivable Branch-Appliance zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="8c3ca-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="8c3ca-138">Verschieben Sie Benutzer aus der Survivable Branch-Appliance in den lync Server-Front-End-Pool am zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="8c3ca-139">Ausführliche Informationen finden Sie unter [Verschieben von Benutzern in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ca-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="8c3ca-140">Beenden Sie alle lync Server-Dienste auf der Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="8c3ca-141">(Weitere Informationen finden Sie in der Dokumentation zum Survivable Branch Appliance-Hersteller).</span><span class="sxs-lookup"><span data-stu-id="8c3ca-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="8c3ca-142">Führen Sie die folgenden Schritte aus, um den lync Server-Front-End-Pool zu aktualisieren, dem die Survivable Branch-Appliance zugeordnet ist:</span><span class="sxs-lookup"><span data-stu-id="8c3ca-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="8c3ca-143">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="8c3ca-144">Erweitern Sie **Zweigstellen**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="8c3ca-145">Klicken Sie mit der rechten Maustaste auf das zu ändernde Survivable Branch Appliance-Objekt, und klicken Sie auf **Eigenschaften bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="8c3ca-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="8c3ca-146">Wählen Sie unter Widerstandsfähigkeit den neuen Front-End-Pool aus, dem die Survivable Branch-Appliance zugeordnet werden soll, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="8c3ca-147">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf die neue Survivable Branch-Appliance, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="8c3ca-148">Starten Sie alle lync Server-Dienste auf der Survivable Branch-Appliance neu.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="8c3ca-149">Testen Sie die Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="8c3ca-150">Ausführliche Informationen finden Sie unter [private Benutzer auf einer Survivable Branch-Appliance oder einem Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="8c3ca-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="8c3ca-151">Verschieben Sie Benutzer aus dem lync Server-Front-End-Pool am zentralen Standort in die Survivable Branch-Appliance.</span><span class="sxs-lookup"><span data-stu-id="8c3ca-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

