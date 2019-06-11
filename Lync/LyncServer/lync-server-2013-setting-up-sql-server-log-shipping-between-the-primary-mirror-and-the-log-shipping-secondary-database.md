---
title: 'Lync Server 2013: Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48184119
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3758e654826de42f6bf6bed8ead29ce03adb6ca5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database-in-lync-server-2013"></a><span data-ttu-id="62df2-102">Einrichten des SQL Server-Protokollversands zwischen der primären Spiegeldatenbank und der sekundären Datenbank des Protokollversands in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62df2-102">Setting up SQL Server Log Shipping between the primary mirror and the Log Shipping secondary database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62df2-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="62df2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="62df2-104">Führen Sie die folgenden Schritte aus, damit der Protokollversand fortgesetzt wird, wenn die primäre Datenbank für beständige Chats auf die Spiegeldatenbank übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="62df2-104">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>

1.  <span data-ttu-id="62df2-105">Manuelles Failover der primären persistent-Chat-Datenbank auf die Spiegelung.</span><span class="sxs-lookup"><span data-stu-id="62df2-105">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="62df2-106">Dies erfolgt mithilfe der lync Server-Verwaltungsshell und des **Invoke-CsDatabaseFailover-** Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="62df2-106">This is done by using the Lync Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="62df2-107">Ausführliche Informationen finden Sie unter "Verwenden von Cmdlets für die lync Server-Verwaltungsshell" unter [Bereitstellen der SQL-Spiegelung für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="62df2-107">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

2.  <span data-ttu-id="62df2-108">Stellen Sie mithilfe von SQL Server Management Studio eine Verbindung mit der primären persistent Chat Server-Spiegelungs Instanz her.</span><span class="sxs-lookup"><span data-stu-id="62df2-108">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>

3.  <span data-ttu-id="62df2-109">Stellen Sie sicher, dass der SQL Server-Agent ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="62df2-109">Be sure that the SQL Server Agent is running.</span></span>

4.  <span data-ttu-id="62df2-110">Klicken Sie mit der rechten Maustaste auf die mgc-Datenbank und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="62df2-110">Right-click the mgc database, and then click **Properties**.</span></span>

5.  <span data-ttu-id="62df2-111">Klicken Sie unter **Seite auswählen** auf **Transaktionsprotokollversand**.</span><span class="sxs-lookup"><span data-stu-id="62df2-111">Under **Select a page**, click **Transaction Log Shipping**.</span></span>

6.  <span data-ttu-id="62df2-112">Aktivieren Sie das Kontrollkästchen **Diese Datenbank als primäre Datenbank in einer Protokollversandkonfiguration aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="62df2-112">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>

7.  <span data-ttu-id="62df2-113">Klicken Sie unter **Transaktionsprotokollsicherungen** auf **Sicherungseinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="62df2-113">Under **Transaction log backups**, click **Backup Settings**.</span></span>

8.  <span data-ttu-id="62df2-114">Geben Sie im Feld **Netzwerkpfad zum Sicherungsordner** den Netzwerkpfad zu der Freigabe ein, die Sie für den Transaktionsprotokoll-Sicherungsordner erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="62df2-114">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>

9.  <span data-ttu-id="62df2-p102">Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Sicherungsordner im Feld **Wenn sich der Sicherungsordner auf dem primären Server befindet, geben Sie den lokalen Pfad zum Ordner ein** ein. (Wenn sich der Sicherungsordner nicht auf dem primären Server befindet, können Sie dieses Feld leer lassen.)</span><span class="sxs-lookup"><span data-stu-id="62df2-p102">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="62df2-117">Wenn das SQL Server-Dienstkonto auf dem primären Server unter dem lokalen Systemkonto ausgeführt wird, müssen Sie den Sicherungsordner auf dem primären Server erstellen und einen lokalen Pfad zu diesem Ordner angeben.</span><span class="sxs-lookup"><span data-stu-id="62df2-117">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span>

    
    </div>

10. <span data-ttu-id="62df2-118">Konfigurieren Sie den Parameter **Dateien löschen, die älter sind als** und den Parameter **Warnen, wenn keine Sicherung erfolgt in**.</span><span class="sxs-lookup"><span data-stu-id="62df2-118">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>

11. <span data-ttu-id="62df2-119">Schauen Sie sich den Sicherungszeitplan im Feld **Zeitplan** unter **Sicherungsauftrag** an.</span><span class="sxs-lookup"><span data-stu-id="62df2-119">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="62df2-120">Wenn Sie den Zeitplan für Ihre Installation anpassen möchten, klicken Sie auf **Planen**, und passen Sie den Zeitplan des SQL Server-Agents nach Bedarf an.</span><span class="sxs-lookup"><span data-stu-id="62df2-120">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="62df2-121">Verwenden Sie die gleichen Einstellungen, die Sie auch für die primäre Datenbank verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="62df2-121">Use the same settings that you used for the primary database.</span></span>

    
    </div>

12. <span data-ttu-id="62df2-122">Wählen Sie unter **Komprimierung** den Eintrag **Standardservereinstellung verwenden** aus und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62df2-122">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>

13. <span data-ttu-id="62df2-123">Klicken Sie unter **Sekundäre Serverinstanzen und Datenbanken** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="62df2-123">Under **Secondary server instances and databases**, click **Add**.</span></span>

14. <span data-ttu-id="62df2-124">Klicken Sie auf **Verbinden** und stellen Sie eine Verbindung mit der Instanz von SQL Server her, die Sie als sekundären Server konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="62df2-124">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>

15. <span data-ttu-id="62df2-125">Wählen Sie im Feld **Sekundäre Datenbank** die Datenbank **mgc** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="62df2-125">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>

16. <span data-ttu-id="62df2-126">Wählen Sie auf der Registerkarte **Sekundäre Datenbank initialisieren** die Option **Nein, die sekundäre Datenbank ist initialisiert** aus.</span><span class="sxs-lookup"><span data-stu-id="62df2-126">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>

17. <span data-ttu-id="62df2-p104">Geben Sie auf der Registerkarte **Dateien kopieren** unter **Zielordner für kopierte Dateien** den Pfad des Ordners ein, in den die Transaktionsprotokollsicherungen kopiert werden sollen, und klicken Sie auf **OK**. Dieser Ordner befindet sich in der Regel auf dem sekundären Server.</span><span class="sxs-lookup"><span data-stu-id="62df2-p104">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>

18. <span data-ttu-id="62df2-129">Öffnen Sie die Dropdownliste **Skript für Konfiguration erstellen** und wählen Sie **Skript für Konfiguration in Fenster 'Neue Abfrage' schreiben** aus.</span><span class="sxs-lookup"><span data-stu-id="62df2-129">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>

19. <span data-ttu-id="62df2-130">Klicken Sie im neuen Abfragefenster unter **Datenbankeigenschaften** auf **OK**, um mit der Konfiguration zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="62df2-130">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>

20. <span data-ttu-id="62df2-131">Wählen Sie die erste Hälfte der Abfrage aus, und führen Sie Sie aus (siehe Schritt 18) bis zur \* \* \* \* \* \* Zeile:--Ende: Skript, das \* \* \* \* \* \*bei primär ausgeführt werden soll:.</span><span class="sxs-lookup"><span data-stu-id="62df2-131">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="62df2-132">Das manuelle Ausführen dieses Skripts ist erforderlich, da SQL Server Management Studio mehrere primäre Datenbanken in einer SQL Server-Protokollversandkonfiguration nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="62df2-132">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span>

    
    </div>

21. <span data-ttu-id="62df2-133">Wählen Sie **Abbrechen** aus, um das Konfigurationsfenster für den Protokolldateiversand zu schließen und ein funktionierendes Setup zu erstellen, das den Protokolldateiversand für die primäre und für die gespiegelte Datenbank (bei einem Failover) ordnungsgemäß implementiert. </span><span class="sxs-lookup"><span data-stu-id="62df2-133">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>

22. <span data-ttu-id="62df2-134">Manuelles Zurücksetzen der primären beständigen Chat Datenbank auf das primäre.</span><span class="sxs-lookup"><span data-stu-id="62df2-134">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="62df2-135">Dies erfolgt mithilfe der lync Server-Verwaltungsshell und des Cmdlets **Invoke-CsDatabaseFailover** .</span><span class="sxs-lookup"><span data-stu-id="62df2-135">This is done by using the Lync Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span> <span data-ttu-id="62df2-136">Ausführliche Informationen finden Sie unter "Verwenden von Cmdlets für die lync Server-Verwaltungsshell" unter [Bereitstellen der SQL-Spiegelung für den Back-End-Server mit einer höheren Verfügbarkeit in lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="62df2-136">For details, see "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="62df2-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62df2-137">See Also</span></span>


[<span data-ttu-id="62df2-138">Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62df2-138">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[<span data-ttu-id="62df2-139">Bereitstellen der SQL-Spiegelung für eine hohe Verfügbarkeit von Back-End-Servern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="62df2-139">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

