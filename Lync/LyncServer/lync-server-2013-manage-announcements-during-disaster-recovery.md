---
title: 'Lync Server 2013: Verwalten von Ankündigungen während der Notfallwiederherstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f7c54293205ac9246db39950e701074b12a42a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="947d6-102">Verwalten von Ankündigungen während der Notfallwiederherstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="947d6-102">Manage announcements during disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="947d6-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="947d6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="947d6-104">Lync Server 2013 unterstützt Ankündigungen für Anrufe bei nicht zugewiesenen Nummern während Ausfällen.</span><span class="sxs-lookup"><span data-stu-id="947d6-104">Lync Server 2013 supports announcements for calls to unassigned numbers during outages.</span></span> <span data-ttu-id="947d6-105">Die Wiederherstellung der Ansagefunktionalität bei einem Ausfall ist optional.</span><span class="sxs-lookup"><span data-stu-id="947d6-105">Restoring announcement functionality during an outage is optional.</span></span> <span data-ttu-id="947d6-106">Wenn Sie sich dafür entscheiden, Ansagen bei einem Ausfall wiederherzustellen, müssen Sie die Ansagekonfiguration im Sicherungspool erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="947d6-106">If you choose to restore announcements during an outage, you need recreate your announcement configuration in the backup pool.</span></span> <span data-ttu-id="947d6-107">In diesem Abschnitt wird die Vorgehensweise beschrieben, falls Sie Ansagen bei einer Notfallwiederherstellung wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="947d6-107">This section describes what you need to do if you choose to restore announcements during disaster recovery.</span></span>

<span data-ttu-id="947d6-108">Dieser Abschnitt bezieht sich auf nicht zugewiesene Nummernbereiche, die das Ankündigungsanwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="947d6-108">This section applies to unassigned number ranges that use the Announcement application.</span></span> <span data-ttu-id="947d6-109">Für nicht zugewiesene Nummernbereiche, die die automatische Telefonzentrale von Exchange Unified Messaging (UM) verwenden, ist dieser Abschnitt nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="947d6-109">This section does not apply to unassigned number ranges that use Exchange Unified Messaging (UM) Auto Attendant.</span></span>

<div>

## <a name="before-an-outage"></a><span data-ttu-id="947d6-110">Vor einem Ausfall</span><span class="sxs-lookup"><span data-stu-id="947d6-110">Before an Outage</span></span>

<span data-ttu-id="947d6-111">Unabhängig davon, ob Sie Ankündigungen während Ausfällen verwenden, sollten Sie separate Sicherungen aller benutzerdefinierten Audiodateien durchführen, die Sie für die Ankündigungsanwendung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="947d6-111">Regardless of whether you choose to use announcements during outages, you should take separate backups of any customized audio files that you configured for the Announcement application.</span></span> <span data-ttu-id="947d6-112">Benutzerdefinierte Ankündigungen werden im Rahmen des lync Server Notfall Wiederherstellungsprozesses nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="947d6-112">Customized announcements are not backed up as part of the Lync Server disaster recovery process.</span></span> <span data-ttu-id="947d6-113">Wenn Sie keine separaten Backups der Dateien erstellen und die auf den Server oder in den Pool hochgeladenen Dateien beschädigt, infiziert oder gelöscht werden, sind die Dateien verloren.</span><span class="sxs-lookup"><span data-stu-id="947d6-113">If you do not take separate backups of the files and the files that you uploaded to the server or pool are damaged, corrupted, or erased, the files will be lost.</span></span>

<span data-ttu-id="947d6-114">Wenn Sie keine Sicherungskopien von benutzerdefinierten Audiodateien haben und die ursprünglichen Audiodateien nicht mehr verfügbar sind, finden Sie die Audiodateien, die Sie für eine Ankündigungsanwendung konfiguriert haben, indem Sie in der Dateispeicher für den Server oder Pool suchen, in dem Sie ursprünglich die Dateien wurden importiert.</span><span class="sxs-lookup"><span data-stu-id="947d6-114">If you do not have backup copies of customized audio files, and the original audio files are no longer available, you can find the audio files that you configured for an Announcement application by looking in the File Store for the server or pool where you originally imported the files.</span></span> <span data-ttu-id="947d6-115">Sie können alle Audiodateien, die Sie für den Ankündigungsanwendung konfiguriert haben, aus dem Dateispeicher kopieren.</span><span class="sxs-lookup"><span data-stu-id="947d6-115">You can copy all the audio files that you configured for the Announcement application from the File Store.</span></span>

<span data-ttu-id="947d6-116">**So kopieren Sie Audiodateien aus dem Dateispeicher**</span><span class="sxs-lookup"><span data-stu-id="947d6-116">**To copy audio files from the file store**</span></span>

1.  <span data-ttu-id="947d6-117">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="947d6-117">At the command line, run:</span></span>
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    <span data-ttu-id="947d6-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="947d6-118">For example:</span></span>
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    <span data-ttu-id="947d6-119">Dabei steht X-ApplicationServer-X für die Dienst-ID des Anwendungsservers des Pools (z. B. 1-ApplicationServer-1).</span><span class="sxs-lookup"><span data-stu-id="947d6-119">Where X-ApplicationServer-X refers to the service ID of the Application Server of the pool (for example, 1-ApplicationServer-1")</span></span>


</div>

<div>

## <a name="during-an-outage"></a><span data-ttu-id="947d6-120">Bei einem Ausfall</span><span class="sxs-lookup"><span data-stu-id="947d6-120">During an Outage</span></span>

<span data-ttu-id="947d6-121">Wenn Sie die Ankündigungsanwendung während eines Ausfalls verwenden möchten, müssen Sie die Ankündigungs Konfiguration im Sicherungspool durch Ausführen der in diesem Abschnitt beschriebenen Aufgaben neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="947d6-121">To use the Announcement application during an outage, you need to recreate the announcement configuration in the backup pool by performing the tasks described in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="947d6-122">Es wird empfohlen, diese Schritte nach dem Failover auf den Sicherungspool auszuführen. Sobald Sie nämlich Schritt 2 ausführen, wird der Sicherungspool zum Besitzer der nicht zugewiesenen Nummernbereiche.</span><span class="sxs-lookup"><span data-stu-id="947d6-122">We recommend that you perform these tasks after you fail over to the backup pool, because as soon as you perform step 2, the backup pool takes ownership of the unassigned number ranges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="947d6-123">Für Nummernbereiche, die eine Exchange UM-Rufnummer der automatischen Telefonzentrale verwenden, sind diese Schritte nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="947d6-123">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="947d6-124">**So erstellen Sie die Ankündigungs Konfiguration im Sicherungspool neu**</span><span class="sxs-lookup"><span data-stu-id="947d6-124">**To recreate the announcement configuration in the backup pool**</span></span>

1.  <span data-ttu-id="947d6-125">Führen Sie die folgenden Aktionen aus, um die Ansagen, die Sie im primären Pool erstellt haben, im Sicherungspool erneut zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="947d6-125">Recreate the announcements that you deployed in the primary pool in the backup pool by doing the following:</span></span>
    
    1.  <span data-ttu-id="947d6-126">Importieren Sie alle im primären Pool verwendeten Audiodateien in den Sicherungspool, indem Sie das Cmdlet **Import-CsAnnouncementFile** verwenden und den Sicherungspool für den Parameter Parent angeben.</span><span class="sxs-lookup"><span data-stu-id="947d6-126">Import any audio files used in the primary pool to the backup pool by using the **Import-CsAnnouncementFile** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    2.  <span data-ttu-id="947d6-127">Erstellen Sie jede Ansage mit dem **New-CsAnnouncement-Cmdlet neu** , und geben Sie den Sicherungspool für den Parameter Parent an.</span><span class="sxs-lookup"><span data-stu-id="947d6-127">Recreate each announcement by using the **New-CsAnnouncement** cmdlet and specifying the backup pool for the Parent parameter.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="947d6-128">Ausführliche Informationen zur Verwendung dieser Parameter zum Erstellen von Ankündigungen im Sicherungspool finden Sie unter <A href="lync-server-2013-create-an-announcement.md">Create a Announcement in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="947d6-128">For details about using these parameters to create announcements in the backup pool, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="947d6-129">Nachdem Sie alle Ansagen im Sicherungspool erneut erstellt haben, leiten Sie alle nicht zugewiesenen Nummernbereiche, die Ansagen im primären Pool verwenden, an die erneut erstellten Ansagen im Sicherungspool um.</span><span class="sxs-lookup"><span data-stu-id="947d6-129">After all announcements are recreated in the backup pool, redirect all the unassigned number ranges that use announcements in the primary pool to the recreated announcements in the backup pool.</span></span>
    
    <span data-ttu-id="947d6-130">Für jeden nicht zugewiesenen Nummernbereich, der eine Ansage im primären Pool verwendet, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="947d6-130">For each unassigned number range that uses an announcement in the primary pool, run the following:</span></span>
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a><span data-ttu-id="947d6-131">Nach einem Ausfall</span><span class="sxs-lookup"><span data-stu-id="947d6-131">After the Outage</span></span>

<span data-ttu-id="947d6-132">Wenn der primäre Pool nicht mehr verfügbar ist, müssen Sie die nicht zugewiesenen Nummernbereiche, die Sie für den Ausfall geändert haben, wieder an den primären Pool umleiten.</span><span class="sxs-lookup"><span data-stu-id="947d6-132">When the primary pool becomes available, you need to redirect the unassigned number ranges that you changed for the outage back to the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="947d6-133">Für Nummernbereiche, die eine Exchange UM-Rufnummer der automatischen Telefonzentrale verwenden, sind diese Schritte nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="947d6-133">These steps are not required for number ranges that use an Exchange UM Auto Attendant phone number.</span></span>



</div>

<span data-ttu-id="947d6-134">**So stellen Sie Ankündigungen im primären Pool wieder her**</span><span class="sxs-lookup"><span data-stu-id="947d6-134">**To restore announcements in the primary pool**</span></span>

1.  <span data-ttu-id="947d6-p105">Wenn Sie den primären Pool während der Wiederherstellung erneut erstellen mussten, müssen Sie die Ansagen im primären Pool erneut erstellen. Dazu importieren Sie die Audiodateien und erstellen Ankündigungen, so wie das beim Sicherungspool der Fall war, außer dass Sie den primären Pool für den Parent-Parameter angeben. Weitere Informationen hierzu finden Sie unter "Bei einem Ausfall" weiter oben in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="947d6-p105">If you had to rebuild the primary pool during the recovery, you need to recreate the announcements in the primary pool by importing the audio files and creating announcements, just as you did in the backup pool, except that you specify the primary pool for the Parent parameter. For details, see "During an Outage" earlier in this topic.</span></span>

2.  <span data-ttu-id="947d6-137">Für jeden nicht zugewiesenen Nummernbereich, den Sie für den Ausfall geändert haben, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="947d6-137">For each unassigned number range that you changed for the outage, run the following:</span></span>
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  <span data-ttu-id="947d6-138">Entfernen Sie optional die Ansagen, die Sie im Sicherungspool erneut erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="947d6-138">Optionally, remove the announcements that you recreated in the backup pool.</span></span> <span data-ttu-id="947d6-139">Hier erhalten Sie eine Liste der Ankündigungen für den Sicherungspool Ankündigungsanwendung.</span><span class="sxs-lookup"><span data-stu-id="947d6-139">Get a list of announcements for the backup pool Announcement application.</span></span> <span data-ttu-id="947d6-140">Führen Sie an der Eingabeaufforderung Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="947d6-140">At the command line, run:</span></span>
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    <span data-ttu-id="947d6-141">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="947d6-141">For example:</span></span>
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    <span data-ttu-id="947d6-p107">Suchen Sie in der zurückgegebenen Liste die Ansagen, die Sie entfernen möchten, und kopieren Sie die GUIDs. Führen Sie für jede Ansage, die Sie entfernen möchten, Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="947d6-p107">In the resulting list, locate the announcements you want to remove and copy the GUIDs. For each announcement you want to remove, run:</span></span>
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    <span data-ttu-id="947d6-144">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="947d6-144">For example:</span></span>
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

