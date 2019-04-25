---
title: Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015.'
ms.openlocfilehash: 5c53652cf5084b5a6c021c38f71f1cccc0322efa
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225490"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="43949-103">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="43949-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="43949-104">**Zusammenfassung:** Lesen Sie dieses Thema, um Informationen zum Konfigurieren von hoher Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="43949-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="43949-105">Skype für Business Server unterstützt mehrere Unterhaltungsmodi hohe Verfügbarkeit für die Back-End-Server, die einschließlich der datenbankspiegelung.</span><span class="sxs-lookup"><span data-stu-id="43949-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="43949-106">Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="43949-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="43949-107">AlwaysOn Availability Groups werden für Persistent Chatserver nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43949-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="43949-108">Bevor Sie Ihre Bereitstellung beständigen Chat für hohe Verfügbarkeit und notfallwiederherstellung konfigurieren, achten Sie darauf, dass Sie mit den Konzepten in [Planen für hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="43949-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="43949-109">Die Lösung für die notfallwiederherstellung für Persistent Chat Server in diesen Themen beschriebenen basiert auf einer ausgedehnten Persistent Chat Server Pool.</span><span class="sxs-lookup"><span data-stu-id="43949-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="43949-110">Der Planung Inhalt beschreibt Ressourcenbedarf und die ausgedehnte pooltopologie, die hohe Verfügbarkeit und notfallwiederherstellung für Persistent Chat Server, einschließlich der Verwendung von SQL Server-Spiegelung für hohe Verfügbarkeit und SQL Server-Protokollversand für ermöglicht Disaster Recovery.</span><span class="sxs-lookup"><span data-stu-id="43949-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="43949-111">Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="43949-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="43949-112">Führen Sie mit dem Topologie-Generator die folgenden Schritte aus, um die Funktionen für hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="43949-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="43949-113">Fügen Sie die Spiegeldatenbanken und die Protokolldateien des Protokollversands sekundäre Datenbank, die SQL Server-Speicher.</span><span class="sxs-lookup"><span data-stu-id="43949-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="43949-114">Bearbeiten der Eigenschaften des Persistent Chat Server zu:</span><span class="sxs-lookup"><span data-stu-id="43949-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="43949-115">a.</span><span class="sxs-lookup"><span data-stu-id="43949-115">a.</span></span> <span data-ttu-id="43949-116">Aktivieren Sie die Spiegelung für die primäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="43949-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="43949-117">b.</span><span class="sxs-lookup"><span data-stu-id="43949-117">b.</span></span> <span data-ttu-id="43949-118">Fügen Sie den primären spiegelspeicher für SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43949-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="43949-119">c.</span><span class="sxs-lookup"><span data-stu-id="43949-119">c.</span></span> <span data-ttu-id="43949-120">Aktivieren Sie die SQL Server-Protokollversand-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="43949-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="43949-121">d.</span><span class="sxs-lookup"><span data-stu-id="43949-121">d.</span></span> <span data-ttu-id="43949-122">Fügen Sie den SQL Server-Protokollversand sekundären SQL Server-Speicher.</span><span class="sxs-lookup"><span data-stu-id="43949-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="43949-123">e.</span><span class="sxs-lookup"><span data-stu-id="43949-123">e.</span></span> <span data-ttu-id="43949-124">Fügen Sie der SQL Server-speicherspiegel für die sekundäre Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="43949-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="43949-125">f.</span><span class="sxs-lookup"><span data-stu-id="43949-125">f.</span></span> <span data-ttu-id="43949-126">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="43949-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="43949-127">Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="43949-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="43949-128">Mithilfe von SQL Server Management Studio eine Verbindung mit der sekundären Protokollversand Datenbankinstanz von Persistent Chat Server, und stellen Sie sicher, dass SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="43949-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="43949-129">Klicken Sie dann eine Verbindung mit der primären Datenbank-Instanz beständigen Chat, und führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="43949-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="43949-130">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="43949-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="43949-131">Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="43949-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="43949-132">Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="43949-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="43949-133">Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="43949-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="43949-134">Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="43949-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="43949-p110">Befindet sich der Sicherungsordner auf dem primären Server, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein (Beispiel: c:\Sicherung)** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="43949-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="43949-137">Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie Ihren Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad dieses Ordners angeben.</span><span class="sxs-lookup"><span data-stu-id="43949-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="43949-138">Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.</span><span class="sxs-lookup"><span data-stu-id="43949-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="43949-139">Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an.</span><span class="sxs-lookup"><span data-stu-id="43949-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="43949-140">Um den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, und passen Sie den SQL Server-Agent Zeitplan nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="43949-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="43949-141">Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="43949-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="43949-142">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="43949-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="43949-143">Klicken Sie auf **Verbinden** , und eine Verbindung mit der Instanz von SQL Server, die Sie als sekundären Server konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="43949-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="43949-144">Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="43949-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="43949-145">Aktivieren Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Ja, eine vollständige Sicherung der primären Datenbank generieren und diese Sicherung in der sekundären Datenbank wiederherstellen (und die sekundäre Datenbank erstellen, falls diese nicht vorhanden ist)**.</span><span class="sxs-lookup"><span data-stu-id="43949-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="43949-p112">Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="43949-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="43949-148">Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan.</span><span class="sxs-lookup"><span data-stu-id="43949-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="43949-149">Um den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, und passen Sie den SQL Server-Agent Zeitplan nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="43949-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="43949-150">Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.</span><span class="sxs-lookup"><span data-stu-id="43949-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="43949-151">Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.</span><span class="sxs-lookup"><span data-stu-id="43949-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="43949-152">Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.</span><span class="sxs-lookup"><span data-stu-id="43949-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="43949-153">Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.</span><span class="sxs-lookup"><span data-stu-id="43949-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="43949-154">Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an.</span><span class="sxs-lookup"><span data-stu-id="43949-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="43949-155">Um den Zeitplan für die Installation anzupassen, klicken Sie auf **Zeitplan**, passen Sie den SQL Server-Agent Zeitplan nach Bedarf, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="43949-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="43949-156">Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.</span><span class="sxs-lookup"><span data-stu-id="43949-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="43949-157">Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="43949-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="43949-158">Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank</span><span class="sxs-lookup"><span data-stu-id="43949-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="43949-159">Führen Sie die folgenden Schritte für den Protokollversand, um fortzufahren, wenn die primäre Datenbank für beständigen Chat ein Failover auf die Spiegeldatenbank durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="43949-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="43949-160">Manuell ein Failover der primären Datenbank für beständigen Chat mit dem Spiegelserver.</span><span class="sxs-lookup"><span data-stu-id="43949-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="43949-161">Dies erfolgt mithilfe der Skype für Business Server-Verwaltungsshell und das Cmdlet " **Invoke-CsDatabaseFailover** ".</span><span class="sxs-lookup"><span data-stu-id="43949-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="43949-162">Verwenden das SQL Server Management Studio, verbinden Sie mit der primären Persistent Chat Server-Spiegelinstanz.</span><span class="sxs-lookup"><span data-stu-id="43949-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="43949-163">Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="43949-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="43949-164">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="43949-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="43949-165">Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="43949-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="43949-166">Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="43949-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="43949-167">Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="43949-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="43949-168">Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="43949-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="43949-p116">Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="43949-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="43949-171">Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie Ihren Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad dieses Ordners angeben.</span><span class="sxs-lookup"><span data-stu-id="43949-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="43949-172">Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.</span><span class="sxs-lookup"><span data-stu-id="43949-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="43949-173">Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an.</span><span class="sxs-lookup"><span data-stu-id="43949-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="43949-174">Um den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, und passen Sie den SQL Server-Agent-Zeitplan, nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="43949-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="43949-175">Verwenden Sie die gleichen Einstellungen, die Sie auch für die primäre Datenbank verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="43949-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="43949-176">Wählen Sie unter **Komprimierung** den Eintrag **Standardservereinstellung verwenden** aus und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="43949-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="43949-177">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="43949-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="43949-178">Klicken Sie auf **Verbinden** und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="43949-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="43949-179">Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="43949-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="43949-180">Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Nein, die sekundäre Datenbank ist initialisiert** aus.</span><span class="sxs-lookup"><span data-stu-id="43949-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="43949-p118">Geben Sie auf der Registerkarte **Dateien kopieren** unter **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen, und klicken Sie auf **OK**. Dieser Ordner befindet sich in der Regel auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="43949-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="43949-183">Öffnen Sie die Dropdownliste **Skript für Konfiguration erstellen** und wählen Sie **Skript für Konfiguration in Fenster 'Neue Abfrage' schreiben** aus.</span><span class="sxs-lookup"><span data-stu-id="43949-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="43949-184">Klicken Sie im neuen Abfragefenster unter **Datenbankeigenschaften** auf **OK**, um mit der Konfiguration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="43949-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="43949-185">Wählen Sie aus, und führen Sie der erste Hälfte der Abfrage (siehe Schritt 18) oben in die Zeile:-- \* \* \* \* \* \* End: Skript zum be run at Primary: \* \* \* \* \* \*.</span><span class="sxs-lookup"><span data-stu-id="43949-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="43949-186">Dieses Skript muss manuell ausgeführt ist erforderlich, da SQL Server Management Studio mehrere primäre Datenbanken in einer SQL Server-Protokollversand Konfiguration nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="43949-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="43949-187">Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert. </span><span class="sxs-lookup"><span data-stu-id="43949-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="43949-188">Manuell ein Failback der primären Datenbank für beständigen Chat auf die primäre.</span><span class="sxs-lookup"><span data-stu-id="43949-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="43949-189">Dies erfolgt mithilfe der Skype für Business Server-Verwaltungsshell, und das Cmdlet " **Invoke-CsDatabaseFailover** ".</span><span class="sxs-lookup"><span data-stu-id="43949-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

