---
title: 'Lync Server 2013: Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet'
description: 'Lync Server 2013: Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher hostet.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring the server hosting the Central Management store
ms:assetid: 3bd6c82c-07fb-4798-b8f9-e7c78a5a83d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202172(v=OCS.15)
ms:contentKeyID: 51541464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c07e4c6722695b2bfb4cb478a1f3eefa86b4eb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575451"
---
# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="c9e28-103">Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet</span><span class="sxs-lookup"><span data-stu-id="c9e28-103">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9e28-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c9e28-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c9e28-105">Eine lync Server-Bereitstellung verfügt über einen einzelnen zentralen Verwaltungsspeicher, dessen Kopie auf jeden Server repliziert wird, auf dem eine lync Server-Serverrolle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c9e28-105">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="c9e28-106">In diesem Thema wird beschrieben, wie Sie einen Back-End-Server oder Standard Edition-Server wiederherstellen, der den zentralen Verwaltungsspeicher hostet.</span><span class="sxs-lookup"><span data-stu-id="c9e28-106">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="c9e28-107">Um den Pool zu finden, in dem sich der zentrale Verwaltungsserver befindet, öffnen Sie den Topologie-Generator, klicken Sie auf **lync Server**, und suchen Sie im rechten Bereich unter **zentrale Verwaltungsserver**.</span><span class="sxs-lookup"><span data-stu-id="c9e28-107">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="c9e28-108">Wenn sich der Back-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet, in einem gespiegelten Setup befindet und die Spiegeldatenbank weiterhin funktionsfähig ist, wird empfohlen, dass Sie eine Sicherung dieser noch funktionsfähigen Spiegelung vornehmen und anschließend eine vollständige Wiederherstellung der primären Datenbank und der Spiegeldatenbank mithilfe dieser Sicherung durchführen, indem Sie das folgende Wiederherstellungsverfahren ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-108">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="c9e28-109">Dies ist erforderlich, da für die Back-End-Wiederherstellung die Topologie geändert und veröffentlicht werden muss, und dies ist nur möglich, wenn die primäre Datenbank, die CMS hostet, betriebsbereit ist.</span><span class="sxs-lookup"><span data-stu-id="c9e28-109">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="c9e28-110">Beachten Sie auch, dass die primäre und die Spiegel Datenbankrolle nicht ausgetauscht werden können, wenn die Topologie nicht veröffentlicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9e28-110">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9e28-111">Wenn ein Back-End-Server oder Standard Edition-Server, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird, fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</A> oder <A href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c9e28-111">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="c9e28-112">Wenn sich ein Back-End-Server, der den zentralen Verwaltungsspeicher hostet, in einer gespiegelten Konfiguration befindet und nur die Spiegelung fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror</A>.</span><span class="sxs-lookup"><span data-stu-id="c9e28-112">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="c9e28-113">Wenn ein anderer Server fehlgeschlagen ist, finden Sie weitere Informationen unter <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c9e28-113">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="c9e28-114">Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-114">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="c9e28-115">Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="c9e28-115">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="c9e28-116">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.</span><span class="sxs-lookup"><span data-stu-id="c9e28-116">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="c9e28-117">So stellen Sie den zentralen Verwaltungsspeicher wieder her</span><span class="sxs-lookup"><span data-stu-id="c9e28-117">To restore the Central Management store</span></span>

1.  <span data-ttu-id="c9e28-118">Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="c9e28-118">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9e28-119">Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-119">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="c9e28-120">Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins und der lokalen Administratoren ist, bei dem Server an, den Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c9e28-120">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="c9e28-121">Wenn Sie ein Standard Edition-Server wiederherstellen, stellen Sie das Dateispeicher wieder her, indem Sie das entsprechende Dateispeicher aus $Backup in den Dateispeicher Speicherort auf dem Server kopieren und dann den Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="c9e28-121">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c9e28-122">Der Pfad und der Dateiname für das wiederhergestellte Dateispeicher sollten genau mit dem gesicherten Dateispeicher identisch sein, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c9e28-122">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="c9e28-123">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c9e28-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="c9e28-124">Wenn Sie ein Standard Edition-Server installieren möchten, wechseln Sie zum Installationsordner für lync Server oder Medien, und starten Sie dann den lync Server-Bereitstellungs-Assistenten, der sich unter \\ Setup \\ amd64 \\Setup.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="c9e28-124">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="c9e28-125">Klicken Sie im Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten** , und führen Sie den Assistenten aus, um den zentralen Verwaltungsspeicher zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c9e28-125">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="c9e28-126">Wenn Sie einen Enterprise-Back-End-Server installieren, installieren Sie SQL Server 2012 oder SQL Server 2008 R2, wobei die Instanznamen wie vor dem Fehler beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c9e28-126">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c9e28-127">Je nach dem Server, den Sie wiederherstellen, und in der Bereitstellung kann der Server mehrere zusammenhängende oder getrennte Datenbanken umfassen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-127">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="c9e28-128">Führen Sie das gleiche Verfahren zum Installieren von SQL Server durch, mit dem Sie auch ursprünglich den Server bereitgestellt haben, einschließlich SQL Server-Berechtigungen und -Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-128">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="c9e28-129">Starten Sie in einem Front-End-Server das lync Server-Verwaltungsshell: Klicken Sie auf **Start**, auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c9e28-129">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="c9e28-130">Erstellen Sie den zentralen Verwaltungsspeicher erneut.</span><span class="sxs-lookup"><span data-stu-id="c9e28-130">Re-create the Central Management store.</span></span> <span data-ttu-id="c9e28-131">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c9e28-131">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="c9e28-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9e28-132">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="c9e28-133">Legen Sie den Active Directory-Domänendienste Kontrollpunkt für den zentralen Verwaltungsspeicher fest.</span><span class="sxs-lookup"><span data-stu-id="c9e28-133">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="c9e28-134">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c9e28-134">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="c9e28-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9e28-135">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9e28-136">Sollten Sie den Verbindungspunkt verlieren, können Sie dieses Cmdlet erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-136">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="c9e28-137">Importieren Sie die Daten des zentralen Verwaltungsspeichers aus $Backup.</span><span class="sxs-lookup"><span data-stu-id="c9e28-137">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="c9e28-138">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c9e28-138">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="c9e28-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9e28-139">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="c9e28-p110">Aktivieren Sie die eben vorgenommenen Änderungen. Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c9e28-p110">Enable the changes you have just made. At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c9e28-142">Nach dem Aktivieren der Topologie wird das Topologiedokument in der Datenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9e28-142">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="c9e28-143">Wenn Sie einen Enterprise Edition-Back-End-Server wiederherstellen, der auch den CMS gehostet hat, oder wenn Sie eine Spiegelung des CMS neu erstellen müssen, führen Sie diesen Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="c9e28-143">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="c9e28-144">Fahren Sie andernfalls mit Schritt 11 fort.</span><span class="sxs-lookup"><span data-stu-id="c9e28-144">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="c9e28-145">Installieren Sie die eigenständigen Datenbanken, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c9e28-145">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="c9e28-146">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="c9e28-146">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="c9e28-147">Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c9e28-147">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="c9e28-p112">Wählen Sie die Topologie aus, und klicken Sie auf **Speichern**. Klicken Sie auf **Ja**, um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-p112">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="c9e28-150">Klicken Sie mit der rechten Maustaste auf den Knoten **lync Server 2013** , und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="c9e28-150">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="c9e28-151">Führen Sie den Assistenten zum **Installieren einer Datenbank** aus.</span><span class="sxs-lookup"><span data-stu-id="c9e28-151">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="c9e28-152">Wenn Sie eine andere Datenbank als den zentralen Verwaltungsspeicher auf diesem Server wiederherstellen, wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c9e28-152">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="c9e28-153">Auf der Seite <STRONG>Erstellen von Datenbanken</STRONG> werden nur eigenständige Datenbanken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9e28-153">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="c9e28-154">Zusammengeführte Datenbankenwerden erstellt, wenn Sie den lync Server-Bereitstellungs-Assistenten ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-154">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="c9e28-155">Wenn Sie einen gespiegelten Back-End-Server wiederherstellen, fahren Sie mit dem Rest des Assistenten fort, bis Sie eine Eingabeaufforderung zum Erstellen einer Spiegeldatenbank erhalten.</span><span class="sxs-lookup"><span data-stu-id="c9e28-155">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="c9e28-156">Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie den Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="c9e28-156">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="c9e28-157">Folgen Sie den Anweisungen auf den weiteren Seiten des Assistenten, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c9e28-157">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c9e28-158">Anstatt den Topologie-Generator auszuführen, können Sie das Cmdlet <STRONG>install-CsDatabase</STRONG> verwenden, um die einzelnen Datenbanken zu erstellen, und das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> , um die Spiegelung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9e28-158">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="c9e28-159">Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">install-CsDatabase</A> und <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">install-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="c9e28-159">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="c9e28-160">Wenn Sie ein Standard Edition-Server wiederherstellen, wechseln Sie zum Installationsordner lync Server oder Medien, und starten Sie den lync Server-Bereitstellungs-Assistenten, der sich unter \\ Setup \\ amd64 \\Setup.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="c9e28-160">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="c9e28-161">Verwenden Sie den lync Server-Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="c9e28-161">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="c9e28-162">Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c9e28-162">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="c9e28-163">Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server Komponenten** aus, um die lync Server-Server Rollen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c9e28-163">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="c9e28-164">Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-164">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="c9e28-165">Führen Sie **Schritt 4: Dienste starten** aus, um die Dienste auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="c9e28-165">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="c9e28-166">Ausführliche Informationen zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="c9e28-166">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="c9e28-167">Gehen Sie folgendermaßen vor, um Benutzerdaten wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="c9e28-167">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="c9e28-168">Kopieren Sie ExportedUserData.zip aus $Backup \\ in ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c9e28-168">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="c9e28-169">Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden.</span><span class="sxs-lookup"><span data-stu-id="c9e28-169">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="c9e28-170">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c9e28-170">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="c9e28-171">Geben Sie in die Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="c9e28-171">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="c9e28-172">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9e28-172">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="c9e28-173">Starten Sie lync Services neu, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="c9e28-173">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="c9e28-174">Stellen Sie Standort Informationsdaten im zentralen Verwaltungsspeicher wieder her.</span><span class="sxs-lookup"><span data-stu-id="c9e28-174">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="c9e28-175">Geben Sie in die Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c9e28-175">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="c9e28-176">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9e28-176">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="c9e28-177">Wenn Sie die Reaktionsgruppe in diesem Pool oder Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her.</span><span class="sxs-lookup"><span data-stu-id="c9e28-177">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="c9e28-178">Ausführliche Informationen finden Sie unter [Wiederherstellen von Reaktionsgruppeneinstellungen in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="c9e28-178">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="c9e28-179">Wenn Sie einen Back-End-Server, der Archivierungs-oder Überwachungsdatenbanken enthält, wiederherstellen, stellen Sie die Archivierungs-oder Überwachungsdaten mithilfe eines SQL Server Verwaltungstools wie SQL Server Management Studio wieder her.</span><span class="sxs-lookup"><span data-stu-id="c9e28-179">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="c9e28-180">Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="c9e28-180">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

