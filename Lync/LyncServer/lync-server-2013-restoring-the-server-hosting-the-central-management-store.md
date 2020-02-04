---
title: 'Lync Server 2013: Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher gehostet wird'
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
ms.openlocfilehash: 976f486d096f7be59e2eef74eab7b03d6cc4bab0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-the-server-hosting-the-central-management-store-in-lync-server-2013"></a><span data-ttu-id="ff75d-102">Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet wird</span><span class="sxs-lookup"><span data-stu-id="ff75d-102">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff75d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ff75d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ff75d-104">Eine lync Server-Bereitstellung verfügt über einen einzelnen zentralen Verwaltungsspeicher, dessen Kopie auf jeden Server repliziert wird, auf dem eine lync Server-Serverrolle ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff75d-104">A Lync Server deployment has a single Central Management store, a copy of which is replicated to each server running a Lync Server server role.</span></span> <span data-ttu-id="ff75d-105">In diesem Thema wird beschrieben, wie Sie einen Back-End-Server oder Standard Edition-Server wiederherstellen, der den zentralen Verwaltungsspeicher hostet.</span><span class="sxs-lookup"><span data-stu-id="ff75d-105">This topic describes how to restore a Back End Server or Standard Edition server that hosts the Central Management store.</span></span>

<span data-ttu-id="ff75d-106">Zum Auffinden des Pools, in dem sich der zentrale Verwaltungsserver befindet, öffnen Sie den Topologie-Generator, klicken Sie auf **lync Server**, und suchen Sie im rechten Bereich unter **zentraler Verwaltungsserver**.</span><span class="sxs-lookup"><span data-stu-id="ff75d-106">To find the pool where the Central Management Server is located, open Topology Builder, click **Lync Server**, and look in the right pane under **Central Management Server**.</span></span>

<span data-ttu-id="ff75d-107">Wenn sich der Back-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet, in einem gespiegelten Setup befindet und die Spiegeldatenbank weiterhin funktionsfähig ist, empfehlen wir, dass Sie eine Sicherungskopie dieser noch funktionierenden Spiegelung erstellen und dann eine vollständige Wiederherstellung sowohl auf der primären als auch auf der primären Datenbank durchführen. spiegeln Sie die Datenbank mithilfe dieser Sicherung, indem Sie das nachstehende Wiederherstellungsverfahren ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-107">If the Back End Server that hosts the Central Management store is in a mirrored setup and the mirror database is still functional, we recommend that you make a backup of this still-functioning mirror, and then perform a full restore on both the primary database and the mirror database, using this backup, by following the restoration procedure below.</span></span> <span data-ttu-id="ff75d-108">Dies ist erforderlich, da für die Back-End-Wiederherstellung die Topologie geändert und veröffentlicht werden muss und dies nur möglich ist, wenn die primäre Datenbank-Hosting-CMS funktionsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="ff75d-108">This is necessary because Back End restore requires modifying and publishing the topology, and this can be done only if the primary database hosting CMS is operational.</span></span> <span data-ttu-id="ff75d-109">Beachten Sie auch, dass die Primär-und Spiegel Datenbankrollen nicht austauschbar sind, wenn die Topologie nicht veröffentlicht werden kann.</span><span class="sxs-lookup"><span data-stu-id="ff75d-109">Also note that the primary and mirror database roles cannot be interchanged if the topology cannot be published.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff75d-110">Wenn ein Back-End-Server oder Standard Edition-Server, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird, fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013</A> oder <A href="lync-server-2013-restoring-a-standard-edition-server.md">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ff75d-110">If a Back End Server or Standard Edition server that does not host the Central Management store failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</A> or <A href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</A>.</span></span> <span data-ttu-id="ff75d-111">Wenn sich ein Back-End-Server, auf dem sich der zentrale Verwaltungsspeicher befindet, in einer gespiegelten Konfiguration befindet und nur der Spiegel Fehler aufgetreten ist, lesen Sie <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013</A></span><span class="sxs-lookup"><span data-stu-id="ff75d-111">If a Back End Server that hosts the Central Management store is in a mirrored configuration and only the mirror failed, see <A href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</A>.</span></span> <span data-ttu-id="ff75d-112">Wenn ein anderer Server fehlgeschlagen ist, lesen Sie <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ff75d-112">If any other server failed, see <A href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</A>.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="ff75d-113">Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-113">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="ff75d-114">Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="ff75d-114">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="ff75d-115">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="ff75d-115">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-the-central-management-store"></a><span data-ttu-id="ff75d-116">So stellen Sie den zentralen Verwaltungsspeicher wieder her</span><span class="sxs-lookup"><span data-stu-id="ff75d-116">To restore the Central Management store</span></span>

1.  <span data-ttu-id="ff75d-117">Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="ff75d-117">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff75d-118">Befolgen Sie die Server Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="ff75d-118">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="ff75d-119">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe und der lokalen Gruppe Administratoren ist, bei dem Server an, den Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ff75d-119">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="ff75d-120">Wenn Sie einen Standard Edition-Server wiederherstellen, stellen Sie den Dateispeicher wieder her, indem Sie den entsprechenden Dateispeicher aus $Backup in den Dateispeicher Speicherort auf dem Server kopieren und dann den Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="ff75d-120">If you are restoring a Standard Edition server, restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ff75d-121">Der Pfad und Dateinamen für den wiederhergestellten Dateispeicher sollten exakt mit dem gesicherten Dateispeicher identisch sein, damit die Komponenten, die die Dateien verwenden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ff75d-121">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="ff75d-122">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ff75d-122">Do one of the following:</span></span>
    
      - <span data-ttu-id="ff75d-123">Wenn Sie einen Standard Edition-Server installieren, suchen Sie nach dem lync Server-Installationsordner oder-Medium, und starten Sie dann den lync Server \\-\\Bereitstellungs-Assistenten, der sich unter Setup amd64\\Setup. exe befindet.</span><span class="sxs-lookup"><span data-stu-id="ff75d-123">If you are installing a Standard Edition server, browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="ff75d-124">Klicken Sie im Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten** , und folgen Sie dem Assistenten, um den zentralen Verwaltungsspeicher zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ff75d-124">In the Deployment Wizard, click **Prepare first Standard Edition server** and follow the wizard to install the Central Management store.</span></span>
    
      - <span data-ttu-id="ff75d-125">Wenn Sie einen Enterprise-Back-End-Server installieren, installieren Sie SQL Server 2012 oder SQL Server 2008 R2, wobei die Namen der Instanz wie vor dem Fehler identisch sind.</span><span class="sxs-lookup"><span data-stu-id="ff75d-125">If you are installing an Enterprise Back End Server, install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ff75d-126">Je nach dem Server, den Sie wiederherstellen, und bei der Bereitstellung umfasst der Server möglicherweise mehrere zusammengefasste oder getrennte Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ff75d-126">Depending on the server that you are restoring and on your deployment, the server might include multiple collocated or separate databases.</span></span> <span data-ttu-id="ff75d-127">Führen Sie die gleichen Schritte aus, um SQL Server zu installieren, den Sie ursprünglich für die Bereitstellung des Servers verwendet haben, einschließlich SQL Server-Berechtigungen und-Anmeldungen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-127">Follow the same procedure to install SQL Server that you used originally to deploy the server, including SQL Server permissions and logins.</span></span>

        
        </div>

5.  <span data-ttu-id="ff75d-128">Starten Sie die lync Server-Verwaltungsshell von einem Front-End-Server: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ff75d-128">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

6.  <span data-ttu-id="ff75d-129">Erstellen Sie den zentralen Verwaltungsspeicher erneut.</span><span class="sxs-lookup"><span data-stu-id="ff75d-129">Re-create the Central Management store.</span></span> <span data-ttu-id="ff75d-130">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff75d-130">At the command line, type:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="ff75d-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ff75d-131">For example:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose

7.  <span data-ttu-id="ff75d-132">Legen Sie den Active Directory-Domänendienste-Kontrollpunkt für den zentralen Verwaltungsspeicher fest.</span><span class="sxs-lookup"><span data-stu-id="ff75d-132">Set the Active Directory Domain Services control point for the Central Management store.</span></span> <span data-ttu-id="ff75d-133">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff75d-133">At the command line, type:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn <FQDN> -SqlInstanceName <instance name> -Verbose
    
    <span data-ttu-id="ff75d-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ff75d-134">For example:</span></span>
    
        Set-CsConfigurationStoreLocation -SqlServerFqdn Server01.contoso.com -SqlInstanceName cms -Verbose
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff75d-135">Wenn Sie den Verbindungspunkt verloren haben, können Sie dieses Cmdlet erneut ausführen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-135">If you lose the connection point, you can rerun this cmdlet.</span></span>

    
    </div>

8.  <span data-ttu-id="ff75d-136">Importieren Sie die Daten des zentralen Verwaltungsspeichers aus $Backup.</span><span class="sxs-lookup"><span data-stu-id="ff75d-136">Import the Central Management store data from $Backup.</span></span> <span data-ttu-id="ff75d-137">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff75d-137">At the command line, type:</span></span>
    
        Import-CsConfiguration -FileName <CMS backup file name>
    
    <span data-ttu-id="ff75d-138">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ff75d-138">For example:</span></span>
    
        Import-CsConfiguration -FileName "C:\Config.zip"

9.  <span data-ttu-id="ff75d-139">Aktivieren Sie die soeben vorgenommenen Änderungen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-139">Enable the changes you have just made.</span></span> <span data-ttu-id="ff75d-140">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff75d-140">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ff75d-141">Nachdem Sie die Topologie aktiviert haben, können Sie das Topologie-Dokument in der Datenbank finden.</span><span class="sxs-lookup"><span data-stu-id="ff75d-141">After you enable the topology, you can find the topology document in the database.</span></span>

    
    </div>

10. <span data-ttu-id="ff75d-142">Wenn Sie einen Enterprise Edition-Back-End-Server wiederherstellen, der auch den CMS gehostet hat, oder wenn Sie eine Spiegelung des CMS neu erstellen müssen, führen Sie diesen Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="ff75d-142">If you are restoring an Enterprise Edition Back End Server that also hosted the CMS, or if you need to re-create a mirror of the CMS, then follow this step.</span></span> <span data-ttu-id="ff75d-143">Fahren Sie andernfalls mit Schritt 11 fort.</span><span class="sxs-lookup"><span data-stu-id="ff75d-143">Otherwise, skip to step 11.</span></span>
    
    <span data-ttu-id="ff75d-144">Führen Sie die folgenden Schritte aus, um die eigenständigen Datenbanken zu installieren:</span><span class="sxs-lookup"><span data-stu-id="ff75d-144">Install the stand-alone databases by doing the following:</span></span>
    
    1.  <span data-ttu-id="ff75d-145">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="ff75d-145">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="ff75d-146">Klicken Sie auf **Topologie aus vorhandener Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ff75d-146">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="ff75d-147">Wählen Sie die Topologie aus, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ff75d-147">Select the topology, and then click **Save**.</span></span> <span data-ttu-id="ff75d-148">Klicken Sie auf **Ja** , um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-148">Click **Yes** to confirm your selection.</span></span>
    
    4.  <span data-ttu-id="ff75d-149">Klicken Sie mit der rechten Maustaste auf den **lync Server 2013** -Knoten, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="ff75d-149">Right-click the **Lync Server 2013** node, and then click **Install Database**.</span></span>
    
    5.  <span data-ttu-id="ff75d-150">Folgen Sie dem Assistenten zum **Installieren der Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="ff75d-150">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="ff75d-151">Wenn Sie eine andere Datenbank als den zentralen Verwaltungsspeicher auf diesem Server wiederherstellen, wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ff75d-151">If you are restoring a database other than the Central Management store on this server, on the **Create databases** page, select the databases you want to recreate.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ff75d-152">Auf der Seite " <STRONG>Datenbankenerstellen</STRONG> " werden nur eigenständige Datenbanken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff75d-152">Only stand-alone databases are displayed on the <STRONG>Create databases</STRONG> page.</span></span> <span data-ttu-id="ff75d-153">Wenn Sie den lync Server-Bereitstellungs-Assistenten ausführen, werden die Datenbanken erstellt.</span><span class="sxs-lookup"><span data-stu-id="ff75d-153">Collocated databases are created when you run the Lync Server Deployment Wizard.</span></span>

        
        </div>
    
    6.  <span data-ttu-id="ff75d-154">Wenn Sie einen gespiegelten Back-End-Server wiederherstellen, folgen Sie dem restlichen Assistenten, bis Sie zu einer Aufforderung zum Erstellen einer Spiegeldatenbank gelangen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-154">If you are restoring a mirrored Back End Server, continue to follow the rest of the wizard until you come to a prompt of Create Mirror Database.</span></span> <span data-ttu-id="ff75d-155">Wählen Sie die Datenbank aus, die Sie installieren möchten, und schließen Sie den Vorgang ab.</span><span class="sxs-lookup"><span data-stu-id="ff75d-155">Select the database you want to install, and complete the process.</span></span>
    
    7.  <span data-ttu-id="ff75d-156">Führen Sie den restlichen Assistenten aus, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ff75d-156">Follow the rest of the wizard, and then click **Finish**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ff75d-157">Anstelle des Topologie-Generators können Sie das Cmdlet " <STRONG>install-CsDatabase</STRONG> " verwenden, um jede Datenbank zu erstellen, und das Cmdlet " <STRONG>install-CsMirrorDatabase</STRONG> ", um die Spiegelung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ff75d-157">Instead of running Topology Builder, you can use the <STRONG>Install-CsDatabase</STRONG> cmdlet to create each database, and the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="ff75d-158">Ausführliche Informationen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Installieren-CsDatabase</A> und <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Installieren-CsMirrorDatabase</A>.</span><span class="sxs-lookup"><span data-stu-id="ff75d-158">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsDatabase">Install-CsDatabase</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Install-CsMirrorDatabase">Install-CsMirrorDatabase</A>.</span></span>

    
    </div>

11. <span data-ttu-id="ff75d-159">Wenn Sie einen Standard Edition-Server wiederherstellen, wechseln Sie zum lync Server-Installationsordner oder-Medium, und starten Sie den lync Server \\-\\Bereitstellungs-Assistenten unter Setup amd64\\Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="ff75d-159">If you are restoring a Standard Edition server, browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="ff75d-160">Verwenden Sie den lync Server-Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="ff75d-160">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="ff75d-161">Führen Sie **Schritt 1: Installieren des lokalen Konfigurationsspeichers** aus, um die lokalen Konfigurationsdateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ff75d-161">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="ff75d-162">Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** aus, um die lync Server-Serverrollen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ff75d-162">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="ff75d-163">Führen Sie **Schritt 3 aus: anfordern, installieren oder Zuweisen von Zertifikaten** zum Zuweisen der Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="ff75d-163">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="ff75d-164">Führen Sie **Schritt 4: Dienste starten** aus, um Dienste auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="ff75d-164">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="ff75d-165">Details zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="ff75d-165">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

12. <span data-ttu-id="ff75d-166">Wiederherstellen von Benutzerdaten durch Ausführen der folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="ff75d-166">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="ff75d-167">Kopieren Sie ExportedUserData. zip aus\\ $Backup in ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ff75d-167">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="ff75d-168">Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden.</span><span class="sxs-lookup"><span data-stu-id="ff75d-168">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="ff75d-169">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff75d-169">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="ff75d-170">Geben Sie zum Wiederherstellen der Benutzerdaten in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff75d-170">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="ff75d-171">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ff75d-171">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="ff75d-172">Starten Sie lync Services neu, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="ff75d-172">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

13. <span data-ttu-id="ff75d-173">Wiederherstellen von Standort Informationsdaten im zentralen Verwaltungsspeicher</span><span class="sxs-lookup"><span data-stu-id="ff75d-173">Restore Location Information data to the Central Management store.</span></span> <span data-ttu-id="ff75d-174">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ff75d-174">At the command line, type:</span></span>
    
        Import-CsLisConfiguration -FileName <LIS backup file name>
    
    <span data-ttu-id="ff75d-175">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ff75d-175">For example:</span></span>
    
        Import-CsLisConfiguration -FileName "D:\E911Config.zip"

14. <span data-ttu-id="ff75d-176">Wenn Sie die Reaktionsgruppe auf diesem Pool oder Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her.</span><span class="sxs-lookup"><span data-stu-id="ff75d-176">If you deployed Response Group on this pool or Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="ff75d-177">Ausführliche Informationen finden Sie unter [Wiederherstellen von Einstellungen für die Reaktionsgruppe in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ff75d-177">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

15. <span data-ttu-id="ff75d-178">Wenn Sie einen Back-End-Server wiederherstellen, der Archivierungs-oder Überwachungsdatenbanken umfasst, stellen Sie die Archivierungs-oder Überwachungsdaten mithilfe eines SQL Server-Verwaltungstools wie SQL Server Management Studio wieder her.</span><span class="sxs-lookup"><span data-stu-id="ff75d-178">If you are restoring a Back End Server that includes Archiving or Monitoring databases, restore the Archiving or Monitoring data by using a SQL Server management tool, such as SQL Server Management Studio.</span></span> <span data-ttu-id="ff75d-179">Ausführliche Informationen finden Sie unter [Wiederherstellen von Überwachungs-oder Archivierungsdaten in lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span><span class="sxs-lookup"><span data-stu-id="ff75d-179">For details, see [Restoring monitoring or archiving data in Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

