---
title: 'Lync Server 2013: Backup-Voraussetzungen für das Failover von ABC-Pools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd6bd22b29cd5031e83f0e8e8a09755c730be64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a><span data-ttu-id="ea4e7-102">Sicherungs Voraussetzungen für das Failover von ABC-Pools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea4e7-102">Backup prerequisites for ABC pool failover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea4e7-103">_**Letztes Änderungsstand des Themas:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="ea4e7-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="ea4e7-104">Um den größtmöglichen Nutzen aus dem Failover-Verfahren für das ABC-Pool zu ziehen, müssen Sie vor dem Ausfall und dem Failover bestimmte Sicherungen durchführen:</span><span class="sxs-lookup"><span data-stu-id="ea4e7-104">To get the maximum benefit from using the ABC pool failover procedure, you must perform certain backups before the disaster and failover happen:</span></span>

  - <span data-ttu-id="ea4e7-105">Sie müssen regelmäßig die LIS-Konfigurationsdaten (Location Information Service) aus Pool A mithilfe des **Export-CsLISConfiguration-** Cmdlets sichern.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-105">You must regularly back up the Location Information Service (LIS) configuration data from pool A by using the **Export-CsLISConfiguration** cmdlet.</span></span>
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - <span data-ttu-id="ea4e7-106">Sie müssen die Konfigurationsdaten der Reaktionsgruppe in Pool A mithilfe des Cmdlets **Export-CsRgsConfiguration** regelmäßig sichern.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-106">You must regularly back up the Response Group configuration data in pool A by using the **Export-CsRgsConfiguration** cmdlet.</span></span>
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <span data-ttu-id="ea4e7-107">Im Allgemeinen wird empfohlen, tägliche Sicherungen durchzuführen, wenn jedoch ein hohes Umfang an Änderungen vorliegt, sollten Sie häufiger Sicherungen planen.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-107">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="ea4e7-108">Die Menge an Informationen, die Sie im Falle eines Notfalls verlieren können, hängt von der Häufigkeit Ihrer Sicherungen sowie von der Häufigkeit und dem Umfang der Änderungen ab.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-108">The amount of information that you can lose in the event of a disaster depends on the frequency of your backups, as well as on the frequency and volume of changes.</span></span>
    
    <span data-ttu-id="ea4e7-109">In der Reaktionsgruppenanwendung kann nur eine Gruppe von Einstellungen auf Anwendungsebene pro Pool gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-109">The Response Group application can store only one set of application-level settings per pool.</span></span> <span data-ttu-id="ea4e7-110">Auf diese Einstellungen kann über die Cmdlets **Get-CsRgsConfiguration** zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-110">These settings can be accessed through the **Get-CsRgsConfiguration** cmdlets.</span></span> <span data-ttu-id="ea4e7-111">Die Einstellungen umfassen die standardmäßige Music-on-Hold-Konfiguration, die standardmäßige Music-on-Hold-Audiodatei, die Kulanzzeit für den Agent-Rückruf und die Konfiguration des Anruf Kontexts.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-111">The settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ring-back grace period, and the call context configuration.</span></span> <span data-ttu-id="ea4e7-112">Diese Einstellungen können über das **Import-CsRgsConfiguration-** Cmdlet mithilfe des **ReplaceExistingSettings** -Parameters von einem Pool an einen anderen übertragen werden, aber mit diesem Vorgang werden alle Einstellungen auf Anwendungsebene im Ziel Pool außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-112">These settings can be transferred from one pool to another through the **Import-CsRgsConfiguration** cmdlet by using the **ReplaceExistingSettings** parameter, but this operation will override any application-level settings in the destination pool.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ea4e7-113">Bewahren Sie an einem separaten Speicherort eine Sicherungskopie aller Original-Audiodateien auf, die zum Konfigurieren des Reaktionsgruppenanwendung verwendet wurden (also alle Aufzeichnungen oder Musikdateien, die in einem Archiv gespeichert sind).</span><span class="sxs-lookup"><span data-stu-id="ea4e7-113">In a separate location, keep a backup copy of all the original audio files that have been used to configure the Response Group application (that is, any recordings or music-on-hold files).</span></span>

    
    </div>
    
    <span data-ttu-id="ea4e7-114">Wenn Sie über benutzerdefinierte Musikarchiv Dateien verfügen, die in einem Pool für das Parken von Anrufen hochgeladen wurden, sollten Sie eine Kopie davon an einem anderen Speicherort aufbewahren.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-114">If you have any customized music-on-hold files that have been uploaded for Call Park in a pool, you should keep a copy of these in another location.</span></span> <span data-ttu-id="ea4e7-115">Diese Dateien werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-115">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea4e7-116">Das Anwendung zum Parken von anrufen kann nur einen Einstellungssatz und eine benutzerdefinierte Audiodatei pro Pool speichern.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-116">The Call Park application can store only one set of settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="ea4e7-117">Auf diese Einstellungen kann über das Cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-117">These settings can be accessed through the <STRONG>Get-CsCpsConfiguration</STRONG> cmdlet.</span></span> <span data-ttu-id="ea4e7-118">Da der Notfall Wiederherstellungsmechanismus für das Parken von Anrufen auf dem Anwendung zum Parken von Anrufen des Sicherungs Pools beruht, werden die Einstellungen des primären Pools nicht gesichert oder erhalten, wenn ein Notfall auftritt.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-118">Because the disaster recovery mechanism for Call Park relies on the Call Park application of the backup pool, the settings of the primary pool are not backed up or preserved if a disaster occurs.</span></span> <span data-ttu-id="ea4e7-119">Wenn der primäre Pool verloren geht, können diese Einstellungen nicht wiederhergestellt werden, und wenn ein neuer Pool bereitgestellt wird, um den primären Pool zu ersetzen, müssen die Einstellungen für das Parken von Anrufen und alle angepassten Musikdateien, die in der Warteschleife gespeichert sind, neu konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-119">If the primary pool is lost, these settings cannot be recovered, and when a new pool is deployed to replace the primary pool, the Call Park settings and any customized music-on-hold audio file would need to be reconfigured.</span></span>

    
    </div>

  - <span data-ttu-id="ea4e7-120">Wenn Sie Ankündigungen als Teil des Voice-Features für nicht zugewiesene Nummern konfigurieren, wird empfohlen, dass Sie an einem anderen Speicherort eine Kopie jeder Originalaudiodatei aufbewahren, die bei der Erstkonfiguration verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-120">If you configure any announcements as part of the Unassigned Number Voice Feature, we recommend that you keep in another location a copy of any original audio file used during the initial configuration.</span></span> <span data-ttu-id="ea4e7-121">Wenn Sie dies nicht getan haben, können Sie eine Kopie der konfigurierten Audiodateien im Dateispeicher des Servers oder Pools abrufen, in den die Audiodateien importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-121">If you did not do that, you can get a copy of the configured audio files in the file store of the server or pool to which the audio files were imported.</span></span> <span data-ttu-id="ea4e7-122">Diese Dateien werden nicht als Teil des lync Server 2013 Notfall Wiederherstellungsprozesses gesichert, und Sie gehen verloren, wenn die in den Pool hochgeladenen Dateien beschädigt, beschädigt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-122">These files are not backed up as part of the Lync Server 2013 disaster recovery process, and they will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span> <span data-ttu-id="ea4e7-123">Wenn Sie alle Audiodateien kopieren möchten, die zum Konfigurieren der VoIP-Funktion für nicht zugewiesene Nummern aus dem Dateispeicher eines Servers oder Pools verwendet werden, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ea4e7-123">To copy all the audio files used to configure the Unassigned Number Voice Feature from the file store of a server or a pool, use:</span></span>
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - <span data-ttu-id="ea4e7-124">Wenn Sie Überwachungs-und Archivierungsdatenbanken in einem Pool haben, sollten Sie SQL Server-Verwaltungstools verwenden, um Sie zu sichern.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-124">If you have Monitoring and Archiving databases in a pool, you should use SQL Server management tools to back them up.</span></span> <span data-ttu-id="ea4e7-125">Im ABC-Failover-Verfahren werden Überwachungs-und Archivierungsdatenbanken nicht beibehalten, wenn Sie in Pool A zusammengefasst werden, da diese Datenbanken nicht über lync Server Sicherungsdienst gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="ea4e7-125">In the ABC failover procedure, Monitoring and Archiving databases are not preserved if they are collocated in pool A, because these databases are not backed up through Lync Server Backup Service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

