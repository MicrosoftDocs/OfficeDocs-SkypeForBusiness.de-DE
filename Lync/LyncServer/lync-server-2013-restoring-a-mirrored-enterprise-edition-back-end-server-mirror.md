---
title: Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers – Spiegelung
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
ms.openlocfilehash: 84a7c5a2aa12c1599d16ec563d10e8f5147df400
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="97941-102">Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – Spiegelung</span><span class="sxs-lookup"><span data-stu-id="97941-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97941-103">_**Letztes Änderungsdatum des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="97941-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="97941-104">Wenn Sie über einen Enterprise Edition-Back-End-Server in einer gespiegelten Konfiguration verfügen und nur die Spiegelung fehlschlägt, führen Sie die Verfahren in diesem Abschnitt aus.</span><span class="sxs-lookup"><span data-stu-id="97941-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="97941-105">Wenn sowohl die primäre Datenbank als auch die Spiegelung fehlerhaft sind, lesen Sie [Wiederherstellen eines Enterprise Edition-Back-End-Servers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="97941-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="97941-106">Wenn nur der primäre Fehler auftritt, lesen Sie [Wiederherstellen eines gespiegelten Enterprise Edition-Back-End-Servers in lync Server 2013 – primär](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span><span class="sxs-lookup"><span data-stu-id="97941-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="97941-107">Wenn die Datenbank, die den zentralen Verwaltungsspeicher hostet, fehlschlägt, lesen Sie [Wiederherstellen des Servers, auf dem der zentrale Verwaltungsspeicher in lync Server 2013 gehostet](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)wird.</span><span class="sxs-lookup"><span data-stu-id="97941-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="97941-108">Wenn ein Enterprise Edition-Mitgliedsserver, der nicht der Back-End-Server ist, fehlschlägt, lesen Sie [Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md)</span><span class="sxs-lookup"><span data-stu-id="97941-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="97941-109">Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="97941-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="97941-110">Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="97941-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="97941-111">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="97941-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="97941-112">So stellen Sie eine Spiegeldatenbank für den Back-End-Server eines Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="97941-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="97941-113">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="97941-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="97941-114">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="97941-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="97941-115">Deinstallieren Sie die Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="97941-115">Uninstall mirroring.</span></span> <span data-ttu-id="97941-116">Geben Sie zuerst das folgende Cmdlet ein:</span><span class="sxs-lookup"><span data-stu-id="97941-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="97941-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97941-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="97941-118">Führen Sie diese Schritte für alle Datenbanktypen auf diesem Server aus.</span><span class="sxs-lookup"><span data-stu-id="97941-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="97941-119">Erstellen Sie einen sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) (db1.contoso.com) wie der fehlerhafte Computer, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="97941-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="97941-120">Dieser Server wird als neue Spiegelungsfunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="97941-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="97941-121">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, beim neuen Server an.</span><span class="sxs-lookup"><span data-stu-id="97941-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="97941-122">Installieren Sie SQL Server 2012 oder SQL Server 2008 R2, und halten Sie die Namen der Instanz wie vor dem Fehler.</span><span class="sxs-lookup"><span data-stu-id="97941-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="97941-123">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei einem Front-End-Server an.</span><span class="sxs-lookup"><span data-stu-id="97941-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="97941-124">Verwenden Sie den Topologie-Generator, um die Spiegeldatenbank zu installieren.</span><span class="sxs-lookup"><span data-stu-id="97941-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="97941-125">Führen Sie die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="97941-125">Perform the following:</span></span>
    
      - <span data-ttu-id="97941-126">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="97941-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="97941-127">Klicken Sie mit der rechten Maustaste auf den lync Server 2013-Knoten, klicken Sie auf **Topologie**, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="97941-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="97941-128">Folgen Sie dem Assistenten zum **Installieren der Datenbank** .</span><span class="sxs-lookup"><span data-stu-id="97941-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="97941-129">Wählen Sie auf der Seite **create databases** die Datenbanken aus, die Sie neu erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="97941-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="97941-130">Folgen Sie dem Assistenten, bis eine Aufforderung zum **Erstellen einer Spiegeldatenbank** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="97941-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="97941-131">Wählen Sie die Datenbank aus, die Sie installieren möchten, und führen Sie diesen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="97941-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="97941-132">Anstelle des Topologie-Generators können Sie das Cmdlet <STRONG>install-CsMirrorDatabase</STRONG> verwenden, um die Spiegelung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="97941-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="97941-133">Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="97941-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

