---
title: 'Lync Server 2013: Front-End-Pool ABC-Failover-Verfahren'
description: 'Lync Server 2013: Front-End-Pool ABC-Failover-Verfahren.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86f196d53afdc1dcad6fe41191c2aa1582f717e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567141"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="2ce5e-103">Front-End-Pool ABC-Failover-Verfahren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ce5e-103">Front End pool ABC failover procedure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ce5e-104">_**Letztes Änderungsstand des Themas:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="2ce5e-104">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="2ce5e-105">Führen Sie die folgenden Schritte aus, um das ABC-Failover-Verfahren durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-105">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="2ce5e-106">Dieses Verfahren enthält eine allgemeine Beschreibung der einzelnen Schritte, gefolgt von Befehlen und Cmdlets, die für jeden Schritt ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-106">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="2ce5e-107">Öffnen Sie zum Ausführen der Cmdlets ein lync Server-Verwaltungsshell verwenden Sie als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-107">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="2ce5e-108">So führen Sie ein ABC-Failover aus</span><span class="sxs-lookup"><span data-stu-id="2ce5e-108">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="2ce5e-109">Überprüfen Sie, ob der Pool A der Host für den zentralen Verwaltungs Server (CMS) ist.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-109">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="2ce5e-110">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-110">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="2ce5e-111">Wenn das Feld "Identity" des aktiven CMS auf den vollqualifizierten Domänennamen (FQDN) von Pool A verweist, verwenden Sie die Schritte 2 und 3 dieses Verfahrens, um zuerst einen Failover des zentralen Verwaltungsservers durchführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-111">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="2ce5e-112">Fahren Sie andernfalls mit Schritt 4 fort.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-112">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="2ce5e-113">Führen Sie einen Failover des CMS zu Pool B im Notfall Wiederherstellungsmodus durch, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-113">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="2ce5e-114">Nachdem Sie dies getan haben, empfehlen wir Ihnen, den CMS von Pool B in einen anderen vorhandenen gekoppelten Pool zu versetzen, um zusätzliche Ausfallsicherheit zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-114">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="2ce5e-115">Ausführliche Informationen finden Sie unter [CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span><span class="sxs-lookup"><span data-stu-id="2ce5e-115">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="2ce5e-116">Wenn Pool a CMS enthält, importieren Sie die LIS-Konfiguration aus Pool a in die LIS-Datenbank von Pool B (LIS. mdf).</span><span class="sxs-lookup"><span data-stu-id="2ce5e-116">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="2ce5e-117">Dies ist nur möglich, wenn Sie regelmäßig LIS-Daten gesichert haben.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-117">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="2ce5e-118">Führen Sie die folgenden Cmdlets aus, um die LIS-Konfiguration zu importieren:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-118">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="2ce5e-119">Importieren Sie die gesicherten lync Server-Reaktionsgruppendienst-Workflows von Pool a in Pool B.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-119">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ce5e-120">Das Cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> erfordert derzeit, dass sich die Warteschlangen-und Workflownamen in Pool a von den Warteschlangen-und Workflownamen in Pool B unterscheiden. Wenn die Namen nicht unterschiedlich sind, erhalten Sie eine Fehlermeldung, wenn Sie das <STRONG>Import-CsRgsConfiguration-</STRONG> Cmdlet ausführen, und die Warteschlangen und Workflows müssen in Pool B umbenannt werden, bevor Sie mit <STRONG>Import-CsRgsConfiguration-</STRONG> Cmdlet fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-120">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="2ce5e-121">Sie haben zwei Optionen zum Importieren der Reaktionsgruppen Konfiguration von Pool a in Pool B. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool B mit den Einstellungen auf Anwendungsebene in Pool A überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-121">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="2ce5e-122">Wenn Sie die Pool B-Einstellungen überschreiben möchten, führen Sie das **Import-CsRgsConfiguration-** Cmdlet mit der Option **ReplaceExistingSettings** aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-122">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="2ce5e-123">Wenn Sie die Einstellungen für Pool B nicht überschreiben möchten, verwenden Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="2ce5e-123">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2ce5e-124">Beachten Sie, dass, wenn Sie die Einstellungen auf Anwendungsebene des Sicherungs Pools (Pool B) nicht mit den Einstellungen des primären Pools (Pool a) überschreiben möchten, die Einstellungen auf Anwendungsebene von Pool a verloren gehen, wenn Pool a verloren geht, da die Reaktionsgruppenanwendung nur eine Gruppe von Einstellungen auf Anwendungsebene pro Pool speichern kann.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-124">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="2ce5e-125">Wenn Pool C zum Ersetzen von Pool A bereitgestellt wird, müssen die Einstellungen auf Anwendungsebene neu konfiguriert werden, einschließlich der standardmäßigen Musikarchiv-Audiodatei.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-125">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="2ce5e-126">Stellen Sie sicher, dass der Konfigurations Import für Reaktionsgruppen erfolgreich war, indem Sie die folgenden Cmdlets ausführen, um die importierten Reaktionsgruppen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-126">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="2ce5e-127">Beachten Sie, dass die importierten Reaktionsgruppen weiterhin im Besitz von Pool A sind.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-127">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="2ce5e-128">Für nicht zugewiesene Nummern müssen Sie die Bereiche mit der nicht zugewiesenen Nummer, die "Ansage" verwenden, als ausgewählten Ankündigungsdienst von Pool a in Pool B verlagern. Dazu:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-128">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="2ce5e-129">Erstellen Sie alle Ankündigungen neu, die in Pool a in Pool B bereitgestellt wurden. Wenn beim Bereitstellen der Ankündigungen in Pool A Audiodateien verwendet wurden, werden diese Dateien benötigt, um die Ankündigungen in Pool B neu zu erstellen. Um die Ankündigungen in Pool b neu zu erstellen, verwenden Sie die Cmdlets **New-CsAnnouncement** , wobei Pool b als übergeordneter Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-129">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="2ce5e-130">Richten Sie alle nicht zugewiesenen Nummernbereiche, die auf eine Ansage in Pool a Zielen, auf die neu bereitgestellten Ankündigungen in Pool B aus. führen Sie das folgende Cmdlet für jeden nicht zugewiesenen Nummernbereich aus, der auf eine Ankündigung von Pool a abzielt:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-130">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ce5e-131">Dieser Schritt ist für nicht zugewiesene Nummernbereiche nicht erforderlich, die "Exchange um" als ausgewählten Ankündigungsdienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-131">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="2ce5e-132">Führen Sie ein Failover von Pool a an Pool B im Notfall Wiederherstellungsmodus (Dr) durch, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-132">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="2ce5e-133">Erstellen Sie Pool c, starten Sie jedoch keine Dienste in Pool c.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-133">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="2ce5e-134">Beachten Sie, dass dieser Schritt gleichzeitig mit den Schritten 5 und 6 ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-134">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="2ce5e-135">Erzwingen, dass Benutzer in Pool A in Pool C verschoben werden, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-135">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="2ce5e-136">Zu diesem Zeitpunkt beginnt der Benutzer, der in Pool A verwaltet wird, einen Dienstausfall zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-136">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="2ce5e-137">Dieser Ausfall wird fortgesetzt, bis Schritt 16, an dem Punkt Dienste in Pool C gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-137">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="2ce5e-138">Erzwingen Sie, dass das Konferenzverzeichnis von Pool A in Pool C wechselt, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-138">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="2ce5e-139">Erzwingen Sie, dass das Kontaktobjekt der automatischen Telefonzentrale (CAA) von Pool A zu Pool C wechselt, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-139">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="2ce5e-140">Kopieren von Konferenz Inhalten von Pool B in Pool C.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-140">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="2ce5e-141">Exportieren Sie Benutzerdaten aus Pool B, und importieren Sie die Benutzerdaten in Pool C, indem Sie die folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-141">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="2ce5e-142">Stellen Sie die gesicherten Anwendung zum Parken von Anrufen Daten von Pool a in Pool c wieder her, und weisen Sie den orbitbereich des Anruf Parks von Pool a dem Pool c zu.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-142">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="2ce5e-143">Sie können einen orbitbereich für das Parken von Anrufen an Pool C entweder über die lync Server-Systemsteuerung oder den lync Server-Verwaltungsshell neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-143">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="2ce5e-144">Führen Sie für den lync Server-Verwaltungsshell das folgende Cmdlet für jeden orbitbereich für das Parken von Anrufen aus, der Pool a zugewiesen ist (Beachten Sie, dass der Parameter Identity auf die orbitbereiche zum Parken von Anrufen verweist, die zu Pool a gehören):</span><span class="sxs-lookup"><span data-stu-id="2ce5e-144">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="2ce5e-145">Wenn ein benutzerdefiniertes Music-on-Hold-Objekt in Pool a für das Parken von Anrufen konfiguriert wurde, stellen Sie die angepasste Music-on-Hold-Datei für das Parken von Anrufen in Pool C wieder her.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-145">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="2ce5e-146">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-146">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="2ce5e-147">Konfigurieren Sie schließlich die Einstellungen für das Parken von Anrufen in Pool C mithilfe des Cmdlets " **CsCpsConfiguration** ".</span><span class="sxs-lookup"><span data-stu-id="2ce5e-147">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="2ce5e-148">Das Anwendung zum Parken von anrufen kann nur einen Einstellungssatz und eine benutzerdefinierte Audiodatei pro Pool speichern, und diese Einstellungen werden im Falle eines Notfalls nicht gesichert oder beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-148">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="2ce5e-149">Wenn der Pool für den nächsten Hop für den beständigen Chat auf Pool A zeigt, stellen und veröffentlichen Sie Topologie-Änderungen, sodass der Server des nächsten Hops auf Pool C verweist.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-149">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="2ce5e-150">Ändern Sie im Topologie-Generator den Pool für beständigen Chat so, dass er als nächster Hop auf Pool C verweist.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-150">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="2ce5e-151">Klicken Sie dazu mit der rechten Maustaste auf den Pool für beständigen Chat, klicken Sie auf die Registerkarte **Allgemein** , und geben Sie dann den Namen des Pools C im **Pool nächster Hop**ein.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-151">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="2ce5e-152">Starten Sie die Dienste in Pool C, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-152">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="2ce5e-153">An diesem Punkt endet der Dienstausfall für Benutzer, die ursprünglich in Pool A verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-153">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="2ce5e-154">Exportieren Sie lync Server Workflows für Reaktionsgruppen Dienste von Pool B im Besitz von Pool a für den Import in Pool C, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-154">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="2ce5e-155">Importieren Sie lync Server Workflows für Reaktionsgruppen Dienste in Pool C aus Pool B.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-155">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="2ce5e-156">Sie haben zwei Möglichkeiten zum Importieren der Reaktionsgruppen Konfiguration von Pool B in Pool C. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool C mit den Einstellungen auf Anwendungsebene in Pool B überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-156">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="2ce5e-157">Wenn Sie die Pool-C-Einstellungen überschreiben möchten, führen Sie das **Import-CsRgsConfiguration-** Cmdlet mit der Option **ReplaceExistingSettings** aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-157">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="2ce5e-158">Wenn Sie die Pool C-Einstellungen nicht überschreiben möchten, verwenden Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="2ce5e-158">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="2ce5e-159">Beachten Sie, dass, wenn Sie die Einstellungen auf Anwendungsebene von Pool C nicht mit den Einstellungen des Sicherungs Pools (Pool b) überschreiben möchten, die Einstellungen auf Anwendungsebene von Pool b verloren gehen, da der Reaktionsgruppenanwendung nur eine Gruppe von Einstellungen auf Anwendungsebene pro Pool speichern kann.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-159">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="2ce5e-160">Stellen Sie sicher, dass der Konfigurations Import für Reaktionsgruppen erfolgreich war, indem Sie die folgenden Cmdlets ausführen, um die Reaktionsgruppen anzuzeigen, die in Pool C importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-160">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="2ce5e-161">Wenn die importierte Konfiguration in Pool C überprüft wurde, entfernen Sie die Reaktionsgruppen im Besitz des primären Pools aus Pool B. Dadurch wird die Ausfallzeit der Reaktionsgruppen minimiert.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-161">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="2ce5e-162">In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt, und die Datei wird dann aus Pool B entfernt.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-162">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="2ce5e-163">Verschieben Sie den Bereich nicht zugewiesene Nummernbereiche, die von Pool a in Pool B verschoben wurden, in Pool C.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-163">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="2ce5e-164">Erstellen Sie alle Ankündigungen, die aus Pool a in Pool B neu erstellt wurden, in Pool C neu. Wenn beim Bereitstellen der zu verschiebenden Ankündigungen Audiodateien verwendet wurden, müssen Sie diese Dateien verwenden, um die Ankündigungen in Pool C neu zu erstellen. Um die Ankündigungen in Pool c neu zu erstellen, verwenden Sie die Cmdlets **New-CsAnnouncement** , wobei Pool c als übergeordneter Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-164">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="2ce5e-165">Retarget to Pool C alle nicht zugewiesenen Nummernbereiche, die von Pool a auf Pool B umzielt wurden führen Sie das folgende Cmdlet für jeden nicht zugewiesenen Nummernbereich aus, der neu ausgerichtet werden muss:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-165">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="2ce5e-166">Optional Entfernen Sie aus Pool b die Ankündigungen, die in Pool C neu erstellt wurden, wenn Sie in Pool b nicht mehr verwendet werden. Verwenden Sie das Cmdlet **Remove-CsAnnouncement** , um Ankündigungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-166">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2ce5e-167">Dieser Schritt ist für nicht zugewiesene Nummernbereiche nicht erforderlich, die "Exchange um" als Ankündigungsdienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-167">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="2ce5e-168">Bereinigen Sie die Benutzerdaten von Pool a in Pool B, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-168">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="2ce5e-169">Führen Sie im Topologie-Generator folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-169">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="2ce5e-170">Unpair Pool a und Pool b. Pair Pool b und Pool C. Entfernen Sie dann Pool A aus der Topologie, und veröffentlichen Sie es.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-170">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="2ce5e-171">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-171">To do so:</span></span>
        
          - <span data-ttu-id="2ce5e-172">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf Pool B, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-172">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="2ce5e-173">Klicken Sie im linken Bereich auf **Ausfallsicherheit** .</span><span class="sxs-lookup"><span data-stu-id="2ce5e-173">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="2ce5e-174">Wählen Sie im Feld unter **zugeordneter Sicherungspool**die Option Pool C. Beachten Sie, dass im zugehörigen Auswahlfeld Sicherungspool zunächst Pool a angezeigt wird, da Pool B zuvor diesem Pool zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-174">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="2ce5e-175">Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-175">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="2ce5e-176">Wenn Sie die Details zu diesem Pool anzeigen, erscheint der neu zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-176">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="2ce5e-177">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf Pool A, und klicken Sie dann auf Löschen.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-177">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="2ce5e-178">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-178">Publish the topology.</span></span>

23. <span data-ttu-id="2ce5e-179">Führen Sie die Bootstrapping-Anwendung in Pool c aus, um die Sicherungsdienst Anwendung zu installieren, und starten Sie dann die Sicherungsdienst Anwendung, indem Sie den folgenden Befehl aus dem Bereitstellungsordner auf einem lokalen Computer in Pool c ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-179">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="2ce5e-180">Starten Sie die Sicherungsdienst Anwendung in Pool B neu, indem Sie die folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-180">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="2ce5e-181">Wenn Pool c ein Standard Edition-Pool (SE) ist und Pool B über einen CMS verfügt, installieren Sie die CMS-Datenbank manuell in Pool c, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-181">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="2ce5e-182">Rufen Sie den Sicherungsdienst auf, um alte Konferenzinhalte von Pool b mit Pool c zu synchronisieren, die vor dem Koppeln von b und c generiert wurden, und um neue Konferenzinhalte von Pool c zu Pool b zu synchronisieren, die nach dem Starten von Pool c generiert wurden und bevor b und c zusammen gekoppelt wurden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-182">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="2ce5e-183">Führen Sie dazu die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-183">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="2ce5e-184">Für jede Survivable Branch Appliance X, die mit Pool A verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-184">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="2ce5e-185">Fahren Sie SBA X herunter, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-185">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="2ce5e-186">Erstellen Sie eine Datei, die eine Liste der Benutzer enthält, die in SBA X verwaltet werden. Die Liste wird benötigt, wenn die Benutzer in Schritt 30 zurück zu SBA X verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-186">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="2ce5e-187">Führen Sie dazu das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-187">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="2ce5e-188">Erzwingen Sie, dass Benutzer, die in SBA X verwaltet werden, zu Pool C migrieren, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-188">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="2ce5e-189">Aktualisieren Sie die Daten dieser Benutzer, indem Sie zunächst die folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-189">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="2ce5e-190">Und führen Sie dann dieses Skript aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-190">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2ce5e-191">Für Benutzer, die in SBAS verwaltet werden, die mit Pool a verbunden sind, tritt ein Dienstausfall auf, bis diese Benutzer zu Pool C verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-191">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="2ce5e-192">Führen Sie im Topologie-Generator für jede SBA X, die zuvor mit Pool A verbunden ist, folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-192">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="2ce5e-193">Ändern Sie die Zuordnung zu Pool C. Klicken Sie dazu auf den Zweigstellenstandort, erweitern Sie den Knoten Survivable Branch Appliances oder Servers, und klicken Sie auf **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-193">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="2ce5e-194">Wählen Sie dann die **Front-End-Pool, den Benutzer Dienste-Pool** , mit dem dieser Survivable Branch Appliance eine Verbindung herstellen wird, als Pool C aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-194">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="2ce5e-195">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-195">Publish the topology.</span></span> <span data-ttu-id="2ce5e-196">Klicken Sie dazu in der Konsolenstruktur mit der rechten Maustaste auf den neuen **Survivable Branch Appliance**, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-196">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="2ce5e-197">Für jede SBA X, die jetzt mit Pool C verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-197">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="2ce5e-198">Starten Sie SBA X, indem Sie das folgende Cmdlet auf der Survivable Branch Appliance ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ce5e-198">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="2ce5e-199">Führen Sie das folgende Cmdlet aus, um Benutzer zu migrieren, die ursprünglich in SBA x von Pool C nach SBA x verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="2ce5e-199">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

