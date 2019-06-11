---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – primär
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="dc155-102">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär</span><span class="sxs-lookup"><span data-stu-id="dc155-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc155-103">_**Letztes Änderungsdatum des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="dc155-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="dc155-104">Wenn Sie über einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration verfügen und nur die primäre Datenbank fehlschlägt, führen Sie die Verfahren in diesem Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="dc155-105">Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, lesen Sie [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="dc155-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="dc155-106">Wenn nur die Spiegelung fehlschlägt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="dc155-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="dc155-107">Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)wird.</span><span class="sxs-lookup"><span data-stu-id="dc155-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="dc155-108">Wenn ein Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, fehlschlägt, lesen Sie [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md)</span><span class="sxs-lookup"><span data-stu-id="dc155-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="dc155-109">Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="dc155-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="dc155-110">Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="dc155-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="dc155-111">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="dc155-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="dc155-112">In diesem Thema verfügt die primäre Beispieldatenbank über einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) von BE1.contoso.com, und die Spiegeldatenbank verfügt über einen FQDN von BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="dc155-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="dc155-113">So stellen Sie eine primäre Datenbank für den Back-End-Server eines Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="dc155-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="dc155-114">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="dc155-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="dc155-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="dc155-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="dc155-116">Erzwingen Sie, dass alle konfigurierten Datenbanken ein Failover zur Spiegelung durchführen.</span><span class="sxs-lookup"><span data-stu-id="dc155-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="dc155-117">Geben Sie für jeden der Datenbanktypen, die Sie auf diesem Server konfiguriert haben, das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="dc155-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="dc155-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dc155-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="dc155-119">Wenn Sie Ihre Back-End-Datenbank so konfiguriert haben, dass die synchronisierte Spiegelung mit einem Zeugen verwendet wird, ist das Failover automatisch.</span><span class="sxs-lookup"><span data-stu-id="dc155-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="dc155-120">Führen Sie nach Abschluss des Failovers die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="dc155-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="dc155-121">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="dc155-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="dc155-122">Deaktivieren der Spiegelung auf dem Back-End-Server: Klicken Sie mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="dc155-123">Deaktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="dc155-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="dc155-124">Führen Sie diese Schritte für die Archivierung und Überwachung nach Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="dc155-125">Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc155-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="dc155-126">Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="dc155-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="dc155-127">Wählen Sie das noch funktionierende Back-End (BE2.contoso.com) als neuen SQL Store aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="dc155-128">Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="dc155-129">Geben Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**den FQDN des funktionierenden Back-Ends im Feld **SQL Server Store** ein (in unserem Beispiel BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="dc155-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="dc155-130">Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="dc155-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="dc155-131">Starten Sie Dienste neu, damit jeder Server die neue Topologie lesen kann.</span><span class="sxs-lookup"><span data-stu-id="dc155-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="dc155-132">Führen Sie in einer lync Server-Verwaltungsshell die folgenden Cmdlets auf jedem Front-End-Server aus, der zu diesem Pool gehört:</span><span class="sxs-lookup"><span data-stu-id="dc155-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="dc155-133">Deinstallieren Sie die Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="dc155-133">Uninstall mirroring.</span></span> <span data-ttu-id="dc155-134">Führen Sie in einer lync Server-Verwaltungsshell das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="dc155-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="dc155-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="dc155-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="dc155-136">Führen Sie diese Schritte für alle Datenbanktypen auf diesem Server aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="dc155-137">Erstellen Sie einen sauberen oder neuen Server mit dem gleichen FQDN (in diesem Beispiel db1.contoso.com) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="dc155-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="dc155-138">Dieser Server wird als neue Spiegelungsfunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="dc155-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="dc155-139">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, beim neuen Server an.</span><span class="sxs-lookup"><span data-stu-id="dc155-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="dc155-140">Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz wie vor dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="dc155-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="dc155-141">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="dc155-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="dc155-142">Verwenden Sie den Topologie-Generator zum Installieren der Spiegelungs-DB.</span><span class="sxs-lookup"><span data-stu-id="dc155-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="dc155-143">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dc155-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="dc155-144">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="dc155-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="dc155-145">Aktivieren der Spiegelung auf dem Back-End-Server.</span><span class="sxs-lookup"><span data-stu-id="dc155-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="dc155-146">Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="dc155-147">Aktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **Spiegelung des SQL Server-Speichers aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="dc155-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="dc155-148">Dies gilt auch für die Archivierung und Überwachung, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dc155-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="dc155-149">Geben Sie im Feld **Spiegelung des SQL Server** -Speichers den FQDN des neuen Servers ein (n diesem Beispiel BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="dc155-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="dc155-150">Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc155-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="dc155-151">Klicken Sie mit der rechten Maustaste auf den lync Server 2013-Knoten, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="dc155-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="dc155-152">Folgen Sie dem Assistenten zum **Installieren der Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="dc155-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="dc155-153">Wählen Sie auf der Seite **Create** Databases die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="dc155-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="dc155-154">Folgen Sie dem Assistenten, bis Sie zur Eingabeaufforderung gelangen, **Spiegelungsdatenbank erstellen**.</span><span class="sxs-lookup"><span data-stu-id="dc155-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="dc155-155">Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="dc155-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

