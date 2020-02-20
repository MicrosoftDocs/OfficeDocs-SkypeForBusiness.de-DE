---
title: 'Lync Server 2013: Anhang B: Verwalten eines Survivable Branch Appliance'
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
ms.openlocfilehash: df6e2dc473da81177dacb8d53ee673c9a5457c98
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-b-managing-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="ffbe5-102">Anhang B: Verwalten einer Survivable Branch Appliance in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffbe5-102">Appendix B: Managing a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffbe5-103">_**Letztes Änderungsstand des Themas:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="ffbe5-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="ffbe5-104">In diesem Thema werden die Verfahren zum Verwalten eines Survivable Branch Appliance beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-104">This topic describes the procedures for managing a Survivable Branch Appliance.</span></span> <span data-ttu-id="ffbe5-105">Insbesondere wird das ersetzen und Umbenennen eines Survivable Branch Appliance und das Ändern der lync Server 2013 Front-End-Pool, der das Survivable Branch Appliance zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-105">Specifically, how to replace and rename a Survivable Branch Appliance, and how to change the Lync Server 2013 Front End pool that the Survivable Branch Appliance is associated with.</span></span>

<div>

## <a name="to-replace-a-survivable-branch-appliance"></a><span data-ttu-id="ffbe5-106">So ersetzen Sie eine Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="ffbe5-106">To Replace a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="ffbe5-107">Beenden Sie alle lync Server 2013 Dienste auf dem Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-107">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="ffbe5-108">(Informationen hierzu finden Sie in der Herstellerdokumentation zur Survivable Branch Appliance.)</span><span class="sxs-lookup"><span data-stu-id="ffbe5-108">(See the Survivable Branch Appliance vendor documentation.)</span></span>

2.  <span data-ttu-id="ffbe5-109">Empfohlen Entfernen Sie die Survivable Branch Appliance aus der Domäne.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-109">(Recommended) Remove the Survivable Branch Appliance from the domain.</span></span>

3.  <span data-ttu-id="ffbe5-110">Löschen Sie das Survivable Branch Appliance Computerobjekt in Active Directory-Domänendienste, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffbe5-110">Delete the Survivable Branch Appliance computer object in Active Directory Domain Services, by following these steps:</span></span>
    
      - <span data-ttu-id="ffbe5-111">Melden Sie sich bei einem Mitgliedsserver als Mitglied der Gruppe "Organisations-Admins" an.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-111">Log on to a member server as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="ffbe5-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-112">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="ffbe5-113">Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance Objekt, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-113">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

4.  <span data-ttu-id="ffbe5-114">Fügen Sie das Computerobjekt Survivable Branch Appliance erneut hinzu.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-114">Add the Survivable Branch Appliance computer object again.</span></span> <span data-ttu-id="ffbe5-115">(Weitere Informationen finden Sie unter [Add a Survivable Branch Appliance to Active Directory in lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span><span class="sxs-lookup"><span data-stu-id="ffbe5-115">(See [Add a Survivable Branch Appliance to Active Directory in Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md).)</span></span>

5.  <span data-ttu-id="ffbe5-116">Warten Sie, bis Active Directory Replikation stattfindet.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-116">Wait for Active Directory replication to take place.</span></span>

6.  <span data-ttu-id="ffbe5-117">Öffnen Sie die lync Server-Verwaltungsshell, und geben Sie **enable-CSTopology**ein.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-117">Open the Lync Server Management Shell, and type **Enable-CSTopology**.</span></span>

7.  <span data-ttu-id="ffbe5-118">Verbinden Sie den neuen Survivable Branch Appliance mit dem Netzwerk, und führen Sie die Schritte unter [Deploying a Survivable Branch Appliance or Server with lync Server 2013-Central Site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) aus, und [Stellen Sie einen Survivable Branch Appliance oder Server mit lync Server 2013-Branch Site Task bereit](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="ffbe5-118">Connect the new Survivable Branch Appliance to the network, and follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

</div>

<div>

## <a name="to-rename-a-survivable-branch-appliance"></a><span data-ttu-id="ffbe5-119">So benennen Sie eine Survivable Branch Appliance um</span><span class="sxs-lookup"><span data-stu-id="ffbe5-119">To Rename a Survivable Branch Appliance</span></span>

1.  <span data-ttu-id="ffbe5-120">Verschieben Sie die Benutzer an den zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-120">Move users to the central site.</span></span> <span data-ttu-id="ffbe5-121">Ausführliche Informationen finden Sie unter [Verschiebe Benutzer in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ffbe5-121">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="ffbe5-122">Beenden Sie alle lync Server 2013 Dienste auf dem Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-122">Stop all Lync Server 2013 services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="ffbe5-123">(Informationen hierzu finden Sie in der Herstellerdokumentation zur Survivable Branch Appliance.)</span><span class="sxs-lookup"><span data-stu-id="ffbe5-123">(See the Survivable Branch Appliance vendor documentation.)</span></span>

3.  <span data-ttu-id="ffbe5-124">Führen Sie die folgenden Schritte aus, um den Survivable Branch Appliance aus der Topologie zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="ffbe5-124">Remove the Survivable Branch Appliance from the topology, by following these steps:</span></span>
    
      - <span data-ttu-id="ffbe5-125">Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-125">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="ffbe5-126">Erweitern Sie in der Konsolenstruktur **Zweigstellen**, klicken Sie auf die Survivable Branch Appliance, und klicken Sie dann im Aktionsbereich auf **Löschen** .</span><span class="sxs-lookup"><span data-stu-id="ffbe5-126">In the console tree, expand **Branch Sites**, click the Survivable Branch Appliance, and then click **Delete** on the Action pane.</span></span>

4.  <span data-ttu-id="ffbe5-127">Entfernen Sie die Survivable Branch Appliance aus der Domäne.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-127">Remove the Survivable Branch Appliance from the domain.</span></span>

5.  <span data-ttu-id="ffbe5-128">Löschen Sie das Survivable Branch Appliance Computerobjekt in Active Directory, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffbe5-128">Delete the Survivable Branch Appliance computer object in Active Directory, by following these steps:</span></span>
    
      - <span data-ttu-id="ffbe5-129">Melden Sie sich bei einem Domänencontroller als Mitglied der Gruppe "Organisations-Admins" an.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-129">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>
    
      - <span data-ttu-id="ffbe5-130">Klicken Sie nacheinander auf **Start**, **Verwaltungstools** und dann auf **Active Directory-Benutzer und -Computer**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-130">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>
    
      - <span data-ttu-id="ffbe5-131">Klicken Sie mit der rechten Maustaste auf das Survivable Branch Appliance Objekt, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-131">Right-click the Survivable Branch Appliance object, and click **Delete**.</span></span>

6.  <span data-ttu-id="ffbe5-132">Stellen Sie die Survivable Branch Appliance auf Werkseinstellungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-132">Restore the Survivable Branch Appliance to factory defaults.</span></span> <span data-ttu-id="ffbe5-133">(Informationen hierzu finden Sie in der Herstellerdokumentation zur Survivable Branch Appliance.)</span><span class="sxs-lookup"><span data-stu-id="ffbe5-133">(See the Survivable Branch Appliance vendor documentation.)</span></span>

7.  <span data-ttu-id="ffbe5-134">Befolgen Sie die Schritte unter [Deploying a Survivable Branch Appliance or Server with lync Server 2013-Central Site Tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) und [Deploy a Survivable Branch Appliance or Server with lync Server 2013-Branch Site Task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span><span class="sxs-lookup"><span data-stu-id="ffbe5-134">Follow the steps in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md) and [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md).</span></span>

8.  <span data-ttu-id="ffbe5-135">Benutzer in das umbenannte Survivable Branch Appliance umsetzen.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-135">Move users to the renamed Survivable Branch Appliance.</span></span> <span data-ttu-id="ffbe5-136">Ausführliche Informationen finden Sie unter [Verschiebe Benutzer in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ffbe5-136">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

</div>

<div>

## <a name="to-change-the-lync-server-front-end-pool-that-the-survivable-branch-appliance-is-associated-with"></a><span data-ttu-id="ffbe5-137">So ändern Sie den der Survivable Branch Appliance zugeordneten Lync Server-Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="ffbe5-137">To Change the Lync Server Front End Pool that the Survivable Branch Appliance Is Associated With</span></span>

1.  <span data-ttu-id="ffbe5-138">Migrieren von Benutzern aus dem Survivable Branch Appliance zum lync Server Front-End-Pool am zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-138">Move users from the Survivable Branch Appliance to the Lync Server Front End pool at the central site.</span></span> <span data-ttu-id="ffbe5-139">Ausführliche Informationen finden Sie unter [Verschiebe Benutzer in einen anderen Pool in lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span><span class="sxs-lookup"><span data-stu-id="ffbe5-139">For details, see [Move users to another pool in Lync Server 2013](lync-server-2013-move-users-to-another-pool.md).</span></span>

2.  <span data-ttu-id="ffbe5-140">Beenden Sie alle lync Server Dienste auf dem Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-140">Stop all Lync Server services on the Survivable Branch Appliance.</span></span> <span data-ttu-id="ffbe5-141">(Weitere Informationen finden Sie in der Dokumentation zum Survivable Branch Appliance Anbieter).</span><span class="sxs-lookup"><span data-stu-id="ffbe5-141">(See the Survivable Branch Appliance vendor documentation).</span></span>

3.  <span data-ttu-id="ffbe5-142">Führen Sie die folgenden Schritte aus, um die lync Server Front-End-Pool, der die Survivable Branch Appliance zugeordnet ist, zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="ffbe5-142">Update the Lync Server Front End pool that the Survivable Branch Appliance is associated with, by following these steps:</span></span>
    
      - <span data-ttu-id="ffbe5-143">Klicken Sie auf **Start**, **Alle Programme**, **Microsoft Lync Server** und anschließend auf **Lync Server-Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-143">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="ffbe5-144">Erweitern Sie **Zweigniederlassungen**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-144">Expand **Branch Sites**.</span></span>
    
      - <span data-ttu-id="ffbe5-145">Klicken Sie mit der rechten Maustaste auf das zu ändernde Survivable Branch Appliance Objekt, und klicken Sie auf **Eigenschaften bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="ffbe5-145">Right-click the Survivable Branch Appliance object to modify, and click **Edit Properties**</span></span>
    
      - <span data-ttu-id="ffbe5-146">Wählen Sie unter Ausfallsicherheit die neue Front-End-Pool der Survivable Branch Appliance zugeordnet werden soll, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-146">Under Resiliency, select the new Front End pool the Survivable Branch Appliance is to be associated to, and then click **Next**.</span></span>
    
      - <span data-ttu-id="ffbe5-147">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf den neuen Survivable Branch Appliance, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-147">In the console tree, right-click the new Survivable Branch Appliance, click **Topology**, and then click **Publish**.</span></span>

4.  <span data-ttu-id="ffbe5-148">Starten Sie alle lync Server Dienste auf dem Survivable Branch Appliance neu.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-148">Restart all Lync Server Services on the Survivable Branch Appliance.</span></span>

5.  <span data-ttu-id="ffbe5-149">Testen Sie die Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-149">Test the Survivable Branch Appliance.</span></span> <span data-ttu-id="ffbe5-150">Ausführliche Informationen finden Sie unter [Home users on a Survivable Branch Appliance or Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="ffbe5-150">For details, see [Home users on a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md).</span></span>

6.  <span data-ttu-id="ffbe5-151">Migrieren von Benutzern aus dem lync Server Front-End-Pool am zentralen Standort in den Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="ffbe5-151">Move users from the Lync Server Front End pool at the central site to the Survivable Branch Appliance.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

