---
title: 'Lync Server 2013: Ausführen eines Failovers für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="32cae-102">Ausführen eines Failovers für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32cae-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32cae-103">_**Letztes Änderungsdatum des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="32cae-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="32cae-104">Das Failover für beständigen Chat Server ist hauptsächlich ein manueller Prozess.</span><span class="sxs-lookup"><span data-stu-id="32cae-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="32cae-105">Das Failover-Verfahren basiert auf der Annahme, dass das sekundäre Rechenzentrum in Betrieb ist, aber die Server Dienste für beständigen Chat, bei denen sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="32cae-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="32cae-106">Die primäre Datenbank des beständigen Chat Servers und die Spiegeldatenbank des beständigen Chat Servers sind nicht mehr vorhanden.</span><span class="sxs-lookup"><span data-stu-id="32cae-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="32cae-107">Der lync Server-Front-End-Server ist ausgefallen.</span><span class="sxs-lookup"><span data-stu-id="32cae-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="32cae-108">Das Verfahren basiert auf zwei grundlegenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="32cae-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="32cae-109">Wiederherstellen der primären persistent Chat-Datenbank (MGC)</span><span class="sxs-lookup"><span data-stu-id="32cae-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="32cae-110">Einrichten der Spiegelung für die neue Primärdatenbank</span><span class="sxs-lookup"><span data-stu-id="32cae-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="32cae-111">Die beständige Chat-Kompatibilitätsdatenbank (mgccomp) ist nicht fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="32cae-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="32cae-112">Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="32cae-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="32cae-113">Es liegt in ihrer Verantwortung als Administrator des beständigen Chats, die Adapter Ausgabe ordnungsgemäß zu verwalten, um Datenverluste zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="32cae-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="32cae-114">So führen Sie einen Failover für beständigen Chat Server durch</span><span class="sxs-lookup"><span data-stu-id="32cae-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="32cae-115">Entfernen Sie den Protokollversand aus der Datenbank des beständigen Chat Server-Sicherungs Protokolls.</span><span class="sxs-lookup"><span data-stu-id="32cae-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="32cae-116">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Datenbankinstanz her, in der sich die Datenbank des beständigen Chat Server-Backup MGC befindet.</span><span class="sxs-lookup"><span data-stu-id="32cae-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="32cae-117">Öffnen Sie ein Abfragefenster zur Masterdatenbank.</span><span class="sxs-lookup"><span data-stu-id="32cae-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="32cae-118">Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:</span><span class="sxs-lookup"><span data-stu-id="32cae-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="32cae-119">Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.</span><span class="sxs-lookup"><span data-stu-id="32cae-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="32cae-120">Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="32cae-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="32cae-121">Ausführliche Informationen finden Sie unter "Vorgehensweise: Anwenden einer Transaktionsprotokollsicherung (Transact-SQL http://go.microsoft.com/fwlink/p/?linkid=247428)" unter.</span><span class="sxs-lookup"><span data-stu-id="32cae-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="32cae-p103">Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="32cae-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="32cae-124">Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:</span><span class="sxs-lookup"><span data-stu-id="32cae-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="32cae-125">**exec SP\_who2** , um Verbindungen zur MGC-Datenbank zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="32cae-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="32cae-126">\*\*Kill \<SPID\> \*\* , um diese Verbindungen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="32cae-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="32cae-127">Stellen Sie die Datenbank online bereit:</span><span class="sxs-lookup"><span data-stu-id="32cae-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="32cae-128">**restore database mgc with recovery**.</span><span class="sxs-lookup"><span data-stu-id="32cae-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="32cae-129">Verwenden Sie in der lync Server-Verwaltungsshell den Befehl **Satz-CsPersistentChatState-Identity "Service: ATL-CS-001.litwareinc.com" – PoolState FailedOver** , um ein Failover zur MGC-Sicherungsdatenbank durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="32cae-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="32cae-130">Achten Sie darauf, den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat durch „atl-cs-001.litwareinc.com“ zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="32cae-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="32cae-131">Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.</span><span class="sxs-lookup"><span data-stu-id="32cae-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="32cae-132">Verwenden Sie in der lync Server-Verwaltungsshell das Cmdlet " **install-CsMirrorDatabase** ", um eine Hochverfügbarkeits-Spiegelung für die Sicherungsdatenbank einzurichten, die jetzt als primäre Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="32cae-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="32cae-133">Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz.</span><span class="sxs-lookup"><span data-stu-id="32cae-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="32cae-134">Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="32cae-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="32cae-135">Ausführliche Informationen finden Sie im Abschnitt "Verwenden von lync Server-Verwaltungsshell-Cmdlets" unter [Bereitstellen der SQL-Spiegelung für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="32cae-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="32cae-136">Setzen Sie die aktiven Server für den beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="32cae-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="32cae-137">Verwenden Sie in der lync Server-Befehlsshell das Cmdlet " **Satz-CsPersistentChatActiveServer** ", um die Liste der aktiven Server einzurichten.</span><span class="sxs-lookup"><span data-stu-id="32cae-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="32cae-138">Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="32cae-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="32cae-139">An diesem Punkt wird das Failover von der primären Datenbank des beständigen Chat Servers zur Datenbank des beständigen Chat Servers erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="32cae-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

