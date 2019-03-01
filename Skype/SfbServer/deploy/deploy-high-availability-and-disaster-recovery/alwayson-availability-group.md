---
title: Bereitstellen einer immer auf Verfügbarkeitsgruppe auf einem Back-End-Server in Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Bereitstellen Sie Bereitstellung (Installation) immer auf Verfügbarkeit in eine Gruppe Ihrer Skype zu Business Server.
ms.openlocfilehash: b773c10766b33e57eb8a132d98ef0e0cdc180123
ms.sourcegitcommit: a4f2d3440399f0a17fb8f6d364cfd2dc4b0bf8db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "30342219"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="854b2-103">Bereitstellen einer immer auf Verfügbarkeitsgruppe auf einem Back-End-Server in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="854b2-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="854b2-104">Bereitstellen Sie Bereitstellung (Installation) ein immer auf Availability Group (AG) in Ihrer Skype zu Business Server.</span><span class="sxs-lookup"><span data-stu-id="854b2-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="854b2-105">Wie Sie eine AG bereitstellen, hängt davon ab, ob Sie bereitstellen werden sie in einen neuen Pool, einem vorhandenen Pool, das Spiegelung verwendet oder einen vorhandenen Pool aus, der derzeit keine hohen Verfügbarkeit für die Back-End-Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="854b2-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="854b2-106">Verwendung einer AG mit einer Persistent Chat Server-Rolle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="854b2-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="854b2-107">Bereitstellen einer immer auf Availability Group auf einen neuen Front-End-pool</span><span class="sxs-lookup"><span data-stu-id="854b2-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="854b2-108">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das der datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="854b2-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="854b2-109">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das nicht-datenbankspiegelung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="854b2-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="854b2-110">Bereitstellen einer immer auf Availability Group auf einen neuen Front-End-pool</span><span class="sxs-lookup"><span data-stu-id="854b2-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="854b2-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="854b2-111"></span></span>

1. <span data-ttu-id="854b2-112">Aktivieren Sie das Feature Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird.</span><span class="sxs-lookup"><span data-stu-id="854b2-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="854b2-113">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="854b2-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="854b2-114">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="854b2-p102">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="854b2-117">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="854b2-118">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="854b2-119">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="854b2-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="854b2-120">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="854b2-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="854b2-121">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="854b2-122">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-123">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="854b2-p103">Überprüfen Sie im Kästchen **Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="854b2-p103">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="854b2-p104">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="854b2-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="854b2-129">Erstellen Sie die Windows Server-Failovercluster (WSFC).</span><span class="sxs-lookup"><span data-stu-id="854b2-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="854b2-130">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="854b2-131">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-p105">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-134">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-135">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="854b2-p106">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="854b2-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="854b2-138">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="854b2-139">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="854b2-140">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="854b2-141">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-142">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="854b2-143">Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="854b2-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="854b2-p107">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="854b2-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="854b2-p108">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="854b2-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="854b2-148">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="854b2-148">Create the availability group.</span></span>
    
   - <span data-ttu-id="854b2-149">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="854b2-149">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="854b2-150">Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** .</span><span class="sxs-lookup"><span data-stu-id="854b2-150">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="854b2-151">Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="854b2-151">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="854b2-152">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-152">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-153">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-153">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-154">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="854b2-154">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="854b2-155">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-155">Then click **Next**.</span></span>
    
     <span data-ttu-id="854b2-156">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="854b2-156">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="854b2-157">Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.</span><span class="sxs-lookup"><span data-stu-id="854b2-157">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="854b2-158">Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="854b2-158">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="854b2-p112">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="854b2-161">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="854b2-161">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="854b2-p113">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="854b2-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="854b2-164">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-164">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="854b2-p114">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="854b2-p115">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="854b2-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="854b2-169">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-169">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-170">Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="854b2-170">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="854b2-171">Topologie-Generator zum Erstellen des Front-End-Pools verwenden, wie im erläutert [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="854b2-171">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="854b2-172">Wenn Sie dies tun, geben Sie die AG als SQL-Speicher für den Pool.</span><span class="sxs-lookup"><span data-stu-id="854b2-172">When you do, specify the AG as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="854b2-173">Führen Sie nach dem Pool und die AG bereitgestellt werden, einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.</span><span class="sxs-lookup"><span data-stu-id="854b2-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="854b2-174">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="854b2-175">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="854b2-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="854b2-176">Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="854b2-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="854b2-177">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.</span><span class="sxs-lookup"><span data-stu-id="854b2-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="854b2-p118">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="854b2-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="854b2-182">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG.</span><span class="sxs-lookup"><span data-stu-id="854b2-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="854b2-183">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="854b2-184">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="854b2-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="854b2-185">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="854b2-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="854b2-186">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das der datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="854b2-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="854b2-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="854b2-187"></span></span>

> [!NOTE]
> <span data-ttu-id="854b2-188">Wenn der Pool, für den Sie zu einer AG Upgrade des zentralen Verwaltungsspeichers für Ihre Organisation gehostet wird, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="854b2-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="854b2-189">Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“.</span><span class="sxs-lookup"><span data-stu-id="854b2-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="854b2-190">Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="854b2-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="854b2-191">Alle Daten aus dem Spiegel zum Prinzipal Knoten, Öffnen von Skype für Business Server-Verwaltungsshell und geben das folgende Cmdlet ein Failover.</span><span class="sxs-lookup"><span data-stu-id="854b2-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="854b2-p121">Wiederholen Sie dieses cmdlet für jeden Datenbanktypen im Pool. Mit dem folgenden cmdlet können Sie alle Datenbanktypen finden, die im Pool gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="854b2-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="854b2-194">Verwenden Sie Topologie-Generator zum Entfernen der datenbankspiegelung aus dem Pool.</span><span class="sxs-lookup"><span data-stu-id="854b2-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="854b2-195">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="854b2-195">Open Topology Builder.</span></span> <span data-ttu-id="854b2-196">Erweitern Sie in Ihrer Topologie den Eintrag **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="854b2-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="854b2-197">Deaktivieren Sie für jeden SQL-Speichertyp des Pools das Kontrollkästchen **SQL-Speicherspiegelung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="854b2-p123">Veröffentlichen der geänderten Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="854b2-201">Teilen Sie mit SQL Server Management Studio den Spiegel auf.</span><span class="sxs-lookup"><span data-stu-id="854b2-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="854b2-p124">Öffnen SQL Server Management Studio, navigieren Sie zu Ihren Datenbanken, klicken Sie mit der rechten Maustaste auf **Aufgaben** und klicken Sie auf **Spiegel**. Klicken Sie dann auf **Spiegel entfernen** und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="854b2-204">Wiederholen Sie diesen Schritt für alle Datenbanken im Pool die an ein AG konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="854b2-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="854b2-205">Richten Sie die Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird.</span><span class="sxs-lookup"><span data-stu-id="854b2-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="854b2-206">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="854b2-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="854b2-207">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="854b2-p126">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="854b2-210">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="854b2-211">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="854b2-212">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="854b2-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="854b2-213">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="854b2-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="854b2-214">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="854b2-215">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-216">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="854b2-p127">Überprüfen Sie im Kästchen **Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="854b2-p127">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="854b2-p128">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="854b2-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="854b2-222">Erstellen Sie Windows Server-Failovercluster.</span><span class="sxs-lookup"><span data-stu-id="854b2-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="854b2-223">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="854b2-224">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-p129">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-227">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-228">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="854b2-p130">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="854b2-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="854b2-231">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="854b2-232">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="854b2-233">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="854b2-234">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-235">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="854b2-236">Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="854b2-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="854b2-p131">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="854b2-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="854b2-p132">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="854b2-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="854b2-241">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="854b2-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="854b2-242">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="854b2-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="854b2-243">Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** .</span><span class="sxs-lookup"><span data-stu-id="854b2-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="854b2-244">Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="854b2-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="854b2-245">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="854b2-246">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="854b2-247">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="854b2-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="854b2-248">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="854b2-249">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="854b2-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="854b2-250">Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.</span><span class="sxs-lookup"><span data-stu-id="854b2-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="854b2-251">Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="854b2-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="854b2-p136">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="854b2-254">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="854b2-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="854b2-p137">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="854b2-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="854b2-257">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="854b2-p138">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="854b2-p139">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="854b2-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="854b2-262">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="854b2-263">Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="854b2-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="854b2-264">Erstellen eines neuen Speichers AG Listener angeben und den Prinzipal der alten Spiegelung als dem primären Knoten, der die AG angeben.</span><span class="sxs-lookup"><span data-stu-id="854b2-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="854b2-265">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="854b2-265">Open Topology Builder.</span></span> <span data-ttu-id="854b2-266">Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="854b2-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="854b2-267">Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.</span><span class="sxs-lookup"><span data-stu-id="854b2-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="854b2-268">Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="854b2-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="854b2-269">Klicken Sie im **SQL Server-FQDN** Geben Sie den FQDN für den primären Knoten des dem AG, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="854b2-270">Dies sollte der Prinzipal des alten Spiegels dieses Speichers sein.</span><span class="sxs-lookup"><span data-stu-id="854b2-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="854b2-271">Ordnen Sie den Front-End-Pool mit die neue AG.</span><span class="sxs-lookup"><span data-stu-id="854b2-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="854b2-272">Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, die die AG zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="854b2-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="854b2-273">Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** die AG aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="854b2-274">Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AG verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="854b2-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="854b2-275">Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AG festgelegt sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="854b2-276">Veröffentlichen der Topologie.</span><span class="sxs-lookup"><span data-stu-id="854b2-276">Publish the topology.</span></span> <span data-ttu-id="854b2-277">Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="854b2-278">Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="854b2-279">Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.</span><span class="sxs-lookup"><span data-stu-id="854b2-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="854b2-280">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="854b2-281">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="854b2-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="854b2-282">Mit der rechten Maustaste in des SQL-Speichers, der die neue AG, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="854b2-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="854b2-283">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.</span><span class="sxs-lookup"><span data-stu-id="854b2-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="854b2-p145">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="854b2-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="854b2-288">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG.</span><span class="sxs-lookup"><span data-stu-id="854b2-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="854b2-289">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="854b2-290">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="854b2-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="854b2-291">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="854b2-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="854b2-292">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das nicht-datenbankspiegelung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="854b2-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="854b2-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="854b2-293"></span></span>

> [!NOTE]
> <span data-ttu-id="854b2-294">Wenn der Pool, für den Sie zu einer AG Upgrade des zentralen Verwaltungsspeichers für Ihre Organisation gehostet wird, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="854b2-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="854b2-295">Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“.</span><span class="sxs-lookup"><span data-stu-id="854b2-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="854b2-296">Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="854b2-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="854b2-297">Richten Sie die Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird.</span><span class="sxs-lookup"><span data-stu-id="854b2-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="854b2-298">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="854b2-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="854b2-299">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="854b2-p149">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="854b2-302">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="854b2-303">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="854b2-304">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="854b2-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="854b2-305">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="854b2-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="854b2-306">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="854b2-307">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-308">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="854b2-p150">Überprüfen Sie im Kästchen **Zusammenfassung** alle Fehler, die der Assistent meldet. Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="854b2-p150">In the **Summary** box, check any errors that the wizard reports. Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="854b2-p151">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="854b2-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="854b2-314">Erstellen Sie die Windows Server-Failovercluster (WSFC).</span><span class="sxs-lookup"><span data-stu-id="854b2-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="854b2-315">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="854b2-316">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-p152">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-319">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-320">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="854b2-p153">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="854b2-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="854b2-323">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="854b2-324">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="854b2-325">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="854b2-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="854b2-326">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-327">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="854b2-328">Aktivieren Sie auf jedem Server im Cluster AG in SQL Server-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="854b2-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="854b2-p154">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="854b2-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="854b2-p155">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="854b2-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="854b2-333">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="854b2-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="854b2-334">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="854b2-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="854b2-335">Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** .</span><span class="sxs-lookup"><span data-stu-id="854b2-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="854b2-336">Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="854b2-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="854b2-337">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-338">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-339">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AG einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="854b2-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="854b2-340">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="854b2-341">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in AG, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="854b2-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="854b2-342">Sie können alle anderen Skype für Business Server-Datenbanken in der AG einschließen.</span><span class="sxs-lookup"><span data-stu-id="854b2-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="854b2-343">Klicken Sie auf der Registerkarte **Replikate** , auf der Seite **Replikate angeben** . Anschließend klicken Sie auf die Schaltfläche **Hinzufügen Replikate** und Verbinden mit anderen SQL-Instanzen, die Sie als Knoten des dem WSFC verbunden.</span><span class="sxs-lookup"><span data-stu-id="854b2-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="854b2-p159">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="854b2-346">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="854b2-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="854b2-p160">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="854b2-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="854b2-349">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="854b2-p161">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="854b2-p162">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="854b2-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="854b2-354">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="854b2-355">Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="854b2-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="854b2-356">Erstellen eines neuen Speichers AG Listener angeben.</span><span class="sxs-lookup"><span data-stu-id="854b2-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="854b2-357">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="854b2-357">Open Topology Builder.</span></span> <span data-ttu-id="854b2-358">Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="854b2-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="854b2-359">Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.</span><span class="sxs-lookup"><span data-stu-id="854b2-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="854b2-360">Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="854b2-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="854b2-361">Klicken Sie im **SQL Server-FQDN** Geben Sie den FQDN für den primären Knoten des dem AG, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="854b2-362">Ordnen Sie den Front-End-Pool mit der neuen immer auf Availability Group.</span><span class="sxs-lookup"><span data-stu-id="854b2-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="854b2-363">Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, die die AG zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="854b2-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="854b2-364">Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** die AG aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="854b2-365">Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AG verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="854b2-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="854b2-366">Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AG festgelegt sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="854b2-367">Veröffentlichen der Topologie.</span><span class="sxs-lookup"><span data-stu-id="854b2-367">Publish the topology.</span></span> <span data-ttu-id="854b2-368">Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="854b2-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="854b2-369">Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="854b2-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="854b2-370">Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Benutzernamen aller Replikate in die AG sind.</span><span class="sxs-lookup"><span data-stu-id="854b2-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="854b2-371">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="854b2-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="854b2-372">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="854b2-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="854b2-373">Mit der rechten Maustaste in des SQL-Speichers, der die neue AG, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="854b2-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="854b2-374">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.</span><span class="sxs-lookup"><span data-stu-id="854b2-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="854b2-p167">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="854b2-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="854b2-379">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG.</span><span class="sxs-lookup"><span data-stu-id="854b2-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="854b2-380">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="854b2-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="854b2-381">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="854b2-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="854b2-382">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="854b2-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
