---
title: Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern
description: Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit des Back-End-Servers.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying SQL mirroring for Back End Server high availability
ms:assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204992(v=OCS.15)
ms:contentKeyID: 48184451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2ab2d598249c12231668a888b442f830c5d65f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566001"
---
# <a name="deploying-sql-mirroring-for-back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="e5f70-103">Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5f70-103">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5f70-104">_**Letztes Änderungsstand des Themas:** 2014-01-08_</span><span class="sxs-lookup"><span data-stu-id="e5f70-104">_**Topic Last Modified:** 2014-01-08_</span></span>

<span data-ttu-id="e5f70-105">Um die SQL-Spiegelung bereitstellen zu können, müssen die Server mindestens SQL Server 2008 R2 ausführen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-105">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="e5f70-106">Diese Version muss auf allen beteiligten Servern ausgeführt werden: primär, Spiegel und Zeuge.</span><span class="sxs-lookup"><span data-stu-id="e5f70-106">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="e5f70-107">Ausführliche Informationen finden Sie unter [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921) .</span><span class="sxs-lookup"><span data-stu-id="e5f70-107">For details, see [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=2083921](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2083921).</span></span>

<span data-ttu-id="e5f70-108">Im Allgemeinen erfordert das Einrichten der SQL-Spiegelung zwischen den beiden Back-End-Servern mit einem Zeugen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e5f70-108">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

  - <span data-ttu-id="e5f70-109">Die SQL Server Version des primären Servers muss die SQL-Spiegelung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-109">The primary server’s version of SQL Server must support SQL mirroring.</span></span>

  - <span data-ttu-id="e5f70-110">Der primäre, der Spiegel und der Zeuge (falls bereitgestellt) müssen dieselbe Version von SQL Server haben.</span><span class="sxs-lookup"><span data-stu-id="e5f70-110">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

  - <span data-ttu-id="e5f70-111">Der primäre und der Spiegel müssen dieselbe Edition von SQL Server aufweisen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-111">The primary and the mirror must have the same edition of SQL Server.</span></span> <span data-ttu-id="e5f70-112">Der Zeugen kann eine andere Edition haben.</span><span class="sxs-lookup"><span data-stu-id="e5f70-112">The witness may have a different edition.</span></span>

<span data-ttu-id="e5f70-113">Informationen zu SQL-Best Practices in Bezug auf die Unterstützung von SQL-Versionen für eine Zeugenrolle finden Sie unter "Datenbank-Spiegelungs Zeuge" in der MSDN Library unter [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345) .</span><span class="sxs-lookup"><span data-stu-id="e5f70-113">For SQL best practices in terms of what SQL versions are supported for a Witness role, see "Database Mirroring Witness" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247345](https://go.microsoft.com/fwlink/p/?linkid=247345).</span></span>

<span data-ttu-id="e5f70-114">Verwenden Sie den Topologie-Generator, um die SQL-Spiegelung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-114">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="e5f70-115">Sie wählen eine Option im Topologie-Generator aus, um die Datenbanken zu spiegeln, und der Topologie-Generator richtet die Spiegelung (einschließlich Einrichten eines Zeugen, falls gewünscht) ein, wenn Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-115">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="e5f70-116">Beachten Sie, dass Sie den Zeugen gleichzeitig einrichten oder entfernen, wenn Sie die Spiegelung einrichten oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-116">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="e5f70-117">Es gibt keinen separaten Befehl zum Bereitstellen oder Entfernen eines Zeugen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-117">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="e5f70-118">Zum Konfigurieren der Server Spiegelung müssen Sie zunächst die SQL-Datenbankberechtigungen ordnungsgemäß einrichten.</span><span class="sxs-lookup"><span data-stu-id="e5f70-118">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="e5f70-119">Ausführliche Informationen finden Sie unter "Einrichten von Anmeldekonten für die Datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454) .</span><span class="sxs-lookup"><span data-stu-id="e5f70-119">For details, see "Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268454](https://go.microsoft.com/fwlink/p/?linkid=268454).</span></span>

<span data-ttu-id="e5f70-120">Bei der SQL-Spiegelung ist der Wiederherstellungsmodus der Datenbank immer auf **Full**festgelegt, was bedeutet, dass Sie die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern müssen, um zu vermeiden, dass der Speicherplatz auf den Back-End-Servern knapp wird.</span><span class="sxs-lookup"><span data-stu-id="e5f70-120">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="e5f70-121">Die Häufigkeit der Transaktionsprotokollsicherungen hängt von der Protokoll Wachstumsrate ab, die wiederum von Datenbanktransaktionen abhängt, die von Benutzeraktivitäten auf dem Front-End-Pool verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="e5f70-121">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="e5f70-122">Es wird empfohlen, festzulegen, wie viel Transaktionsprotokoll Wachstum für Ihre lync-Bereitstellungs Arbeitsauslastung erwartet wird, damit Sie die Planung entsprechend durchführen können.</span><span class="sxs-lookup"><span data-stu-id="e5f70-122">We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="e5f70-123">Die folgenden Artikel bieten zusätzliche Informationen zur SQL-Sicherung und-Protokollverwaltung:</span><span class="sxs-lookup"><span data-stu-id="e5f70-123">The following articles provide additional information on SQL backup and log management:</span></span>

  - <span data-ttu-id="e5f70-124">Daten Bank Wiederherstellungsmodelle: "Wiederherstellungsmodelle (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span><span class="sxs-lookup"><span data-stu-id="e5f70-124">Database recovery models: "Recovery Models (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268446](https://go.microsoft.com/fwlink/p/?linkid=268446)</span></span>

  - <span data-ttu-id="e5f70-125">Übersicht über die Sicherung: "Übersicht über Sicherungen (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span><span class="sxs-lookup"><span data-stu-id="e5f70-125">Backup overview: "Backup Overview (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268449](https://go.microsoft.com/fwlink/p/?linkid=268449)</span></span>

  - <span data-ttu-id="e5f70-126">Sicherungs Transaktionsprotokoll: "Sichern eines Transaktionsprotokolls (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span><span class="sxs-lookup"><span data-stu-id="e5f70-126">Backup transaction log: "Backup a Transaction Log (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268452](https://go.microsoft.com/fwlink/p/?linkid=268452)</span></span>

<span data-ttu-id="e5f70-127">Bei der SQL-Spiegelung können Sie entweder die Topologie für die Spiegelung konfigurieren, wenn Sie die Pools erstellen oder nachdem die Pools bereits erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e5f70-127">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>



> [!IMPORTANT]
> <span data-ttu-id="e5f70-128">Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die primären, Spiegel-und Zeugenserver (falls gewünscht) zu derselben Domäne gehören.</span><span class="sxs-lookup"><span data-stu-id="e5f70-128">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="e5f70-129">Wenn Sie die SQL-Spiegelung zwischen Servern in unterschiedlichen Domänen einrichten möchten, lesen Sie Ihre SQL Server Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="e5f70-129">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>





> [!IMPORTANT]
> <span data-ttu-id="e5f70-130">Wenn Sie eine Änderung an einer Back-End-Daten Bank Spiegelungs Beziehung vornehmen, müssen Sie alle Front-End-Server im Pool neu starten.</span><span class="sxs-lookup"><span data-stu-id="e5f70-130">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span><BR><span data-ttu-id="e5f70-131">Für eine Änderung der Spiegelung (beispielsweise das Ändern des Speicherorts einer Spiegelung) müssen Sie den Topologie-Generator verwenden, um diese drei Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="e5f70-131">For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="e5f70-132">Entfernen Sie die Spiegelung vom alten Spiegelserver.</span><span class="sxs-lookup"><span data-stu-id="e5f70-132">Remove mirroring from the old mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="e5f70-133">Fügen Sie dem neuen Spiegelserver die Spiegelung hinzu.</span><span class="sxs-lookup"><span data-stu-id="e5f70-133">Add mirroring to the new mirror server.</span></span></P>
> <LI>
> <P><span data-ttu-id="e5f70-134">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="e5f70-134">Publish the topology.</span></span></P></LI></OL>




> [!NOTE]
> <span data-ttu-id="e5f70-135">Es muss eine Dateifreigabe erstellt werden, in die die Spiegeldateien geschrieben werden sollen, und der Dienst, auf dem SQL Server und SQL-Agent ausgeführt werden, benötigt Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="e5f70-135">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="e5f70-136">Wenn der SQL Server Dienst unter dem Kontext von Netzwerkdienst läuft, können Sie &lt; Domänen &gt;&#92;&lt; SQLServerName &gt; $ sowohl der Prinzipal-als auch der Mirror SQL-Server den Freigabeberechtigungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-136">If the SQL Server service is running under the context of Network Service, you can add &lt;Domain&gt;&#92;&lt;SQLSERVERNAME&gt;$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="e5f70-137">Der Wert $ ist wichtig, um festzustellen, dass es sich um ein Computerkonto handelt.</span><span class="sxs-lookup"><span data-stu-id="e5f70-137">The $ is important to identify that this is a computer account.</span></span>


<div>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="e5f70-138">So konfigurieren Sie die SQL-Spiegelung beim Erstellen eines Pools im Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="e5f70-138">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1.  <span data-ttu-id="e5f70-139">Klicken Sie auf der Seite **SQL-Speicher definieren** neben dem Feld **SQL-Speicher** auf **neu** .</span><span class="sxs-lookup"><span data-stu-id="e5f70-139">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2.  <span data-ttu-id="e5f70-140">Geben Sie auf der Seite **neuen SQL-Speicher definieren** den primären Speicher an, wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung aus**, geben Sie die SQL-Spiegelungs Portnummer an (Standardwert 5022), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-140">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3.  <span data-ttu-id="e5f70-141">Wählen Sie zurück auf der Seite **SQL-Speicher definieren** die Option **SQL-Speicherspiegelung aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="e5f70-141">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4.  <span data-ttu-id="e5f70-142">Geben Sie auf der Seite **neuen SQL-Speicher definieren** den SQL-Speicher an, der als Spiegel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5f70-142">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror.</span></span> <span data-ttu-id="e5f70-143">Wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung**aus, geben Sie die Portnummer an (Standardwert 5022), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-143">Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="e5f70-144">Wenn Sie einen Zeugen für diesen Spiegel verwenden möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e5f70-144">If you want a witness for this mirror, do the following:</span></span>
    
    1.  <span data-ttu-id="e5f70-145">Wählen Sie **zum Aktivieren des automatischen Failovers die Option SQL-Spiegelungs Zeugen verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="e5f70-145">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>
    
    2.  <span data-ttu-id="e5f70-146">Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **Automatisches Failover mithilfe des SQL-Spiegelungs Zeugen aktivieren**aus, und geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5f70-146">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>
    
    3.  <span data-ttu-id="e5f70-147">Geben Sie die Portnummer an (der Standardwert lautet 7022), und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-147">Specify the port number (the default is 7022) and click **OK**.</span></span>

6.  <span data-ttu-id="e5f70-148">Nachdem Sie die Front-End-Pool und alle anderen Rollen in Ihrer Topologie definiert haben, verwenden Sie den Topologie-Generator, um die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-148">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="e5f70-149">Wenn die Topologie veröffentlicht wird und die Front-End-Pool, die den zentralen Verwaltungsspeicher hostet, die SQL-Spiegelung aktiviert hat, wird eine Option zum Erstellen von primären und Spiegel-SQL-Speicher Datenbanken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e5f70-149">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>
    
    <span data-ttu-id="e5f70-150">Klicken Sie auf **Einstellungen**, und geben Sie den Pfad ein, der als Dateifreigabe für die Spiegelungs Sicherung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5f70-150">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>
    
    <span data-ttu-id="e5f70-151">Klicken Sie auf **OK** und dann auf **weiter** , um die Datenbanken zu erstellen und die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-151">Click **OK** and then **Next** to create the databases and publish the topology.</span></span> <span data-ttu-id="e5f70-152">Die Spiegelung und der Zeuge (sofern angegeben) werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e5f70-152">The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="e5f70-153">Sie können den Topologie-Generator zum Bearbeiten der Eigenschaften eines bereits vorhandenen Pools verwenden, um die SQL-Spiegelung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e5f70-153">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

</div>

<div>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="e5f70-154">So fügen Sie eine SQL-Spiegelung zu einer vorhandenen Front-End-Pool im Topologie-Generator hinzu</span><span class="sxs-lookup"><span data-stu-id="e5f70-154">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1.  <span data-ttu-id="e5f70-155">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-155">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e5f70-156">Wählen Sie **SQL-Speicherspiegelung aktivieren**aus, und klicken Sie dann neben **Spiegelungs-SQL-Speicher**auf **neu** .</span><span class="sxs-lookup"><span data-stu-id="e5f70-156">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3.  <span data-ttu-id="e5f70-157">Geben Sie den SQL-Speicher an, der als Spiegel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5f70-157">Specify the SQL store that you want to use as the mirror.</span></span>

4.  <span data-ttu-id="e5f70-158">Wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung**aus, geben Sie die SQL-Spiegelungs Portnummer an, die den Standardport 5022 ist), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-158">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5.  <span data-ttu-id="e5f70-159">Wenn Sie einen Zeugen konfigurieren möchten, wählen Sie **zum Aktivieren des automatischen Failovers die Option SQL-Spiegelungs Zeugen verwenden**aus, und klicken Sie auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-159">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6.  <span data-ttu-id="e5f70-160">Geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5f70-160">Specify the SQL store that you want to use as the witness.</span></span>

7.  <span data-ttu-id="e5f70-161">Wählen Sie **diese SQL-Instanz befindet sich in einer Spiegelungs Beziehung**aus, geben Sie die Portnummer für die SQL-Spiegelung an (der Standardport lautet 7022), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-161">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8.  <span data-ttu-id="e5f70-162">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-162">Click **OK**.</span></span>

9.  <span data-ttu-id="e5f70-163">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="e5f70-163">Publish the topology.</span></span> <span data-ttu-id="e5f70-164">Wenn Sie dies tun, werden Sie aufgefordert, die Datenbank zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e5f70-164">When you do so, you will be prompted to install the database.</span></span>
    
    <span data-ttu-id="e5f70-165">Während des Veröffentlichungsprozesses der Topologie werden Sie aufgefordert, einen Dateifreigabepfad zu definieren.</span><span class="sxs-lookup"><span data-stu-id="e5f70-165">During the topology publishing process, you will be asked to define a file share path.</span></span> <span data-ttu-id="e5f70-166">Die SQL-Server, die an der Spiegelung teilnehmen, müssen über Lese-/Schreibzugriff auf diese Dateifreigabe verfügen, damit die Spiegelung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e5f70-166">The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="e5f70-167">Anschließend müssen Sie die Datenbank installieren, bevor Sie mit dem nächsten Verfahren fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e5f70-167">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="e5f70-168">Beachten Sie beim Einrichten der SQL-Spiegelung Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e5f70-168">You should keep the following in mind when setting up SQL mirroring:</span></span>

  - <span data-ttu-id="e5f70-169">Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird er mithilfe der dort definierten Ports wieder verwendet und ignoriert diejenigen, die Sie in der Topologie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e5f70-169">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

  - <span data-ttu-id="e5f70-170">Jeder Port, der bereits für andere Anwendungen auf demselben Server reserviert ist, einschließlich der für andere SQL-Instanzen, sollte nicht für die installierten SQL-Instanzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e5f70-170">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand.</span></span> <span data-ttu-id="e5f70-171">Dies bedeutet, dass Sie bei mehr als einer SQL-Instanz auf demselben Server nicht denselben Port für die Spiegelung verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-171">This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring.</span></span> <span data-ttu-id="e5f70-172">Ausführliche Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="e5f70-172">For details, see the following articles:</span></span>
    
      - <span data-ttu-id="e5f70-173">"Angeben einer Server Netzwerkadresse (Datenbankspiegelung)" in der MSDN Library unter [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span><span class="sxs-lookup"><span data-stu-id="e5f70-173">"Specify a Server Network Address (Database Mirroring)" in the MSDN Library at [https://go.microsoft.com/fwlink/p/?LinkId=247346](https://go.microsoft.com/fwlink/p/?linkid=247346)</span></span>
    
      - <span data-ttu-id="e5f70-174">"Der Datenbankspiegelungsendpunkt (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span><span class="sxs-lookup"><span data-stu-id="e5f70-174">"The Database Mirroring Endpoint (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=247347](https://go.microsoft.com/fwlink/p/?linkid=247347)</span></span>

</div>

<div>

## <a name="using-lync-server-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="e5f70-175">Verwenden von lync Server-Verwaltungsshell-Cmdlets zum Einrichten der SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="e5f70-175">Using Lync Server Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="e5f70-176">Die einfachste Möglichkeit zum Einrichten der Spiegelung ist die Verwendung des Topologie-Generators, aber Sie können dies auch mithilfe von Cmdlets tun.</span><span class="sxs-lookup"><span data-stu-id="e5f70-176">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1.  <span data-ttu-id="e5f70-177">Öffnen Sie ein lync Server-Verwaltungsshell Fenster, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="e5f70-177">Open a Lync Server Management Shell window and run the following cmdlet:</span></span>
    
        Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose 
    
    <span data-ttu-id="e5f70-178">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e5f70-178">For example:</span></span>
    
        Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose 
    
    <span data-ttu-id="e5f70-179">Folgendes wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e5f70-179">You will see the following:</span></span>
    
        Database Name:rtcxds 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcshared 
                Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf 
                 Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rtcab 
                Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf 
                 Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsconfig 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:rgsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:cpsdyn 
                Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf 
                 Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:xds 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$ 
            Database Name:lis 
                Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf 
                 Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf 
              Primary SQL: e04-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\e04-ocs$ 
               Mirror SQL: K16-ocs.los_a.lsipt.local\rtc 
                  Account: LOS_A\K16-ocs$ 
             Witness SQL : AB14-lct.los_a.lsipt.local\rtc 
                  Account: LOS_A\AB14-lct$
        [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): 

2.  <span data-ttu-id="e5f70-180">Überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e5f70-180">Verify the following:</span></span>
    
      - <span data-ttu-id="e5f70-181">Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im primären SQL Server "E04-OCS. Los \_ a. lsipt. local RTC aktiviert ist \\ .</span><span class="sxs-lookup"><span data-stu-id="e5f70-181">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="e5f70-182">Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Spiegel SQL Server "K16-OCS. Los \_ a. lsipt. local RTC aktiviert ist \\ .</span><span class="sxs-lookup"><span data-stu-id="e5f70-182">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="e5f70-183">Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall im Zeugen SQL Server "ab14-LCT. Los \_ a. lsipt. local RTC aktiviert ist \\ .</span><span class="sxs-lookup"><span data-stu-id="e5f70-183">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los\_a.lsipt.local\\rtc.</span></span>
    
      - <span data-ttu-id="e5f70-184">Konten, die die SQL-Server auf allen primären und Spiegel-SQL-Servern durchführen, verfügen über Lese-/Schreibzugriff auf die Dateifreigabe \\ \\ E04 – OCS- \\ csdatabackup</span><span class="sxs-lookup"><span data-stu-id="e5f70-184">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\\\E04-OCS\\csdatabackup</span></span>
    
      - <span data-ttu-id="e5f70-185">Stellen Sie sicher, dass der WMI-Anbieter (Windows Management Instrumentation) auf allen diesen Servern läuft.</span><span class="sxs-lookup"><span data-stu-id="e5f70-185">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers.</span></span> <span data-ttu-id="e5f70-186">Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für SQL Server Dienste zu finden, die auf allen primären, Spiegel-und Zeugen Servern aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="e5f70-186">The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>
    
      - <span data-ttu-id="e5f70-187">Stellen Sie sicher, dass das Konto, mit dem dieses Cmdlet ausgeführt wird, über die Berechtigung zum Erstellen der Ordner für die Daten-und Protokolldateien für alle Spiegelserver verfügt.</span><span class="sxs-lookup"><span data-stu-id="e5f70-187">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>
    
      - <span data-ttu-id="e5f70-188">Beachten Sie, dass das Benutzerkonto, das von der SQL-Instanz zur Ausführung verwendet wird, über Lese-/Schreibzugriff auf die Dateifreigabe verfügen muss.</span><span class="sxs-lookup"><span data-stu-id="e5f70-188">Note that the user account that the SQL instance uses to run must have read/write permission to the file share.</span></span> <span data-ttu-id="e5f70-189">Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL-Instanz ein lokales Systemkonto ausführt, müssen Sie dem Server, auf dem die SQL-Instanz gehostet wird, Dateifreigabeberechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-189">If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3.  <span data-ttu-id="e5f70-190">Geben Sie A ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="e5f70-190">Type A and press ENTER.</span></span>
    
    <span data-ttu-id="e5f70-191">Die Spiegelung wird konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e5f70-191">The mirroring will be configured.</span></span>

<span data-ttu-id="e5f70-192">**Install-CsMirrorDatabase** installiert die Spiegelung und konfiguriert die Spiegelung für alle Datenbanken, die auf dem primären SQL-Speicher vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e5f70-192">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="e5f70-193">Wenn Sie die Spiegelung nur für bestimmte Datenbanken konfigurieren möchten, können Sie die Option – DatabaseType verwenden, oder wenn Sie die Spiegelung für alle Datenbanken mit Ausnahme einiger weniger konfigurieren möchten, können Sie die Option-ExcludeDatabaseList zusammen mit einer durch Trennzeichen getrennten Liste der auszuschließenden Datenbanknamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5f70-193">If you want to configure mirroring for only specific databases, you can use the –DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

<span data-ttu-id="e5f70-194">Wenn Sie beispielsweise die folgende Option zum Installieren von **-CsMirrorDatabase**hinzufügen, werden alle Datenbanken mit Ausnahme von RTCAb und "rtcxds" gespiegelt.</span><span class="sxs-lookup"><span data-stu-id="e5f70-194">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

`-ExcludeDatabaseList rtcab,rtcxds`

<span data-ttu-id="e5f70-195">Wenn Sie beispielsweise die folgende Option zum Installieren von **-CsMirrorDatabase**hinzufügen, werden nur die RTCAb-, rtcshared-und "rtcxds"-Datenbanken gespiegelt.</span><span class="sxs-lookup"><span data-stu-id="e5f70-195">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

`-DatabaseType User`

</div>

<div>

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="e5f70-196">Entfernen oder Ändern der SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="e5f70-196">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="e5f70-197">Um die SQL-Spiegelung eines Pools im Topologie-Generator zu entfernen, müssen Sie zuerst ein Cmdlet verwenden, um die Spiegelung in SQL Server zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-197">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server.</span></span> <span data-ttu-id="e5f70-198">Anschließend können Sie den Topologie-Generator verwenden, um den Spiegel aus der Topologie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-198">You can then use Topology Builder to remove the mirror from the topology.</span></span> <span data-ttu-id="e5f70-199">Verwenden Sie das folgende Cmdlet, um die Spiegelung in SQL Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="e5f70-199">To remove the mirror in SQL Server, use the following cmdlet:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

<span data-ttu-id="e5f70-200">Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu löschen:</span><span class="sxs-lookup"><span data-stu-id="e5f70-200">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

<span data-ttu-id="e5f70-201">Die `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betroffenen Datenbanken aus dem Spiegel gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e5f70-201">The `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="e5f70-202">Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="e5f70-202">Then, to remove the mirror from the topology, do the following:</span></span>

1.  <span data-ttu-id="e5f70-203">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-203">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e5f70-204">Deaktivieren Sie die **Option SQL-Speicherspiegelung aktivieren** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-204">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3.  <span data-ttu-id="e5f70-205">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="e5f70-205">Publish the topology.</span></span>

</div>

<div>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="e5f70-206">Entfernen eines Spiegelungs Zeugen</span><span class="sxs-lookup"><span data-stu-id="e5f70-206">Removing a Mirroring Witness</span></span>

<span data-ttu-id="e5f70-207">Verwenden Sie dieses Verfahren, wenn Sie den Zeugen aus einer Back-End-Server-Spiegelungskonfiguration entfernen müssen.</span><span class="sxs-lookup"><span data-stu-id="e5f70-207">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1.  <span data-ttu-id="e5f70-208">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-208">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="e5f70-209">Deaktivieren Sie **die Option verwenden Sie SQL Server Spiegelungs Zeugen, um das automatische Failover zu aktivieren** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e5f70-209">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3.  <span data-ttu-id="e5f70-210">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="e5f70-210">Publish the topology.</span></span>
    
    <span data-ttu-id="e5f70-211">Nach dem Veröffentlichen der Topologie wird im Topologie-Generator eine Meldung mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e5f70-211">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>
    
        Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
    
    <span data-ttu-id="e5f70-212">Führen Sie diesen Schritt jedoch nicht aus, und geben Sie nicht `Uninstall-CsMirrorDatabase` so ein, dass die gesamte Spiegelungskonfiguration deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="e5f70-212">However, do not follow that step, and do not type `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4.  <span data-ttu-id="e5f70-213">Wenn Sie lediglich den Zeugen aus der SQL Server Konfiguration entfernen möchten, befolgen Sie die Anweisungen unter "Entfernen des Zeugen aus einer Datenbank-Spiegelungssitzung (SQL Server)" unter [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456) .</span><span class="sxs-lookup"><span data-stu-id="e5f70-213">To remove just the witness from the SQL Server configuration, follow the instructions in "Remove the Witness from a Database Mirroring Session (SQL Server)" at [https://go.microsoft.com/fwlink/p/?LinkId=268456](https://go.microsoft.com/fwlink/p/?linkid=268456).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

