---
title: 'Lync Server 2013: Zuordnen eines überwachungsspeichers zu einem Front-End-Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfdff8863c0e629c99d0e64aca0b7f84dcb63a43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="ddc18-102">Zuordnen eines überwachungsspeichers zu einem Front-End-Pool in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ddc18-102">Associating a monitoring store with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ddc18-103">_**Letztes Änderungsstand des Themas:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="ddc18-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="ddc18-104">In Microsoft lync Server 2013 Überwachungsdaten nur in Front-End-Pools gesammelt werden können, die einem Überwachungsspeicher zugeordnet wurden, wird in der Regel eine Aufgabe definiert, die Sie im Topologie-Generator ein Front-End-Pool definieren.</span><span class="sxs-lookup"><span data-stu-id="ddc18-104">In Microsoft Lync Server 2013 monitoring data can only be collected on Front End pools that have been associated with a monitoring store, a task typically carried out you define a Front End pool in Topology Builder.</span></span> <span data-ttu-id="ddc18-105">Wenn Sie einen Überwachungsspeicher einer neuen Front-End-Pool zuordnen möchten, stellen Sie sicher, dass Sie auf der Seite **Features auswählen** des Assistenten zum Definieren eines neuen Front-End-Pools die Option **Überwachung (Aufzeichnung von Kommunikationsdatensätzen und Protokollierung der Metriken für die Qualität der Erfahrung)** auswählen.</span><span class="sxs-lookup"><span data-stu-id="ddc18-105">To associate a monitoring store with a new Front End pool, make sure that you select the option **Monitoring (call detail recording and logging of quality of experience metrics)** on the **Select Features** page of the Define New Front End Pool wizard.</span></span> <span data-ttu-id="ddc18-106">Beachten Sie, dass Sie bei Auswahl dieser Option auch einen SQL-Speicher angeben müssen, um den Assistenten abzuschließen. Dieser Speicher muss jedoch nicht zum Zeitpunkt der Ausführung des Assistenten vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ddc18-106">Note that, if you select this option, you must also specify a SQL store in order to complete the wizard; however, this store does not have to exist at the time you run the wizard.</span></span> <span data-ttu-id="ddc18-107">Das bedeutet, dass Sie zuerst einen Pool einem Überwachungsspeicher zuordnen können, dann später Setup und diesen Speicher konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ddc18-107">That means that you can first associate a pool with a monitoring store, then later setup and configure that store.</span></span>

<span data-ttu-id="ddc18-108">Alternativ können Sie einem vorhandenen Front-End-Pool anhand des folgenden Verfahrens einen neuen oder anderen Überwachungsspeicher zuordnen:</span><span class="sxs-lookup"><span data-stu-id="ddc18-108">Alternatively, you can associate an existing Front End pool with a new or different monitoring store by completing the following procedure:</span></span>

1.  <span data-ttu-id="ddc18-109">Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-109">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ddc18-110">Wählen Sie im Dialogfeld **Topologie-Generator** die Option **Topologie aus vorhandener Bereitstellung herunterladen** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-110">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="ddc18-p102">Geben Sie im Dialogfeld **Speichern unter** einen Dateinamen für Ihre aktuelle Topologie ein, und klicken Sie dann auf **Speichern**. Die gespeicherte Topologie kann später abgerufen und erneut veröffentlicht werden, falls es Probleme mit der neuen Topologie gibt.</span><span class="sxs-lookup"><span data-stu-id="ddc18-p102">In the **Save As** dialog box, enter a file name for your current topology and then click **Save**. The saved topology can later be retrieved and re-published in case there are problems with the new topology.</span></span>

4.  <span data-ttu-id="ddc18-113">Erweitern Sie im Topologie-Generator **lync Server 2013**, erweitern Sie den Namen des Standorts, der den Front-End-Pool enthält, und klicken Sie dann auf **Enterprise Edition-Front-End-Pools**erweitern.</span><span class="sxs-lookup"><span data-stu-id="ddc18-113">In Topology Builder, expand **Lync Server 2013**, expand the name of the site containing the Front End pool, then click expand **Enterprise Edition Front End pools**.</span></span>

5.  <span data-ttu-id="ddc18-114">Klicken Sie mit der rechten Maustaste auf den Namen des Pools, dem der Überwachungsspeicher zugeordnet werden soll, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-114">Right-click the name of the pool to be associated with the monitoring store and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="ddc18-p103">Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** auf der Registerkarte **Allgemein** die Option **Überwachung (CDR- und QoE-Metriken)** aus, und wählen Sie dann in der Dropdownliste **SQL Server-Speicher für Überwachung** eine vorhandene SQL Server-Datenbank aus. (Oder klicken Sie auf **Neu**, um dem Pool einen neuen Datenbankspeicher zuzuordnen.) Wenn Sie einen neuen Datenbankspeicher verwenden möchten, geben Sie im Dialogfeld **Neuen SQL-Speicher definieren** den vollqualifizierten Domänenname des SQL Server-Computers im Feld **SQL Server-FQDN** ein. Wenn Sie die SQL Server-Standardinstanz für diesen Speicher verwenden möchten, wählen Sie **Standardinstanz** aus. Andernfalls wählen Sie **Benannte Instanz** aus und geben den Namen der Instanz im Feld **Benannte Instanz** ein.</span><span class="sxs-lookup"><span data-stu-id="ddc18-p103">In the **Edit Properties** dialog box, on the **General** tab, select the option **Monitoring (CDR and QoE metrics)** and then select an existing SQL Server database from the **Monitoring SQL Server store** dropdown list. (Or, click **New** to associate the pool with a new database store.) If you choose to use a new database store then, in the **Define New SQL Store** dialog box, enter the fully qualified domain name of the SQL Server computer in the **Sql Server FQDN** box. If you want to use the default SQL Server instance for that store select **Default Instance**; otherwise select **Named Instance** and enter the instance name in the **Named Instance** box.</span></span>
    
    <span data-ttu-id="ddc18-p104">Im Dialogfeld **Eigenschaften bearbeiten** haben Sie auch die Möglichkeit, einen SQL-Spiegel für Ihre Überwachungsdatenbank zu erstellen (mit einem SQL-Spiegel können Sie zwei Kopien Ihrer Überwachungsdatenbank verwalten, wobei eine Kopie auf dem Überwachungsspeichercomputer und die andere Kopie auf dem SQL-Spiegelcomputer verwaltet wird). Zum Aktivieren der Spiegelung wählen Sie **Diese SQL-Instanz befindet sich in einer Spiegelungsbeziehung** aus und geben die Portnummer für den Spiegelserver im Feld **Spiegelportnummer** ein.</span><span class="sxs-lookup"><span data-stu-id="ddc18-p104">The **Edit Properties** dialog box also gives you the option of creating a SQL mirror for your monitoring database (a SQL mirror enables you to maintain two copies of your monitoring database, one copy stored on the monitoring store computer and the other on the SQL mirror computer). To enable mirroring, select T**his SQL instance is in mirroring relation** and enter the port number for the mirror server in the **Mirroring port number** box.</span></span>

7.  <span data-ttu-id="ddc18-120">Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-120">In the **Edit Properties** dialog box, click **OK**.</span></span>

<span data-ttu-id="ddc18-p105">Nachdem Sie den Überwachungsspeicher einem Front-End-Pool zugeordnet haben, müssen Sie die neue Topologie veröffentlichen, damit die Änderungen wirksam werden. Zum Veröffentlichen der neuen Topologie führen Sie die folgenden Schritte im Topologie-Generator aus:</span><span class="sxs-lookup"><span data-stu-id="ddc18-p105">After associating the monitoring store with a Front End pool you must publish the new topology before the changes take effect. To publish your new topology, complete the following steps in Topology Builder:</span></span>

1.  <span data-ttu-id="ddc18-123">Klicken Sie auf **Aktion**, zeigen Sie auf **Topologie**, und klicken Sie dann auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-123">Click **Action**, point to **Topology**, and then click **Publish**.</span></span>

2.  <span data-ttu-id="ddc18-124">Klicken Sie im Assistenten zum Veröffentlichen der Topologie auf der Seite **Topologie veröffentlichen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-124">In the Publish Topology wizard, on the **Publish the topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="ddc18-125">Klicken Sie auf der Seite **Assistent für die Veröffentlichung abgeschlossen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-125">On the **Publishing wizard complete** page, click **Finish**.</span></span>

<span data-ttu-id="ddc18-126">Nachdem die Topologie veröffentlicht wurde, können Sie die Überwachungsdatenbank auf dem Computer installieren, auf dem der Überwachungsspeicher gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ddc18-126">After the topology has been published you can then install the monitoring database on the computer that will host the monitoring store.</span></span> <span data-ttu-id="ddc18-127">Die Überwachungsdatenbank kann mithilfe der lync Server-Verwaltungsshell und Windows PowerShell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ddc18-127">The monitoring database can be installed by using the Lync Server Management Shell and Windows PowerShell.</span></span> <span data-ttu-id="ddc18-128">Um die Datenbank lokal zu installieren (um die Datenbank auf demselben Computer zu installieren, auf dem Sie die lync Server-Verwaltungsshell ausführen), starten Sie die Verwaltungsshell auf dem entsprechenden Computer, geben Sie dann den folgenden Befehl ein, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="ddc18-128">To install the database locally (that is, to install the database on the same computer where you are running the Lync Server Management Shell), start the Management Shell on the appropriate computer, then type in the following command and press ENTER:</span></span>

    Install-CsDatabase -LocalDatabases

<span data-ttu-id="ddc18-129">Wenn Sie den obigen Befehl ausführen, liest install-CsDatabase die aktuelle lync Server-Topologie, ermittelt, welche Datenbanken auf dem lokalen Computer installiert werden müssen, und installiert und konfiguriert dann automatisch jede dieser Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ddc18-129">When you run the preceding command, Install-CsDatabase will read the current Lync Server topology, determine which databases need to be installed on the local computer, and then automatically install and configure each of those databases.</span></span>

<span data-ttu-id="ddc18-130">Zum Installieren der Datenbank auf einem Remotecomputer (also einem anderen Computer als dem Computer, auf dem die Verwaltungsshell läuft) müssen Sie mindestens zwei Parameter einschließen: den ConfiguredDatabases-Parameter und den sqlserverfqdn "nicht-Parameter.</span><span class="sxs-lookup"><span data-stu-id="ddc18-130">To install the database on a remote computer (that is, a computer other than the computer where the Management Shell is running) you must include at least two parameters: the ConfiguredDatabases parameter and the SqlServerFqdn parameter.</span></span> <span data-ttu-id="ddc18-131">Mit diesen Parametern wird das Cmdlet Install-CsDatabase dazu aufgefordert, die lync Server Topologie abzurufen und anschließend die erforderlichen Datenbanken auf dem durch den Parameter sqlserverfqdn "nicht angegebenen Computer zu installieren und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ddc18-131">These parameters tell the Install-CsDatabase cmdlet to retrieve the Lync Server topology and then install and configure the required databases on the computer specified by the SqlServerFqdn parameter.</span></span> <span data-ttu-id="ddc18-132">Der Parameter sqlserverfqdn "nicht muss einen Parameterwert verwenden, der den vollqualifizierten Domänennamen des Computers darstellt, auf dem die Datenbanken installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ddc18-132">The SqlServerFqdn parameter must use a parameter value representing the fully qualified domain name of the computer where the databases are to be installed.</span></span>

<span data-ttu-id="ddc18-133">Beispielsweise wird mit dem folgenden Befehl die Überwachungsdatenbank auf dem Computer atl-sql-001.litwareinc.com installiert:</span><span class="sxs-lookup"><span data-stu-id="ddc18-133">For example, this command installs the monitoring database on the computer atl-sql-001.litwareinc.com:</span></span>

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

<span data-ttu-id="ddc18-134">Alternativ können Sie die Überwachungsdatenbank installieren, indem Sie den lync Server-Bereitstellungs-Assistenten auf dem Computer ausführen, auf dem der Überwachungsspeicher gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ddc18-134">Alternatively, you can install the monitoring database by running the Lync Server Deployment Wizard on the computer that will host the monitoring store.</span></span> <span data-ttu-id="ddc18-135">Dazu melden Sie sich am entsprechenden Computer an und führen das folgende Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="ddc18-135">To do this, log on to the appropriate computer and complete the following procedure:</span></span>

1.  <span data-ttu-id="ddc18-136">Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Bereitstellungs-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-136">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="ddc18-137">Klicken Sie im Bereitstellungs-Assistenten auf **Lync Server-System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-137">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="ddc18-138">Klicken Sie auf der Seite **Bereitstellen** unter **Schritt  2: Lync Server-Komponenten einrichten oder entfernen** auf **Erneut ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-138">On the **Deploy** page, under **Step 2: Setup or Remove Lync Server Components**, click **Run Again**.</span></span>

4.  <span data-ttu-id="ddc18-139">Klicken Sie im Assistenten zum Einrichten von Lync Server-Komponenten auf der Seite **Lync Server-Komponenten einrichten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-139">In the Setup Lync Server components wizard, on the **Setup Lync Server components** page, click **Next**.</span></span>

5.  <span data-ttu-id="ddc18-140">Geben Sie auf der Seite **Pfad zu MSIs angeben** den Pfad zur Datei OCSCore. msi ein (eine Datei, die im lync Server Installationsmedium enthalten ist), und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-140">On the **Specify path to MSIs** page, type the path to the file Ocscore.msi (a file included with your Lync Server installation media) and then click **Next**.</span></span>

6.  <span data-ttu-id="ddc18-141">Klicken Sie auf der Seite **Befehle ausführen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ddc18-141">On the **Executing Commands** page, click **Finish**.</span></span>

<span data-ttu-id="ddc18-142">Um sicherzustellen, dass alle erforderlichen lync Server Dienste gestartet wurden, klicken Sie unter der Überschrift **Schritt 4: Starten von Diensten** auf der Seite **Bereitstellen** auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="ddc18-142">To ensure that all the required Lync Server services have started, click **Run** under the heading **Step 4: Start Services** on the **Deploy** page</span></span>

</div>

<span> </span>

</div>

</div>

</div>

