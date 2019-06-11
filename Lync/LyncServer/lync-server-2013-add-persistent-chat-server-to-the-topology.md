---
title: 'Lync Server 2013: Hinzufügen eines Server für beständigen Chat zu einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8985ee2fd28a81f3630e4f80c0ac4dd5a23d4475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="c0d8b-102">Hinzufügen eines Server für beständigen Chat zu einer Topologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0d8b-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0d8b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="c0d8b-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="c0d8b-104">Sie müssen lync Server 2013 und die Unterstützung für beständigen Chat Server in Ihre Topologie einbeziehen, bevor Sie Ihre Bereitstellung für die Unterstützung des beständigen Chat Servers konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="c0d8b-105">Die Informationen in diesem Thema beschreiben, wie Sie mithilfe des Topologie-Generators Ihrer vorhandenen Topologie Unterstützung für beständigen Chat Server hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="c0d8b-106">So fügen Sie einen beständigen Chat Server zu einer Topologie hinzu</span><span class="sxs-lookup"><span data-stu-id="c0d8b-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="c0d8b-107">Führen Sie die folgenden Schritte aus, um einen einzelnen beständigen Chat Server Pool ohne Disaster Recovery-Konfiguration zu installieren.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="c0d8b-108">Informationen zum Konfigurieren eines gestreckten beständigen Chat-Server Pools für Hochverfügbarkeits-und Disaster Recovery finden Sie unter Konfigurieren des beständigen [Chat Servers für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="c0d8b-109">Zum Bereitstellen mehrerer beständiger Chat Server-Pools wiederholen Sie diesen Vorgang für jeden Pool.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="c0d8b-110">Melden Sie sich auf einem Computer, auf dem lync Server 2013 ausgeführt wird oder auf dem die lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Gruppe "Benutzer" (oder einem Konto mit entsprechenden Benutzerrechten) ist.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0d8b-111">Sie können eine Topologie mithilfe eines Kontos definieren, das ein Mitglied der lokalen Benutzergruppe ist, aber zum Veröffentlichen einer Topologie, die für die Installation eines lync Server 2013-Servers erforderlich ist, müssen Sie ein Konto verwenden, das ein Mitglied der Gruppe der <STRONG>Domänenadministratoren</STRONG> und der <STRONG>RTCUniversalS ist. erverAdmins</STRONG> -Gruppe, die über die Berechtigung "Vollzugriff" (also lesen, schreiben und ändern) für den Dateispeicher verfügt, den Sie für den Dateispeicher des beständigen Chat Servers verwenden werden (d.-a., damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann) oder ein Konto mit entsprechenden Rechten.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="c0d8b-112">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="c0d8b-113">Navigieren Sie in der Konsolenstruktur zum Knoten **beständiger Chat Pools** , und erweitern Sie ihn, um einen Server Pool für beständigen Chat auszuwählen, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **neuer beständiger Chat Pool**aus.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="c0d8b-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="c0d8b-115">Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="c0d8b-116">Wählen Sie die erste Option aus, wenn Sie beabsichtigen, mehr als einen beständigen Chat Server-Front-End-Server in Ihrem beständigen Chat-Serverpool zu haben.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="c0d8b-117">Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="c0d8b-118">Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen beständigen Chat Server-Front-End-Server ein, aus denen sich der Pool zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0d8b-119">Wenn die Serverrolle "beständiger Chat" auf einem lync Server&nbsp;2013 Standard Edition-Server installiert wird, muss der FQDN dem FQDN des Standard Edition-Servers entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="c0d8b-120">Definieren Sie einen einfachen **Anzeige Namen** für den Server Pool des beständigen Chats.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="c0d8b-121">Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, insbesondere dann, wenn mehrere beständige Chat Server Pools vorhanden sind, um Räume zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="c0d8b-122">Definieren Sie den Port, der vom beständigen Chat Server für die Kommunikation mit lync Server-Front-End-Servern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="c0d8b-123">Der Standardport lautet 5041.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="c0d8b-124">Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="c0d8b-125">Falls ausgewählt, wird der beständige Chat Server-Kompatibilitätsdienst auf demselben Computer wie der Front-End-Server des beständigen Chats installiert.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="c0d8b-126">Sie werden aufgefordert, einen SQL Server-Back-End-Server für die beständige Chat Server-Kompatibilität zu einem späteren Zeitpunkt auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="c0d8b-127">Zuweisen einer Website Affinität für den Server Pool für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="c0d8b-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="c0d8b-128">Aktivieren Sie das Kontrollkästchen **diesen Pool als Standard \<für\> Website Sitename verwenden** , oder **verwenden Sie diesen Pool als Standard für alle Websites** , um diesen Server Pool für beständigen Chat als Standardpool für die aktuelle Website oder alle Websites festzulegen.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="c0d8b-129">Wenn der lync 2013-Client zum Erstellen und Verwalten von Räumen verwendet wird, wird der Standardpool, der der Website des Benutzers zugeordnet ist, von der raumerstellung und-Verwaltung verwendet, um Raum Erstellungs-und Verwaltungsvorgänge an diesen Pool weiterleiten zu können.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="c0d8b-130">Dies gilt nur, wenn Sie mehrere beständige Chat Server Pools bereitgestellt haben und die Funktionen zur raumerstellung und-Verwaltung des beständigen Chat Servers verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0d8b-131">Sie können die Funktionen zur raumerstellung und-Verwaltung mithilfe des beständigen Chat-Servers Software Development Kit (SDK) anpassen.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="c0d8b-132">Ausführliche Informationen zum Konfigurieren von SQL Server-Sicherungsdatenbanken für die Disaster Recovery finden Sie unter Konfigurieren des beständigen <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Chat Servers für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="c0d8b-133">Definieren Sie den **SQL Store für den beständigen Chat Server-Back-End (wobei Chatroom-Inhalte gespeichert werden)** , indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="c0d8b-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="c0d8b-134">Wenn Sie eine vorhandene SQL Server-Datenbank verwenden möchten, klicken Sie in der Dropdownliste auf den Namen der SQL Server-Datenbank, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="c0d8b-135">Wenn Sie eine neue SQL Server-Datenbank angeben möchten, klicken Sie auf **neu**, und führen Sie im **neuen SQL Store definieren**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c0d8b-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="c0d8b-136">Geben Sie im **SQL Server-FQDN**den FQDN des SQL Server an, auf dem Sie die neue SQL Server-Datenbank erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="c0d8b-137">Wählen Sie entweder **Standardinstanz** aus, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="c0d8b-138">Definieren Sie die SQL Server-Kompatibilitätsdatenbank, wenn Sie die Kompatibilität aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0d8b-139">Informationen zum Konfigurieren von SQL Server-Spiegelungen für die Hochverfügbarkeits-Datenbank für die persistente Chat Server-Datenbank und die Datenbank für beständigen Chat Server finden Sie unter Konfigurieren des beständigen <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Chat Servers für Hochverfügbarkeits-und Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="c0d8b-140">Definieren Sie den Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-140">Define the file store.</span></span> <span data-ttu-id="c0d8b-141">Bei einem Dateispeicher handelt es sich um einen Ordner, in dem eine Kopie einer Datei, die in das Datei-Repository hochgeladen wurde, gespeichert wird (beispielsweise das Speichern von Dateianlagen, die in einem Chatroom gepostet wurden).</span><span class="sxs-lookup"><span data-stu-id="c0d8b-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="c0d8b-142">Bei einer persistenten Chat Server Topologie mit mehreren Servern muss es sich um einen UNC-Pfad (Universal Naming Convention) handeln. und bei einer Server Topologie mit einem Server für beständigen Chat kann es sich um einen lokalen Dateipfad handeln.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="c0d8b-143">Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="c0d8b-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="c0d8b-144">Geben Sie im **FQDN des Dateiservers**den FQDN des Dateispeichers an, für den Sie den neuen Dateispeicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="c0d8b-145">Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0d8b-146">Sie können den Dateispeicher in Topology Builder definieren, bevor Sie den Dateispeicher erstellen, aber Sie müssen den Dateispeicher am definierten Speicherort erstellen, den Sie definieren, bevor Sie die Topologie veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="c0d8b-147">Wählen Sie den Front-End-Serverpool aus, der als nächster Hop für diesen beständigen Chat Serverpool verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="c0d8b-148">Dies ist der Front-End-Serverpool, der beständige Chat Server Anforderungen an diesen Pool weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="c0d8b-149">Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="c0d8b-150">Der Server Pool für beständigen Chat wird im Topologie-Generator mit ihren spezifischen Pooleinstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="c0d8b-151">Wenn Sie jetzt Ihre aktualisierte Topologie veröffentlichen möchten, auf der Sie den persistenten Chat Server haben, lesen Sie [Veröffentlichen der aktualisierten Topologie in lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0d8b-152">Wenn der Topologie-Generator bereits geöffnet ist, können Sie mit Schritt 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Veröffentlichen der aktualisierten Topologie in lync Server 2013</A> fortfahren, um mit der Veröffentlichung ihrer aktualisierten Topologie zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="c0d8b-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

