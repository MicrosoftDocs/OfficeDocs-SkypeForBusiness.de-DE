---
title: Verwalten der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Persistent Chat Server hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015.'
ms.openlocfilehash: 3c3da985f8d68f257257909fbc06e93868233468
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21008223"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="516b3-103">Verwalten der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="516b3-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="516b3-104">**Zusammenfassung:** Informationen Sie zum Verwalten von Persistent Chat Server hohe Verfügbarkeit und notfallwiederherstellung in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="516b3-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="516b3-105">In diesem Thema wird beschrieben, wie Failover und wieder Persistent Chatserver fehl.</span><span class="sxs-lookup"><span data-stu-id="516b3-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="516b3-106">Sollten Sie bevor dieses Thema lesen [für hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015 planen](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) und [Konfigurieren hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Lesen Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="516b3-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="516b3-107">Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="516b3-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="516b3-108">Die gleiche Funktionalität ist in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="516b3-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="516b3-109">Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="516b3-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="516b3-110">Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden.</span><span class="sxs-lookup"><span data-stu-id="516b3-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="516b3-111">Ausführen eines Failovers Persistent Chat-Server</span><span class="sxs-lookup"><span data-stu-id="516b3-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="516b3-112">Failover für Persistent Chat Server soll in erster Linie als manueller Prozess konzipiert.</span><span class="sxs-lookup"><span data-stu-id="516b3-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="516b3-113">Das Failover-Verfahren basiert auf der Annahme, der im sekundären Rechenzentrum installiert ist und ausgeführt wird, aber die Persistent Chat Server-Dienste, wo sich die primäre Datenbank für beständigen Chat befindet, sind vollständig nicht verfügbar ist, einschließlich der folgenden:</span><span class="sxs-lookup"><span data-stu-id="516b3-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="516b3-114">Persistent Chat Server-Primärdatenbank und Persistent Chat Server-Spiegeldatenbank sind ausgefallen.</span><span class="sxs-lookup"><span data-stu-id="516b3-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="516b3-115">Skype für Business Server-Front-End-Server ist ausgefallen.</span><span class="sxs-lookup"><span data-stu-id="516b3-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="516b3-116">Das Verfahren basiert auf zwei grundlegenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="516b3-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="516b3-117">Wiederherstellen der Persistent Chat-Primärdatenbank (Mgc).</span><span class="sxs-lookup"><span data-stu-id="516b3-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="516b3-118">Einrichten der Spiegelung für die neue Primärdatenbank</span><span class="sxs-lookup"><span data-stu-id="516b3-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="516b3-119">Die beständigen Chat Kompatibilitätsdatenbank (Mgccomp) ist nicht über fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="516b3-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="516b3-120">Die Inhalte dieser Datenbank sind flüchtig und werden gelöscht, wenn der Konformitätsadapter die Daten verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="516b3-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="516b3-121">Es liegt in Ihrer Verantwortung, als Persistent Chat Administrator richtig verwalten die Ausgabe Adapter um Datenverluste zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="516b3-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="516b3-122">Ausführen eines Failovers für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="516b3-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="516b3-123">Entfernt den Protokollversand aus der Datenbank Persistent Chat Server-Sicherung für den Protokollversand.</span><span class="sxs-lookup"><span data-stu-id="516b3-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
  - <span data-ttu-id="516b3-124">Verbinden Sie über SQL Server Management Studio mit der Datenbankinstanz, wo sich die Mgc-Sicherungsdatenbank Persistent Chat Server befindet.</span><span class="sxs-lookup"><span data-stu-id="516b3-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
  - <span data-ttu-id="516b3-125">Öffnen Sie ein Abfragefenster zur Masterdatenbank.</span><span class="sxs-lookup"><span data-stu-id="516b3-125">Open a query window to the master database.</span></span>
    
  - <span data-ttu-id="516b3-126">Verwenden Sie den folgenden Befehl, um den Protokollversand zu verwerfen:</span><span class="sxs-lookup"><span data-stu-id="516b3-126">Use the following command to drop log shipping:</span></span>
    
  ```
  exec sp_delete_log_shipping_secondary_database mgc
  ```

2. <span data-ttu-id="516b3-127">Kopieren Sie alle nicht kopierten Sicherungsdateien von der Sicherungsfreigabe in den Kopierzielordner des Sicherungsservers.</span><span class="sxs-lookup"><span data-stu-id="516b3-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="516b3-128">Wenden Sie alle nicht angewendeten Sicherungen des Transaktionsprotokolls nacheinander auf die sekundäre Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="516b3-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="516b3-129">Weitere Informationen hierzu finden Sie unter [Vorgehensweise: Anwenden einer Transaktionsprotokollsicherung (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="516b3-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="516b3-p105">Stellen Sie die mgc-Sicherungsdatenbank online bereit. Führen Sie im Abfragefenster, das in Schritt 1b oben geöffnet wird, folgende Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="516b3-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
  - <span data-ttu-id="516b3-132">Beenden Sie alle Verbindungen mit der mgc-Datenbank, falls vorhanden:</span><span class="sxs-lookup"><span data-stu-id="516b3-132">End all connections to the mgc database, if there are any:</span></span>
    
  - <span data-ttu-id="516b3-133">Geben Sie **exec sp_who2** ein, um Verbindungen mit der mgc-Datenbank zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="516b3-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
  - <span data-ttu-id="516b3-134">**kill \<Spid\> ** an diese Verbindungen zu beenden.</span><span class="sxs-lookup"><span data-stu-id="516b3-134">**kill \<spid\>** to end these connections.</span></span>
    
  - <span data-ttu-id="516b3-135">Stellen Sie die Datenbank online bereit:</span><span class="sxs-lookup"><span data-stu-id="516b3-135">Bring the database online:</span></span>
    
  - <span data-ttu-id="516b3-136">**restore database mgc with recovery**.</span><span class="sxs-lookup"><span data-stu-id="516b3-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="516b3-137">In Skype für Business Server-Verwaltungsshell, verwenden Sie den Befehl **"Set-cspersistentchatstate"-Identity "Service: Atl-Cs-001.litwareinc.com" - PoolState FailedOver** Failover auf die Mgc-Sicherungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="516b3-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="516b3-138">Achten Sie darauf, den vollqualifizierten Domänennamen Ihres Pools für beständigen Chat durch „atl-cs-001.litwareinc.com“ zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="516b3-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="516b3-139">Die mgc-Sicherungsdatenbank dient jetzt als Primärdatenbank.</span><span class="sxs-lookup"><span data-stu-id="516b3-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="516b3-140">Verwenden Sie in Skype für Business Server-Verwaltungsshell das Cmdlet **Install-csmirrordatabase anfügen** , eine hohe Verfügbarkeit Spiegelung für die Sicherungsdatenbank herzustellen, die jetzt als die primäre Datenbank fungiert.</span><span class="sxs-lookup"><span data-stu-id="516b3-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="516b3-141">Verwenden Sie die Sicherungsdatenbankinstanz als Primärdatenbank und die Instanz der Sicherungsspiegeldatenbank als Spiegelinstanz.</span><span class="sxs-lookup"><span data-stu-id="516b3-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="516b3-142">Dies ist nicht dieselbe Spiegelung, die anfänglich beim Setup für die Primärdatenbank eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="516b3-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="516b3-143">Legen Sie die aktiven Server für Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="516b3-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="516b3-144">Verwenden Sie das Cmdlet " **Set-CsPersistentChatActiveServer** " aus der Skype für Business Server-Verwaltungsshell Festlegen der Liste der aktiven Server.</span><span class="sxs-lookup"><span data-stu-id="516b3-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="516b3-145">Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="516b3-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="516b3-146">Zu diesem Zeitpunkt wird das Failover aus der primären Datenbank Persistent Chat Server zu der Persistent Chat Server-Sicherungsdatenbank erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="516b3-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="516b3-147">Fail Persistent Chatserver</span><span class="sxs-lookup"><span data-stu-id="516b3-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="516b3-148">In diesem Verfahren wird beschrieben, die Schritte zum Wiederherstellen nach einem Fehler für Persistent Chat Server und Betriebs im primären Rechenzentrum wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="516b3-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="516b3-149">Bei Ausfall der Persistent Chat Server im primären Rechenzentrum sinkt vollständige Ausfall und die primäre und Spiegeldatenbanken nicht mehr verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="516b3-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="516b3-150">Für das primäre Rechenzentrum erfolgt ein Failover auf den Sicherungsserver.</span><span class="sxs-lookup"><span data-stu-id="516b3-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="516b3-151">Wenn das primäre Rechenzentrum wieder verfügbar ist und die Server wiederhergestellt sind, wird anhand der folgenden Verfahrensweise der normale Betrieb wieder aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="516b3-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="516b3-152">Das Verfahren wird davon ausgegangen, dass im primären Rechenzentrum aus insgesamt Ausfall wiederhergestellt wurde und die Mgc-Datenbank und der Mgccomp-Datenbank neu erstellt und mithilfe des Topologie-Generators neu installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="516b3-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="516b3-153">Des Weiteren wird vorausgesetzt, dass während der Dauer des Ausfalls keine neuen Spiegel- und Sicherungsserver bereitgestellt wurden und dass die einzigen bereitgestellten Server der Sicherungsserver und sein Spiegelserver sind (wie in „Ausführen eines Failovers für den Server für beständigen Chat“ festgelegt).</span><span class="sxs-lookup"><span data-stu-id="516b3-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="516b3-154">Mit den folgenden Schritten soll die Konfiguration so wiederhergestellt werden, wie sie vor dem Ausfall vorlag, der zu dem Failover vom primären Server auf den Sicherungsserver geführt hat.</span><span class="sxs-lookup"><span data-stu-id="516b3-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="516b3-155">Deaktivieren Sie alle Server aus der Liste Persistent Chat Server Active Server mit dem Cmdlet **Set-CsPersistentChatActiveServer** aus der Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="516b3-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="516b3-156">Dadurch werden alle Persistent Chat-Server eine Verbindung zu der Mgc-Datenbank und der Mgccomp-Datenbank während des Failbacks beendet.</span><span class="sxs-lookup"><span data-stu-id="516b3-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="516b3-157">Der SQL Server-Agent auf die sekundäre sollte unter eines privilegierten Kontos Persistent Chat Server Back-End Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="516b3-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="516b3-158">Dieses Konto muss insbesondere über die folgenden Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="516b3-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="516b3-159">Lesezugriff auf die Netzwerkfreigabe, in der Sicherungen abgelegt werden sollen</span><span class="sxs-lookup"><span data-stu-id="516b3-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="516b3-160">Schreibzugriff auf das lokale Verzeichnis, in das die Sicherungen kopiert werden sollen</span><span class="sxs-lookup"><span data-stu-id="516b3-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="516b3-161">Deaktivieren Sie die Spiegelung für die mgc-Sicherungsdatenbank:</span><span class="sxs-lookup"><span data-stu-id="516b3-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="516b3-162">Mithilfe von SQL Server Management Studio eine Verbindung mit der Mgc-Sicherungsdatenbank-Instanz.</span><span class="sxs-lookup"><span data-stu-id="516b3-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="516b3-163">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="516b3-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="516b3-164">Klicken Sie auf **Spiegelung entfernen**.</span><span class="sxs-lookup"><span data-stu-id="516b3-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="516b3-165">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="516b3-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="516b3-166">Führen Sie die gleichen Schritte mit der mgccomp-Datenbank durch.</span><span class="sxs-lookup"><span data-stu-id="516b3-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="516b3-167">Sichern Sie die mgc-Datenbank, damit sie in der neuen primären Datenbank wiederhergestellt werden kann:</span><span class="sxs-lookup"><span data-stu-id="516b3-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="516b3-168">Mithilfe von SQL Server Management Studio eine Verbindung mit der Mgc-Sicherungsdatenbank-Instanz.</span><span class="sxs-lookup"><span data-stu-id="516b3-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="516b3-p113">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben** und klicken Sie dann auf **Sichern**. Das Dialogfeld **Datenbank sichern** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="516b3-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="516b3-171">Wählen Sie unter **Sicherungstyp** die Option **Vollständig** aus.</span><span class="sxs-lookup"><span data-stu-id="516b3-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="516b3-172">Klicken Sie unter **Sicherungskomponente** auf **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="516b3-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="516b3-173">Akzeptieren Sie den Standardnamen für den Sicherungssatz, der in **Name** vorgeschlagen wird, oder geben Sie einen anderen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="516b3-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="516b3-174">* \<Optional\> *  Geben Sie im Feld **Beschreibung**eine Beschreibung für den Sicherungssatz ein.</span><span class="sxs-lookup"><span data-stu-id="516b3-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="516b3-175">Entfernen Sie den standardmäßigen Sicherungsspeicherort aus der Zielliste.</span><span class="sxs-lookup"><span data-stu-id="516b3-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="516b3-p114">Fügen Sie der Liste eine Datei mit dem Pfad zu dem Freigabespeicherort ein, den Sie für Protokollversand eingerichtet haben. Dieser Pfad ist für die primäre und die Sicherungsdatenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="516b3-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="516b3-178">Klicken Sie auf **OK**, um das Dialogfeld zu schließen und mit dem Sicherungsvorgang zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="516b3-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="516b3-179">Stellen Sie die primäre Datenbank unter Verwendung der im vorherigen Schritt erstellten Sicherungsdatenbank wieder her.</span><span class="sxs-lookup"><span data-stu-id="516b3-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="516b3-180">Mithilfe von SQL Server Management Studio, eine Verbindung mit der primären Mgc-Instanz.</span><span class="sxs-lookup"><span data-stu-id="516b3-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="516b3-p115">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank, zeigen Sie auf **Aufgaben**, zeigen Sie auf **Wiederherstellen** und klicken Sie dann auf **Datenbank**. Das Dialogfeld **Datenbank wiederherstellen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="516b3-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="516b3-183">Wählen Sie **Von Medium** aus.</span><span class="sxs-lookup"><span data-stu-id="516b3-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="516b3-p116">Klicken Sie auf die Schaltfläche zum Durchsuchen. Das Dialogfeld **Sicherung angeben** wird geöffnet. Wählen Sie in **Sicherungsmedium** die Option **Datei** aus. Klicken Sie auf **Hinzufügen**, wählen Sie die Sicherungsdatei aus, die Sie in Schritt 3 erstellt haben, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="516b3-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="516b3-187">Wählen Sie in **Wählen Sie die wiederherzustellenden Sicherungssätze aus** die Sicherung aus.</span><span class="sxs-lookup"><span data-stu-id="516b3-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="516b3-188">Klicken Sie im Bereich **Seite auswählen** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="516b3-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="516b3-189">Aktivieren Sie unter **Wiederherstellungsoptionen** die Option **Vorhandene Datenbank überschreiben**.</span><span class="sxs-lookup"><span data-stu-id="516b3-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="516b3-190">Aktivieren Sie in **Wiederherstellungsstatus** die Option **Datenbank betriebsbereit belassen**.</span><span class="sxs-lookup"><span data-stu-id="516b3-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="516b3-191">Klicken Sie auf **OK**, um mit dem Wiederherstellungsvorgang zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="516b3-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="516b3-192">Konfigurieren von SQL Server-Protokollversand für die primäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="516b3-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="516b3-193">Führen Sie die Verfahren in [Configure hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) Protokollversand für die primären Mgc-Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="516b3-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="516b3-194">Legen Sie die aktiven Server für Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="516b3-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="516b3-195">Verwenden Sie das Cmdlet " **Set-CsPersistentChatActiveServer** " aus der Skype für Business Server-Verwaltungsshell Festlegen der Liste der aktiven Server.</span><span class="sxs-lookup"><span data-stu-id="516b3-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="516b3-196">Alle aktiven Server müssen sich im gleichen Rechenzentrum wie die neue primäre Datenbank oder in einem Rechenzentrum befinden, das über eine Verbindung mit geringer Latenz und hohen Bandbreite zur Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="516b3-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="516b3-197">Um den Pool, führen Sie den folgenden Windows PowerShell-Befehl Normalzustand wiederherzustellen:</span><span class="sxs-lookup"><span data-stu-id="516b3-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="516b3-198">Weitere Informationen finden Sie im Hilfethema für das Cmdlet ["Set-cspersistentchatstate"](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="516b3-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

