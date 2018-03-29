---
title: Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in Ihrer Skype (Installation) für Business Server-Bereitstellung.
ms.openlocfilehash: 858f8cd317ecccde315475bc6489c74d79bf72c6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-an-alwayson-availability-group-on-a-back-end-server-in-skype-for-business-server-2015"></a><span data-ttu-id="34010-103">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="34010-103">Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="34010-104">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in Ihrer Skype (Installation) für Business Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="34010-104">Deploy (install) an AlwaysOn Availability Group in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="34010-105">Wie Sie eine AlwaysOn Availability Group bereitstellen, hängt davon ab, ob Sie bereitstellen werden sie in einen neuen Pool, einem vorhandenen Pool, das Spiegelung verwendet oder einen vorhandenen Pool aus, der derzeit keine hohen Verfügbarkeit für die Back-End-Datenbank verfügt.</span><span class="sxs-lookup"><span data-stu-id="34010-105">How you deploy an AlwaysOn Availability Group depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="34010-106">Verwendung einer Verfügbarkeitsgruppe "AlwaysOn" mit einer Persistent Chat Server-Rolle wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="34010-106">Using an AlwaysOn Availability Group with a Persistent Chat Server role is not supported.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="34010-107">Instanznamen für mehrere Instanzen von AlwaysOn Availability Group müssen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="34010-107">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
- [<span data-ttu-id="34010-108">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem neuen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="34010-108">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="34010-109">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem bereits vorhandenen Pool, der Datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="34010-109">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="34010-110">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem bereits vorhandenen Pool, der keine Datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="34010-110">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-alwayson-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="34010-111">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem neuen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="34010-111">Deploy an AlwaysOn Availability Group on a new Front End pool</span></span>
<span data-ttu-id="34010-112"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="34010-112"></span></span>

1. <span data-ttu-id="34010-113">Einrichten von Windows Server Failover Clustering ein, auf allen Datenbankservern, die Teil der AlwaysOn Availability Group sein werden.</span><span class="sxs-lookup"><span data-stu-id="34010-113">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-114">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="34010-114">On each server, do the following</span></span>
    
   - <span data-ttu-id="34010-115">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34010-115">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="34010-p102">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="34010-p102">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="34010-118">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34010-118">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="34010-119">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-119">Click **Install**.</span></span>
    
2. <span data-ttu-id="34010-120">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="34010-120">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="34010-121">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="34010-121">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="34010-122">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="34010-122">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="34010-123">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-123">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-124">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="34010-124">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="34010-125">Überprüfen Sie im Feld**Zusammenfassung** , die der Assistent meldet Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="34010-125">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="34010-126">Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="34010-126">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="34010-p104">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="34010-p104">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="34010-130">Erstellen Sie den Cluster.</span><span class="sxs-lookup"><span data-stu-id="34010-130">Create the cluster.</span></span>
    
   - <span data-ttu-id="34010-131">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="34010-131">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="34010-132">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-132">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-p105">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p105">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-135">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-135">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-136">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="34010-136">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="34010-p106">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="34010-p106">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="34010-139">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-139">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="34010-140">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="34010-140">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="34010-141">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-141">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="34010-142">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-142">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="34010-143">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-143">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="34010-144">Aktivieren Sie im SQL Server-Konfigurations-Manager jedes Clusters „Always On“.</span><span class="sxs-lookup"><span data-stu-id="34010-144">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="34010-p107">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="34010-p107">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="34010-p108">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="34010-p108">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="34010-149">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="34010-149">Create the availability group.</span></span>
    
   - <span data-ttu-id="34010-150">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="34010-150">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="34010-p109">Erweitern Sie im Objekt-Explorer den Ordner **Hohe Verfügbarkeit AlwaysOn**. Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="34010-p109">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="34010-153">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-153">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-154">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-154">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="34010-155">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="34010-155">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-156">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-156">Then click **Next**.</span></span>
    
    <span data-ttu-id="34010-157">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="34010-157">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="34010-158">Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.</span><span class="sxs-lookup"><span data-stu-id="34010-158">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="34010-159">Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="34010-159">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="34010-p112">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="34010-p112">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="34010-162">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="34010-162">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="34010-p113">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="34010-p113">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="34010-165">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-165">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="34010-p114">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p114">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="34010-p115">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="34010-p115">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="34010-170">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-170">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="34010-171">Prüfen Sie auf der Seite**Zusammenfassung** alle Einstellungen, und klicken Sie auf Fertig stellen.</span><span class="sxs-lookup"><span data-stu-id="34010-171">In the**Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="34010-172">Topologie-Generator zum Erstellen des Front-End-Pools verwenden, wie im erläutert [Erstellen und veröffentlichen Sie die neue Topologie in Skype für Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="34010-172">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="34010-173">Wenn Sie dies tun, geben Sie die AlwaysOn Availability Group als SQL-Speicher für den Pool.</span><span class="sxs-lookup"><span data-stu-id="34010-173">When you do, specify the AlwaysOn Availability Group as the SQL store for the pool.</span></span>
    
8. <span data-ttu-id="34010-174">Nachdem die Pools und der AlwaysOn Availability Group bereitgestellt werden, führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.</span><span class="sxs-lookup"><span data-stu-id="34010-174">After the pool and the AlwaysOn Availability Group are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="34010-175">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-175">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="34010-176">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="34010-176">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="34010-177">Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf ** Bearbeiten Eigenschaften **.</span><span class="sxs-lookup"><span data-stu-id="34010-177">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="34010-178">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des der Listener die AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-178">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="34010-p118">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="34010-p118">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="34010-183">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-183">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-184">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="34010-184">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="34010-185">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="34010-185">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="34010-186">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="34010-186">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="34010-187">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem bereits vorhandenen Pool, der Datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="34010-187">Deploy an AlwaysOn Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="34010-188"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="34010-188"></span></span>

> [!NOTE]
> <span data-ttu-id="34010-189">Wenn für Ihre Organisation eine AlwaysOn Availability Group Hosts zentralen zum Aktualisieren auf Pool gespeichert werden sollen, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="34010-189">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="34010-190">Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“.</span><span class="sxs-lookup"><span data-stu-id="34010-190">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="34010-191">Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie ein des Pools auf der AlwaysOn Availability Group Upgrade.</span><span class="sxs-lookup"><span data-stu-id="34010-191">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="34010-192">Alle Daten aus dem Spiegel zum Prinzipal Knoten, Öffnen von Skype für Business Server-Verwaltungsshell und geben das folgende Cmdlet ein Failover.</span><span class="sxs-lookup"><span data-stu-id="34010-192">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="34010-p121">Wiederholen Sie dieses cmdlet für jeden Datenbanktypen im Pool. Mit dem folgenden cmdlet können Sie alle Datenbanktypen finden, die im Pool gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="34010-p121">Repeat this cmdlet for each database type in the pool. You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="34010-195">Anschließend können Sie mithilfe des Topologie-Generators die Datenbankspiegelung aus dem Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="34010-195">Use Topology Builder to remove database mirroring from the pool</span></span>
    
   - <span data-ttu-id="34010-196">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34010-196">Open Topology Builder.</span></span> <span data-ttu-id="34010-197">Erweitern Sie in Ihrer Topologie den Eintrag **Enterprise Edition-Front-End-Pools**, klicken Sie mit der rechten Maustaste auf den Namen des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="34010-197">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="34010-198">Deaktivieren Sie für jeden SQL-Speichertyp des Pools das Kontrollkästchen **SQL-Speicherspiegelung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-198">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="34010-p123">Veröffentlichen der geänderten Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p123">Publish the changed topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="34010-202">Teilen Sie mit SQL Server Management Studio den Spiegel auf.</span><span class="sxs-lookup"><span data-stu-id="34010-202">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="34010-p124">Öffnen SQL Server Management Studio, navigieren Sie zu Ihren Datenbanken, klicken Sie mit der rechten Maustaste auf **Aufgaben** und klicken Sie auf **Spiegel**. Klicken Sie dann auf **Spiegel entfernen** und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-p124">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**. Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="34010-205">Wiederholen Sie diesen Schritt für alle Datenbanken im Pool die einer AlwaysOn-verfügbarkeitsgruppe konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="34010-205">Repeat this for all databases in the pool which will be converted to an AlwaysOn Availability Group.</span></span>
    
5. <span data-ttu-id="34010-206">Einrichten von Windows Server Failover Clustering ein, auf allen Datenbankservern, die Teil der AlwaysOn Availability Group sein werden.</span><span class="sxs-lookup"><span data-stu-id="34010-206">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-207">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="34010-207">On each server, do the following</span></span>
    
   - <span data-ttu-id="34010-208">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34010-208">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="34010-p126">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="34010-p126">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="34010-211">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34010-211">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="34010-212">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-212">Click **Install**.</span></span>
    
6. <span data-ttu-id="34010-213">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="34010-213">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="34010-214">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="34010-214">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="34010-215">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="34010-215">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="34010-216">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-216">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-217">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="34010-217">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="34010-218">Überprüfen Sie im Feld**Zusammenfassung** , die der Assistent meldet Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="34010-218">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="34010-219">Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="34010-219">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="34010-p128">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="34010-p128">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="34010-223">Erstellen Sie den Cluster.</span><span class="sxs-lookup"><span data-stu-id="34010-223">Create the cluster.</span></span>
    
   - <span data-ttu-id="34010-224">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="34010-224">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="34010-225">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-225">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-p129">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p129">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-228">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-228">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-229">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="34010-229">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="34010-p130">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="34010-p130">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="34010-232">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-232">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="34010-233">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="34010-233">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="34010-234">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-234">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="34010-235">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-235">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="34010-236">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-236">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="34010-237">Aktivieren Sie im SQL Server-Konfigurations-Manager jedes Clusters „Always On“.</span><span class="sxs-lookup"><span data-stu-id="34010-237">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="34010-p131">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="34010-p131">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="34010-p132">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="34010-p132">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="34010-242">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="34010-242">Create the availability group.</span></span>
    
    - <span data-ttu-id="34010-243">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="34010-243">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="34010-p133">Erweitern Sie im Objekt-Explorer den Ordner **Hohe Verfügbarkeit AlwaysOn**. Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="34010-p133">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="34010-246">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-246">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="34010-247">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-247">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="34010-248">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="34010-248">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-249">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-249">Then click **Next**.</span></span>
    
    <span data-ttu-id="34010-250">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="34010-250">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="34010-251">Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.</span><span class="sxs-lookup"><span data-stu-id="34010-251">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="34010-252">Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="34010-252">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="34010-p136">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="34010-p136">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="34010-255">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="34010-255">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
     - <span data-ttu-id="34010-p137">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="34010-p137">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="34010-258">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-258">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="34010-p138">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p138">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="34010-p139">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="34010-p139">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="34010-263">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-263">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="34010-264">Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="34010-264">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="34010-265">Erstellen eines neuen Speichers den Listener AlwaysOn Availability Group, und Angeben des Prinzipals der alten Spiegelung als primäre Knoten die AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-265">Create a new store specifying the AlwaysOn Availability Group listener, and specifying the principal of the old mirror as the primary node of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="34010-266">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34010-266">Open Topology Builder.</span></span> <span data-ttu-id="34010-267">Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="34010-267">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="34010-268">Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.</span><span class="sxs-lookup"><span data-stu-id="34010-268">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="34010-269">Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="34010-269">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="34010-270">Geben Sie den FQDN des primären Knotens die AlwaysOn Availability Group im Feld **SQL Server-FQDN** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-270">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span> <span data-ttu-id="34010-271">Dies sollte der Prinzipal des alten Spiegels dieses Speichers sein.</span><span class="sxs-lookup"><span data-stu-id="34010-271">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="34010-272">Ordnen Sie den Front-End-Pool mit der neuen AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-272">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
    - <span data-ttu-id="34010-273">Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools der AlwaysOn Availability Group zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="34010-273">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="34010-274">Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** der AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-274">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-275">Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AlwaysOn Availability Group verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="34010-275">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="34010-276">Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AlwaysOn Availability Group festgelegt sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-276">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
13. <span data-ttu-id="34010-p143">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p143">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="34010-280">Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.</span><span class="sxs-lookup"><span data-stu-id="34010-280">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="34010-281">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-281">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="34010-282">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="34010-282">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="34010-283">Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="34010-283">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="34010-284">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des der Listener die AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-284">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="34010-p145">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="34010-p145">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="34010-289">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-289">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-290">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="34010-290">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="34010-291">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="34010-291">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="34010-292">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="34010-292">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-alwayson-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="34010-293">Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe in einem bereits vorhandenen Pool, der keine Datenbankspiegelung verwendet</span><span class="sxs-lookup"><span data-stu-id="34010-293">Deploy an AlwaysOn Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="34010-294"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="34010-294"></span></span>

> [!NOTE]
> <span data-ttu-id="34010-295">Wenn für Ihre Organisation eine AlwaysOn Availability Group Hosts zentralen zum Aktualisieren auf Pool gespeichert werden sollen, müssen Sie zuerst die CMS in einen anderen Pool verschieben, vor dem upgrade in diesem Pool.</span><span class="sxs-lookup"><span data-stu-id="34010-295">If the pool you are upgrading to an AlwaysOn Availability Group hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="34010-296">Verschieben Sie den Pool mit dem Cmdlet „Move-CsManagementServer“.</span><span class="sxs-lookup"><span data-stu-id="34010-296">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="34010-297">Wenn Sie einen anderen Pool nicht in Ihrer Organisation verfügen, können Sie vorübergehend Standard Edition-Server bereitstellen und CMS an diesen Server verschieben, bevor Sie ein des Pools auf der AlwaysOn Availability Group Upgrade.</span><span class="sxs-lookup"><span data-stu-id="34010-297">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AlwaysOn Availability Group.</span></span> 
  
1. <span data-ttu-id="34010-298">Einrichten von Windows Server Failover Clustering ein, auf allen Datenbankservern, die Teil der AlwaysOn Availability Group sein werden.</span><span class="sxs-lookup"><span data-stu-id="34010-298">Set up Windows Server Failover Clustering on all the database servers which will be part of the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-299">Führen Sie auf jedem Server die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="34010-299">On each server, do the following</span></span>
    
   - <span data-ttu-id="34010-300">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34010-300">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="34010-p149">Klicken Sie auf **Weiter** bis Sie das Kästchen **Funktionen auswählen** erreichen. Aktivieren Sie hier das Kontrollkästchen **Failoverclustering**.</span><span class="sxs-lookup"><span data-stu-id="34010-p149">Click **Next** until you reach the **Select features** box. Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="34010-303">Klicken Sie im Kästchen **Funktionen hinzufügen, die für Failoverclustering erforderlich sind?** auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34010-303">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="34010-304">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-304">Click **Install**.</span></span>
    
2. <span data-ttu-id="34010-305">Überprüfen Sie die Clusterkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="34010-305">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="34010-306">Klicken Sie im Server-Manager auf das Menü **Tools** und dann auf **Failovercluster-Manager**.</span><span class="sxs-lookup"><span data-stu-id="34010-306">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="34010-307">Klicken Sie unter **Aktionen** am rechten Bildschirmrand auf **Konfiguration überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="34010-307">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="34010-308">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-308">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-309">Wählen Sie die Server aus, die dem Cluster hinzugefügt werden sollen, und klicken Sie dann auf **Alle Tests ausführen**.</span><span class="sxs-lookup"><span data-stu-id="34010-309">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="34010-310">Überprüfen Sie im Feld**Zusammenfassung** , die der Assistent meldet Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="34010-310">In the**Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="34010-311">Klicken Sie dann auf **Fertig stellen**, um die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="34010-311">Then click **Finish** to complete the validation.</span></span>
    
    <span data-ttu-id="34010-p151">Der Assistent zeigt wahrscheinlich mehrere Warnungen an, vor allem dann, wenn Sie keine freigegebenen Speicher verwenden. Sie sind nicht daran gebunden, freigegebene Speicher zu verwenden. Sie müssen jedoch angezeigte **Fehler** zuerst beheben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="34010-p151">The wizard will probably report several warnings, especially if you are not using shared storage. You are not required to use shared storage. However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="34010-315">Erstellen Sie den Cluster.</span><span class="sxs-lookup"><span data-stu-id="34010-315">Create the cluster.</span></span>
    
   - <span data-ttu-id="34010-316">Klicken Sie im Assistenten **Failovercluster-Management**mit der rechten Maustaste auf **Failovercluster-Management** und dann auf **Cluster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="34010-316">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="34010-317">Klicken Sie auf der Seite **Vorbereiten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-317">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-p152">Fügen Sie Clustername und IP-Adresse hinzu. Wenn die Einstellungen überprüft wurden, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p152">Add the cluster name and IP address. When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-320">Klicken Sie auf der Seite „Bestätigung“ auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-320">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-321">Nachdem der Cluster erstellt wurde, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="34010-321">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="34010-p153">Wir empfehlen, die Clusterquorum-Einstellungen zu konfigurieren und einen Dateifreigabenzeugen zu verwenden. Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="34010-p153">We recommend that you configure the cluster quorum settings to use a file share witness. To do so, use these steps:</span></span>
    
   - <span data-ttu-id="34010-324">Klicken Sie mit der rechten Maustaste auf den Clusternamen, dann **Weitere Aktionen** und **Clusterquorum-Einstellungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-324">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="34010-325">Klicken Sie auf der Seite **Quorumkonfigurationsoption auswählen** auf **Quorumszeugen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="34010-325">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="34010-326">Klicken Sie auf der Seite **Quorumszeugen auswählen** auf **Dateifreigabenzeugen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="34010-326">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="34010-327">Geben Sie auf der Seite **Dateifreigabenzeugen konfigurieren** den Pfad der Dateifreigabe ein, die Sie verwenden möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-327">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="34010-328">Klicken Sie auf der Seite **Bestätigung** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-328">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="34010-329">Aktivieren Sie im SQL Server-Konfigurations-Manager jedes Clusters „Always On“.</span><span class="sxs-lookup"><span data-stu-id="34010-329">On each server in the cluster, enable Always On in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="34010-p154">Öffnen Sie den SQL Server-Konfigurations-Manager. Klicken Sie in der Struktur am linken Bildschirmrand auf **SQL Server-Dienste** und doppelklicken Sie darauf. </span><span class="sxs-lookup"><span data-stu-id="34010-p154">Open SQL Server Configuration Manager. In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="34010-p155">Wählen Sie im Kästchen **Eigenschaften** die Registerkarte **Hohe Verfügbarkeit AlwaysOn** aus. Aktivieren Sie das Kontrollkästchen **AlwaysOn-Verfügbarkeitsgruppen aktivieren**. Starten Sie SQL Server-Dienste neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="34010-p155">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box. Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="34010-334">Erstellen Sie die Verfügbarkeitsgruppe.</span><span class="sxs-lookup"><span data-stu-id="34010-334">Create the availability group.</span></span>
    
   - <span data-ttu-id="34010-335">Öffnen Sie SQL Server Management Studio und verbinden Sie sich mit der SQL Server-Instanz.</span><span class="sxs-lookup"><span data-stu-id="34010-335">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="34010-p156">Erweitern Sie im Objekt-Explorer den Ordner **Hohe Verfügbarkeit AlwaysOn**. Klicken Sie mit der rechten Maustaste auf den Ordner **Verfügbarkeitsgruppen** und klicken Sie auf **Neuer Verfügbarkeitsgruppen-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="34010-p156">In Object Explorer, expand the **AlwaysOn High Availability** folder. Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="34010-338">Wenn sich die Seite **Einführung** öffnet, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-338">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="34010-339">Geben Sie auf der Seite **Verfügbarkeitsgruppennamen angeben** den Namen der Verfügbarkeitsgruppe ein und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-339">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="34010-340">Datenbanken wählen Sie auf der Seite Wählen Sie die Datenbanken, die Sie in der AlwaysOn Availability Group einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="34010-340">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-341">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-341">Then click **Next**.</span></span>
    
    <span data-ttu-id="34010-342">Schließen Sie nicht die **ReportServer**, **ReportServerTempDB**oder Datenbanken beständigen Chat in der AlwaysOn Availability Group, wie diese in diesem Szenario nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="34010-342">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="34010-343">Sie können alle anderen Skype für Business Server-Datenbanken in der AlwaysOn Availability Group einschließen.</span><span class="sxs-lookup"><span data-stu-id="34010-343">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="34010-344">Klicken Sie auf der Seite **Replikat angeben** auf die Registerkarte **Replikate**. Klicken Sie dann auf die Schaltfläche **Replikate hinzufügen** und verbinden Sie sich mit den anderen SQL-Instanzen, die sie über Knoten des Windows Server Failoverclusters verbunden haben.</span><span class="sxs-lookup"><span data-stu-id="34010-344">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="34010-p159">Wählen Sie für jede Instanz die Optionen **Automatisches Failover** und **Synchrones Commit**. Wählen Sie nicht die Option **Lesbare sekundäre Rolle** aus.</span><span class="sxs-lookup"><span data-stu-id="34010-p159">For each instance, select the **Automatic Failover** and **Synchronous Commit** options. Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="34010-347">Klicken Sie auf die Registerkarte **Endpunkte** und überprüfen Sie, ob die **Portnummer** auf 5022 eingestellt ist.</span><span class="sxs-lookup"><span data-stu-id="34010-347">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="34010-p160">Klicken Sie auf die Registerkarte **Listener**, und wählen Sie die Option **Verfügbarkeitsgruppen-Listener erstellen** aus. Geben Sie unter dieser Option einen Namen für den Listener ein, und legen Sie den **Port** auf „1433“ fest (andere Ports werden für diese Option nicht unterstützt).</span><span class="sxs-lookup"><span data-stu-id="34010-p160">Click the **Listener** tab, and select the **Create an availability group listener** option. Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="34010-350">Klicken Sie auf **Hinzufügen** und dann in das Kästchen **IPv4-Adresse**, geben Sie Ihre bevorzugte virtuelle IP-Adresse an und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-350">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="34010-p161">Wählen Sie auf der Seite **Anfängliche Datensynchronisierung auswählen** „Vollständig“ (Full) aus und geben Sie einen Ordner an, auf den Replikate Zugriff haben und für den das SQL Server-Dienstkonto, das von beiden Replikaten verwendet wird, „Schreibberechtigungen“ hat. Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p161">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for. Then click **Next**.</span></span>
    
    <span data-ttu-id="34010-p162">Diese Dateifreigabe wird vorübergehend benutzt, wenn Sie die Datenbanken initialisieren. Wenn Sie mit großen Datenbanken arbeiten, empfehlen wir, dass Sie sie manuell initialisieren, für den Fall, dass die Größe der Datenbank-Backups Ihre Netzwerkbandbreite übersteigt.</span><span class="sxs-lookup"><span data-stu-id="34010-p162">This file share will be used temporarily when you initialize the databases. If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="34010-355">Kontrollieren Sie auf der Überprüfungsseite, dass alle Überprüfungen erfolgreich waren und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-355">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="34010-356">Überprüfen Sie auf der Seite **Zusammenfassung** alle Einstellungen und klicken Sie dann auf „Fertig stellen“.</span><span class="sxs-lookup"><span data-stu-id="34010-356">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="34010-357">Erstellen eines neuen Speichers angeben des Listeners AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-357">Create a new store specifying the AlwaysOn Availability Group listener.</span></span>
    
   - <span data-ttu-id="34010-358">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34010-358">Open Topology Builder.</span></span> <span data-ttu-id="34010-359">Erweitern Sie in Ihrer Topologie den Eintrag **Freigegebene Komponenten**, klicken Sie mit der rechten Maustaste auf **SQL Server-Speicher**, und klicken Sie auf **Neuer SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="34010-359">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="34010-360">Aktivieren Sie auf der Seite **Neuen SQL-Speicher definieren** erst das Kontrollkästchen **Einstellungen der hohen Verfügbarkeit** und stellen Sie dann sicher, dass SQL AlwaysOn Verfügbarkeitsgruppe im Dropdownfeld erscheint.</span><span class="sxs-lookup"><span data-stu-id="34010-360">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="34010-361">Geben Sie in das Kästchen **FQDN des SQL Server Verfügbarkeitslisteners** die FQDN des Listeners ein, die sie erstellt haben, als Sie die Verfügbarkeitsgruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="34010-361">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="34010-362">Geben Sie den FQDN des primären Knotens die AlwaysOn Availability Group im Feld **SQL Server-FQDN** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-362">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AlwaysOn Availability Group, and then click **OK**.</span></span>
    
8. <span data-ttu-id="34010-363">Ordnen Sie den Front-End-Pool mit der neuen AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-363">Associate the new AlwaysOn Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="34010-364">Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools der AlwaysOn Availability Group zugeordnet, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="34010-364">In Topology Builder, right-click the pool to associate with the AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="34010-365">Wählen Sie unter **Zuordnungen**klicken Sie im **SQL Server-Speicher** der AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-365">Under **Associations**, in the **SQL Server Store** box, select the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-366">Wählen Sie die gleiche Gruppe für andere Datenbanken im Pool, die Sie in der AlwaysOn Availability Group verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="34010-366">Select the same group for any other databases in the pool which you want to move to the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="34010-367">Wenn Sie sicher sind, dass alle benötigte Datenbanken auf die AlwaysOn Availability Group festgelegt sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-367">When you're sure that all needed databases are set to the AlwaysOn Availability Group, click **OK**.</span></span>
    
9. <span data-ttu-id="34010-p165">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und dann auf **Veröffentlichen**. Klicken Sie dann auf der Bestätigungsseite auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="34010-p165">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="34010-371">Führen Sie einige abschließende Schritte, um sicherzustellen, dass die SQL-Anmeldungen auf den einzelnen Replikate in der AlwaysOn Availability Group sind.</span><span class="sxs-lookup"><span data-stu-id="34010-371">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="34010-372">Öffnen Sie Topologie-Generator zu, wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen**aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="34010-372">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="34010-373">Erweitern Sie erst „Skype for Business Server“, dann Ihre Topologie und dann **SQL Server-Speicher**.</span><span class="sxs-lookup"><span data-stu-id="34010-373">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="34010-374">Mit der rechten Maustaste in des SQL-Speichers der neuen AlwaysOn Availability Group, und klicken Sie auf ** Bearbeiten Eigenschaften **.</span><span class="sxs-lookup"><span data-stu-id="34010-374">Right-click the SQL store of the new AlwaysOn Availability Group, and click ** Edit Properties**.</span></span>
    
    - <span data-ttu-id="34010-375">Ändern Sie den Wert am unteren Rand der Seite in das Feld **SQL Server-FQDN** dem vollqualifizierten Domänennamen des der Listener die AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-375">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="34010-p167">Veröffentlichen der Topologie. Klicken Sie im Menü **Aktion** auf **Topologie** und anschließend auf **Veröffentlichen**. Klicken Sie als Nächstes auf der Bestätigungsseite auf **Weiter**. Warten Sie einige Minuten, bis sich die neue Topologie repliziert hat.</span><span class="sxs-lookup"><span data-stu-id="34010-p167">Publish the topology. From the **Action** menu click **Topology** and then **Publish**. Then in the confirmation page click **Next**. Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="34010-380">Öffnen Sie SQL Server Management Studio, und navigieren Sie zu der AlwaysOn Availability Group.</span><span class="sxs-lookup"><span data-stu-id="34010-380">Open SQL Server Management Studio, and navigate to the AlwaysOn Availability Group.</span></span> <span data-ttu-id="34010-381">Führen Sie ein Failover zu einem sekundären Replikat aus.</span><span class="sxs-lookup"><span data-stu-id="34010-381">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="34010-382">Öffnen von Skype für Business Server-Verwaltungsshell, und geben Sie das folgende Cmdlet aus, um die SQL-Anmeldungen auf dieses Replikat zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="34010-382">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
     ```
     Install-CsDatabase -Update
     ```

     - <span data-ttu-id="34010-383">Wiederholen Sie die vorherigen beiden Schritte (verwenden Sie ein Failover der Gruppe sein, um ein sekundäres Replikat `Install-CsDatabase -Update`) für jedes Replikat in der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="34010-383">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    

