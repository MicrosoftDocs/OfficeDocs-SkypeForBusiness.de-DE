---
title: Bereitstellen der SQL-Spiegelung für hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: Damit eine SQL-Spiegelung bereitgestellt werden kann, müssen Ihre Server mindestens SQL Server 2008 R2 ausführen. Diese Version muss auf allen beteiligten Servern (primärer Server, Spiegel und Zeuge) ausgeführt werden. Weitere Informationen hierzu finden Sie unter kumulative Paket 9 für SQL Server 2008 Service Pack 1 aktualisiert.
ms.openlocfilehash: ebf1d222bff572100fe7824e52acdef2ff85216d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886275"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="67e47-105">Bereitstellen von SQL-Spiegelung für hohe Verfügbarkeit in Skype Back-End-Server für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="67e47-105">Deploy SQL mirroring for Back End Server high availability in Skype for Business server 2015</span></span>


<span data-ttu-id="67e47-106">Damit eine SQL-Spiegelung bereitgestellt werden kann, müssen Ihre Server mindestens SQL Server 2008 R2 ausführen.</span><span class="sxs-lookup"><span data-stu-id="67e47-106">To be able to deploy SQL mirroring, your servers must run a minimum of SQL Server 2008 R2.</span></span> <span data-ttu-id="67e47-107">Diese Version muss auf allen beteiligten Servern (primärer Server, Spiegel und Zeuge) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="67e47-107">This version must run on all the involved servers: the primary, mirror, and the witness.</span></span> <span data-ttu-id="67e47-108">Weitere Informationen hierzu finden Sie unter [kumulative Paket 9 für SQL Server 2008 Service Pack 1 zu aktualisieren ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span><span class="sxs-lookup"><span data-stu-id="67e47-108">For details, see [Cumulative update package 9 for SQL Server 2008 Service Pack 1 ](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921).</span></span>

<span data-ttu-id="67e47-109">Im Allgemeinen müssen folgende Voraussetzungen erfüllt sein, um eine SQL-Spiegelung zwischen zwei Back-End-Servern mit einem Zeugen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="67e47-109">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>

- <span data-ttu-id="67e47-110">Der primäre Server-Version von SQL Server muss SQL-Spiegelung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="67e47-110">The primary server's version of SQL Server must support SQL mirroring.</span></span>

- <span data-ttu-id="67e47-111">Prinzipal, Spiegel und Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server verwenden.</span><span class="sxs-lookup"><span data-stu-id="67e47-111">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span>

- <span data-ttu-id="67e47-p103">Prinzipal und Spiegel müssen dieselbe Version von SQL Server verwenden. Der Zeuge darf eine andere Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="67e47-p103">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>

<span data-ttu-id="67e47-114">Best Practices für SQL im Hinblick auf die für eine Rolle Zeugen welche SQL-Versionen unterstützt werden finden Sie unter [Datenbank-Spiegelungszeuge](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span><span class="sxs-lookup"><span data-stu-id="67e47-114">For SQL best practices in terms of what SQL versions are supported for a Witness role, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/p/?LinkId=247345).</span></span>

<span data-ttu-id="67e47-115">Sie verwenden die Topologie-Generator zum Bereitstellen von SQL-Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="67e47-115">You use Topology Builder to deploy SQL mirroring.</span></span> <span data-ttu-id="67e47-116">Wählen Sie eine Option im Topologie-Generator zu spiegelnden Datenbanken und Topologie-Generator richtet die Spiegelung (einschließlich der Einrichtung von ein Zeuge wie gewünscht) Wenn Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="67e47-116">You select an option in Topology Builder to mirror the databases, and Topology Builder sets up the mirroring (including setting up a witness, if you want) when you publish the topology.</span></span> <span data-ttu-id="67e47-117">Beachten Sie, dass Sie den Zeugen zum selben Zeitpunkt wie den Spiegel einrichten oder entfernen müssen.</span><span class="sxs-lookup"><span data-stu-id="67e47-117">Note that you set up or remove the witness at the same time you set up or remove the mirror.</span></span> <span data-ttu-id="67e47-118">Es gibt keinen separaten Befehl, mit dem Sie nur einen Zeugen bereitstellen oder entfernen können.</span><span class="sxs-lookup"><span data-stu-id="67e47-118">There is no separate command to deploy or remove only a witness.</span></span>

<span data-ttu-id="67e47-119">Wenn Sie eine Serverspiegelung konfigurieren möchten, müssen Sie zuerst die SQL-Datenbankberechtigungen korrekt einrichten.</span><span class="sxs-lookup"><span data-stu-id="67e47-119">To configure server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="67e47-120">Weitere Informationen hierzu finden Sie unter [Von Anmeldung Konten für Database Mirroring oder AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span><span class="sxs-lookup"><span data-stu-id="67e47-120">For details, see [Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>

<span data-ttu-id="67e47-p106">Bei der SQL-Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, d. h., Sie müssen die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern. Damit verhindern Sie, dass der Speicherplatz auf den Datenträgern der Back-End-Server zur Neige geht. Die Häufigkeit der Transaktionsprotokollsicherungen ist abhängig von der Wachstumsrate des Protokolls. Letztere richtet sich wiederum nach den Datenbanktransaktionen, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, das zu erwartende Wachstum des Transaktionsprotokolls für Ihre Bereitstellungsarbeitsauslastung zu ermitteln und entsprechend zu planen. In den folgenden Artikeln finden Sie zusätzliche Informationen zur SQL-Sicherung und Protokollverwaltung:</span><span class="sxs-lookup"><span data-stu-id="67e47-p106">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>

- [<span data-ttu-id="67e47-125">Wiederherstellungsmodelle für Datenbanken</span><span class="sxs-lookup"><span data-stu-id="67e47-125">Database recovery models</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [<span data-ttu-id="67e47-126">Sicherung (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="67e47-126">Backup overview</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [<span data-ttu-id="67e47-127">Transaktionsprotokoll sichern</span><span class="sxs-lookup"><span data-stu-id="67e47-127">Backup transaction log</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=268452)

<span data-ttu-id="67e47-128">Bei der SQL-Spiegelung können Sie die Topologie für die Spiegelung entweder beim Erstellen der Pools oder erst nach dem Erstellen der Pools konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="67e47-128">With SQL mirroring, you can either configure the topology for mirroring when you create the pools, or after the pools are already created.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67e47-129">Über Topologie-Generator oder Cmdlets zum Einrichten und Entfernen von SQL-Spiegelung werden nur, wenn die primäre, Spiegel und Zeuge (sofern gewünscht) Server derselben Domäne angehören.</span><span class="sxs-lookup"><span data-stu-id="67e47-129">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="67e47-130">Wenn Sie die SQL-Spiegelung für Server einrichten möchten, die sich in unterschiedlichen Domänen befinden, erhalten Sie weitere Informationen in der Dokumentation zu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="67e47-130">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67e47-131">Bei jeder Änderung an einer Spiegelungsbeziehung einer Back-End-Datenbank müssen Sie alle Front-End-Server im Pool neu starten. </span><span class="sxs-lookup"><span data-stu-id="67e47-131">Whenever you make a change to a Back End Database mirroring relationship, you must restart all the Front End Servers in the pool.</span></span> <span data-ttu-id="67e47-132">> für eine Änderung der Spiegelung, (z. B. "ändern den Speicherort der Spiegelung), Sie müssen Topologie-Generator zum Verwenden dieser drei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="67e47-132">> For a change in mirroring, (such as changing the location of a mirror), you must use Topology Builder to perform these three steps:</span></span>

1. <span data-ttu-id="67e47-133">Entfernen Sie die Spiegelung vom alten Spiegelserver.</span><span class="sxs-lookup"><span data-stu-id="67e47-133">Remove mirroring from the old mirror server.</span></span>

2. <span data-ttu-id="67e47-134">Fügen Sie dem neuen Spiegelserver die Spiegelung hinzu.</span><span class="sxs-lookup"><span data-stu-id="67e47-134">Add mirroring to the new mirror server.</span></span>

3. <span data-ttu-id="67e47-135">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="67e47-135">Publish the topology.</span></span>

> [!NOTE]
> <span data-ttu-id="67e47-136">Sie müssen eine Dateifreigabe erstellen, in die die Spiegeldateien geschrieben werden, und der Dienst, unter dem SQL Server und SQL Agent ausgeführt werden, benötigt Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="67e47-136">A file share has to be created for the mirror files to be written to, and the service that SQL Server and SQL Agent are running under needs read/write access.</span></span> <span data-ttu-id="67e47-137">Wenn der SQL Server-Dienst im Kontext des Netzwerkdienst ausgeführt wird, können Sie hinzufügen \<Domäne\>\\<SQLSERVERNAME\>$ von Haupt- und SQL-Spiegelserver an die Freigabeberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="67e47-137">If the SQL Server service is running under the context of Network Service, you can add \<Domain\>\\<SQLSERVERNAME\>$ of both the Principal and Mirror SQL Servers to the share permissions.</span></span> <span data-ttu-id="67e47-138">Das $-Zeichen ist wichtig, um anzugeben, dass es sich um ein Computerkonto handelt.</span><span class="sxs-lookup"><span data-stu-id="67e47-138">The $ is important to identify that this is a computer account.</span></span>

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a><span data-ttu-id="67e47-139">So konfigurieren Sie SQL-Spiegelung bei der Erstellung eines Pools im Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="67e47-139">To configure SQL mirroring while creating a pool in Topology Builder</span></span>

1. <span data-ttu-id="67e47-140">Klicken Sie auf der Seite **SQL-Speicher definieren** neben dem Feld **SQL-Speicher** auf **Neu**. </span><span class="sxs-lookup"><span data-stu-id="67e47-140">On the **Define the SQL Store** page, click **New** next to the **SQL store** box.</span></span>

2. <span data-ttu-id="67e47-141">Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den primären Speicher ein, wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die SQL-Spiegelportnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e47-141">On the **Define new SQL Store** page, specify the primary store, select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default is 5022), and then click **OK**.</span></span>

3. <span data-ttu-id="67e47-142">Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **SQL-Speicherspiegelung aktivieren** aus. </span><span class="sxs-lookup"><span data-stu-id="67e47-142">Back on the **Define the SQL store** page, select **Enable SQL Store mirroring**.</span></span>

4. <span data-ttu-id="67e47-p110">Geben Sie auf der Seite **Neuen SQL-Speicher definieren** den SQL-Speicher an, der als Spiegel verwendet werden soll. Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer an (Standardwert 5022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e47-p110">In the **Define new SQL Store** page, specify the SQL store to be used as the mirror. Select **This SQL instance is in mirroring relation**, specify the port number (the default is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="67e47-145">Wenn Sie einen Zeugen für diesen Spiegel verwenden möchten, führen Sie folgende Schritte aus: </span><span class="sxs-lookup"><span data-stu-id="67e47-145">If you want a witness for this mirror, do the following:</span></span>

    <span data-ttu-id="67e47-146">a.</span><span class="sxs-lookup"><span data-stu-id="67e47-146">a.</span></span> <span data-ttu-id="67e47-147">Wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus. </span><span class="sxs-lookup"><span data-stu-id="67e47-147">Select **Use SQL mirroring witness to enable automatic failover**.</span></span>

    <span data-ttu-id="67e47-148">b.</span><span class="sxs-lookup"><span data-stu-id="67e47-148">b.</span></span> <span data-ttu-id="67e47-149">Wählen Sie auf der Seite **SQL-Speicher definieren** die Option **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. </span><span class="sxs-lookup"><span data-stu-id="67e47-149">In the **Define the SQL Store** page, select **Use SQL mirroring witness to enable automatic failover**, and specify the SQL store to be used as the witness.</span></span>

    <span data-ttu-id="67e47-150">c.</span><span class="sxs-lookup"><span data-stu-id="67e47-150">c.</span></span> <span data-ttu-id="67e47-151">Geben Sie die Portnummer an (Standardwert 7022), und klicken Sie auf **OK**. </span><span class="sxs-lookup"><span data-stu-id="67e47-151">Specify the port number (the default is 7022) and click **OK**.</span></span>

6. <span data-ttu-id="67e47-152">Sobald Sie fertig sind definieren des Front-End-Pools und alle anderen Rollen in Ihrer Topologie Topologie-Generator verwenden, um die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="67e47-152">After you are done defining your Front End pool and all other roles in your topology, use Topology Builder to publish the topology.</span></span> <span data-ttu-id="67e47-153">Wenn die Topologie, veröffentlicht wird Wenn der Front-End-Pool, auf dem zentralen Verwaltungsspeicher gehostet hat, SQL-Spiegelung aktiviert, sehen Sie eine Option zum Erstellen von Primär- und SQL-Datenbanken im Verzeichnis zu spiegeln.</span><span class="sxs-lookup"><span data-stu-id="67e47-153">When the topology is published, if the Front End pool that hosts Central Management store has SQL mirroring enabled, you will see an option to create both primary and mirror SQL store databases.</span></span>

    <span data-ttu-id="67e47-154">Klicken Sie auf **Einstellungen**, und geben Sie den Pfad ein, den Sie als Dateifreigabe für die Spiegelungssicherung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="67e47-154">Click **Settings**, and type the path to use as the file share for the mirroring backup.</span></span>

    <span data-ttu-id="67e47-p115">Klicken Sie auf **OK** und anschließend auf **Weiter**, um die Datenbanken zu erstellen und die Topologie zu veröffentlichen. Die Spiegel- und die Zeugeninstanz (sofern angegeben) werden bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="67e47-p115">Click **OK** and then **Next** to create the databases and publish the topology. The mirroring and the witness (if specified) will be deployed.</span></span>

<span data-ttu-id="67e47-157">Topologie-Generator können zum Bearbeiten der Eigenschaften eines bereits bestehenden Pools zu SQL-Spiegelung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="67e47-157">You can use Topology Builder to edit the properties of an already existing pool to enable SQL mirroring.</span></span>

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a><span data-ttu-id="67e47-158">Hinzufügen des SQL-Spiegelung einem bestehenden Front-End-Pool im Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="67e47-158">To add SQL mirroring to an existing Front End pool in Topology Builder</span></span>

1. <span data-ttu-id="67e47-159">Klicken Sie im Topologie-Generator mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="67e47-159">In Topology Builder, right-click the pool and then click **Edit Properties**.</span></span>

2. <span data-ttu-id="67e47-160">Wählen Sie **SQL-Speicherspiegelung aktivieren** aus, und klicken Sie dann neben **Spiegelungs-SQL-Speicher** auf **Neu**. </span><span class="sxs-lookup"><span data-stu-id="67e47-160">Select **Enable SQL Store Mirroring**, and then click **New** next to **Mirroring SQL Store**.</span></span>

3. <span data-ttu-id="67e47-161">Geben Sie den SQL-Speicher an, der als Spiegel verwendet werden soll. </span><span class="sxs-lookup"><span data-stu-id="67e47-161">Specify the SQL store that you want to use as the mirror.</span></span>

4. <span data-ttu-id="67e47-162">Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 5022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e47-162">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number the default port is 5022), and then click **OK**.</span></span>

5. <span data-ttu-id="67e47-163">Wenn Sie einen Zeugen konfigurieren möchten, wählen Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren** aus, und klicken Sie dann auf **Neu**. </span><span class="sxs-lookup"><span data-stu-id="67e47-163">If you want to configure a witness, select **Use SQL mirroring witness to enable automatic failover**, and click **New**.</span></span>

6. <span data-ttu-id="67e47-164">Geben Sie den SQL-Speicher an, der als Zeuge verwendet werden soll. </span><span class="sxs-lookup"><span data-stu-id="67e47-164">Specify the SQL store that you want to use as the witness.</span></span>

7. <span data-ttu-id="67e47-165">Wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus, geben Sie die Portnummer für die SQL-Spiegelung an (Standardwert 7022), und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e47-165">Select **This SQL instance is in mirroring relation**, specify the SQL mirroring port number (the default port is 7022), and then click **OK**.</span></span>

8. <span data-ttu-id="67e47-166">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e47-166">Click **OK**.</span></span>

9. <span data-ttu-id="67e47-p116">Veröffentlichen Sie die Topologie. Dabei werden Sie zur Installation der Datenbank aufgefordert. </span><span class="sxs-lookup"><span data-stu-id="67e47-p116">Publish the topology. When you do so, you will be prompted to install the database.</span></span>

    <span data-ttu-id="67e47-p117">Während der Topologieveröffentlichung werden Sie aufgefordert, einen Dateifreigabepfad zu definieren. Die SQL-Server, die an der Spiegelung teilnehmen, benötigen Lese-/Schreibzugriff auf diese Dateifreigabe, damit der Spiegel eingerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="67e47-p117">During the topology publishing process, you will be asked to define a file share path. The SQL Servers that participate in the mirroring must have read/write access to this file share for the mirror to be established.</span></span>

<span data-ttu-id="67e47-171">Sie müssen nun erst die Datenbank installieren, bevor Sie mit dem nächsten Schritt fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="67e47-171">You must then install the database before going on to the next procedure.</span></span>

<span data-ttu-id="67e47-172">Bei der Einrichtung einer SQL-Spiegelung sollten Sie die folgenden Aspekte berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="67e47-172">You should keep the following in mind when setting up SQL mirroring:</span></span>

- <span data-ttu-id="67e47-173">Wenn bereits ein Spiegelungsendpunkt vorhanden ist, wird dieser mit den definierten Ports erneut verwendet. Die von Ihnen in der Topologie angegebenen Ports werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="67e47-173">If a mirroring endpoint already exists, it will be reused using the ports defined there, and will ignore the ones you specify in the topology.</span></span>

- <span data-ttu-id="67e47-p118">Alle bereits anderen Anwendungen auf demselben Server zugewiesenen Ports, einschließlich der Ports für andere SQL-Instanzen, sollten nicht für die jeweils installierten SQL-Instanzen verwendet werden. Das bedeutet, wenn mehrere SQL-Instanzen auf demselben Server installiert sind, dürfen diese Instanzen nicht denselben Port für die Spiegelung verwenden. Ausführliche Informationen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="67e47-p118">Any port already allocated for other applications on the same server, including those for other SQL instances, should not be used for the installed SQL instances at hand. This implies that if you have more than one SQL instance installed on the same server, they must not use the same port for mirroring. For details, see the following articles:</span></span>

  - [<span data-ttu-id="67e47-177">Angeben einer Servernetzwerkadresse (Datenbankspiegelung)</span><span class="sxs-lookup"><span data-stu-id="67e47-177">Specify a Server Network Address (Database Mirroring)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [<span data-ttu-id="67e47-178">Die Datenbank Spiegelung Endpunkt (SQLServer)</span><span class="sxs-lookup"><span data-stu-id="67e47-178">The Database Mirroring Endpoint (SQL Server)</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a><span data-ttu-id="67e47-179">Verwenden von Skype für Business Server 2015-Verwaltungsshell-Cmdlets zum Set Up SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="67e47-179">Using Skype for Business Server 2015 Management Shell Cmdlets to Set Up SQL Mirroring</span></span>

<span data-ttu-id="67e47-180">Die einfachste Möglichkeit zum Einrichten der Spiegelung wird mithilfe des Topologie-Generator, aber Sie können auch hierfür Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="67e47-180">The easiest way to set up mirroring is by using Topology Builder, but you can also do so using cmdlets.</span></span>

1. <span data-ttu-id="67e47-181">Öffnen Sie eine Skype für Business Server 2015-Verwaltungsshell-Fenster, und führen Sie das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="67e47-181">Open a Skype for Business Server 2015 Management Shell window and run the following cmdlet:</span></span>

   ```
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    <span data-ttu-id="67e47-182">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="67e47-182">For example:</span></span>

   ```
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    <span data-ttu-id="67e47-183">Folgendes wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="67e47-183">You will see the following:</span></span>

   <pre>
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
   </pre>

2. <span data-ttu-id="67e47-184">Überprüfen Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="67e47-184">Verify the following:</span></span>

    - <span data-ttu-id="67e47-185">Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem primären SQL-Server „e04-ocs.los_a.lsipt.local\rtc“ aktiviert ist. </span><span class="sxs-lookup"><span data-stu-id="67e47-185">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the primary SQL Server e04-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="67e47-186">Auf Port 5022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem SQL-Spiegelserver „K16-ocs.los_a.lsipt.local\rtc“ aktiviert ist. </span><span class="sxs-lookup"><span data-stu-id="67e47-186">Port 5022 is accessible through the firewall if Windows Firewall is enabled in the mirror SQL Server K16-ocs.los_a.lsipt.local\rtc.</span></span>

    - <span data-ttu-id="67e47-187">Auf Port 7022 kann über die Firewall zugegriffen werden, wenn die Windows-Firewall auf dem SQL-Zeugenserver „AB14-lct.los_a.lsipt.local\rtc“ aktiviert ist. </span><span class="sxs-lookup"><span data-stu-id="67e47-187">Port 7022 is accessible through the firewall if Windows Firewall is enabled in the witness SQL Server AB14-lct.los_a.lsipt.local\rtc.</span></span>

   - <span data-ttu-id="67e47-188">Ausführen des SQL Server auf allen primären und SQL-Spiegelserver Konten haben Lese-/Schreibberechtigung für die Dateifreigabe \\E04 OCS\csdatabackup</span><span class="sxs-lookup"><span data-stu-id="67e47-188">Accounts running the SQL Servers on all primary and mirror SQL servers have read/write permission to the file share \\E04-OCS\csdatabackup</span></span>

   - <span data-ttu-id="67e47-p119">Stellen Sie sicher, dass der Windows-Verwaltungsinstrumentationsanbieter (Windows Management Instrumentation, WMI) auf allen diesen Servern ausgeführt wird. Das Cmdlet verwendet diesen Anbieter, um die Kontoinformationen für die SQL Server-Dienste zu ermitteln, die auf allen primären, Spiegel- und Zeugenservern ausgeführt werden. </span><span class="sxs-lookup"><span data-stu-id="67e47-p119">Verify that the Windows Management Instrumentation (WMI) provider is running on all these servers. The cmdlet uses this provider to find the account information for SQL Server services running on all primary, mirror and witness servers.</span></span>

   - <span data-ttu-id="67e47-191">Stellen Sie sicher, dass das Konto, unter dem dieses Cmdlet ausgeführt wird, für alle Spiegelserver über die Berechtigung zum Erstellen von Ordnern für die Daten- und Protokolldateien verfügt. </span><span class="sxs-lookup"><span data-stu-id="67e47-191">Verify that the account running this cmdlet has permission to create the folders for the data and log files for all the mirror servers.</span></span>

   - <span data-ttu-id="67e47-p120">Beachten Sie, dass das Benutzerkonto, unter dem die SQL-Instanz ausgeführt wird, über die Lese-/Schreibberechtigung für die Dateifreigabe verfügt. Wenn sich die Dateifreigabe auf einem anderen Server befindet und die SQL-Instanz unter einem lokalen Systemkonto ausgeführt wird, müssen Sie dem Server, auf dem die SQL-Instanz gehostet wird, Dateifreigabeberechtigungen erteilen.</span><span class="sxs-lookup"><span data-stu-id="67e47-p120">Note that the user account that the SQL instance uses to run must have read/write permission to the file share. If the file share is on a different server, and the SQL instance runs a local system account, you must grant file share permissions to the server that hosts the SQL instance.</span></span>

3. <span data-ttu-id="67e47-194">Geben Sie „A“ ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="67e47-194">Type A and press ENTER.</span></span>

    <span data-ttu-id="67e47-195">Die Spiegelung wird konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="67e47-195">The mirroring will be configured.</span></span>

    <span data-ttu-id="67e47-196">**Install-csmirrordatabase anfügen** Spiegel installiert und konfiguriert die Spiegelung für alle Datenbanken, die auf dem primären SQL-Speicher vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="67e47-196">**Install-CsMirrorDatabase** installs the mirror and configures mirroring for all the databases that are present on the primary SQL store.</span></span> <span data-ttu-id="67e47-197">Wenn Sie nur bestimmte Datenbanken für die Spiegelung konfigurieren möchten, können Sie die Option "databasetype"-, oder wenn Sie für alle Datenbanken mit Ausnahme von ein paar Spiegelung konfigurieren möchten, können Sie die Option - ExcludeDatabaseList zusammen mit einer durch Trennzeichen getrennte Liste der Datenbank verwenden Namen, ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="67e47-197">If you want to configure mirroring for only specific databases, you can use the -DatabaseType option, or if you want to configure mirroring for all databases except for a few, you can use the -ExcludeDatabaseList option, along with a comma-separated list of database names to exclude.</span></span>

    <span data-ttu-id="67e47-198">Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden alle Datenbanken außer „rtcab“ und „rtcxds“ gespiegelt.</span><span class="sxs-lookup"><span data-stu-id="67e47-198">For example, if you add the following option to **Install-CsMirrorDatabase**, all databases except rtcab and rtcxds will be mirrored.</span></span>

    `-ExcludeDatabaseList rtcab,rtcxds`

   <span data-ttu-id="67e47-199">Wenn Sie beispielsweise die folgende Option an **Install-CsMirrorDatabase** anfügen, werden nur die Datenbanken „rtcab“, „rtcshared“ und „rtcxds“ gespiegelt.</span><span class="sxs-lookup"><span data-stu-id="67e47-199">For example, if you add the following option to **Install-CsMirrorDatabase**, only the rtcab, rtcshared, and rtcxds databases will be mirrored.</span></span>

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a><span data-ttu-id="67e47-200">Entfernen oder Ändern der SQL-Spiegelung</span><span class="sxs-lookup"><span data-stu-id="67e47-200">Removing or Changing SQL Mirroring</span></span>

<span data-ttu-id="67e47-p122">Wenn Sie die SQL-Spiegelung eines Pools im Topologie-Generator entfernen möchten, müssen Sie zuerst mithilfe eines Cmdlets den Spiegel in SQL Server entfernen. Anschließend können Sie mithilfe des Topologie-Generators den Spiegel aus der Topologie entfernen. Verwenden Sie das folgende Cmdlet, um den Spiegel in SQL Server zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="67e47-p122">To remove the SQL mirroring of a pool in Topology Builder, you must first use a cmdlet to remove the mirror in SQL Server. You can then use Topology Builder to remove the mirror from the topology. To remove the mirror in SQL Server, use the following cmdlet:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

<span data-ttu-id="67e47-204">Geben Sie beispielsweise Folgendes ein, um die Spiegelung zu entfernen und die Datenbanken für die Benutzerdatenbanken zu verwerfen:</span><span class="sxs-lookup"><span data-stu-id="67e47-204">For example, to remove mirroring and drop the databases for the User databases, type the following:</span></span>

```
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

<span data-ttu-id="67e47-205">Die `-DropExistingDatabasesOnMirror` Option bewirkt, dass die betreffenden Datenbanken aus dem Spiegel gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="67e47-205">The  `-DropExistingDatabasesOnMirror` option causes the affected databases to be deleted from the mirror.</span></span>

<span data-ttu-id="67e47-206">Führen Sie anschließend die folgenden Schritte aus, um den Spiegel aus der Topologie zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="67e47-206">Then, to remove the mirror from the topology, do the following:</span></span>

1. <span data-ttu-id="67e47-207">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="67e47-207">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="67e47-208">Deaktivieren Sie **SQL-Speicherspiegelung aktivieren**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e47-208">Uncheck **Enable SQL Store Mirroring** and click **OK**.</span></span>

3. <span data-ttu-id="67e47-209">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="67e47-209">Publish the topology.</span></span>

## <a name="removing-a-mirroring-witness"></a><span data-ttu-id="67e47-210">Entfernen eines Spiegelungszeugen</span><span class="sxs-lookup"><span data-stu-id="67e47-210">Removing a Mirroring Witness</span></span>

<span data-ttu-id="67e47-211">Verwenden Sie dieses Verfahren, wenn Sie benötigen, um den Zeugen aus einem Back End-Server Spiegelungskonfiguration zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="67e47-211">Use this procedure if you need to remove the witness from a Back End Server mirroring configuration.</span></span>

1. <span data-ttu-id="67e47-212">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="67e47-212">In Topology Builder, right-click the pool and click **Edit Properties**.</span></span>

2. <span data-ttu-id="67e47-213">Deaktivieren Sie **Automatisches Failover mithilfe des SQL Server-Spiegelungszeugen aktivieren**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="67e47-213">Uncheck **Use SQL Server mirroring witness to enable automatic failover** and click **OK**.</span></span>

3. <span data-ttu-id="67e47-214">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="67e47-214">Publish the topology.</span></span>

    <span data-ttu-id="67e47-215">Nach der Veröffentlichung der Topologie, Topologie-Generator sehen Sie eine Nachricht, die Folgendes enthält,</span><span class="sxs-lookup"><span data-stu-id="67e47-215">After publishing the topology, Topology Builder you will see a message that includes the following</span></span>

   ```
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    <span data-ttu-id="67e47-216">Führen Sie diesen Schritt nicht jedoch, und geben Sie keine `Uninstall-CsMirrorDatabase` wie, die die gesamte Spiegelungskonfiguration würde.</span><span class="sxs-lookup"><span data-stu-id="67e47-216">However, do not follow that step, and do not type  `Uninstall-CsMirrorDatabase` as that would uninstall the entire mirroring configuration.</span></span>

4. <span data-ttu-id="67e47-217">Wenn Sie lediglich den Zeugen aus der SQL Server-Konfiguration entfernen möchten, befolgen Sie die Anweisungen [Entfernen des Zeugen aus einer Datenbankspiegelung Sitzung (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span><span class="sxs-lookup"><span data-stu-id="67e47-217">To remove just the witness from the SQL Server configuration, follow the instructions in [Remove the Witness from a Database Mirroring Session (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=268456).</span></span>


