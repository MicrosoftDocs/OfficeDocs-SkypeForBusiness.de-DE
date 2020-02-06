---
title: Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server konfigurieren.'
ms.openlocfilehash: a1589dbb22b3737cab1957637b98477502445958
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798262"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="b2d79-103">Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung für Server für beständigen Chat in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b2d79-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b2d79-104">**Zusammenfassung:** Lesen Sie dieses Thema, um zu erfahren, wie Sie in Skype for Business Server 2015 die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b2d79-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b2d79-105">Skype for Business Server unterstützt mehrere Modi mit höherer Verfügbarkeit für Ihre Back-End-Server, einschließlich der Datenbankspiegelung.</span><span class="sxs-lookup"><span data-stu-id="b2d79-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="b2d79-106">Weitere Informationen finden Sie unter [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="b2d79-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2d79-107">AlwaysOn-Verfügbarkeitsgruppen werden von beständigen Chat Servern nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b2d79-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="b2d79-108">Stellen Sie sicher, dass Sie mit den Konzepten in [Plan für Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)vertraut sind, bevor Sie die Bereitstellung des beständigen Chats für eine höhere Verfügbarkeit und Disaster Recovery konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b2d79-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="b2d79-109">Die in diesen Themen beschriebene Disaster Recovery-Lösung für beständigen Chat Server basiert auf einem gedehnten beständigen Chat Serverpool.</span><span class="sxs-lookup"><span data-stu-id="b2d79-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="b2d79-110">Der Planning-Inhalt beschreibt die Ressourcenanforderungen und die gedehnte Pooltopologie, die eine höhere Verfügbarkeit und Disaster Recovery für beständigen Chat Server ermöglicht, einschließlich der Verwendung der SQL Server-Spiegelung für die höchst Verfügbarkeit und des SQL Server-Protokollversands für Disaster Recovery.</span><span class="sxs-lookup"><span data-stu-id="b2d79-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="b2d79-111">Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="b2d79-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="b2d79-112">Führen Sie mit dem Topologie-Generator die folgenden Schritte aus, um die Funktionen für hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="b2d79-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="b2d79-113">Hinzufügen der Spiegeldatenbanken und der sekundären Datenbank des Protokollversands SQL Server Stores.</span><span class="sxs-lookup"><span data-stu-id="b2d79-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="b2d79-114">Bearbeiten Sie die Diensteigenschaften des beständigen Chat-Servers wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b2d79-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="b2d79-115">a.</span><span class="sxs-lookup"><span data-stu-id="b2d79-115">a.</span></span> <span data-ttu-id="b2d79-116">Aktivieren Sie die Spiegelung für die primäre Datenbank.</span><span class="sxs-lookup"><span data-stu-id="b2d79-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="b2d79-117">b.</span><span class="sxs-lookup"><span data-stu-id="b2d79-117">b.</span></span> <span data-ttu-id="b2d79-118">Fügen Sie den primären Spiegelungs-SQL Server-Speicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2d79-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="b2d79-119">c.</span><span class="sxs-lookup"><span data-stu-id="b2d79-119">c.</span></span> <span data-ttu-id="b2d79-120">Aktivieren Sie die SQL Server-Protokollversanddatenbank.</span><span class="sxs-lookup"><span data-stu-id="b2d79-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="b2d79-121">d.</span><span class="sxs-lookup"><span data-stu-id="b2d79-121">d.</span></span> <span data-ttu-id="b2d79-122">Fügen Sie den SQL Server-Protokollversand-sekundären SQL Server-Speicher hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2d79-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="b2d79-123">e.</span><span class="sxs-lookup"><span data-stu-id="b2d79-123">e.</span></span> <span data-ttu-id="b2d79-124">Fügen Sie die SQL Server Store-Spiegelung für die sekundäre Datenbank hinzu.</span><span class="sxs-lookup"><span data-stu-id="b2d79-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="b2d79-125">f.</span><span class="sxs-lookup"><span data-stu-id="b2d79-125">f.</span></span> <span data-ttu-id="b2d79-126">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="b2d79-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="b2d79-127">Einrichten des SQL Server-Protokollversands für die primäre Datenbank des Servers für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="b2d79-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="b2d79-128">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der sekundären Protokollversand-Datenbankinstanz des beständigen Chat Servers her, und stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b2d79-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="b2d79-129">Stellen Sie dann eine Verbindung mit der primären Datenbankinstanz des persistenten Chats her, und führen Sie die folgenden Schritte aus</span><span class="sxs-lookup"><span data-stu-id="b2d79-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="b2d79-130">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="b2d79-131">Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="b2d79-132">Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="b2d79-133">Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="b2d79-134">Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zur Freigabe ein, die Sie für den Ordner mit den Transaktionsprotokollsicherungen erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b2d79-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="b2d79-p110">Befindet sich der Sicherungsordner auf dem primären Server, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein (Beispiel: c:\Sicherung)** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="b2d79-p110">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b2d79-137">Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.</span><span class="sxs-lookup"><span data-stu-id="b2d79-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="b2d79-138">Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="b2d79-139">Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an.</span><span class="sxs-lookup"><span data-stu-id="b2d79-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b2d79-140">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="b2d79-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="b2d79-141">Wählen Sie unter **Komprimierung** die Option **Standardservereinstellung verwenden** aus und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="b2d79-142">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="b2d79-143">Klicken Sie auf **verbinden** , und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="b2d79-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="b2d79-144">Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b2d79-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="b2d79-145">Aktivieren Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Ja, eine vollständige Sicherung der primären Datenbank generieren und diese Sicherung in der sekundären Datenbank wiederherstellen (und die sekundäre Datenbank erstellen, falls diese nicht vorhanden ist)**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="b2d79-p112">Geben Sie auf der Registerkarte **Dateien kopieren** im Feld **Zielordner für kopierte Dateien** den Pfad zum Ordner ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen. Dieser Ordner befindet sich oft auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="b2d79-p112">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="b2d79-148">Beachten Sie den im Feld **Zeitplan** unter **Kopierauftrag** aufgeführten Kopierzeitplan.</span><span class="sxs-lookup"><span data-stu-id="b2d79-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="b2d79-149">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="b2d79-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="b2d79-150">Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b2d79-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="b2d79-151">Wählen Sie auf der Registerkarte **Wiederherstellen** unter **Datenbankstatus beim Wiederherstellen von Sicherungen** die Option **Kein Wiederherstellungsmodus** aus.</span><span class="sxs-lookup"><span data-stu-id="b2d79-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="b2d79-152">Wählen Sie unter **Wiederherstellen von Sicherungen verzögern um mindestens:** die Option **0 Minuten** aus.</span><span class="sxs-lookup"><span data-stu-id="b2d79-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="b2d79-153">Wählen Sie unter **Warnen, wenn keine Wiederherstellung erfolgt in** einen Warnschwellenwert aus.</span><span class="sxs-lookup"><span data-stu-id="b2d79-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="b2d79-154">Sehen Sie sich den im Feld **Zeitplan** unter **Wiederherstellungsauftrag** aufgeführten Wiederherstellungszeitplan an.</span><span class="sxs-lookup"><span data-stu-id="b2d79-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="b2d79-155">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Zeitplan**, passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="b2d79-156">Dieser Zeitplan sollte in etwa dem Sicherungszeitplan entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b2d79-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="b2d79-157">Klicken Sie im Dialogfeld **Datenbankeigenschaften** auf **OK**, um den Konfigurationsprozess zu starten.</span><span class="sxs-lookup"><span data-stu-id="b2d79-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="b2d79-158">Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank</span><span class="sxs-lookup"><span data-stu-id="b2d79-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="b2d79-159">Führen Sie die folgenden Schritte aus, damit der Protokollversand fortgesetzt wird, wenn die primäre Datenbank für beständige Chats auf die Spiegeldatenbank übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="b2d79-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="b2d79-160">Manuelles Failover der primären persistent-Chat-Datenbank auf die Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="b2d79-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="b2d79-161">Dies erfolgt über die Skype for Business Server-Verwaltungsshell und das Cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="b2d79-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="b2d79-162">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der primären persistent Chat Server-Spiegelungs Instanz her.</span><span class="sxs-lookup"><span data-stu-id="b2d79-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="b2d79-163">Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b2d79-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="b2d79-164">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="b2d79-165">Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="b2d79-166">Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="b2d79-167">Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="b2d79-168">Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b2d79-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="b2d79-p116">Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="b2d79-p116">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b2d79-171">Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.</span><span class="sxs-lookup"><span data-stu-id="b2d79-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="b2d79-172">Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="b2d79-173">Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an.</span><span class="sxs-lookup"><span data-stu-id="b2d79-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b2d79-174">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="b2d79-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b2d79-175">Verwenden Sie die gleichen Einstellungen, die Sie auch für die primäre Datenbank verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="b2d79-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="b2d79-176">Wählen Sie unter **Komprimierung** den Eintrag **Standardservereinstellung verwenden** aus und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="b2d79-177">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b2d79-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="b2d79-178">Klicken Sie auf **Verbinden** und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="b2d79-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="b2d79-179">Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b2d79-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="b2d79-180">Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Nein, die sekundäre Datenbank ist initialisiert** aus.</span><span class="sxs-lookup"><span data-stu-id="b2d79-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="b2d79-p118">Geben Sie auf der Registerkarte **Dateien kopieren** unter **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen, und klicken Sie auf **OK**. Dieser Ordner befindet sich in der Regel auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="b2d79-p118">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="b2d79-183">Öffnen Sie die Dropdownliste **Skript für Konfiguration erstellen** und wählen Sie **Skript für Konfiguration in Fenster 'Neue Abfrage' schreiben** aus.</span><span class="sxs-lookup"><span data-stu-id="b2d79-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="b2d79-184">Klicken Sie im neuen Abfragefenster unter **Datenbankeigenschaften** auf **OK**, um mit der Konfiguration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b2d79-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="b2d79-185">Wählen Sie die erste Hälfte der Abfrage aus, und führen Sie Sie aus (siehe Schritt 18) bis zur \* \* \* \* \* \* Zeile:--Ende: Skript, das \* \* \* \* \* \*bei primär ausgeführt werden soll:.</span><span class="sxs-lookup"><span data-stu-id="b2d79-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b2d79-186">Das manuelle Ausführen dieses Skripts ist erforderlich, da SQL Server Management Studio mehrere primäre Datenbanken in einer SQL Server-Protokollversandkonfiguration nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b2d79-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="b2d79-187">Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert. </span><span class="sxs-lookup"><span data-stu-id="b2d79-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="b2d79-188">Manuelles Zurücksetzen der primären beständigen Chat Datenbank auf das primäre.</span><span class="sxs-lookup"><span data-stu-id="b2d79-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="b2d79-189">Dies erfolgt über die Skype for Business Server-Verwaltungsshell und das Cmdlet **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="b2d79-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

