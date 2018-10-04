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
ms.openlocfilehash: eaf0c935f246cfdd00aa0707475442c88dc89b8a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374372"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="7330b-103">Bereitstellen einer immer auf Verfügbarkeitsgruppe auf einem Back-End-Server in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="7330b-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="7330b-104">Bereitstellen Sie Bereitstellung (Installation) ein immer auf Availability Group (AG) in Ihrer Skype zu Business Server.</span><span class="sxs-lookup"><span data-stu-id="7330b-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="7330b-105">Wie Sie eine AG bereitstellen, hängt davon ab, ob Sie bereitstellen werden sie in einen neuen Pool, einem vorhandenen Pool, das Spiegelung verwendet oder einen vorhandenen Pool aus, der derzeit keine hohen Verfügbarkeit für die Back-End-Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="7330b-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7330b-106">Verwendung einer AG mit einer Persistent Chat Server-Rolle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7330b-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="7330b-107">Bereitstellen einer immer auf Availability Group auf einen neuen Front-End-pool</span><span class="sxs-lookup"><span data-stu-id="7330b-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="7330b-108">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das der datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="7330b-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="7330b-109">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das nicht-datenbankspiegelung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="7330b-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="7330b-110">Bereitstellen einer immer auf Availability Group auf einen neuen Front-End-pool</span><span class="sxs-lookup"><span data-stu-id="7330b-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="7330b-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="7330b-111"></span></span>

1. <span data-ttu-id="7330b-112">Aktivieren Sie das Feature Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird.</span><span class="sxs-lookup"><span data-stu-id="7330b-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="7330b-113">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7330b-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="7330b-114">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="7330b-p102">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="7330b-117">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="7330b-118">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="7330b-119">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7330b-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="7330b-120">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="7330b-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="7330b-121">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="7330b-122">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-123">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="7330b-124">Überprüfen Sie im Feld**Zusammenfassung** , die der Assistent meldet Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-124">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="7330b-125">Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7330b-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="7330b-p104">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7330b-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="7330b-129">Erstellen Sie die Windows Server-Failovercluster (WSFC).</span><span class="sxs-lookup"><span data-stu-id="7330b-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="7330b-130">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="7330b-131">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-p105">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-134">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-135">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="7330b-p106">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7330b-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="7330b-138">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="7330b-139">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="7330b-140">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="7330b-141">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-142">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="7330b-143">Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="7330b-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="7330b-p107">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="7330b-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="7330b-p108">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7330b-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="7330b-148">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="7330b-148">Create the availability group.</span></span>
    
   - <span data-ttu-id="7330b-149">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="7330b-149">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="7330b-150">Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** .</span><span class="sxs-lookup"><span data-stu-id="7330b-150">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="7330b-151">Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="7330b-151">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="7330b-152">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-152">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-153">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-153">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-154">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="7330b-154">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="7330b-155">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-155">Then click **Next**.</span></span>
    
     <span data-ttu-id="7330b-156">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7330b-156">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="7330b-157">Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.</span><span class="sxs-lookup"><span data-stu-id="7330b-157">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="7330b-158">Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="7330b-158">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="7330b-p112">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="7330b-161">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="7330b-161">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="7330b-p113">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="7330b-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="7330b-164">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-164">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="7330b-p114">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="7330b-p115">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="7330b-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="7330b-169">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-169">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-170">Prüfen Sie auf der Seite**Zusammenfassung** alle Einstellungen, und klicken Sie auf Fertig stellen.</span><span class="sxs-lookup"><span data-stu-id="7330b-170">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="7330b-171">Topologie-Generator zum Erstellen des Front-End-Pools verwenden, wie im erläutert [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="7330b-171">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="7330b-172">Wenn Sie dies tun, geben Sie die AG als SQL-Speicher für den Pool.</span><span class="sxs-lookup"><span data-stu-id="7330b-172">When you do, specify the AG as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="7330b-173">Führen Sie nach dem Pool und die AG bereitgestellt werden, einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.</span><span class="sxs-lookup"><span data-stu-id="7330b-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="7330b-174">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="7330b-175">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="7330b-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="7330b-176">Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7330b-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="7330b-177">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.</span><span class="sxs-lookup"><span data-stu-id="7330b-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="7330b-p118">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="7330b-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="7330b-182">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG.</span><span class="sxs-lookup"><span data-stu-id="7330b-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="7330b-183">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="7330b-184">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7330b-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="7330b-185">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="7330b-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="7330b-186">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das der datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="7330b-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="7330b-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="7330b-187"></span></span>

> [!NOTE]
> <span data-ttu-id="7330b-188">Wenn der Pool, für den Sie zu einer AG Upgrade des zentralen Verwaltungsspeichers für Ihre Organisation gehostet wird, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="7330b-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="7330b-189">Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“.</span><span class="sxs-lookup"><span data-stu-id="7330b-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="7330b-190">Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7330b-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="7330b-191">Alle Daten aus dem Spiegel zum Prinzipal Knoten, Öffnen von Skype für Business Server-Verwaltungsshell und geben das folgende Cmdlet ein Failover.</span><span class="sxs-lookup"><span data-stu-id="7330b-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="7330b-p121">Wiederholen Sie dieses cmdlet für jeden Datenbanktypen im Pool. Mit dem folgenden cmdlet können Sie alle Datenbanktypen finden, die im Pool gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="7330b-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="7330b-194">Anschließend können Sie mithilfe des Topologie-Generators die Datenbankspiegelung aus dem Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="7330b-194">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="7330b-195">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7330b-195">Open Topology Builder.</span></span> <span data-ttu-id="7330b-196">Erweitern Sie in Ihrer Topologie den Eintrag **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7330b-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="7330b-197">Deaktivieren Sie für jeden SQL-Speichertyp des Pools das Kontrollkästchen **SQL-Speicherspiegelung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="7330b-p123">Veröffentlichen der geänderten Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="7330b-201">Teilen Sie mit SQL Server Management Studio den Spiegel auf.</span><span class="sxs-lookup"><span data-stu-id="7330b-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="7330b-p124">Öffnen SQL Server Management Studio, navigieren Sie zu Ihren Datenbanken, klicken Sie mit der rechten Maustaste auf **Aufgaben** und klicken Sie auf **Spiegel**. Klicken Sie dann auf **Spiegel entfernen** und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="7330b-204">Wiederholen Sie diesen Schritt für alle Datenbanken im Pool die an ein AG konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="7330b-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="7330b-205">Richten Sie die Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird.</span><span class="sxs-lookup"><span data-stu-id="7330b-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="7330b-206">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7330b-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="7330b-207">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="7330b-p126">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="7330b-210">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="7330b-211">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="7330b-212">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7330b-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="7330b-213">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="7330b-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="7330b-214">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="7330b-215">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-216">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="7330b-217">Überprüfen Sie im Feld**Zusammenfassung** , die der Assistent meldet Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-217">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="7330b-218">Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7330b-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="7330b-p128">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7330b-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="7330b-222">Erstellen Sie Windows Server-Failovercluster.</span><span class="sxs-lookup"><span data-stu-id="7330b-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="7330b-223">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="7330b-224">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-p129">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-227">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-228">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="7330b-p130">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7330b-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="7330b-231">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="7330b-232">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="7330b-233">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="7330b-234">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-235">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="7330b-236">Aktivieren Sie auf jedem Server im Cluster das AG-Feature in SQL Server-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="7330b-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="7330b-p131">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="7330b-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="7330b-p132">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7330b-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="7330b-241">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="7330b-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="7330b-242">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="7330b-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="7330b-243">Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** .</span><span class="sxs-lookup"><span data-stu-id="7330b-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="7330b-244">Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="7330b-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="7330b-245">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="7330b-246">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="7330b-247">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="7330b-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="7330b-248">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="7330b-249">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7330b-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="7330b-250">Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.</span><span class="sxs-lookup"><span data-stu-id="7330b-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="7330b-251">Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="7330b-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="7330b-p136">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="7330b-254">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="7330b-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="7330b-p137">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="7330b-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="7330b-257">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="7330b-p138">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="7330b-p139">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="7330b-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="7330b-262">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="7330b-263">Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="7330b-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="7330b-264">Erstellen eines neuen Speichers AG Listener angeben und den Prinzipal der alten Spiegelung als dem primären Knoten, der die AG angeben.</span><span class="sxs-lookup"><span data-stu-id="7330b-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="7330b-265">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7330b-265">Open Topology Builder.</span></span> <span data-ttu-id="7330b-266">Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="7330b-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="7330b-267">Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.</span><span class="sxs-lookup"><span data-stu-id="7330b-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="7330b-268">Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7330b-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="7330b-269">Klicken Sie im **SQL Server-FQDN** Geben Sie den FQDN für den primären Knoten des dem AG, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="7330b-270">Dies sollte der Prinzipal des alten Spiegels dieses Speichers sein.</span><span class="sxs-lookup"><span data-stu-id="7330b-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="7330b-271">Ordnen Sie den Front-End-Pool mit die neue AG.</span><span class="sxs-lookup"><span data-stu-id="7330b-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="7330b-272">Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, die die AG zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7330b-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="7330b-273">Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** die AG aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="7330b-274">Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AG verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7330b-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="7330b-275">Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AG festgelegt sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="7330b-p143">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="7330b-279">Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.</span><span class="sxs-lookup"><span data-stu-id="7330b-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="7330b-280">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="7330b-281">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="7330b-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="7330b-282">Mit der rechten Maustaste in des SQL-Speichers, der die neue AG, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7330b-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="7330b-283">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.</span><span class="sxs-lookup"><span data-stu-id="7330b-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="7330b-p145">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="7330b-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="7330b-288">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG.</span><span class="sxs-lookup"><span data-stu-id="7330b-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="7330b-289">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="7330b-290">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7330b-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="7330b-291">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="7330b-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="7330b-292">Bereitstellen einer immer auf Availability Group in einem vorhandenen Pool, das nicht-datenbankspiegelung verwendet wird</span><span class="sxs-lookup"><span data-stu-id="7330b-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="7330b-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="7330b-293"></span></span>

> [!NOTE]
> <span data-ttu-id="7330b-294">Wenn der Pool, für den Sie zu einer AG Upgrade des zentralen Verwaltungsspeichers für Ihre Organisation gehostet wird, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="7330b-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="7330b-295">Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“.</span><span class="sxs-lookup"><span data-stu-id="7330b-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="7330b-296">Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie den Pool auf die AG aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7330b-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="7330b-297">Richten Sie die Failover-Clusterunterstützung auf allen Datenbankservern, die Teil der AG sein wird.</span><span class="sxs-lookup"><span data-stu-id="7330b-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="7330b-298">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7330b-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="7330b-299">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="7330b-p149">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="7330b-302">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="7330b-303">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="7330b-304">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="7330b-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="7330b-305">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="7330b-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="7330b-306">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="7330b-307">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-308">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="7330b-309">Überprüfen Sie im Feld**Zusammenfassung** , die der Assistent meldet Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-309">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="7330b-310">Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7330b-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="7330b-p151">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7330b-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="7330b-314">Erstellen Sie die Windows Server-Failovercluster (WSFC).</span><span class="sxs-lookup"><span data-stu-id="7330b-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="7330b-315">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="7330b-316">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-p152">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-319">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-320">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="7330b-p153">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7330b-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="7330b-323">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="7330b-324">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="7330b-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="7330b-325">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7330b-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="7330b-326">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-327">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="7330b-328">Aktivieren Sie auf jedem Server im Cluster AG in SQL Server-Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="7330b-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="7330b-p154">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="7330b-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="7330b-p155">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="7330b-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="7330b-333">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="7330b-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="7330b-334">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="7330b-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="7330b-335">Erweitern Sie im Objekt-Explorer den Ordner **Immer auf hohe Verfügbarkeit** .</span><span class="sxs-lookup"><span data-stu-id="7330b-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="7330b-336">Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="7330b-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="7330b-337">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-338">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-339">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AG einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="7330b-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="7330b-340">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="7330b-341">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in AG, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7330b-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="7330b-342">Sie können alle anderen Skype für Business Server-Datenbanken in der AG einschließen.</span><span class="sxs-lookup"><span data-stu-id="7330b-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="7330b-343">Klicken Sie auf der Registerkarte **Replikate** , auf der Seite **Replikate angeben** . Anschließend klicken Sie auf die Schaltfläche **Hinzufügen Replikate** und Verbinden mit anderen SQL-Instanzen, die Sie als Knoten des dem WSFC verbunden.</span><span class="sxs-lookup"><span data-stu-id="7330b-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="7330b-p159">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="7330b-346">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="7330b-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="7330b-p160">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="7330b-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="7330b-349">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="7330b-p161">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
     <span data-ttu-id="7330b-p162">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="7330b-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="7330b-354">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="7330b-355">Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="7330b-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="7330b-356">Erstellen eines neuen Speichers AG Listener angeben.</span><span class="sxs-lookup"><span data-stu-id="7330b-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="7330b-357">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7330b-357">Open Topology Builder.</span></span> <span data-ttu-id="7330b-358">Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="7330b-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="7330b-359">Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.</span><span class="sxs-lookup"><span data-stu-id="7330b-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="7330b-360">Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="7330b-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="7330b-361">Klicken Sie im **SQL Server-FQDN** Geben Sie den FQDN für den primären Knoten des dem AG, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="7330b-362">Ordnen Sie den Front-End-Pool mit der neuen immer auf Availability Group.</span><span class="sxs-lookup"><span data-stu-id="7330b-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="7330b-363">Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, die die AG zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7330b-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="7330b-364">Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** die AG aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="7330b-365">Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AG verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="7330b-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="7330b-366">Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AG festgelegt sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="7330b-p165">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7330b-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="7330b-370">Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Benutzernamen aller Replikate in die AG sind.</span><span class="sxs-lookup"><span data-stu-id="7330b-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="7330b-371">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7330b-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="7330b-372">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="7330b-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="7330b-373">Mit der rechten Maustaste in des SQL-Speichers, der die neue AG, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="7330b-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="7330b-374">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des dem die AG-Listener.</span><span class="sxs-lookup"><span data-stu-id="7330b-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="7330b-p167">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="7330b-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="7330b-379">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AG.</span><span class="sxs-lookup"><span data-stu-id="7330b-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="7330b-380">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="7330b-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="7330b-381">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7330b-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="7330b-382">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="7330b-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>