---
title: 'Lync Server 2013: ABC-Failover-Verfahren im Front-End-Pool'
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
ms.openlocfilehash: edf3d12aa519ab7746ccec92998995ed463aa9be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a><span data-ttu-id="35c08-102">ABC-Failover-Verfahren im Front-End-Pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="35c08-102">Front End pool ABC failover procedure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35c08-103">_**Letztes Änderungsdatum des Themas:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="35c08-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="35c08-104">Führen Sie die folgenden Schritte aus, um die ABC-Failover-Prozedur durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="35c08-104">Use the following steps to perform the ABC failover procedure.</span></span> <span data-ttu-id="35c08-105">Dieses Verfahren enthält eine allgemeine Beschreibung der einzelnen Schritte, gefolgt von Befehlen und Cmdlets, die für jeden Schritt ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="35c08-105">This procedure contains a high-level description of each step, followed by commands and cmdlets to be run for each step.</span></span>

<span data-ttu-id="35c08-106">Wenn Sie die Cmdlets ausführen möchten, öffnen Sie eine lync Server-Verwaltungsshell mithilfe von "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="35c08-106">To run the cmdlets, open a Lync Server Management Shell using Run as Administrator.</span></span>

<div>

## <a name="to-perform-an-abc-failover"></a><span data-ttu-id="35c08-107">So führen Sie ein ABC-Failover durch</span><span class="sxs-lookup"><span data-stu-id="35c08-107">To Perform an ABC Failover</span></span>

1.  <span data-ttu-id="35c08-108">Überprüfen Sie, ob der Pool A der Host für den zentralen Verwaltungs Server (CMS) ist.</span><span class="sxs-lookup"><span data-stu-id="35c08-108">Check whether the pool A is the host for the Central Management Server (CMS).</span></span>
    
      - <span data-ttu-id="35c08-109">Führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="35c08-109">Run the following cmdlet:</span></span>
        
            Get-CsService -CentralManagement
        
        <span data-ttu-id="35c08-110">Wenn das Feld Identity des aktiven CMS auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) von Pool A zeigt, führen Sie die Schritte 2 und 3 dieses Verfahrens aus, um zuerst einen Failover für den zentralen Verwaltungs Server auszuführen.</span><span class="sxs-lookup"><span data-stu-id="35c08-110">If the Identity field of the active CMS points to the fully qualified domain name (FQDN) of Pool A, then you use steps 2 and 3 of this procedure to fail over the Central Management Server first.</span></span> <span data-ttu-id="35c08-111">Fahren Sie andernfalls mit Schritt 4 fort.</span><span class="sxs-lookup"><span data-stu-id="35c08-111">Otherwise, skip to step 4.</span></span>

2.  <span data-ttu-id="35c08-112">Führen Sie bei einem Failover des CMS zu Pool B im Disaster Recovery-Modus, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-112">Fail over the CMS to Pool B in disaster recovery mode by running the following cmdlet:</span></span>
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    <span data-ttu-id="35c08-113">Nachdem Sie dies tun, empfehlen wir, dass Sie das CMS aus Pool B in einen anderen vorhandenen gekoppelten Pool verschieben, um eine zusätzliche Widerstandsfähigkeit zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="35c08-113">After you do this, we recommend that you move the CMS from pool B to another existing paired pool for extra resiliency.</span></span> <span data-ttu-id="35c08-114">Ausführliche Informationen finden Sie unter [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer).</span><span class="sxs-lookup"><span data-stu-id="35c08-114">For details, see [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..</span></span>

3.  <span data-ttu-id="35c08-115">Wenn Pool a CMS enthält, importieren Sie die LIS-Konfiguration aus Pool a in die LIS-Datenbank von Pool B (LIS. mdf).</span><span class="sxs-lookup"><span data-stu-id="35c08-115">If Pool A contains CMS, import the LIS configuration from pool A into pool B’s LIS database (Lis.mdf).</span></span> <span data-ttu-id="35c08-116">Dies funktioniert nur, wenn Sie die LIS-Daten in regelmäßigen Abständen gesichert haben.</span><span class="sxs-lookup"><span data-stu-id="35c08-116">This will work only if you have been backing up LIS data on a regular basis.</span></span> <span data-ttu-id="35c08-117">Führen Sie die folgenden Cmdlets aus, um die LIS-Konfiguration zu importieren:</span><span class="sxs-lookup"><span data-stu-id="35c08-117">To import the LIS configuration, run the following cmdlets:</span></span>
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  <span data-ttu-id="35c08-118">Importieren von gesicherten lync Server Response Group Service-Workflows aus Pool a in Pool B.</span><span class="sxs-lookup"><span data-stu-id="35c08-118">Import backed-up Lync Server Response Group service workflows from pool A into pool B.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35c08-119">Zurzeit erfordert das Cmdlet " <STRONG>Import-CsRgsConfiguration</STRONG> ", dass sich die Warteschlangen-und Workflownamen in Pool a von den Warteschlangen-und Workflownamen in Pool B unterscheiden. Wenn die Namen nicht unterschiedlich sind, erhalten Sie eine Fehlermeldung, wenn Sie das Cmdlet " <STRONG>Import-CsRgsConfiguration</STRONG> " ausführen, und die Warteschlangen und Workflows müssen in Pool B umbenannt werden, bevor Sie mit dem Cmdlet " <STRONG>Import-CsRgsConfiguration</STRONG> " fortfahren.</span><span class="sxs-lookup"><span data-stu-id="35c08-119">Currently, the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet requires that the queue and workflow names on pool A are distinct from the queue and workflow names on pool B. If the names are not distinct, you will get an error when running the <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet, and the queues and workflows will need to be renamed in pool B before proceeding with <STRONG>Import-CsRgsConfiguration</STRONG> cmdlet.</span></span>

    
    </div>
    
    <span data-ttu-id="35c08-120">Sie haben zwei Möglichkeiten zum Importieren der Reaktionsgruppen Konfiguration aus Pool a in Pool B. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool B mit den Einstellungen auf Anwendungsebene in Pool A überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="35c08-120">You have two options for importing the Response Group configuration from pool A to pool B. Which option you use depends on whether you want to overwrite the application-level settings of pool B with the application-level settings in pool A.</span></span>
    
      - <span data-ttu-id="35c08-121">Wenn Sie die Pool B-Einstellungen überschreiben möchten, führen Sie das Cmdlet " **Import-CsRgsConfiguration** " mit der Option " **ReplaceExistingSettings** " aus:</span><span class="sxs-lookup"><span data-stu-id="35c08-121">If you want to overwrite the Pool B settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="35c08-122">Wenn Sie die Pool B-Einstellungen nicht überschreiben möchten, verwenden Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="35c08-122">If you do not want to overwrite the Pool B settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="35c08-123">Beachten Sie, dass, wenn Sie die Einstellungen auf Anwendungsebene des Sicherungs Pools (Pool B) nicht mit den Einstellungen des primären Pools (Pool a) überschreiben möchten, die Einstellungen auf Anwendungsebene von Pool a verloren gehen, wenn Pool a verloren geht, weil die Antwortgruppen Anwendung Speichern Sie nur einen Satz von Einstellungen auf Anwendungsebene pro Pool.</span><span class="sxs-lookup"><span data-stu-id="35c08-123">Keep in mind that if you do not want to overwrite the application-level settings of the backup pool (pool B) with the settings of the primary pool (pool A), pool A’s application-level settings will be lost if pool A is lost, because the Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="35c08-124">Wenn Pool C zum Ersetzen von Pool A bereitgestellt wird, müssen die Einstellungen auf Anwendungsebene neu konfiguriert werden, einschließlich der standardmäßigen Musik-in-Halt-Audiodatei.</span><span class="sxs-lookup"><span data-stu-id="35c08-124">When pool C is deployed to replace pool A, the application-level settings must be reconfigured, including the default music-on-hold audio file.</span></span>

    
    </div>

5.  <span data-ttu-id="35c08-125">Überprüfen Sie, ob der Import der Reaktionsgruppen Konfiguration erfolgreich war, indem Sie die folgenden Cmdlets ausführen, um die importierten Antwortgruppen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="35c08-125">Verify that the Response Group configuration import was successful by running the following cmdlets to display the imported response groups.</span></span> <span data-ttu-id="35c08-126">Beachten Sie, dass die importierten Antwortgruppen weiterhin im Besitz von Pool A sind.</span><span class="sxs-lookup"><span data-stu-id="35c08-126">Note that the imported response groups are still owned by pool A.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  <span data-ttu-id="35c08-127">Verschieben Sie für nicht zugewiesene Nummern die nicht zugewiesenen Nummernbereiche, die "Ankündigung" verwenden, als ausgewählten Ankündigungsdienst von Pool A zu Pool B. Gehen Sie dazu wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="35c08-127">For Unassigned Numbers, move the Unassigned Number ranges that are using "Announcement" as the selected announcement service from pool A to pool B. To do so:</span></span>
    
      - <span data-ttu-id="35c08-128">Erstellen Sie alle Ankündigungen, die in Pool a im Pool B bereitgestellt wurden, erneut. Wenn beim Bereitstellen der Ankündigungen in Pool A Audiodateien verwendet wurden, werden diese Dateien benötigt, um die Ankündigungen in Pool B erneut zu erstellen. Verwenden Sie die Cmdlets **New-CsAnnouncement** mit Pool b als übergeordneten Dienst, um die Ankündigungen in Pool b erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35c08-128">Re-create all announcements that were deployed in pool A on pool B. If any audio files were used when deploying the announcements in pool A, these files will be needed to re-create the announcements in pool B. To re-create the announcements in pool B, use the **New-CsAnnouncement** cmdlets, with pool B as the Parent service.</span></span>
    
      - <span data-ttu-id="35c08-129">Zielen Sie alle nicht zugewiesenen Nummernbereiche, die auf eine Ankündigung in Pool a ausgerichtet sind, auf die neu bereitgestellten Ankündigungen in Pool B ab. führen Sie das folgende Cmdlet für jeden nicht zugewiesenen Nummernbereich aus, der auf eine Ankündigung von Pool a ausgerichtet ist:</span><span class="sxs-lookup"><span data-stu-id="35c08-129">Retarget all the Unassigned Number ranges that are targeting an announcement in pool A to the newly deployed announcements in pool B. Run the following cmdlet for every Unassigned Number range targeting an announcement of pool A:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="35c08-130">Dieser Schritt ist nicht für nicht zugewiesene Nummernbereiche erforderlich, die "Exchange um" als ausgewählten Ankündigungsdienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="35c08-130">This step is not required for unassigned number ranges that use "Exchange UM" as the selected announcement service.</span></span>

    
    </div>

7.  <span data-ttu-id="35c08-131">Führen Sie einen Failover für Pool a an Pool B im Disaster Recovery-Modus (Dr) durch, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-131">Fail over Pool A to Pool B in Disaster Recovery (DR) mode, by running the following cmdlet:</span></span>
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  <span data-ttu-id="35c08-132">Erstellen Sie Pool c, aber starten Sie keine Dienste im Pool c.</span><span class="sxs-lookup"><span data-stu-id="35c08-132">Build pool C, but do not start any services on pool C.</span></span>
    
    <span data-ttu-id="35c08-133">Beachten Sie, dass dieser Schritt gleichzeitig mit den Schritten 5 und 6 ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="35c08-133">Note that this step can be carried out concurrently with steps 5 and 6.</span></span>

9.  <span data-ttu-id="35c08-134">Erzwingen Sie, dass Benutzer, die in Pool A verwaltet werden, zu Pool C wechseln, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-134">Force users homed on pool A to move to pool C by running the following cmdlet:</span></span>
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    <span data-ttu-id="35c08-135">An diesem Punkt beginnt der Benutzer, der in Pool A verwaltet wird, mit einem Dienstausfall.</span><span class="sxs-lookup"><span data-stu-id="35c08-135">At this point, users homed on pool A will begin to experience a service outage.</span></span> <span data-ttu-id="35c08-136">Dieser Ausfall wird bis zum Schritt 16 fortgesetzt, bei dem Point Services im Pool C gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="35c08-136">This outage will continue until step 16, at which point services are started on pool C.</span></span>

10. <span data-ttu-id="35c08-137">Erzwingen Sie das Konferenzverzeichnis von Pool A, um zu Pool C zu wechseln, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-137">Force the conference directory of pool A to move to pool C by running the following cmdlet:</span></span>
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. <span data-ttu-id="35c08-138">Erzwingen Sie das Contact-Objekt der Konferenz-Telefonzentrale (CAA), um von Pool A zu Pool C zu wechseln, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-138">Force the Conference Auto Attendant (CAA) Contact Object to move from pool A to pool C by running the following cmdlet:</span></span>
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. <span data-ttu-id="35c08-139">Kopieren Sie Konferenzinhalte aus Pool B in Pool C.</span><span class="sxs-lookup"><span data-stu-id="35c08-139">Copy conference content from pool B to pool C.</span></span>

13. <span data-ttu-id="35c08-140">Exportieren Sie Benutzerdaten aus Pool B, und importieren Sie die Benutzerdaten in Pool C, indem Sie die folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-140">Export user data from pool B and import the user data into pool C by running the following cmdlets:</span></span>
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. <span data-ttu-id="35c08-141">Wiederherstellen von gesicherten Anruf Park-Anwendungsdaten aus Pool a in Pool c und Zuweisen des Anruf Bereichs für den Orbit von Pool a an Pool c.</span><span class="sxs-lookup"><span data-stu-id="35c08-141">Restore backed-up Call Park application data from pool A into pool C and assign the Call Park orbit ranges of pool A to pool C.</span></span>
    
      - <span data-ttu-id="35c08-142">Sie können einen Bereich für den Orbit eines Anruf Parks für Pool a an Pool C entweder über die lync Server-Systemsteuerung oder die lync Server-Verwaltungsshell neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="35c08-142">You can reassign a Call Park orbit range of pool A to pool C either through the Lync Server Control Panel or the Lync Server Management Shell.</span></span> <span data-ttu-id="35c08-143">Führen Sie für die lync Server-Verwaltungsshell das folgende Cmdlet für jeden für Pool a zugewiesenen orbitbereich des Anruf Parks aus (Beachten Sie, dass sich der Parameter Identity auf die orbitbereiche des Anruf Parks bezieht, die zu Pool a gehören):</span><span class="sxs-lookup"><span data-stu-id="35c08-143">For the Lync Server Management Shell, run the following cmdlet for every Call Park orbit range assigned to pool A (note that the Identity parameter refers to the Call Park Orbit Ranges that belong to pool A):</span></span>
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - <span data-ttu-id="35c08-144">Wenn ein benutzerdefiniertes Musik-on-halten für den Parken von Anrufen in Pool a konfiguriert wurde, stellen Sie die angepasste Musik-in-halten-Datei für den Anruf Park in Pool C wieder her.</span><span class="sxs-lookup"><span data-stu-id="35c08-144">If a customized music-on-hold has been configured for Call Park in pool A, restore the Call Park customized music-on-hold file in pool C.</span></span>
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        <span data-ttu-id="35c08-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="35c08-145">For example:</span></span>
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - <span data-ttu-id="35c08-146">Konfigurieren Sie schließlich die Einstellungen des Anruf Parks im Pool C mithilfe des Cmdlets " **CsCpsConfiguration** " neu.</span><span class="sxs-lookup"><span data-stu-id="35c08-146">Finally, reconfigure the Call Park settings on pool C by using the **Set-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="35c08-147">Die Anwendung "Parken" kann nur einen Satz von Einstellungen und eine angepasste Musik-zu-halten-Audiodatei pro Pool speichern, und diese Einstellungen werden nicht gesichert oder im Fall eines Notfalls erhalten.</span><span class="sxs-lookup"><span data-stu-id="35c08-147">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool, and these settings are not backed up or preserved in the event of a disaster.</span></span>

15. <span data-ttu-id="35c08-148">Wenn der Pool für den nächsten Hop für beständigen Chat auf Pool A zeigt, erstellen und veröffentlichen Sie Topologie-Änderungen, damit der Server für den nächsten Hop auf Pool C verweist.</span><span class="sxs-lookup"><span data-stu-id="35c08-148">If the next hop pool for Persistent Chat is pointing to pool A, make and publish topology changes so that the next hop server points to pool C.</span></span>
    
      - <span data-ttu-id="35c08-149">Ändern Sie im Topologie-Generator den beständigen Chat Pool so, dass er als nächster Hop auf Pool C verweist.</span><span class="sxs-lookup"><span data-stu-id="35c08-149">In Topology Builder, change the Persistent Chat pool to point to Pool C as its next hop.</span></span> <span data-ttu-id="35c08-150">Klicken Sie dazu mit der rechten Maustaste auf den beständigen Chat-Pool, klicken Sie dann auf die Registerkarte **Allgemein** , und geben Sie dann den Namen des Pools C in den **nächsten Hop-Pool**ein.</span><span class="sxs-lookup"><span data-stu-id="35c08-150">To do so, right-click on the Persistent Chat pool, then click the **General** tab, and then type the name of Pool C in **Next Hop Pool**.</span></span>
    
      - <span data-ttu-id="35c08-151">Starten Sie Dienste im Pool C, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-151">Start services on pool C by running the following cmdlet:</span></span>
        
            Start-csWindowsService
    
    <span data-ttu-id="35c08-152">An diesem Punkt endet der Dienstausfall für Benutzer, die sich ursprünglich in Pool A befanden.</span><span class="sxs-lookup"><span data-stu-id="35c08-152">At this point, the service outage ends for users originally homed on pool A.</span></span>

16. <span data-ttu-id="35c08-153">Exportieren von lync Server Response Group Service-Workflows aus Pool B im Besitz von Pool a für den Import in Pool C durch Ausführen des folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="35c08-153">Export Lync Server Response Group service workflows from pool B owned by pool A for import into pool C by running the following cmdlet:</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. <span data-ttu-id="35c08-154">Importieren Sie den lync Server Response Group Service-Workflow in Pool C aus Pool B.</span><span class="sxs-lookup"><span data-stu-id="35c08-154">Import Lync Server Response Group service workflows into pool C from pool B.</span></span>
    
    <span data-ttu-id="35c08-155">Sie haben zwei Möglichkeiten zum Importieren der Reaktionsgruppen Konfiguration aus Pool B in Pool C. Welche Option Sie verwenden, hängt davon ab, ob Sie die Einstellungen auf Anwendungsebene von Pool C mit den Einstellungen auf Anwendungsebene in Pool B überschreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="35c08-155">You have two options are for importing the Response Group configuration from pool B to pool C. Which option you use depends on whether you want to overwrite the application-level settings of pool C with the application-level settings in pool B.</span></span>
    
      - <span data-ttu-id="35c08-156">Wenn Sie die Pool C-Einstellungen überschreiben möchten, führen Sie das Cmdlet " **Import-CsRgsConfiguration** " mit der Option " **ReplaceExistingSettings** " aus:</span><span class="sxs-lookup"><span data-stu-id="35c08-156">If you want to overwrite the Pool C settings, run the **Import-CsRgsConfiguration** cmdlet with the **ReplaceExistingSettings** option:</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - <span data-ttu-id="35c08-157">Wenn Sie die Pool C-Einstellungen nicht überschreiben möchten, verwenden Sie das Cmdlet **Import-CsRgsConfiguration** ohne die Option **ReplaceExistingSettings** .</span><span class="sxs-lookup"><span data-stu-id="35c08-157">If you do not want to overwrite the Pool C settings, use the **Import-CsRgsConfiguration** cmdlet without the **ReplaceExistingSettings** option.</span></span>
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="35c08-158">Beachten Sie, dass die Einstellungen auf Anwendungsebene des Pools b verloren gehen, wenn Sie die Einstellungen auf Anwendungsebene von Pool C mit den Einstellungen des Sicherungs Pools (Pool b) nicht überschreiben möchten, weil die Anwendung der Reaktionsgruppe nur einen Satz von Anwendungsebene speichern kann. Einstellungen pro Pool.</span><span class="sxs-lookup"><span data-stu-id="35c08-158">Keep in mind that if you do not want to overwrite the application-level settings of Pool C with the settings of the backup pool (pool B), pool B’s application-level settings will be lost because the Response Group application can store only one set of application-level settings per pool.</span></span>

    
    </div>

18. <span data-ttu-id="35c08-159">Überprüfen Sie, ob der Import der Reaktionsgruppen Konfiguration erfolgreich war, indem Sie die folgenden Cmdlets ausführen, um die in Pool C importierten Reaktionsgruppen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="35c08-159">Verify that the Response Group configuration import was successful by running the following cmdlets to display the response groups that have been imported to Pool C.</span></span>
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. <span data-ttu-id="35c08-160">Wenn die importierte Konfiguration in Pool C überprüft wurde, entfernen Sie die Antwortgruppen, die dem primären Pool gehören, aus Pool B. Dadurch wird die Ausfallzeit der Reaktionsgruppen minimiert.</span><span class="sxs-lookup"><span data-stu-id="35c08-160">When the imported configuration has been verified in pool C, remove the response groups owned by the primary pool from pool B. This will minimize the downtime of the response groups.</span></span>
    
    <span data-ttu-id="35c08-161">In diesem Schritt wird eine neue Datei mit der exportierten Konfiguration erstellt, und die Datei wird aus Pool B entfernt.</span><span class="sxs-lookup"><span data-stu-id="35c08-161">This step creates a new file with the exported configuration, and then removes the file from pool B.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. <span data-ttu-id="35c08-162">Wechseln Sie zu Pool C der nicht zugewiesenen Nummernbereiche, die von Pool a in Pool B verschoben wurden.</span><span class="sxs-lookup"><span data-stu-id="35c08-162">Move to pool C the Unassigned Number ranges that were moved from pool A to pool B.</span></span>
    
      - <span data-ttu-id="35c08-163">Erstellen Sie alle Ankündigungen, die aus Pool a in Pool B neu erstellt wurden, in Pool C neu. Wenn beim Bereitstellen der zu verschiebenden Ankündigungen Audiodateien verwendet wurden, müssen Sie diese Dateien verwenden, um die Ankündigungen in Pool C neu zu erstellen. Verwenden Sie die Cmdlets **New-CsAnnouncement** mit Pool c als übergeordneten Dienst, um die Ankündigungen in Pool c erneut zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35c08-163">Re-create in pool C all announcements that were re-created from pool A in pool B. If any audio files were used when deploying the announcements to be moved, you will need to use these files to re-create the announcements in pool C. To re-create the announcements in pool C, use the **New-CsAnnouncement** cmdlets, with pool C as the Parent service.</span></span>
    
      - <span data-ttu-id="35c08-164">Retarget to Pool C alle nicht zugewiesenen Nummernbereiche, die von Pool a an Pool B erneut ausgerichtet wurden. führen Sie das folgende Cmdlet für jeden nicht zugewiesenen Nummernbereich aus, der neu ausgerichtet werden muss:</span><span class="sxs-lookup"><span data-stu-id="35c08-164">Retarget to pool C all the unassigned number ranges that were retargeted from pool A to pool B. Run the following cmdlet for every Unassigned Number range that needs to be retargeted:</span></span>
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - <span data-ttu-id="35c08-165">Optional Entfernen Sie aus Pool b die Ankündigungen, die in Pool C neu erstellt wurden, wenn Sie in Pool b nicht mehr verwendet werden. Verwenden Sie das Cmdlet **Remove-CsAnnouncement** , um Ankündigungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="35c08-165">(Optional) Remove from pool B the announcements that were re-created in pool C if they are no longer in use in pool B. To remove announcements, use the **Remove-CsAnnouncement** cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="35c08-166">Dieser Schritt ist nicht für nicht zugewiesene Nummernbereiche erforderlich, die "Exchange um" als Ankündigungsdienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="35c08-166">This step is not required for unassigned number ranges that use "Exchange UM" as the announcement service.</span></span>

        
        </div>

21. <span data-ttu-id="35c08-167">Bereinigen Sie die Benutzerdaten von Pool a in Pool B, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-167">Clean up user data of pool A in pool B by running the following cmdlet:</span></span>
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. <span data-ttu-id="35c08-168">Gehen Sie im Topologie-Generator wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="35c08-168">Do the following in Topology Builder:</span></span>
    
      - <span data-ttu-id="35c08-169">Koppeln Sie Pool a und Pool b. Pair Pool b und Pool C. Entfernen Sie dann Pool A aus der Topologie, und veröffentlichen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="35c08-169">Unpair pool A and pool B. Pair pool B and pool C. Then remove Pool A from the topology and publish it.</span></span> <span data-ttu-id="35c08-170">Gehen Sie hierfür wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="35c08-170">To do so:</span></span>
        
          - <span data-ttu-id="35c08-171">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf Pool B, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="35c08-171">In Topology Builder, right-click on Pool B, and then click **Edit Properties**.</span></span>
        
          - <span data-ttu-id="35c08-172">Klicken Sie im linken Bereich auf **Widerstandsfähigkeit** .</span><span class="sxs-lookup"><span data-stu-id="35c08-172">Click **Resiliency** in the left pane.</span></span>
        
          - <span data-ttu-id="35c08-173">Wählen Sie im Feld unterhalb des **zugehörigen Backup-Pools**Pool C aus. Beachten Sie, dass im zugehörigen Auswahlfeld des Sicherungs Pools zunächst Pool A angezeigt wird, da Pool B zuvor diesem Pool zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="35c08-173">In the box below **Associated Backup Pool**, select Pool C. Note that the Associated Backup Pool selection box will initially display pool A, because pool B was previously associated with this pool.</span></span>
        
          - <span data-ttu-id="35c08-174">Wählen Sie **Automatisches Failover und Failback für Sprachdienste** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="35c08-174">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
            
            <span data-ttu-id="35c08-175">Wenn Sie die Details zu diesem Pool anzeigen, erscheint der zugeordnete Pool jetzt im rechten Bereich unter **Flexibilität**. </span><span class="sxs-lookup"><span data-stu-id="35c08-175">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>
        
          - <span data-ttu-id="35c08-176">Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf Pool A, und klicken Sie dann auf Löschen.</span><span class="sxs-lookup"><span data-stu-id="35c08-176">In the console tree, right-click pool A, and then click Delete.</span></span>
        
          - <span data-ttu-id="35c08-177">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="35c08-177">Publish the topology.</span></span>

23. <span data-ttu-id="35c08-178">Führen Sie die Trap Ping-Anwendung im Pool c aus, um die Backup-Dienstanwendung zu installieren, und starten Sie dann die Sicherungsdienst Anwendung, indem Sie die folgenden Schritte aus dem Bereitstellungsordner auf einem lokalen Computer in Pool c ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-178">Run the bootstrapping application on pool C to install the backup service application, and then start the backup service application by running the following from the deployment folder on a local machine in pool C:</span></span>
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. <span data-ttu-id="35c08-179">Starten Sie die Sicherungsdienst Anwendung in Pool B neu, indem Sie die folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-179">Restart the backup service application on pool B by running the following cmdlets:</span></span>
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. <span data-ttu-id="35c08-180">Wenn Pool c ein Standard Edition (SE)-Pool und Pool B über CMS verfügt, installieren Sie die CMS-Datenbank manuell in Pool c, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-180">If pool C is a Standard Edition (SE) Pool and pool B has CMS, install the CMS database manually on pool C by running the following cmdlet:</span></span>
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. <span data-ttu-id="35c08-181">Rufen Sie den Sicherungsdienst auf, um alte Konferenzinhalte von Pool b zu Pool c zu synchronisieren, die vor dem Kombinieren von b und c generiert wurden, und zum Synchronisieren von neuem Konferenz Inhalt von Pool c zu Pool b, der nach dem Starten von Pool c und vor dem Kombinieren von b und c generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="35c08-181">Invoke the backup service to sync old conferencing content from pool B to pool C that was generated before pairing B and C together, and to sync new conferencing content from pool C to pool B that was generated after starting pool C and before B and C were paired together.</span></span> <span data-ttu-id="35c08-182">Führen Sie dazu die folgenden Cmdlets aus:</span><span class="sxs-lookup"><span data-stu-id="35c08-182">To do so, run the following cmdlets:</span></span>
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. <span data-ttu-id="35c08-183">Für jede überlebensfähige Branch Appliance X, die mit Pool A verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="35c08-183">For each Survivable Branch Appliance X associated with pool A:</span></span>
    
      - <span data-ttu-id="35c08-184">Beenden Sie SBA X, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-184">Shut down SBA X by running the following cmdlet:</span></span>
        
            Stop-CsWindowsService
    
      - <span data-ttu-id="35c08-185">Erstellen Sie eine Datei, die eine Liste der Benutzer enthält, die in SBA X verwaltet werden. Die Liste wird benötigt, wenn die Benutzer in Schritt 30 zurück in SBA X verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="35c08-185">Create a file that contains a list of users homed on SBA X. The list will be needed when the users are moved back to SBA X in step 30.</span></span> <span data-ttu-id="35c08-186">Führen Sie dazu das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="35c08-186">To do so, run the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - <span data-ttu-id="35c08-187">Erzwingen Sie, dass Benutzer, die sich in SBA X befinden, zu Pool C wechseln, indem Sie das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-187">Force users homed on SBA X to move to pool C by running the following cmdlet:</span></span>
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - <span data-ttu-id="35c08-188">Aktualisieren Sie die Daten dieser Benutzer, indem Sie zunächst die folgenden Cmdlets ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-188">Update the data of these users by first running the following cmdlets:</span></span>
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        <span data-ttu-id="35c08-189">Und führen Sie dann das folgende Skript aus:</span><span class="sxs-lookup"><span data-stu-id="35c08-189">And then run this script:</span></span>
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="35c08-190">Für Benutzer, die sich in SBAS befinden, die mit Pool a verknüpft sind, tritt ein Dienstausfall auf, bis diese Benutzer in Pool C verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="35c08-190">A service outage will occur for users who are homed on SBAs that are associated with pool A until these users are moved to pool C.</span></span>

        
        </div>

28. <span data-ttu-id="35c08-191">Gehen Sie im Topologie-Generator für jedes SBA X, das zuvor mit Pool A verknüpft ist, wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="35c08-191">In Topology Builder, for each SBA X previously associated with Pool A, do the following:</span></span>
    
      - <span data-ttu-id="35c08-192">Ändern Sie die Zuordnung in Pool C. Klicken Sie dazu auf die Verzweigungs Website, erweitern Sie den Knoten Survivable Branch Appliances oder Servers, und klicken Sie auf **Survivable Branch Appliance**.</span><span class="sxs-lookup"><span data-stu-id="35c08-192">Change the association to Pool C. To do so, click the branch site, expand the Survivable Branch Appliances or Servers node, and click **Survivable Branch Appliance**.</span></span> <span data-ttu-id="35c08-193">Wählen Sie dann den **Front-End-Pool, den Benutzer Dienste-Pool** , mit dem diese Survivable Branch-Appliance eine Verbindung herstellen soll, als Pool C aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="35c08-193">Then select the **Front End pool, User Services Pool** that this Survivable Branch Appliance will connect to as Pool C, and then click **Next**.</span></span>
    
      - <span data-ttu-id="35c08-194">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="35c08-194">Publish the topology.</span></span> <span data-ttu-id="35c08-195">Klicken Sie dazu in der Konsolenstruktur mit der rechten Maustaste auf die neue **Survivable Branch-Appliance**, klicken Sie auf **Topologie**, und klicken Sie dann auf **veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="35c08-195">To do so, in the console tree, right-click the new **Survivable Branch Appliance**, click **Topology**, and then click **Publish**.</span></span>

29. <span data-ttu-id="35c08-196">Für jede SBA X, die jetzt mit Pool C verbunden ist:</span><span class="sxs-lookup"><span data-stu-id="35c08-196">For each SBA X now associated with pool C:</span></span>
    
      - <span data-ttu-id="35c08-197">Starten Sie SBA X, indem Sie das folgende Cmdlet auf der Survivable Branch-Appliance ausführen:</span><span class="sxs-lookup"><span data-stu-id="35c08-197">Start SBA X by running the following cmdlet on the survivable branch appliance:</span></span>
        
            Start-CsWindowsService
    
      - <span data-ttu-id="35c08-198">Führen Sie das folgende Cmdlet aus, um Benutzer zu verschieben, die ursprünglich in SBA x von Pool C nach SBA x verlagert wurden.</span><span class="sxs-lookup"><span data-stu-id="35c08-198">Move users who were originally homed on SBA X from pool C to SBA X by running the following cmdlet.</span></span>
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

