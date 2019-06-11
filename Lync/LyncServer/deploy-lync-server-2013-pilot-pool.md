---
title: Bereitstellen des lync Server 2013-pilotpools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="0d979-102">Bereitstellen des lync Server 2013-pilotpools</span><span class="sxs-lookup"><span data-stu-id="0d979-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d979-103">_**Letztes Änderungsdatum des Themas:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="0d979-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="0d979-104">Einer der ersten Schritte, die für die Migration zu lync Server 2013 erforderlich sind, ist die Bereitstellungeines pilotpools.</span><span class="sxs-lookup"><span data-stu-id="0d979-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="0d979-105">Im Pilot Pool wird die Koexistenz von lync Server 2013 mit ihrer lync Server 2010-Bereitstellung getestet.</span><span class="sxs-lookup"><span data-stu-id="0d979-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Lync Server 2010 deployment.</span></span> <span data-ttu-id="0d979-106">Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in lync Server 2013 verschoben haben.</span><span class="sxs-lookup"><span data-stu-id="0d979-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="0d979-107">Wenn Sie einen Pilot Pool bereitstellen, verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="0d979-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="0d979-108">Sie sollten dieselben Features und Arbeitsauslastungen in Ihrem lync Server 2013-Pilot Pool bereitstellen, die Sie in Ihrem lync Server 2010-Pool haben.</span><span class="sxs-lookup"><span data-stu-id="0d979-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Lync Server 2010 pool.</span></span> <span data-ttu-id="0d979-109">Wenn Sie den Archivierungsserver, den Monitoring Server oder den System Center Operations Manager zum Archivieren oder Überwachen Ihrer lync Server 2010-Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie diese auch bereitstellen. Features in ihrer Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="0d979-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Lync Server 2010 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="0d979-110">Mit der Version, die Sie zum Archivieren oder Überwachen Ihrer lync Server 2010-Umgebung bereitgestellt haben, werden keine Daten in ihrer lync Server 2013-Umgebung erfasst.</span><span class="sxs-lookup"><span data-stu-id="0d979-110">The version you deployed to archive or monitor your Lync Server 2010 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0d979-111">Im folgenden Verfahren werden die Features und Einstellungen erörtert, die Sie im Rahmen des gesamten Bereitstellungsprozesses für pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="0d979-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="0d979-112">In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="0d979-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="0d979-113">Detaillierte Anweisungen finden Sie im Bereitstellungshandbuch für die <A href="lync-server-2013-deploying-lync-server.md">Bereitstellung von lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="0d979-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="0d979-114">**Bereitstellen eines lync Server 2013-pilotpools**</span><span class="sxs-lookup"><span data-stu-id="0d979-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="0d979-115">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="0d979-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="0d979-116">Erweitern Sie die Struktur, bis Sie die **lync Server 2013** **Enterprise Edition-Front-End-Pools**erreichen.</span><span class="sxs-lookup"><span data-stu-id="0d979-116">Expand the tree until you reach **Lync Server 2013** **Enterprise Edition Front End pools**.</span></span>

3.  <span data-ttu-id="0d979-117">Klicken Sie mit der rechten Maustaste auf **Enterprise Edition-Front-End-Pools**, und wählen Sie **neuer Frontend-Pool**</span><span class="sxs-lookup"><span data-stu-id="0d979-117">Right click **Enterprise Edition Front End pools**, and select **New Front End Pool**.</span></span>
    
    <span data-ttu-id="0d979-118">![Menü "Auswahl" des Topologie-Generator-Server Pools] (images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Menü \"Auswahl\" des Topologie-Generator-Server Pools")</span><span class="sxs-lookup"><span data-stu-id="0d979-118">![Topology Builder Server pool selection submenu](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Topology Builder Server pool selection submenu")</span></span>

4.  <span data-ttu-id="0d979-119">Geben Sie den Pool-FQDN ein.</span><span class="sxs-lookup"><span data-stu-id="0d979-119">Enter the pool FQDN.</span></span> <span data-ttu-id="0d979-120">Wenn Sie Ihren Pilot Pool definieren, können Sie auswählen, ob Sie einen Enterprise Edition-Front-End-Pool oder einen Standard Edition-Server bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0d979-120">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="0d979-121">Für lync Server 2013 ist es nicht erforderlich, dass die Features Ihres pilotpools mit dem übereinstimmen, was in Ihrem Legacy Pool bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0d979-121">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0d979-122">Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools oder Servers, den Sie für den Pilot Pool definieren, muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="0d979-122">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="0d979-123">Sie kann nicht mit dem Namen des derzeit bereitgestellten lync Server 2010-Pools oder aller anderen Server übereinstimmen, die derzeit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0d979-123">It cannot match the name of the currently deployed Lync Server 2010 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="0d979-124">![Seite "neuen Front-End-Pool-Assistenten definieren"] (images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Seite \"neuen Front-End-Pool-Assistenten definieren\"")</span><span class="sxs-lookup"><span data-stu-id="0d979-124">![Define New Front End Pool Wizard FQDN page](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Define New Front End Pool Wizard FQDN page")</span></span>

5.  <span data-ttu-id="0d979-125">Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0d979-125">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="0d979-126">Wenn Sie beispielsweise nur Chat-und Anwesenheitsfeatures bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzen, um mehrteilige Chats zu ermöglichen, aber nicht die Kontrollkästchen Einwahl (PSTN) Conferencing, Enterprise Voice oder Anrufsteuerung aktivieren, Da es sich um sprach-, Video-und kollaborative Konferenzfeatures handelt.</span><span class="sxs-lookup"><span data-stu-id="0d979-126">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="0d979-127">Weitere Informationen zum Auswählen von Features finden Sie unter [definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d979-127">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="0d979-128">![Front-End-Pool auswählen der Seite "Features] " (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool auswählen der Seite \"Features") "</span><span class="sxs-lookup"><span data-stu-id="0d979-128">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

6.  <span data-ttu-id="0d979-129">Auf der Seite **"ausgewählte Serverrollen auswählen** " empfehlen wir, den Vermittlungsserver in lync Server 2013 collocate.</span><span class="sxs-lookup"><span data-stu-id="0d979-129">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="0d979-130">Wenn Sie eine Legacy Topologie mit lync Server 2013 zusammenführen, müssen Sie zuerst den lync Server 2010-Vermittlungsserver collocate.</span><span class="sxs-lookup"><span data-stu-id="0d979-130">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Lync Server 2010 Mediation Server.</span></span> <span data-ttu-id="0d979-131">Nachdem Sie die Topologien zusammengeführt und den lync Server 2013-Vermittlungsserver konfiguriert haben, können Sie entscheiden, ob Sie den beiliegenden Vermittlungsserver beibehalten oder auf einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle später in der Bereitstellung nach lync Server 2013 verschieben. Prozess.</span><span class="sxs-lookup"><span data-stu-id="0d979-131">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="0d979-132">![Front-End-Pool wählen Sie die Seite mit den Serverrollen] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool wählen Sie die Seite mit den Serverrollen")</span><span class="sxs-lookup"><span data-stu-id="0d979-132">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

7.  <span data-ttu-id="0d979-133">Wählen Sie auf der Seite **Associate Server Roles with this Front End Pool** während der Bereitstellung des pilotpools nicht die Option **einen Edge-Pool aktivieren, der von der medienkomponente dieser Front-End-Pool Option verwendet werden soll** .</span><span class="sxs-lookup"><span data-stu-id="0d979-133">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="0d979-134">Dies ist ein Feature, das Sie in einer späteren Migrationsphase aktivieren und online schalten können.</span><span class="sxs-lookup"><span data-stu-id="0d979-134">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="0d979-135">Lassen Sie diese Einstellung für jetzt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="0d979-135">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="0d979-136">![Verknüpfen von Serverrollen mit der Seite "Front-End-Pool"] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Verknüpfen von Serverrollen mit der Seite \"Front-End-Pool\"")</span><span class="sxs-lookup"><span data-stu-id="0d979-136">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

8.  <span data-ttu-id="0d979-137">Klicken Sie auf der Seite **Office Web Apps-Server auswählen** auf **neu**, und geben Sie den FQDN des Anwendungsservers an.</span><span class="sxs-lookup"><span data-stu-id="0d979-137">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="0d979-138">![Definieren von neuen Office Web Apps Server-FQDN-Eigenschaften] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren von neuen Office Web Apps Server-FQDN-Eigenschaften")</span><span class="sxs-lookup"><span data-stu-id="0d979-138">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

9.  <span data-ttu-id="0d979-139">Wählen Sie auf der Seite **Archivierungs-SQL Server-Speicher definieren** beim Definieren des SQL Server-Speichers für die lync Server-Archivierung und-Überwachung die SQL Server-Instanz aus, die zuvor für lync Server 2013 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0d979-139">On the **Define the Archiving SQL Server store** page, when defining the SQL Server store for both Lync Server Archiving and Monitoring, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="0d979-140">![Seite "Archivierungs-SQL Server-Store definieren"] (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Seite \"Archivierungs-SQL Server-Store definieren\"")</span><span class="sxs-lookup"><span data-stu-id="0d979-140">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

10. <span data-ttu-id="0d979-141">Wenn Sie Ihre Topologie veröffentlichen möchten, klicken Sie mit der rechten Maustaste auf den **lync Server** -Knoten, und klicken Sie dann auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="0d979-141">To publish your topology, right-click the **Lync Server** node, and then click **Publish Topology**.</span></span>
    
    <span data-ttu-id="0d979-142">![Topologie-Generator, der eine konfigurierte Topologie anzeigt] (images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topologie-Generator, der eine konfigurierte Topologie anzeigt")</span><span class="sxs-lookup"><span data-stu-id="0d979-142">![Topology Builder displaying a configured topology](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Topology Builder displaying a configured topology")</span></span>

11. <span data-ttu-id="0d979-143">Wenn der Veröffentlichungsprozess abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="0d979-143">When the publish process has completed, click **Finish**.</span></span>

<span data-ttu-id="0d979-144">Wenn Sie eine lokale Kopie des Konfigurationsspeichers installieren und die erforderlichen Dienste starten möchten, lesen Sie [Einrichten der Front-End-Server und der Front-End-Pools für lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d979-144">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

