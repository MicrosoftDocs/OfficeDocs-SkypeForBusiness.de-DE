---
title: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Back-End-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780963614a1d0f5049fdc5226391e2ee2b6d59c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511542"
---
# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a><span data-ttu-id="21ed8-102">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21ed8-102">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21ed8-103">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="21ed8-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="21ed8-104">Verwenden Sie das in diesem Thema beschriebene Verfahren in den folgenden beiden Fällen:</span><span class="sxs-lookup"><span data-stu-id="21ed8-104">Use the procedure described in this topic in the following two cases:</span></span>

  - <span data-ttu-id="21ed8-105">Sowohl die primäre als auch die Spiegeldatenbank eines gespiegelten Enterprise Edition-Back-End-Servers schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="21ed8-105">Both the primary and mirror databases of a mirrored Enterprise Edition Back End Server fail.</span></span>

  - <span data-ttu-id="21ed8-106">Ein nicht gespiegelter Enterprise Edition-Back-End-Server schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="21ed8-106">An Enterprise Edition Back End Server that is not mirrored fails.</span></span>

<span data-ttu-id="21ed8-107">Wenn Sie ein gespiegeltes Enterprise Edition-Back-End haben und nur die Spiegelung oder primäre Datenbank ausfällt, finden Sie weitere Informationen unter [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) zum Wiederherstellen der primären Datenbank und [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)</span><span class="sxs-lookup"><span data-stu-id="21ed8-107">If you have a mirrored Enterprise Edition Back End and only the mirror or primary database fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) for restoring the primary database, and [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) for restoring the mirror.</span></span>

<span data-ttu-id="21ed8-108">Wenn der zentrale Verwaltungsspeicher fehlschlägt, finden Sie weitere Informationen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="21ed8-108">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="21ed8-109">Wenn ein Enterprise Edition-Mitgliedsserver, lync Server 2013 bei dem es sich nicht um den Back-End-Server handelt, fehlerhaft ist, finden Sie unter [Wiederherstellen eines Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md)</span><span class="sxs-lookup"><span data-stu-id="21ed8-109">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="21ed8-110">Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="21ed8-110">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="21ed8-111">Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="21ed8-111">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="21ed8-112">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.</span><span class="sxs-lookup"><span data-stu-id="21ed8-112">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a><span data-ttu-id="21ed8-113">So stellen Sie einen Back-End-Server der Enterprise Edition wieder her</span><span class="sxs-lookup"><span data-stu-id="21ed8-113">To restore an Enterprise Edition Back End Server</span></span>

1.  <span data-ttu-id="21ed8-114">Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="21ed8-114">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21ed8-115">Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="21ed8-115">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="21ed8-116">Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei dem Server an, den Sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="21ed8-116">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="21ed8-117">Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz so wie vor dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="21ed8-117">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21ed8-p103">Je nach vorhandener Bereitstellung umfasst der Back-End-Server möglicherweise mehrere verbundene oder separate Datenbanken. Führen Sie das gleiche Verfahren zum Installieren von SQL Server durch, mit dem Sie auch ursprünglich den Server bereitgestellt haben, einschließlich SQL Server-Berechtigungen und -Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="21ed8-p103">Depending on your deployment, the Back End Server might include multiple collocated or separate databases. Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

    
    </div>

4.  <span data-ttu-id="21ed8-120">Führen Sie nach dem Installieren von SQL Server folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="21ed8-120">After you install SQL Server, perform the following:</span></span>
    
    1.  <span data-ttu-id="21ed8-121">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="21ed8-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="21ed8-122">Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="21ed8-122">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="21ed8-p104">Wählen Sie die Topologie aus, und klicken Sie auf **Speichern**. Klicken Sie auf **Ja**, um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="21ed8-p104">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="21ed8-125">Klicken Sie mit der rechten Maustaste auf den Knoten **lync Server 2013** , und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="21ed8-125">Right-click the **Lync Server 2013** node, and then click **Publish Topology**.</span></span>
    
    5.  <span data-ttu-id="21ed8-126">Folgen Sie den Anweisungen im Assistenten zum Veröffentlichen der Topologie\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="21ed8-126">Follow the **Publish the Topology** wizard.</span></span> <span data-ttu-id="21ed8-127">Wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="21ed8-127">On the **Create databases** page, select the databases that you want to re-create.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="21ed8-128">Auf der Seite <STRONG>Erstellen von Datenbanken</STRONG> werden nur eigenständige Datenbanken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="21ed8-128">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="21ed8-129">Wenn Sie ein gespiegeltes Back-End wiederherstellen, fahren Sie mit dem Rest des Assistenten fort, bis die Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="21ed8-129">If you are restoring a Back End that was mirrored, continue to follow the rest of the wizard until the prompt **Create Mirror Database** appears.</span></span> <span data-ttu-id="21ed8-130">Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie den Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="21ed8-130">Select the database that you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="21ed8-131">Folgen Sie den Anweisungen auf den weiteren Seiten des Assistenten, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="21ed8-131">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="21ed8-132">Anstatt den Topologie-Generator auszuführen, können Sie das Cmdlet <STRONG>install-CsDatabase</STRONG> verwenden, um die einzelnen Datenbanken zu erstellen, und das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> , um die Spiegelung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="21ed8-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="21ed8-133">Einzelheiten finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="21ed8-133">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

5.  <span data-ttu-id="21ed8-134">Stellen Sie die Benutzerdaten wieder her, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="21ed8-134">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="21ed8-135">Kopieren Sie ExportedUserData.zip aus $Backup \\ in ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="21ed8-135">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="21ed8-136">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="21ed8-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    3.  <span data-ttu-id="21ed8-137">Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden.</span><span class="sxs-lookup"><span data-stu-id="21ed8-137">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="21ed8-138">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="21ed8-138">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    4.  <span data-ttu-id="21ed8-139">Geben Sie in die Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="21ed8-139">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="21ed8-140">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="21ed8-140">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  <span data-ttu-id="21ed8-141">Starten Sie lync Services neu, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="21ed8-141">Restart Lync Services by typing:</span></span>
        
            Start-CsWindowsService

6.  <span data-ttu-id="21ed8-142">Wenn Sie die Reaktionsgruppe in diesem Pool bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her.</span><span class="sxs-lookup"><span data-stu-id="21ed8-142">If you deployed Response Group on this pool, restore the Response Group configuration data.</span></span> <span data-ttu-id="21ed8-143">Ausführliche Informationen finden Sie unter [Wiederherstellen von Reaktionsgruppeneinstellungen in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="21ed8-143">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

7.  <span data-ttu-id="21ed8-144">Wenn Sie einen Back-End-Server wiederherstellen, auf dem sich Archivierungs- oder Überwachungsdatenbanken befanden, stellen Sie die Archivierungs- oder Überwachungsdaten mithilfe eines SQL Server-Tools wie etwa SQL Server Management Studio wieder her.</span><span class="sxs-lookup"><span data-stu-id="21ed8-144">If you are restoring a Back End Server that included Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="21ed8-145">Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="21ed8-145">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

