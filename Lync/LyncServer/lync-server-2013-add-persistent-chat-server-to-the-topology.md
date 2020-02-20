---
title: 'Lync Server 2013: Hinzufügen des Servers für beständigen Chat zur Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Persistent Chat Server to the topology
ms:assetid: 8389b307-8c17-4e45-b3b5-5dc9fcfc2ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205049(v=OCS.15)
ms:contentKeyID: 48184682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b857c63b08906ada2cee2611960717f97e7a3cc1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-persistent-chat-server-to-the-topology-in-lync-server-2013"></a><span data-ttu-id="ad31d-102">Hinzufügen eines Servers für beständigen Chat zur Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad31d-102">Add Persistent Chat Server to the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad31d-103">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ad31d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ad31d-104">Sie müssen lync Server 2013 Unterstützung für beständigen Chat Server in Ihrer Topologie integrieren, bevor Sie Ihre Bereitstellung für die Unterstützung des Servers für beständigen Chat konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="ad31d-104">You must incorporate Lync Server 2013, Persistent Chat Server support in your topology before you can configure your deployment to support Persistent Chat Server.</span></span> <span data-ttu-id="ad31d-105">In den Informationen in diesem Thema wird beschrieben, wie Sie mithilfe des Topologie-Generators der vorhandenen Topologie Unterstützung für beständigen Chat hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad31d-105">The information in this topic describes how to use Topology Builder to add Persistent Chat Server support to your existing topology.</span></span>

<div>

## <a name="to-add-persistent-chat-server-to-a-topology"></a><span data-ttu-id="ad31d-106">So fügen Sie einer Topologie einen Server für beständigen Chat hinzu</span><span class="sxs-lookup"><span data-stu-id="ad31d-106">To add Persistent Chat Server to a topology</span></span>

<span data-ttu-id="ad31d-107">Führen Sie die folgenden Schritte aus, um einen einzelnen Server Pool für beständigen Chat ohne Notfall Wiederherstellungskonfiguration zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ad31d-107">Perform the following steps for installing a single Persistent Chat Server pool without a disaster recovery configuration.</span></span> <span data-ttu-id="ad31d-108">Informationen zum Konfigurieren eines ausgedehnten Server Pools für beständigen Chat für hohe Verfügbarkeit und Notfallwiederherstellung finden Sie unter [Configuring persistent Chat Server for High Availability and Disaster Recovery in lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad31d-108">For configuring a stretched Persistent Chat Server pool for high availability and disaster recovery, see [Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) in the Deployment documentation.</span></span>

<span data-ttu-id="ad31d-109">Um mehrere Server Pools für beständigen Chat bereitzustellen, wiederholen Sie diesen Vorgang für jeden Pool.</span><span class="sxs-lookup"><span data-stu-id="ad31d-109">To deploy multiple Persistent Chat Server pools, repeat the same process for each pool.</span></span>

1.  <span data-ttu-id="ad31d-110">Melden Sie sich auf einem Computer, auf dem lync Server 2013 oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der lokalen Benutzergruppe ist (oder mit einem Konto mit gleichwertigen Benutzerrechten).</span><span class="sxs-lookup"><span data-stu-id="ad31d-110">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad31d-111">Sie können eine Topologie definieren, indem Sie ein Konto verwenden, das Mitglied der lokalen Benutzergruppe ist, aber eine Topologie veröffentlichen. für die Installation eines lync Server 2013 Servers müssen Sie ein Konto verwenden, das Mitglied der Gruppe " <STRONG>Domänen-Admins</STRONG> " und der Gruppe " <STRONG>RTCUniversalServerAdmins</STRONG> " ist und das über Vollzugriff auf den Dateispeicher verfügt, den Sie für den Dateispeicher für beständigen Chat Server verwenden möchten (Dies bedeutet, dass der Topologie-Generator die erforderlichen DACLs konfigurieren kann) oder ein Konto mit gleichwertigen Rechten.</span><span class="sxs-lookup"><span data-stu-id="ad31d-111">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to install a Lync Server 2013 server, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file store that you are going to use for the Persistent Chat Server file store (that is, so that Topology Builder can configure the required DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="ad31d-112">Starten Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="ad31d-112">Start Topology Builder.</span></span>

3.  <span data-ttu-id="ad31d-113">Navigieren Sie in der Konsolenstruktur zum Knoten **persistent Chat Pools** , und erweitern Sie ihn, um einen Server Pool für beständigen Chat auszuwählen, oder klicken Sie mit der rechten Maustaste auf den Knoten, und wählen Sie **neuer Pool für beständigen Chat**aus.</span><span class="sxs-lookup"><span data-stu-id="ad31d-113">In the console tree, navigate to the **Persistent Chat Pools** node and expand it to select a Persistent Chat Server pool, or right-click the node and select **New Persistent Chat Pool**.</span></span> <span data-ttu-id="ad31d-114">Sie müssen den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools definieren und festlegen, ob der Pool in der Bereitstellung einen einzelnen oder mehrere Server enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="ad31d-114">You must define the pool’s fully qualified domain name (FQDN), and indicate whether the pool will be a single-server pool or multiple-server pool deployment.</span></span>
    
    <span data-ttu-id="ad31d-115">Wählen Sie **Pool mit mehreren Computern** oder **Pool mit einem Computer** aus.</span><span class="sxs-lookup"><span data-stu-id="ad31d-115">You can choose a **Multiple Computer Pool** or a **Single Computer Pool**.</span></span> <span data-ttu-id="ad31d-116">Wählen Sie die erste Option aus, wenn Sie mehr als einen Server für beständigen Chat Front-End-Server im Serverpool für beständigen Chat planen.</span><span class="sxs-lookup"><span data-stu-id="ad31d-116">Choose the former if you are planning to have more than one Persistent Chat Server Front End Server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="ad31d-117">Wählen Sie diese Option jetzt oder zu einem späteren Zeitpunkt, da Sie einem Pool mit einem Computer später keine zusätzlichen Server hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="ad31d-117">Make this choice now, or at a later point, because after you create a single computer pool, you cannot add additional servers to it later.</span></span> <span data-ttu-id="ad31d-118">Wenn Sie einen Pool mit mehreren Computern auswählen, geben Sie die Namen der einzelnen beständigen Chat Server-Front-End-Server ein, aus denen sich der Pool zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="ad31d-118">If you choose a multiple computer pool, enter the names of the individual Persistent Chat Server Front End Servers that comprise the pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ad31d-119">Wenn die Server Rolle für beständigen Chat auf einem lync Server 2013&nbsp;Standard Edition-Server installiert wird, muss der FQDN mit dem FQDN des Standard Edition-Server übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="ad31d-119">If the Persistent Chat Server role is being installed on a Lync Server 2013&nbsp;Standard Edition server, the FQDN needs to match the FQDN of the Standard Edition server.</span></span>

    
    </div>

4.  <span data-ttu-id="ad31d-120">Definieren Sie einen einfachen **Anzeigenamen** für den Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="ad31d-120">Define a simple **Display Name** for the Persistent Chat Server pool.</span></span> <span data-ttu-id="ad31d-121">Der Anzeigename kann von benutzerdefinierten Clients verwendet werden, insbesondere dann, wenn es mehrere Server Pools für beständigen Chat gibt, um Räume zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ad31d-121">The display name can be used by custom clients, particularly when there are multiple Persistent Chat Server pools, to differentiate rooms.</span></span>

5.  <span data-ttu-id="ad31d-122">Definieren Sie den Port, der vom Server für beständigen Chat verwendet wird, um mit lync Server-Front-End-Servern zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="ad31d-122">Define the port used by the Persistent Chat Server to communicate with Lync Server Front End Servers.</span></span> <span data-ttu-id="ad31d-123">Der Standardport lautet 5041.</span><span class="sxs-lookup"><span data-stu-id="ad31d-123">The default port is 5041.</span></span>

6.  <span data-ttu-id="ad31d-124">Falls in Ihrer Organisation Kompatibilitätsunterstützung erforderlich ist, aktivieren Sie das Kontrollkästchen **Kompatibilität aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="ad31d-124">If your organization requires compliance support, select the **Enable compliance** check box.</span></span> <span data-ttu-id="ad31d-125">Wenn dieser ausgewählt ist, wird der Kompatibilitätsdienst für den Server für beständigen Chat auf dem gleichen Computer wie der Server für beständigen Chat Front-End-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="ad31d-125">If chosen, the Persistent Chat Server Compliance service is installed on the same computer as the Persistent Chat Server Front End Server.</span></span> <span data-ttu-id="ad31d-126">Sie werden aufgefordert, einen SQL Server Back-End-Server für die Kompatibilität mit beständigen Chat Servern zu einem späteren Zeitpunkt auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ad31d-126">You are prompted to select a SQL Server Back End Server for Persistent Chat Server Compliance later.</span></span>

7.  <span data-ttu-id="ad31d-127">Zuweisen der Standortaffinität für den Server Pool für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="ad31d-127">Assign site affinity for the Persistent Chat Server pool.</span></span> <span data-ttu-id="ad31d-128">Aktivieren Sie das Kontrollkästchen **diesen Pool als Standard \<für\> Website Sitename verwenden** , oder **verwenden Sie diesen Pool als Standard für alle Websites** , um diesen Server Pool für beständigen Chat als Standardpool für die aktuelle Website oder alle Websites festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ad31d-128">Select the **Use this pool as default for site \<SiteName\>** check box or **Use this pool as default for all sites** to designate this Persistent Chat Server pool as the default pool for the current site or all sites.</span></span> <span data-ttu-id="ad31d-129">Wenn der lync 2013-Client zum Erstellen und Verwalten von Räumen verwendet wird, wird der Standardpool, der dem Standort des Benutzers zugeordnet ist, von der Raum Erstellungs-und-Verwaltungsumgebung verwendet, damit er Raum Erstellungs-und Verwaltungsvorgänge an diesen Pool weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="ad31d-129">When the Lync 2013 client is used to create and manage rooms, the default pool associated with the user’s site is used by the room creation and management experience so that it can route room creation and management operations to that pool.</span></span> <span data-ttu-id="ad31d-130">Dies gilt nur, wenn Sie mehrere Server Pools für beständigen Chat bereitgestellt haben und die Funktionen zum Erstellen und Verwalten von Räumen für den Server für beständigen Chat verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad31d-130">This only applies when you have multiple Persistent Chat Server pools deployed, and want to use the room creation and management features of Persistent Chat Server.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ad31d-131">Sie können die Raum Erstellungs-und Verwaltungsfunktionen mit dem Server Software Development Kit (SDK) für beständigen Chat anpassen.</span><span class="sxs-lookup"><span data-stu-id="ad31d-131">You can customize the room creation and management features using the Persistent Chat Server Software Development Kit (SDK).</span></span><BR><span data-ttu-id="ad31d-132">Ausführliche Informationen zum Konfigurieren SQL Server Sicherungsdatenbanken für die Notfallwiederherstellung finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent Chat Server for High Availability and Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad31d-132">For details about how to configure SQL Server backup databases for disaster recovery, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="ad31d-133">Definieren Sie den **SQL-Speicher für den Server für beständigen Chat zurück, auf dem Chatroom-Inhalte gespeichert sind** , indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="ad31d-133">Define the **SQL store for the Persistent Chat Server Back End (where chat room content is stored)** by doing one of the following:</span></span>
    
      - <span data-ttu-id="ad31d-134">Um eine vorhandene SQL Server Datenbank zu verwenden, klicken Sie in der Dropdownliste auf den Namen der SQL Server Datenbank, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad31d-134">To use an existing SQL Server database, in the drop-down list, click the name of the SQL Server database that you want to use.</span></span>
    
      - <span data-ttu-id="ad31d-135">Wenn Sie eine neue SQL Server Datenbank angeben möchten, klicken Sie auf **neu**, und führen Sie im **neuen SQL-Speicher definieren**die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="ad31d-135">To specify a new SQL Server database, click **New**, and in **Define New SQL Store**, perform the following:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="ad31d-136">Geben Sie in **SQL Server FQDN**den FQDN des SQL Server an, für den Sie die neue SQL Server Datenbank erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad31d-136">In **SQL Server FQDN**, specify the FQDN of the SQL Server on which you want to create the new SQL Server database.</span></span>
    
      - <span data-ttu-id="ad31d-137">Wählen Sie entweder **Standardinstanz**, um die Standardinstanz zu verwenden, oder wählen Sie **Benannte Instanz** aus, um eine andere Instanz anzugeben, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad31d-137">Either select **Default Instance** to use the default instance or, to specify a different instance, select **Named Instance**, and specify the instance that you want to use.</span></span>

9.  <span data-ttu-id="ad31d-138">Definieren Sie die SQL Server-Kompatibilitätsdatenbank, wenn Sie die Kompatibilität aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ad31d-138">Define the SQL Server compliance database if you enabled Compliance.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ad31d-139">Ausführliche Informationen zum Konfigurieren von SQL Server spiegeln für hohe Verfügbarkeit für die Datenbank für beständigen Chat Server und die Datenbank für beständigen Chat Server finden Sie unter <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring persistent Chat Server for High Availability and Disaster Recovery in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad31d-139">For details about how to configure SQL Server mirrors for high availability for the Persistent Chat Server database and the Persistent Chat Server compliance database, see <A href="lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md">Configuring Persistent Chat Server for high availability and disaster recovery in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

10. <span data-ttu-id="ad31d-140">Definieren Sie den Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="ad31d-140">Define the file store.</span></span> <span data-ttu-id="ad31d-141">Bei einem Dateispeicher handelt es sich um einen Ordner, in dem eine Kopie aller in das Datei-Repository hochgeladenen Dateien gespeichert wird (beispielsweise das Speichern von Dateianlagen, die in einem Chatroom veröffentlicht werden).</span><span class="sxs-lookup"><span data-stu-id="ad31d-141">A file store is a folder where a copy of any file uploaded to the file repository is stored (for example, storing file attachments posted to a chat room).</span></span> <span data-ttu-id="ad31d-142">Wenn es sich um eine Server Topologie mit mehreren Servern für beständigen Chat handelt, muss es sich um einen UNC-Pfad (Universal Naming Convention) handeln. für eine Server Topologie mit einem einzelnen Server kann es sich um einen lokalen Dateipfad handeln.</span><span class="sxs-lookup"><span data-stu-id="ad31d-142">In the case of a multiple-server Persistent Chat Server topology, this must be a Universal Naming Convention (UNC) path; and for a single-server Persistent Chat Server topology, it can be a local file path.</span></span>
    
    <span data-ttu-id="ad31d-143">Führen Sie die folgenden Schritte aus, um einen vorhandenen Dateispeicher zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="ad31d-143">To use an existing file store, perform the following steps:</span></span>
    
      - <span data-ttu-id="ad31d-144">Geben Sie in **Dateiserver-FQDN** den FQDN des Dateispeichers an, auf dem Sie den neuen Dateispeicher erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ad31d-144">In **File Server FQDN**, specify the FQDN of the file store on which you want to create the new file store.</span></span>
    
      - <span data-ttu-id="ad31d-145">Geben Sie in **Dateifreigabe** den Dateispeicher an, den Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ad31d-145">In **File Share**, specify the file store that you want to use.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ad31d-146">Sie können den Dateispeicher im Topologie-Generator definieren, bevor Sie den Dateispeicher erstellen, aber Sie müssen den Dateispeicher an dem definierten Speicherort erstellen, den Sie vor dem Veröffentlichen der Topologie definieren.</span><span class="sxs-lookup"><span data-stu-id="ad31d-146">You can define the file store in Topology Builder before you create the file store, but you must create the file store in the defined location you define before you publish the topology.</span></span>

    
    </div>

11. <span data-ttu-id="ad31d-147">Wählen Sie den Front-End-Server Pool aus, der als nächster Hop für diesen Server Pool für beständigen Chat verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ad31d-147">Select the Front End Server pool to be used as a next hop for this Persistent Chat Server pool.</span></span> <span data-ttu-id="ad31d-148">Dies ist der Front-End-Server Pool, der beständige Chat Server Anforderungen an diesen Pool weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="ad31d-148">This is the Front End Server pool that will be able to route Persistent Chat Server requests to this pool.</span></span>

12. <span data-ttu-id="ad31d-149">Klicken Sie auf **Fertig stellen**, um die Konfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ad31d-149">To save the configuration, click **Finish**.</span></span> <span data-ttu-id="ad31d-150">Der Server Pool für beständigen Chat wird im Topologie-Generator mit ihren speziellen Pooleinstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad31d-150">The Persistent Chat Server pool appears in Topology Builder accompanied by your specific pool settings.</span></span>
    
    <span data-ttu-id="ad31d-151">Informationen zum Veröffentlichen der aktualisierten Topologie, auf der Sie den Server für beständigen Chat haben, finden Sie unter [Veröffentlichen der aktualisierten Topologie in lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ad31d-151">To now publish your updated topology to which you’ve Persistent Chat Server, see [Publish the updated topology in Lync Server 2013](lync-server-2013-publish-the-updated-topology.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad31d-152">Wenn der Topologie-Generator bereits geöffnet ist, können Sie mit Schritt 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Veröffentlichen der aktualisierten Topologie in lync Server 2013</A> fortfahren, um mit der Veröffentlichung ihrer aktualisierten Topologie zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="ad31d-152">With Topology Builder already open, you can proceed to step 3 in <A href="lync-server-2013-publish-the-updated-topology.md">Publish the updated topology in Lync Server 2013</A> to begin publishing your updated topology.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

