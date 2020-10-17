---
title: 'Lync Server 2013: Wiederherstellen einer Standard Edition-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 479e4c690d0ca7931631f3bc553d1dafc2a10ea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511562"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="f8e72-102">Wiederherstellen eines Standard Edition-Servers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8e72-102">Restoring a Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8e72-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f8e72-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f8e72-104">Wenn ein Standard Edition-Server, auf dem der zentrale Verwaltungsspeicher nicht gehostet wird, fehlerhaft ist, führen Sie die Verfahren in diesem Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="f8e72-104">If a Standard Edition server that does not host the Central Management store fails, follow the procedures in this section.</span></span> <span data-ttu-id="f8e72-105">Wenn der zentrale Verwaltungsspeicher fehlschlägt, finden Sie weitere Informationen unter [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="f8e72-105">If the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="f8e72-106">Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="f8e72-106">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="f8e72-107">Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="f8e72-107">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="f8e72-108">Am besten erstellen Sie die Abbildkopie, nachdem Sie das Betriebssystem und SQL Server installiert und die Zertifikate wiederhergestellt oder erneut registriert haben.</span><span class="sxs-lookup"><span data-stu-id="f8e72-108">You might want to take the image copy after you install the operating system and SQL Server, and restore or re-enroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a><span data-ttu-id="f8e72-109">So stellen Sie einen Standard Edition-Server wieder her</span><span class="sxs-lookup"><span data-stu-id="f8e72-109">To restore a Standard Edition server</span></span>

1.  <span data-ttu-id="f8e72-110">Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="f8e72-110">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8e72-111">Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f8e72-111">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="f8e72-112">Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins und der lokalen Administratoren ist, bei dem Server an, den Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="f8e72-112">From a user account that is a member of the RTCUniversalServerAdmins group and the Local Administrators group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="f8e72-113">Stellen Sie die Dateispeicher wieder her, indem Sie den entsprechenden Dateispeicher von $Backup an den Dateispeicher Speicherort auf dem Server kopieren und den Ordner freigeben.</span><span class="sxs-lookup"><span data-stu-id="f8e72-113">Restore the File Store by copying the appropriate File Store from $Backup to the File Store location on the server and share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f8e72-114">Der Pfad und der Dateiname für das wiederhergestellte Dateispeicher sollten genau mit dem gesicherten Dateispeicher identisch sein, damit Komponenten, die die Dateien verwenden, darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="f8e72-114">The path and file name for the restored File Store should be exactly the same as the backed up File Store so that components that use the files can access them.</span></span>

    
    </div>

4.  <span data-ttu-id="f8e72-115">Ausführen des Topologie-Generators:</span><span class="sxs-lookup"><span data-stu-id="f8e72-115">Run Topology Builder:</span></span>
    
    1.  <span data-ttu-id="f8e72-116">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="f8e72-116">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    2.  <span data-ttu-id="f8e72-117">Klicken Sie auf **Topologie aus einer vorhandenen Bereitstellung herunterladen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8e72-117">Click **Download Topology from existing deployment**, and then click **OK**.</span></span>
    
    3.  <span data-ttu-id="f8e72-p103">Wählen Sie die Topologie aus, und klicken Sie auf **Speichern**. Klicken Sie auf **Ja**, um die Auswahl zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="f8e72-p103">Select the topology, and then click **Save**. Click **Yes** to confirm your selection.</span></span>

5.  <span data-ttu-id="f8e72-120">Wechseln Sie zum lync Server Installationsordner oder Medien, und starten Sie dann den lync Server-Bereitstellungs-Assistenten, der sich unter \\ Setup \\ amd64 \\Setup.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="f8e72-120">Browse to the Lync Server installation folder or media, and then start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span> <span data-ttu-id="f8e72-121">Verwenden Sie den lync Server-Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f8e72-121">Use the Lync Server Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="f8e72-122">Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f8e72-122">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="f8e72-123">Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server Komponenten** aus, um die lync Server-Server Rollen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f8e72-123">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server roles.</span></span>
    
    3.  <span data-ttu-id="f8e72-124">Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f8e72-124">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="f8e72-125">Führen Sie **Schritt 4: Dienste starten** aus, um die Dienste auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="f8e72-125">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="f8e72-126">Ausführliche Informationen über die Ausführung des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation zu der Serverrolle, die Sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="f8e72-126">For details about running the Deployment Wizard, see the Deployment documentation for the server role you are restoring.</span></span>

6.  <span data-ttu-id="f8e72-127">Stellen Sie Benutzerdaten wieder her, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="f8e72-127">Restore user data by performing the following:</span></span>
    
    1.  <span data-ttu-id="f8e72-128">Kopieren Sie ExportedUserData.zip aus $Backup \\ in ein lokales Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f8e72-128">Copy ExportedUserData.zip from $Backup\\ to a local directory.</span></span>
    
    2.  <span data-ttu-id="f8e72-129">Bevor Sie die Benutzerdaten wiederherstellen, müssen Sie lync-Dienste beenden.</span><span class="sxs-lookup"><span data-stu-id="f8e72-129">Before you restore the user data, you must stop Lync services.</span></span> <span data-ttu-id="f8e72-130">Geben Sie dazu Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="f8e72-130">To do so, type:</span></span>
        
            Stop-CsWindowsService
    
    3.  <span data-ttu-id="f8e72-131">Geben Sie in die Befehlszeile Folgendes ein, um die Benutzerdaten wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="f8e72-131">To restore the user data, at the command line, type:</span></span>
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        <span data-ttu-id="f8e72-132">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f8e72-132">For example:</span></span>
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  <span data-ttu-id="f8e72-133">Starten Sie lync Services neu, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="f8e72-133">Restart Lync services by typing:</span></span>
        
            Start-CsWindowsService

7.  <span data-ttu-id="f8e72-134">Wenn Sie die Reaktionsgruppe in diesem Standard Edition-Server bereitgestellt haben, stellen Sie die Konfigurationsdaten der Reaktionsgruppe wieder her.</span><span class="sxs-lookup"><span data-stu-id="f8e72-134">If you deployed Response Group on this Standard Edition server, restore the Response Group configuration data.</span></span> <span data-ttu-id="f8e72-135">Ausführliche Informationen finden Sie unter [Wiederherstellen von Reaktionsgruppeneinstellungen in lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f8e72-135">For details, see [Restoring Response Group settings in Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).</span></span>

8.  <span data-ttu-id="f8e72-136">Wenn Sie den beständigen Chat in diesem Standard Edition-Server bereitgestellt haben, stellen Sie die Datenbank für beständigen Chat (MGC. mdf) wieder her.</span><span class="sxs-lookup"><span data-stu-id="f8e72-136">If you deployed Persistent Chat on this Standard Edition server, restore the Persistent Chat database (mgc.mdf).</span></span>
    
    <span data-ttu-id="f8e72-137">Wenn Sie SQL Server Sicherung zum Sichern der Datenbank für beständigen Chat verwendet haben, verwenden Sie SQL Server Wiederherstellungsverfahren, um Sie wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f8e72-137">If you used SQL Server Backup to back up the Persistent Chat database, use SQL Server restore procedures to restore it.</span></span>
    
    <span data-ttu-id="f8e72-138">Wenn Sie das Export-CsPersistentChatData-Cmdlet zum Sichern verwendet haben, verwenden Sie das Import-CsPersistentChatData, um es wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f8e72-138">If you used the Export-CsPersistentChatData cmdlet to back it up, use the Import-CsPersistentChatData to restore it.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

