---
title: Bereitstellen des lync Server 2013-pilotpools
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="e2c5a-102">Bereitstellen des lync Server 2013-pilotpools</span><span class="sxs-lookup"><span data-stu-id="e2c5a-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2c5a-103">_**Letztes Änderungsdatum des Themas:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="e2c5a-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="e2c5a-104">Einer der ersten Schritte, die für die Migration zu lync Server 2013 erforderlich sind, ist die Bereitstellungeines pilotpools.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="e2c5a-105">Im Pilot Pool wird die Koexistenz von lync Server 2013 mit Ihrer Office Communications Server 2007 R2-Bereitstellung getestet.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="e2c5a-106">Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in lync Server 2013 verschoben haben.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="e2c5a-107">Wenn Sie einen Pilot Pool bereitstellen, verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="e2c5a-108">Sie sollten dieselben Features und Arbeitsauslastungen in Ihrem lync Server 2013-Pilot Pool bereitstellen, die Sie in Ihrem Office Communications Server 2007 R2-Pool haben.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="e2c5a-109">Wenn Sie den Archivierungsserver, den Monitoring Server oder den System Center Operations Manager zum Archivieren oder Überwachen Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie Stellen Sie diese Features auch in ihrer Pilotumgebung bereit.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="e2c5a-110">Mit der Version, die Sie zum Archivieren oder Überwachen Ihrer Office Communications Server 2007 R2-Umgebung bereitgestellt haben, werden keine Daten in ihrer lync Server 2013-Umgebung erfasst.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2c5a-111">Im folgenden Verfahren werden die Features und Einstellungen erörtert, die Sie im Rahmen des gesamten Bereitstellungsprozesses für pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="e2c5a-112">In diesem Abschnitt werden nur wichtige Punkte hervorgehoben, die Sie im Rahmen der Bereitstellung des pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="e2c5a-113">Detaillierte Anweisungen finden Sie im Bereitstellungshandbuch für die <A href="lync-server-2013-deploying-lync-server.md">Bereitstellung von lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="e2c5a-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="e2c5a-114">**Bereitstellen eines lync Server 2013-pilotpools**</span><span class="sxs-lookup"><span data-stu-id="e2c5a-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="e2c5a-115">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e2c5a-116">Öffnen Sie den Topologie-Generator, und wählen Sie aus, um eine neue Topologie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="e2c5a-117">Geben Sie die primäre SIP-Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="e2c5a-118">![Erstellen einer neuen Topologie, Seite "primäre Domäne definieren"](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Erstellen einer neuen Topologie, Seite "primäre Domäne definieren"")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="e2c5a-119">Fahren Sie mit dem Abschließen des Assistenten fort, bis Sie den Assistenten zum **Definieren des neuen Front-End-Pools** erreichen.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="e2c5a-120">Klicken Sie auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-120">Click Next.</span></span>

5.  <span data-ttu-id="e2c5a-121">Geben Sie den Pool-FQDN ein.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-121">Enter the pool FQDN.</span></span> <span data-ttu-id="e2c5a-122">Wenn Sie Ihren Pilot Pool definieren, können Sie auswählen, ob Sie einen Enterprise Edition-Front-End-Pool oder einen Standard Edition-Server bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="e2c5a-123">Für lync Server 2013 ist es nicht erforderlich, dass die Features Ihres pilotpools mit dem übereinstimmen, was in Ihrem Legacy Pool bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="e2c5a-124">Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools oder Servers, den Sie für den Pilot Pool definieren, muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="e2c5a-125">Sie kann nicht mit dem Namen des aktuell bereitgestellten Office Communications Server 2007 R2-Pools oder aller anderen Server übereinstimmen, die derzeit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="e2c5a-126">![Definieren der FQDN-Seite des Front-End-Pools](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definieren der FQDN-Seite des Front-End-Pools")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="e2c5a-127">Definieren Sie den Computer, der dem Pool hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="e2c5a-128">![Dialogfeld "neuen Front-End-Pool definieren"](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Dialogfeld "neuen Front-End-Pool definieren"")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="e2c5a-129">Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="e2c5a-130">Wenn Sie beispielsweise nur Chat-und Anwesenheitsfeatures bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzen, um mehrteilige Chats zu ermöglichen, aber nicht die Kontrollkästchen Einwahl (PSTN) Conferencing, Enterprise Voice oder Anrufsteuerung aktivieren, Da es sich um sprach-, Video-und kollaborative Konferenzfeatures handelt.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="e2c5a-131">Weitere Informationen zum Auswählen von Features finden Sie unter [definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="e2c5a-132">![Front-End-Pool auswählen der Seite "Features"](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool auswählen der Seite "Features"")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="e2c5a-133">Auf der Seite **"ausgewählte Serverrollen auswählen** " empfehlen wir, den Vermittlungsserver in lync Server 2013 collocate.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="e2c5a-134">Wenn Sie eine Legacy Topologie mit lync Server 2013 zusammenführen, müssen Sie zuerst den Office Communications Server 2007 R2-Vermittlungsserver collocate.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="e2c5a-135">Nachdem Sie die Topologien zusammengeführt und den lync Server 2013-Vermittlungsserver konfiguriert haben, können Sie entscheiden, ob Sie den beiliegenden Vermittlungsserver beibehalten oder auf einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle später in der Bereitstellung nach lync Server 2013 verschieben. Prozess.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="e2c5a-136">![Front-End-Pool wählen Sie die Seite mit den Serverrollen](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool wählen Sie die Seite mit den Serverrollen")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="e2c5a-137">Wählen Sie auf der Seite **Associate Server Roles with this Front End Pool** während der Bereitstellung des pilotpools nicht die Option **einen Edge-Pool aktivieren, der von der medienkomponente dieser Front-End-Pool Option verwendet werden soll** .</span><span class="sxs-lookup"><span data-stu-id="e2c5a-137">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option.</span></span> <span data-ttu-id="e2c5a-138">Dies ist ein Feature, das Sie in einer späteren Migrationsphase aktivieren und online schalten können.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-138">This is a feature you will enable and bring online in a later phase of migration.</span></span> <span data-ttu-id="e2c5a-139">Lassen Sie diese Einstellung für jetzt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-139">Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="e2c5a-140">![Verknüpfen von Serverrollen mit der Seite "Front-End-Pool"](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Verknüpfen von Serverrollen mit der Seite "Front-End-Pool"")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="e2c5a-141">Klicken Sie auf der Seite **Office Web Apps-Server auswählen** auf **neu**, und geben Sie den FQDN des Anwendungsservers an.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="e2c5a-142">![Definieren von neuen Office Web Apps Server-FQDN-Eigenschaften](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren von neuen Office Web Apps Server-FQDN-Eigenschaften")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="e2c5a-143">Wählen Sie auf der Seite **Archivierungs-SQL Server-Speicher definieren** die SQL Server-Instanz aus, die zuvor für lync Server 2013 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="e2c5a-144">![Seite "Archivierungs-SQL Server-Store definieren"](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Seite "Archivierungs-SQL Server-Store definieren"")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="e2c5a-145">Wählen Sie auf der Seite **SQL Server-Überwachungsspeicher definieren** die SQL Server-Instanz aus, die zuvor für lync Server 2013 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="e2c5a-146">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-146">Click **Finish**.</span></span>

13. <span data-ttu-id="e2c5a-147">Klicken Sie im obersten Knoten des Topologie-Generators mit der rechten Maustaste auf **lync Server** , und klicken Sie auf **Eigenschaften bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="e2c5a-147">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.**</span></span> <span data-ttu-id="e2c5a-148">Klicken Sie auf **einfache URLs**.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-148">Click **Simple URLs**.</span></span>

14. <span data-ttu-id="e2c5a-149">Aktualisieren Sie die **Administratorzugriffs-URL**.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="e2c5a-150">![Bearbeiten von Eigenschaften, Seite "einfache URLs"](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Bearbeiten von Eigenschaften, Seite "einfache URLs"")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="e2c5a-151">Weitere Informationen zu einfachen URLs finden Sie im Thema [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="e2c5a-152">Klicken Sie in den **Eigenschaften bearbeiten**auf **zentraler Verwaltungs Server**.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="e2c5a-153">Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="e2c5a-154">![Eigenschaften bearbeiten, Seite "zentraler Verwaltungs Server"](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Eigenschaften bearbeiten, Seite "zentraler Verwaltungs Server"")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="e2c5a-155">Klicken Sie auf OK, um **die Seite Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="e2c5a-156">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="e2c5a-157">Wenn der Veröffentlichungsprozess abgeschlossen ist, klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="e2c5a-158">Wenn Sie zum lync Server 2013-Bereitstellungs-Assistenten zurückkehren, klicken Sie auf **lync Server System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="e2c5a-159">![Bereitstellungs-Assistent für lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Bereitstellungs-Assistent für lync Server 2013")</span><span class="sxs-lookup"><span data-stu-id="e2c5a-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="e2c5a-160">Wenn Sie eine lokale Kopie des Konfigurationsspeichers installieren und die erforderlichen Dienste starten möchten, lesen Sie [Einrichten der Front-End-Server und der Front-End-Pools für lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e2c5a-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

