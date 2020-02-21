---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers-Primary
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12c4d942bc4f08c12e2ff63250d1b87807a50963
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="624d5-102">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary</span><span class="sxs-lookup"><span data-stu-id="624d5-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="624d5-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="624d5-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="624d5-104">Wenn Sie einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration haben und nur die primäre Datenbank ausfällt, befolgen Sie die Verfahren in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="624d5-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="624d5-105">Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, finden Sie unter [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="624d5-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="624d5-106">Wenn nur die Spiegelung fehlschlägt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="624d5-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="624d5-107">Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="624d5-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="624d5-108">Wenn ein Enterprise Edition-Mitgliedsserver, lync Server 2013 bei dem es sich nicht um den Back-End-Server handelt, fehlerhaft ist, finden Sie unter [Wiederherstellen eines Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md)</span><span class="sxs-lookup"><span data-stu-id="624d5-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="624d5-109">Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="624d5-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="624d5-110">Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="624d5-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="624d5-111">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.</span><span class="sxs-lookup"><span data-stu-id="624d5-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="624d5-112">In diesem Thema weist die Beispieldatenbank einen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) von BE1.contoso.com auf, und die Spiegeldatenbank verfügt über einen FQDN von BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="624d5-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="624d5-113">So stellen Sie eine primäre Datenbank einer Enterprise Edition-Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="624d5-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="624d5-114">Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="624d5-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="624d5-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="624d5-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="624d5-116">Erzwingen Sie, dass für alle konfigurierten Datenbanken ein Failover auf die Spiegelung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="624d5-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="624d5-117">Geben Sie für jeden der Datenbanktypen, die Sie auf diesem Server konfiguriert haben, das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="624d5-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="624d5-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="624d5-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="624d5-119">Wenn Sie die Back-End-Datenbank so konfiguriert haben, dass die synchronisierte Spiegelung mit einem Zeugen verwendet wird, erfolgt das Failover automatisch.</span><span class="sxs-lookup"><span data-stu-id="624d5-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="624d5-120">Führen Sie nach Abschluss des Failovers die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="624d5-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="624d5-121">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="624d5-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="624d5-122">Deaktivieren der Spiegelung auf dem Back-End-Server: Klicken Sie mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="624d5-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="624d5-123">Deaktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **SQL Server Speicherspiegelung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="624d5-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="624d5-124">Tun Sie dies für die Archivierung und Überwachung bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="624d5-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="624d5-125">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="624d5-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="624d5-126">Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="624d5-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="624d5-127">Wählen Sie das noch funktionsfähige Back-End (BE2.contoso.com) als neuen SQL-Speicher aus.</span><span class="sxs-lookup"><span data-stu-id="624d5-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="624d5-128">Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="624d5-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="624d5-129">Geben Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**den FQDN des funktionsfähigen Back-Ends in das Feld **SQL Server Speicher** ein (in unserem Beispiel BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="624d5-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="624d5-130">Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="624d5-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="624d5-131">Starten Sie die Dienste neu, damit jeder Server die neue Topologie lesen kann.</span><span class="sxs-lookup"><span data-stu-id="624d5-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="624d5-132">Führen Sie in einem lync Server-Verwaltungsshell die folgenden Cmdlets für jeden Front-End-Server aus, der zu diesem Pool gehört:</span><span class="sxs-lookup"><span data-stu-id="624d5-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="624d5-133">Deinstallieren Sie die Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="624d5-133">Uninstall mirroring.</span></span> <span data-ttu-id="624d5-134">Führen Sie in einem lync Server-Verwaltungsshell das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="624d5-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="624d5-135">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="624d5-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="624d5-136">Tun Sie dies für alle Datenbanktypen auf diesem Server.</span><span class="sxs-lookup"><span data-stu-id="624d5-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="624d5-137">Erstellen Sie einen sauberen oder neuen Server mit demselben FQDN (in diesem Beispiel db1.contoso.com) als ausgefallenen Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="624d5-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="624d5-138">Dieser Server wird als neue Spiegelungsfunktion fungieren.</span><span class="sxs-lookup"><span data-stu-id="624d5-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="624d5-139">Melden Sie sich bei einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, am neuen Server an.</span><span class="sxs-lookup"><span data-stu-id="624d5-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="624d5-140">Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz so wie vor dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="624d5-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="624d5-141">Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="624d5-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="624d5-142">Verwenden Sie den Topologie-Generator zum Installieren der Spiegeldatenbank.</span><span class="sxs-lookup"><span data-stu-id="624d5-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="624d5-143">Führen Sie die folgenden Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="624d5-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="624d5-144">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="624d5-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="624d5-145">Aktivieren Sie die Spiegelung auf dem Back-End-Server.</span><span class="sxs-lookup"><span data-stu-id="624d5-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="624d5-146">Klicken Sie dazu mit der rechten Maustaste auf den Pool unter **Enterprise Edition-Front-End-Pools** , und wählen Sie **Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="624d5-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="624d5-147">Aktivieren Sie auf der Registerkarte **Allgemein** unter **Zuordnungen**das Kontrollkästchen **SQL Server Speicherspiegelung aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="624d5-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="624d5-148">Tun Sie dies auch für die Archivierung und Überwachung, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="624d5-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="624d5-149">Geben Sie dann im Feld **Spiegelungs SQL Server Speicher** den FQDN des neuen Servers ein (n in diesem Beispiel BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="624d5-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="624d5-150">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="624d5-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="624d5-151">Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="624d5-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="624d5-152">Führen Sie den Assistenten zum **Installieren einer Datenbank** aus.</span><span class="sxs-lookup"><span data-stu-id="624d5-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="624d5-153">Wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="624d5-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="624d5-154">Folgen Sie dem Assistenten, bis Sie zur Eingabeaufforderung kommen, **Spiegeldatenbank erstellen**.</span><span class="sxs-lookup"><span data-stu-id="624d5-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="624d5-155">Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="624d5-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

