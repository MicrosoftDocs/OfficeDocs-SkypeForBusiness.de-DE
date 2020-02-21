---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers-Mirror
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 658b271bc71a78c564c42fc96126ce276071709c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="460d3-102">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Mirror</span><span class="sxs-lookup"><span data-stu-id="460d3-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="460d3-103">_**Letztes Änderungsstand des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="460d3-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="460d3-104">Wenn Sie einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration haben und nur die Spiegelung fehlschlägt, befolgen Sie die Verfahren in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="460d3-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="460d3-105">Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, finden Sie unter [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="460d3-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="460d3-106">Wenn nur der primäre Fehler auftritt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013-Primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span><span class="sxs-lookup"><span data-stu-id="460d3-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="460d3-107">Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, der den zentralen Verwaltungsspeicher in lync Server 2013 hostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="460d3-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="460d3-108">Wenn ein Enterprise Edition-Mitgliedsserver, lync Server 2013 bei dem es sich nicht um den Back-End-Server handelt, fehlerhaft ist, finden Sie unter [Wiederherstellen eines Enterprise Edition](lync-server-2013-restoring-an-enterprise-edition-member-server.md)</span><span class="sxs-lookup"><span data-stu-id="460d3-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="460d3-109">Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="460d3-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="460d3-110">Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="460d3-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="460d3-111">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.</span><span class="sxs-lookup"><span data-stu-id="460d3-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="460d3-112">So stellen Sie eine Spiegeldatenbank einer Enterprise Edition-Back-End-Server</span><span class="sxs-lookup"><span data-stu-id="460d3-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="460d3-113">Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="460d3-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="460d3-114">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="460d3-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="460d3-115">Deinstallieren Sie die Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="460d3-115">Uninstall mirroring.</span></span> <span data-ttu-id="460d3-116">Geben Sie zuerst das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="460d3-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="460d3-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="460d3-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="460d3-118">Tun Sie dies für alle Datenbanktypen auf diesem Server.</span><span class="sxs-lookup"><span data-stu-id="460d3-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="460d3-119">Erstellen Sie einen sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) (db1.contoso.com) als fehlerhaften Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="460d3-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="460d3-120">Dieser Server wird als neue Spiegelungsfunktion fungieren.</span><span class="sxs-lookup"><span data-stu-id="460d3-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="460d3-121">Melden Sie sich bei einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, am neuen Server an.</span><span class="sxs-lookup"><span data-stu-id="460d3-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="460d3-122">Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz so wie vor dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="460d3-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="460d3-123">Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="460d3-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="460d3-124">Verwenden Sie den Topologie-Generator, um die Spiegeldatenbank zu installieren.</span><span class="sxs-lookup"><span data-stu-id="460d3-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="460d3-125">Führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="460d3-125">Perform the following:</span></span>
    
      - <span data-ttu-id="460d3-126">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="460d3-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="460d3-127">Klicken Sie mit der rechten Maustaste auf den Knoten lync Server 2013, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="460d3-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="460d3-128">Führen Sie den Assistenten zum **Installieren einer Datenbank** aus.</span><span class="sxs-lookup"><span data-stu-id="460d3-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="460d3-129">Wählen Sie auf der Seite **Datenbankenerstellen** die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="460d3-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="460d3-130">Führen Sie den Assistenten aus, bis eine Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="460d3-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="460d3-131">Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="460d3-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="460d3-132">Anstatt den Topologie-Generator auszuführen, können Sie das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> verwenden, um die Spiegelung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="460d3-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="460d3-133">Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="460d3-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

