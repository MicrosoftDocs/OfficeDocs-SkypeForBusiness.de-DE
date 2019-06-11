---
title: 'Lync Server 2013: Hinzufügen von Archivierungsdatenbanken zur lync Server 2013-Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Adding Archiving databases to the Lync Server 2013 topology
ms:assetid: 089ab32f-1167-4bb8-a283-fdc6c9613072
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204654(v=OCS.15)
ms:contentKeyID: 48183338
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe77c57050d6d6c70d5818405fd657d5a8fd3f0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-archiving-databases-to-the-lync-server-2013-topology"></a><span data-ttu-id="228af-102">Hinzufügen von Archivierungsdatenbanken zur lync Server 2013-Topologie</span><span class="sxs-lookup"><span data-stu-id="228af-102">Adding Archiving databases to the Lync Server 2013 topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="228af-103">_**Letztes Änderungsdatum des Themas:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="228af-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="228af-104">Sie müssen die Archivierung in Ihre Topologie aufnehmen, bevor Sie Ihre Bereitstellung zur Unterstützung der Archivierung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="228af-104">You must incorporate archiving into your topology before you can configure your deployment to support archiving.</span></span> <span data-ttu-id="228af-105">Die Informationen in diesem Thema erläutern, wie Sie mithilfe des Topologie-Generators Ihrer vorhandenen Topologie Archivierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="228af-105">The information in this topic explains how to use Topology Builder to add archiving to your existing topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="228af-106">Wenn Sie die Microsoft Exchange-Integration zum Speichern von Archivierungsdaten und-Dateien auf Exchange 2013-Servern für alle Benutzer in Ihrer Bereitstellung verwenden möchten, geben Sie keinen <STRONG>Archivierungs-SQL Server-Speicher</STRONG> an, oder verwenden Sie die Spiegelungsinformationen des <STRONG>SQL Server</STRONG> -Speichers.</span><span class="sxs-lookup"><span data-stu-id="228af-106">If you want to use Microsoft Exchange integration to store archiving data and files on Exchange 2013 servers for all your users in your deployment, do not specify <STRONG>Archiving SQL Server store</STRONG> or <STRONG>Use SQL Server Store mirroring</STRONG> information.</span></span>



</div>

<div>

## <a name="to-add-archiving-database-support-to-your-topology"></a><span data-ttu-id="228af-107">So fügen Sie Ihrer Topologie Unterstützung für die Archivierungsdatenbank hinzu</span><span class="sxs-lookup"><span data-stu-id="228af-107">To add Archiving database support to your topology</span></span>

1.  <span data-ttu-id="228af-108">Melden Sie sich auf einem Computer, auf dem lync Server 2013 ausgeführt wird oder auf dem die lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.</span><span class="sxs-lookup"><span data-stu-id="228af-108">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on by using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="228af-109">Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die zum Hinzufügen eines Servers zur Topologie erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe der <STRONG>Domänenadministratoren</STRONG> und der RTCUniversalServer ist. <STRONG> Gruppe "Administratoren</STRONG> ", die über die Berechtigung "Vollzugriff" (also lesen, schreiben und ändern) für die Dateifreigabe verfügt, die Sie für den lync Server 2013-Dateispeicher verwenden (Dies bedeutet, dass der Topologie-Generator die erforderliche DACL (Discretionary Access Control List) konfigurieren kann. oder ein Konto mit entsprechenden Rechten.</span><span class="sxs-lookup"><span data-stu-id="228af-109">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="228af-110">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="228af-110">Start Topology Builder.</span></span>

3.  <span data-ttu-id="228af-111">Navigieren Sie in der Konsolenstruktur zu dem Front-End-Pool, in dem die Archivierung bereitgestellt werden soll, und klicken Sie dann auf den Namen des Front-End-Pools, in dem die Archivierung bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="228af-111">In the console tree, navigate to the Front End pool in which you want to deploy Archiving, and then click the name of the Front End pool where you want to deploy Archiving.</span></span>

4.  <span data-ttu-id="228af-112">Klicken Sie im Menü **Aktionen** auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="228af-112">In the **Action** menu, click **Edit Properties**.</span></span>

5.  <span data-ttu-id="228af-113">Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** auf **Allgemein**.</span><span class="sxs-lookup"><span data-stu-id="228af-113">In the **Edit Properties** dialog box, click **General**.</span></span>

6.  <span data-ttu-id="228af-114">Führen Sie einen Bildlauf nach unten zur **Archivierung** aus.</span><span class="sxs-lookup"><span data-stu-id="228af-114">Scroll down to **Archiving**.</span></span>

7.  <span data-ttu-id="228af-115">Aktivieren Sie das Kontrollkästchen **Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="228af-115">Select the **Archiving** check box.</span></span>

8.  <span data-ttu-id="228af-116">Führen Sie unter **SQL Server-Archivierungsspeicher** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="228af-116">Under **Archiving SQL Server store,** do one of the following:</span></span>
    
      - <span data-ttu-id="228af-117">Zum Verwenden eines vorhandenen SQL Server-Speichers klicken Sie im Dropdown-Listenfeld auf den Namen des SQL Server-Speichers, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-117">To use an existing SQL Server store, in the drop-down list box, click the name of the SQL Server store that you want to use.</span></span> <span data-ttu-id="228af-118">Wenn sich alle Benutzer auf Microsoft Exchange Server 2013 oder höher befinden, können Sie die lync-Kommunikation für alle Benutzer in Exchange archivieren.</span><span class="sxs-lookup"><span data-stu-id="228af-118">If all of your users are homed on Microsoft Exchange Server 2013 or above, you can archive Lync communications for all your users in Exchange.</span></span> <span data-ttu-id="228af-119">In diesem Fall müssen Sie den SQL Server-Archivierungsspeicher nicht konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="228af-119">In this case, you don’t need to configure SQL Server Archiving store.</span></span>
    
      - <span data-ttu-id="228af-120">Wenn Sie einen neuen SQL Server-Speicher angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="228af-120">To specify a new SQL Server store, click **New**, and then in the **Define New SQL Server Store** dialog box, do the following:</span></span>
        
          - <span data-ttu-id="228af-121">Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-121">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server store.</span></span>
        
          - <span data-ttu-id="228af-122">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-122">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named instance**, and then specify the instance you want to use.</span></span>
        
          - <span data-ttu-id="228af-123">Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in** der Spiegelungs Beziehung, und geben Sie dann in Spiegelungs- **Portnummer**die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="228af-123">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

9.  <span data-ttu-id="228af-124">Wenn Sie die SQL Server Store-Spiegelung verwenden möchten, wählen Sie **SQL Server Store-Spiegelung aktivieren**aus, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="228af-124">If you want to use SQL Server store mirroring, select **Enable SQL Server Store mirroring**, and then do the following:</span></span>
    
      - <span data-ttu-id="228af-125">Wenn Sie einen vorhandenen SQL Server-Speicher für die Spiegelung verwenden möchten, klicken Sie im Dropdown-Listenfeld **SQL Server Store Mirror-Archivierung** auf den Namen des SQL Server-Speichers, den Sie für die Spiegelung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-125">To use an existing SQL Server store for mirroring, in the **Archiving SQL Server store mirror** drop-down list box, click the name of the SQL Server store that you want to use for mirroring.</span></span>
    
      - <span data-ttu-id="228af-126">Wenn Sie einen neuen SQL Server-Speicher für die Spiegelung angeben möchten, klicken Sie auf **neu**, und führen Sie dann im Dialogfeld **neuen SQL Server-Speicher definieren** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="228af-126">To specify a new SQL Server store for mirroring, click **New**, and then in the **Define New SQL Server Store** dialog box, do one of the following:</span></span>
        
        1.  <span data-ttu-id="228af-127">Geben Sie im **SQL Server-FQDN**den FQDN des SQL Server an, auf dem Sie den neuen SQL Server-Speicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-127">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server store.</span></span>
        
        2.  <span data-ttu-id="228af-128">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-128">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use.</span></span>
        
        3.  <span data-ttu-id="228af-129">Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in** der Spiegelungs Beziehung, und geben Sie dann in Spiegelungs- **Portnummer**die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="228af-129">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>
    
      - <span data-ttu-id="228af-130">Wenn Sie die SQL Server-Spiegelung aktivieren und einen SQL Server-Spiegelungs Zeugen (eine dritte, separate SQL Server-Instanz, die den Zustand des primären SQL Server-Servers und der Spiegelungs Instanzen erkennen kann) einbeziehen möchten, wählen Sie den **SQL Server-Spiegelungs Zeugen verwenden aus, um ihn zu aktivieren. Kontrollkästchen Automatisches Failover** , und führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="228af-130">If you enable SQL Server mirroring and want to include a SQL Server mirroring witness (a third, separate SQL Server instance that can detect the health of the primary SQL Server server and mirror instances), select the **Use SQL Server mirroring witness to enable automatic failover** check box, and then do one of the following:</span></span>
        
        1.  <span data-ttu-id="228af-131">Geben Sie im **SQL Server-FQDN**den FQDN des Servers an, auf dem Sie den neuen SQL Server-Spiegelungs Zeugen erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-131">In **SQL Server FQDN**, specify the FQDN of the server on which you want to create the new SQL Server mirroring witness.</span></span>
        
        2.  <span data-ttu-id="228af-132">Klicken Sie auf **Standardinstanz**, um die Standardinstanz zu verwenden. Wenn Sie eine andere Instanz verwenden möchten, klicken Sie auf **Benannte Instanz** und geben Sie die Instanz an, die Sie für den Spiegelungszeugen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="228af-132">Either click **Default Instance** to use the default instance, or, to specify a different instance, click **Named Instance**, and then specify the instance you want to use for the mirroring witness.</span></span>
        
        3.  <span data-ttu-id="228af-133">Wenn sich die angegebene SQL Server-Instanz in einer Spiegelungs Beziehung befindet, aktivieren Sie das Kontrollkästchen **diese SQL-Instanz befindet sich in** der Spiegelungs Beziehung, und geben Sie dann in Spiegelungs- **Portnummer**die Portnummer an.</span><span class="sxs-lookup"><span data-stu-id="228af-133">If the specified SQL Server instance is in a mirroring relationship, select the **This SQL instance is in mirroring relation** check box, and then, in **Mirror port number**, specify the port number.</span></span>

10. <span data-ttu-id="228af-134">Klicken Sie zum Speichern der Konfiguration auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="228af-134">To save the configuration, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

