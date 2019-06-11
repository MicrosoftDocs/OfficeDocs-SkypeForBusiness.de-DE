---
title: 'Lync Server 2013: Ausführen eines Failbacks für den Server für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="ddf39-102">Ausführen eines Failbacks für den Server für beständigen Chat in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddf39-102">Failing back Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddf39-103">_**Letztes Änderungsdatum des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="ddf39-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="ddf39-104">In diesem Verfahren werden die erforderlichen Schritte zum Wiederherstellen nach einem Server Fehler des beständigen Chats und zum Wiederherstellen von Vorgängen aus dem primären Rechenzentrum erläutert.</span><span class="sxs-lookup"><span data-stu-id="ddf39-104">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>

<span data-ttu-id="ddf39-105">Beim Server Ausfall des beständigen Chats leidet das primäre Rechenzentrum unter einem vollständigen Ausfall, und die primäre und die Spiegeldatenbank werden nicht mehr zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="ddf39-105">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="ddf39-106">Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.</span><span class="sxs-lookup"><span data-stu-id="ddf39-106">The primary data center fails over to the backup server.</span></span>

<span data-ttu-id="ddf39-107">Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="ddf39-107">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="ddf39-108">Bei diesem Verfahren wird davon ausgegangen, dass das primäre Rechenzentrum vom Totalausfall wiederhergestellt wurde und dass die MGC-Datenbank und die mgccomp-Datenbank mithilfe des Topologie-Generators neu erstellt und neu installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ddf39-108">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>

<span data-ttu-id="ddf39-109">Bei dem Verfahren wird auch davon ausgegangen, dass während des Failovers keine neuen Spiegelungs-und Sicherungsserver bereitgestellt wurden und dass der einzige bereitgestellte Server der Sicherungsserver und sein Spiegelserver ist, wie unter [fehlerhafte Chat Server in lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="ddf39-109">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in [Failing over Persistent Chat Server in Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).</span></span>

<span data-ttu-id="ddf39-110">Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall vorlag, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat.</span><span class="sxs-lookup"><span data-stu-id="ddf39-110">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>

<div>

## <a name="to-fail-back-persistent-chat-server"></a><span data-ttu-id="ddf39-111">So führen Sie einen Ausfall des beständigen Chat Servers aus</span><span class="sxs-lookup"><span data-stu-id="ddf39-111">To fail back Persistent Chat Server</span></span>

1.  <span data-ttu-id="ddf39-112">Löschen Sie alle Server aus der Active Server-Liste des beständigen `Set-CsPersistentChatActiveServer` Chat Servers mithilfe des Cmdlets aus der lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="ddf39-112">Clear all servers from the Persistent Chat Server Active Server list by using the `Set-CsPersistentChatActiveServer` cmdlet from the Lync Server Management Shell.</span></span> <span data-ttu-id="ddf39-113">Dadurch wird verhindert, dass alle beständigen Chat Server während des Failback eine Verbindung mit der MGC-Datenbank und der mgccomp-Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="ddf39-113">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ddf39-114">Der SQL Server-Agent auf dem Back-End-Server des sekundären beständigen Chat Servers sollte unter einem privilegierten Konto ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ddf39-114">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="ddf39-115">Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="ddf39-115">Specifically, the account must include:</span></span> 
    > <UL>
    > <LI>
    > <P><span data-ttu-id="ddf39-116">Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen</span><span class="sxs-lookup"><span data-stu-id="ddf39-116">Read access to the network share that backups are being placed in.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="ddf39-117">Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen</span><span class="sxs-lookup"><span data-stu-id="ddf39-117">Write access to the specific local directory that the backups are being copied to.</span></span></P></LI></UL>

    
    </div>

2.  <span data-ttu-id="ddf39-118">Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:</span><span class="sxs-lookup"><span data-stu-id="ddf39-118">Disable mirroring on the backup mgc database:</span></span>
    
    1.  <span data-ttu-id="ddf39-119">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Sicherungs MGC-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ddf39-119">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="ddf39-120">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-120">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
    3.  <span data-ttu-id="ddf39-121">Klicken Sie auf **Spiegelung entfernen**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-121">Click **Remove Mirroring**.</span></span>
    
    4.  <span data-ttu-id="ddf39-122">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-122">Click **OK**.</span></span>
    
    5.  <span data-ttu-id="ddf39-123">Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.</span><span class="sxs-lookup"><span data-stu-id="ddf39-123">Perform the same steps with the mgccomp database.</span></span>

3.  <span data-ttu-id="ddf39-124">Sichern Sie die mgc-Datenbank, damit sie in der neuen primären Datenbank wiederhergestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="ddf39-124">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
    1.  <span data-ttu-id="ddf39-125">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der Sicherungs MGC-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ddf39-125">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
    2.  <span data-ttu-id="ddf39-p105">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddf39-p105">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="ddf39-128">Wählen Sie unter **Sicherungstyp** die Option **Vollständig** aus.</span><span class="sxs-lookup"><span data-stu-id="ddf39-128">In **Backup type**, select **Full**.</span></span>
    
    4.  <span data-ttu-id="ddf39-129">Klicken Sie unter **Sicherungskomponente** auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-129">For **Backup component**, click **Database**.</span></span>
    
    5.  <span data-ttu-id="ddf39-130">Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie einen anderen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="ddf39-130">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
    6.  <span data-ttu-id="ddf39-131">\* \<Optional\> \* Geben Sie im Feld **Beschreibung**eine Beschreibung für den Sicherungssatz ein.</span><span class="sxs-lookup"><span data-stu-id="ddf39-131">*\<Optional\>* In **Description**, enter a description of the backup set.</span></span>
    
    7.  <span data-ttu-id="ddf39-132">Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.</span><span class="sxs-lookup"><span data-stu-id="ddf39-132">Remove the default backup location from the destination list.</span></span>
    
    8.  <span data-ttu-id="ddf39-p106">Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ddf39-p106">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
    9.  <span data-ttu-id="ddf39-135">Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ddf39-135">Click **OK** to close the dialog box and begin the backup process.</span></span>

4.  <span data-ttu-id="ddf39-136">Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="ddf39-136">Restore the primary database by using the backup database created in the previous step.</span></span>
    
    1.  <span data-ttu-id="ddf39-137">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der primären MGC-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="ddf39-137">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
    2.  <span data-ttu-id="ddf39-p107">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen** und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddf39-p107">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
    3.  <span data-ttu-id="ddf39-140">Wählen Sie **Von Medium** aus.</span><span class="sxs-lookup"><span data-stu-id="ddf39-140">Select **From Device**.</span></span>
    
    4.  <span data-ttu-id="ddf39-p108">Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-p108">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
    5.  <span data-ttu-id="ddf39-144">Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.</span><span class="sxs-lookup"><span data-stu-id="ddf39-144">In **Select the backup sets to restore**, select the backup.</span></span>
    
    6.  <span data-ttu-id="ddf39-145">Klicken Sie im Bereich **Seite auswählen** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-145">Click **Options** in the **Select a page** pane.</span></span>
    
    7.  <span data-ttu-id="ddf39-146">Aktivieren Sie unter **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-146">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
    8.  <span data-ttu-id="ddf39-147">Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.</span><span class="sxs-lookup"><span data-stu-id="ddf39-147">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
    9.  <span data-ttu-id="ddf39-148">Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ddf39-148">Click **OK** to begin the restoration process.</span></span>

5.  <span data-ttu-id="ddf39-149">Konfigurieren Sie den SQL Server-Protokollversand für die primäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ddf39-149">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="ddf39-150">Führen Sie die Verfahren unter Konfigurieren des beständigen [Chat Servers für die Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) aus, um den Protokollversand für die primäre MGC-Datenbank festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ddf39-150">Follow the procedures in [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) to establish log shipping for the primary mgc database.</span></span>

6.  <span data-ttu-id="ddf39-151">Setzen Sie die aktiven Server für den beständigen Chat Server.</span><span class="sxs-lookup"><span data-stu-id="ddf39-151">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="ddf39-152">Verwenden Sie in der lync Server-Verwaltungsshell das Cmdlet " **Satz-CsPersistentChatActiveServer** ", um die Liste der aktiven Server einzurichten.</span><span class="sxs-lookup"><span data-stu-id="ddf39-152">From the Lync Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ddf39-153">Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="ddf39-153">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>

<span data-ttu-id="ddf39-154">Das Wiederherstellen des Pools in seinem normalen Zustand führt den folgenden Windows PowerShell-Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ddf39-154">The restore the pool to its normal state run the following Windows PowerShell command:</span></span>

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

<span data-ttu-id="ddf39-155">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) ".</span><span class="sxs-lookup"><span data-stu-id="ddf39-155">See the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) cmdlet for more information.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

