---
title: 'Lync Server 2013: Ändern von Archivierungsdatenbank Optionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing Archiving database options
ms:assetid: 3775f09d-65b0-48bc-8a4d-d97bd0c3423c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204814(v=OCS.15)
ms:contentKeyID: 48183879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a820ca891ceb8196f8b4e0d2e023799f36e9e9ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-archiving-database-options-in-lync-server-2013"></a><span data-ttu-id="25ba9-102">Ändern von Archivierungsdatenbank Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25ba9-102">Changing Archiving database options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25ba9-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="25ba9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="25ba9-104">Wenn Sie die Archivierung mithilfe SQL Server Speichers für Archivierungsspeicher für alle Ihre Benutzer bereitstellen, können Sie die folgenden Änderungen an der Datenbankspeicherung vornehmen:</span><span class="sxs-lookup"><span data-stu-id="25ba9-104">If you deploy Archiving using SQL Server storage for archiving storage for any of your users, you can make the following database storage changes:</span></span>

  - <span data-ttu-id="25ba9-105">Verwenden Sie für die Archivierungs Speicherung eine andere SQL Server Datenbank.</span><span class="sxs-lookup"><span data-stu-id="25ba9-105">Use a different SQL Server database for archiving storage.</span></span> <span data-ttu-id="25ba9-106">Dies umfasst die primäre Archivierungsdatenbank und alle Datenbanken, die Sie für die SQL Server Spiegelung verwenden.</span><span class="sxs-lookup"><span data-stu-id="25ba9-106">This includes the primary Archiving database and any database you use for SQL Server mirroring.</span></span>

  - <span data-ttu-id="25ba9-107">Wechseln Sie zu Microsoft Exchange Integration, um Archivierungsdaten und-Dateien auf Exchange 2013 Servern zu speichern.</span><span class="sxs-lookup"><span data-stu-id="25ba9-107">Switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers.</span></span> <span data-ttu-id="25ba9-108">Wenn alle Benutzer auf Ihren Exchange 2013 Servern verwaltet werden und Sie Microsoft Exchange Speicher für alle Benutzer in Ihrer Bereitstellung verwenden möchten, sollten Sie die SQL Server Store-Datenbanken aus Ihrer Topologie entfernen.</span><span class="sxs-lookup"><span data-stu-id="25ba9-108">If all your users are homed on your Exchange 2013 servers and you want to use Microsoft Exchange storage for all users in your deployment, you should remove the SQL Server store databases from your topology.</span></span>

<span data-ttu-id="25ba9-109">Um eine dieser Änderungen vornehmen zu können, müssen Sie den Topologie-Generator ausführen, die Änderungen vornehmen und die Topologie dann erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="25ba9-109">To make either of these changes, you must run Topology Builder, make the changes, and then publish the topology again.</span></span> <span data-ttu-id="25ba9-110">Sie können den Topologie-Generator verwenden, um dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="25ba9-110">You can use Topology Builder to do this.</span></span> <span data-ttu-id="25ba9-111">Geben Sie keine **Archivierungs SQL Server speichern** oder **Aktivieren Sie SQL Server Speicher Spiegelungs** Informationen, es sei denn, Sie verfügen über lync-Benutzer, die nicht auf Exchange 2013 Servern verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="25ba9-111">Do not specify **Archiving SQL Server store** or **Enable SQL Server store mirroring** information, unless you have Lync users who are not homed on Exchange 2013 servers.</span></span>

<div>

## <a name="to-change-your-archiving-database-option"></a><span data-ttu-id="25ba9-112">So ändern Sie die Archivierungsdatenbankoption</span><span class="sxs-lookup"><span data-stu-id="25ba9-112">To change your archiving database option</span></span>

1.  <span data-ttu-id="25ba9-113">Melden Sie sich auf einem Computer, auf dem lync Server 2013 läuft oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit gleichwertigen Benutzerrechten).</span><span class="sxs-lookup"><span data-stu-id="25ba9-113">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25ba9-114">Sie können eine Topologie mithilfe eines Kontos definieren, das Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die zum Hinzufügen einer Komponente zur Topologie erforderlich ist. Sie müssen ein Konto verwenden, das Mitglied der Gruppe "Domänen- <STRONG>Admins</STRONG> " und der Gruppe " <STRONG>RTCUniversalServerAdmins</STRONG> " ist und das über die Berechtigung "Vollzugriff" (Lese-, Schreib-und Änderungsberechtigungen) für die Dateifreigabe verfügt, die Sie für den lync Server 2013 Dateispeicher verwenden (damit der Topologie-Generator die erforderlichen Discretionary Access Control Lists konfigurieren kann ( DACLs) oder ein Konto mit gleichwertigen Rechten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-114">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a component to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control lists (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="25ba9-115">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="25ba9-115">Start Topology Builder.</span></span>

3.  <span data-ttu-id="25ba9-116">Navigieren Sie in der Konsolenstruktur zum Front-End-Pool, in dem Sie die Archivierung bereitgestellt haben, und klicken Sie dann auf den Namen des Front-End-Pools, in dem Sie die Datenbankoptionen ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-116">In the console tree, navigate to the Front End pool in which you deployed Archiving, and then click the name of the Front End pool where you want to change the database options.</span></span>

4.  <span data-ttu-id="25ba9-117">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="25ba9-117">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="25ba9-118">Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="25ba9-118">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="25ba9-119">Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.</span><span class="sxs-lookup"><span data-stu-id="25ba9-119">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="25ba9-120">Führen Sie im Dialogfeld **Archivierung** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="25ba9-120">In **Archiving**, do the following:</span></span>
    
      - <span data-ttu-id="25ba9-121">Wenn Sie zu einem anderen SQL Server-Speicher wechseln möchten, gehen Sie unter **SQL Server-Speicher für Archivierung** im Dropdown-Listenfeld wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="25ba9-121">To change to a different existing SQL Server store, under **Archiving SQL Server store**, in the drop-down list box, do the following:</span></span>
        
          - <span data-ttu-id="25ba9-122">Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-122">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
        
          - <span data-ttu-id="25ba9-123">Zum Angeben eines neuen SQL Server-Speichers klicken Sie auf **Neu** und gehen dann im Dialogfeld **Neuen SQL Server-Speicher definieren** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="25ba9-123">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server store** dialog box, do the following:</span></span>
            
              - <span data-ttu-id="25ba9-124">Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-124">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span>
            
              - <span data-ttu-id="25ba9-125">Um einen neuen SQL Server Speicher anzugeben, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="25ba9-125">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
                
                  - <span data-ttu-id="25ba9-126">Geben Sie in **SQL Server FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-126">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
                
                  - <span data-ttu-id="25ba9-127">Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-127">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
                
                  - <span data-ttu-id="25ba9-128">Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="25ba9-128">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="25ba9-129">Wenn Sie einen SQL Server-Speicher zur Spiegelung hinzufügen oder für die SQL Server-Speicherspiegelung zu einem anderen vorhandenen SQL Server-Speicher wechseln möchten, wählen Sie **SQL Server-Speicherspiegelung aktivieren** aus, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="25ba9-129">To add SQL Server store for mirroring or change to a different existing SQL Server store for SQL Server store mirroring, select **Enable SQL Server store mirroring**, and then do the following:</span></span>
        
          - <span data-ttu-id="25ba9-130">Wenn Sie einen vorhandenen SQL Server Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **Archivierung SQL Server Speicher Spiegel** auf den Namen des SQL Server Speichers, den Sie für die Spiegelung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-130">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
        
          - <span data-ttu-id="25ba9-131">Wenn Sie einen neuen SQL Server Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="25ba9-131">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
            
            1.  <span data-ttu-id="25ba9-132">Geben Sie in **SQL Server FQDN**den FQDN des SQL Server an, für den Sie den neuen SQL Server Speicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-132">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
            
            2.  <span data-ttu-id="25ba9-133">Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-133">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
            
            3.  <span data-ttu-id="25ba9-134">Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="25ba9-134">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
        
          - <span data-ttu-id="25ba9-135">Wenn Sie SQL Server Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte separate SQL Server Instanz, die die Integrität des primären SQL Server Servers und der Spiegelungs Instanzen erkennen kann) hinzufügen oder ändern möchten, aktivieren Sie das Kontrollkästchen **verwenden Sie SQL Server Spiegelungs Zeugen zum Aktivieren des automatischen Failovers** , und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="25ba9-135">If you enable SQL Server mirroring and want to add or change a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
            
            1.  <span data-ttu-id="25ba9-136">Geben Sie in **SQL Server FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-136">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
            
            2.  <span data-ttu-id="25ba9-137">Klicken Sie entweder auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz**, und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="25ba9-137">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
            
            3.  <span data-ttu-id="25ba9-138">Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in einer Spiegelungs** Beziehung, und geben Sie dann unter **Spiegel Portnummer**die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="25ba9-138">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="25ba9-139">Wenn Sie zur Microsoft Exchange Integration wechseln möchten, um Archivierungsdaten und-Dateien auf Exchange 2013 Servern zu speichern (wenn alle Benutzer in Ihrer Bereitstellung auf Ihren Exchange 2013 Servern verwaltet werden), löschen Sie alle Informationen für Archivierungsdatenbanken.</span><span class="sxs-lookup"><span data-stu-id="25ba9-139">To switch to Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers (if all users in your deployment are homed on your Exchange 2013 servers), delete all information for Archiving databases.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="25ba9-140">Wenn Sie lync-Benutzer haben, die nicht auf Exchange 2013 Servern verwaltet werden, löschen Sie nicht die SQL Server Informationsspeicher.</span><span class="sxs-lookup"><span data-stu-id="25ba9-140">If you have any Lync users who are not homed on Exchange 2013 servers, do not delete the SQL Server store information.</span></span>

    
    </div>

8.  <span data-ttu-id="25ba9-141">Klicken Sie zum Speichern der Konfiguration auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ba9-141">To save the configuration, click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="25ba9-142">Die im Topologie-Generator vorgenommenen Änderungen werden erst wirksam, wenn Sie die neue Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="25ba9-142">The changes you make in Topology Builder do not take effect until you publish the new topology.</span></span> <span data-ttu-id="25ba9-143">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Veröffentlichen der aktualisierten Topologie zum Hinzufügen von Archivierungsdatenbanken in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="25ba9-143">For details, see <A href="lync-server-2013-publishing-the-updated-topology-to-add-archiving-databases.md">Publishing the updated topology to add Archiving databases in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

