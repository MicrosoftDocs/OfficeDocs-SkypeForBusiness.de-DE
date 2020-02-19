---
title: Bereitstellen lync Server 2013 Pilot-Pools
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
ms.openlocfilehash: 95ce311b5b7c47343c3ec72bf63a7d1b96cf9839
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="37913-102">Bereitstellen lync Server 2013 Pilot-Pools</span><span class="sxs-lookup"><span data-stu-id="37913-102">Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37913-103">_**Letztes Änderungsstand des Themas:** 2013-11-22_</span><span class="sxs-lookup"><span data-stu-id="37913-103">_**Topic Last Modified:** 2013-11-22_</span></span>

<span data-ttu-id="37913-104">Einer der ersten Schritte, die für die Migration zu lync Server 2013 erforderlich sind, ist die Bereitstellungeines pilotpools.</span><span class="sxs-lookup"><span data-stu-id="37913-104">One of the first steps required for migration to Lync Server 2013 is to deploy a pilot pool.</span></span> <span data-ttu-id="37913-105">Der Pilot Pool testet die Koexistenz von lync Server 2013 mit Ihrer Office Communications Server 2007 R2-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="37913-105">The pilot pool is where you test coexistence of Lync Server 2013 with your Office Communications Server 2007 R2 deployment.</span></span> <span data-ttu-id="37913-106">Koexistenz ist ein temporärer Zustand, der dauert, bis Sie alle Benutzer und Pools in lync Server 2013 verschoben haben.</span><span class="sxs-lookup"><span data-stu-id="37913-106">Coexistence is a temporary state that lasts until you have moved all users and pools to Lync Server 2013.</span></span>

<span data-ttu-id="37913-107">Beim Bereitstellen eines Pilotpools verwenden Sie den Assistenten zum Definieren eines neuen Front-End-Pools.</span><span class="sxs-lookup"><span data-stu-id="37913-107">When you deploy a pilot pool, you use the Define New Front End Pool wizard.</span></span> <span data-ttu-id="37913-108">Sie sollten dieselben Funktionen und Arbeitslasten in Ihrem lync Server 2013 Pilot-Pool bereitstellen, die Sie in Ihrem Office Communications Server 2007 R2-Pool haben.</span><span class="sxs-lookup"><span data-stu-id="37913-108">You should deploy the same features and workloads in your Lync Server 2013 pilot pool that you have in your Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="37913-109">Wenn Sie Archivierungsserver, Monitoring Server oder System Center Operations Manager zur Archivierung oder Überwachung Ihrer Office Communications Server 2007 R2 Umgebung bereitgestellt haben und die Archivierung oder Überwachung während der gesamten Migration fortsetzen möchten, müssen Sie Stellen Sie diese Features auch in ihrer Pilotumgebung bereit.</span><span class="sxs-lookup"><span data-stu-id="37913-109">If you deployed Archiving Server, Monitoring Server, or System Center Operations Manager for archiving or monitoring your Office Communications Server 2007 R2 environment, and you want to continue archiving or monitoring throughout the migration, you need to also deploy these features in your pilot environment.</span></span> <span data-ttu-id="37913-110">Die Version, die Sie zum Archivieren oder Überwachen Ihrer Office Communications Server 2007 R2 Umgebung bereitgestellt haben, erfasst keine Daten in ihrer lync Server 2013 Umgebung.</span><span class="sxs-lookup"><span data-stu-id="37913-110">The version you deployed to archive or monitor your Office Communications Server 2007 R2 environment will not capture data in your Lync Server 2013 environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="37913-111">In den nachfolgenden Verfahren werden Features und Einstellungen behandelt, die Sie im Rahmen des allgemeinen Bereitstellungsprozesses für Pilotpools berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="37913-111">The following procedure discusses features and settings you should consider as part of your overall pilot pool deployment process.</span></span> <span data-ttu-id="37913-112">In diesem Abschnitt sind nur die wichtigsten zu beachtenden Punkte für die Bereitstellung Ihres Pilotpools hervorgehoben.</span><span class="sxs-lookup"><span data-stu-id="37913-112">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="37913-113">Ausführliche Anweisungen finden Sie im Bereitstellungshandbuch zur <A href="lync-server-2013-deploying-lync-server.md">Bereitstellung lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="37913-113">For detailed steps, refer to the <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> deployment guide.</span></span>



</div>

<span data-ttu-id="37913-114">**So stellen Sie einen lync Server 2013-Pilot Pool bereit**</span><span class="sxs-lookup"><span data-stu-id="37913-114">**To deploy a Lync Server 2013 pilot pool**</span></span>

1.  <span data-ttu-id="37913-115">Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.</span><span class="sxs-lookup"><span data-stu-id="37913-115">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="37913-116">Öffnen Sie den Topologie-Generator, und wählen Sie die Option zur Erstellung einer neuen Topologie aus.</span><span class="sxs-lookup"><span data-stu-id="37913-116">Open Topology Builder and choose to create a new topology.</span></span>

3.  <span data-ttu-id="37913-117">Geben Sie die primäre SIP-Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="37913-117">Enter the primary SIP domain.</span></span>
    
    <span data-ttu-id="37913-118">![Neue Topologie erstellen, primäre Domänen Seite definieren](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Neue Topologie erstellen, primäre Domänen Seite definieren")</span><span class="sxs-lookup"><span data-stu-id="37913-118">![Create New Topology, Define primary domain page](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Create New Topology, Define primary domain page")</span></span>

4.  <span data-ttu-id="37913-119">Fahren Sie mit der Fertigstellung des Assistenten fort, bis Sie zum Assistenten zum **Definieren eines neuen Front-End-Pools** gelangen.</span><span class="sxs-lookup"><span data-stu-id="37913-119">Continue completing the wizard until you reach the **Define the New Front End pool** wizard.</span></span> <span data-ttu-id="37913-120">Klicken Sie auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="37913-120">Click Next.</span></span>

5.  <span data-ttu-id="37913-121">Geben Sie den Pool-FQDN ein.</span><span class="sxs-lookup"><span data-stu-id="37913-121">Enter the pool FQDN.</span></span> <span data-ttu-id="37913-122">Wenn Sie Ihren Pilot Pool definieren, können Sie eine Enterprise Edition-Front-End-Pool oder ein Standard Edition-Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="37913-122">When you define your pilot pool, you can choose to deploy an Enterprise Edition Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="37913-123">Lync Server 2013 erfordert nicht, dass Ihre Pilot-Pool-Features mit dem übereinstimmen, was in Ihrem Legacy-Pool bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37913-123">Lync Server 2013 does not require that your pilot pool features match what was deployed in your legacy pool.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="37913-124">Der vollqualifizierte Domänenname (FQDN) des Pools oder Servers, den Sie für den Pilotpool festlegen, muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="37913-124">The pool or server fully qualified domain name (FQDN) that you define for the pilot pool must be unique.</span></span> <span data-ttu-id="37913-125">Er kann nicht mit dem Namen des derzeit bereitgestellten Office Communications Server 2007 R2 Pools oder anderen derzeit bereitgestellten Servern übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="37913-125">It cannot match the name of the currently deployed Office Communications Server 2007 R2 pool, or any other servers currently deployed.</span></span>

    
    </div>
    
    <span data-ttu-id="37913-126">![Definieren der Seite "Front-End-Pool FQDN"](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definieren der Seite "Front-End-Pool FQDN"")</span><span class="sxs-lookup"><span data-stu-id="37913-126">![Define the Front End pool FQDN page](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Define the Front End pool FQDN page")</span></span>

6.  <span data-ttu-id="37913-127">Legen Sie den Computer fest, der dem Pool hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="37913-127">Define the computer that will be added to the pool.</span></span>
    
    <span data-ttu-id="37913-128">![Dialogfeld "neuen Front-End-Pool definieren"](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Dialogfeld "neuen Front-End-Pool definieren"")</span><span class="sxs-lookup"><span data-stu-id="37913-128">![Define New Front End Pool dialog](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Define New Front End Pool dialog")</span></span>

7.  <span data-ttu-id="37913-129">Aktivieren Sie auf der Seite **Features auswählen** die Kontrollkästchen für die Features, die in diesem Front-End-Pool werden sollen.</span><span class="sxs-lookup"><span data-stu-id="37913-129">On the **Select features** page, select the check boxes for the features that you want on this Front End pool.</span></span> <span data-ttu-id="37913-130">Wenn Sie beispielsweise nur Chatnachrichten und Anwesenheitsfunktionen bereitstellen, aktivieren Sie das Kontrollkästchen Konferenzen, um mehr Parteien-Chat zu ermöglichen, aber nicht die Kontrollkästchen Einwahl (PSTN) Conferencing, Enterprise-VoIP oder Anrufsteuerung aktivieren, Da Sie sprach-, Video-und kollaborative Konferenzfunktionen darstellen.</span><span class="sxs-lookup"><span data-stu-id="37913-130">For example, if you are deploying only instant messaging (IM) and presence features, you would select the Conferencing check box to allow multiparty IM, but would not select the Dial-in (PSTN) conferencing, Enterprise Voice, or Call Admission Control check boxes, because they represent voice, video, and collaborative conferencing features.</span></span> <span data-ttu-id="37913-131">Weitere Informationen zum Auswählen von Features finden Sie unter [define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="37913-131">For additional information on selecting features, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.</span></span>
    
    <span data-ttu-id="37913-132">![Front-End-Pool Features auswählen (Seite)](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front-End-Pool Features auswählen (Seite)")</span><span class="sxs-lookup"><span data-stu-id="37913-132">![Front End Pool Select features page](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Front End Pool Select features page")</span></span>

8.  <span data-ttu-id="37913-133">Auf der Seite **"verbundene Serverrollen auswählen** " wird empfohlen, die Vermittlungsserver in lync Server 2013 collocate.</span><span class="sxs-lookup"><span data-stu-id="37913-133">On the **Select collocated server roles** page, we recommend you collocate the Mediation Server in Lync Server 2013.</span></span> <span data-ttu-id="37913-134">Wenn Sie eine Legacy Topologie mit lync Server 2013 zusammenführen, müssen Sie zuerst die Office Communications Server 2007 R2 Vermittlungsserver collocate.</span><span class="sxs-lookup"><span data-stu-id="37913-134">When merging a legacy topology with Lync Server 2013, we require that you first collocate the Office Communications Server 2007 R2 Mediation Server.</span></span> <span data-ttu-id="37913-135">Nachdem Sie die Topologien zusammengeführt und die lync Server 2013 Vermittlungsserver konfiguriert haben, können Sie entscheiden, ob Sie die verbundenen Vermittlungsserver beibehalten oder Sie in einen eigenständigen Server ändern möchten, wenn Sie die Vermittlungsserver Rolle später in der Bereitstellung zu lync Server 2013 wechseln. Prozess.</span><span class="sxs-lookup"><span data-stu-id="37913-135">After merging the topologies and configuring the Lync Server 2013 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Lync Server 2013 later in the deployment process.</span></span>
    
    <span data-ttu-id="37913-136">![Front-End-Pool auswählen der Seite "verbundene Serverrollen"](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front-End-Pool auswählen der Seite "verbundene Serverrollen"")</span><span class="sxs-lookup"><span data-stu-id="37913-136">![Front End Pool Select collocated server roles page](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Front End Pool Select collocated server roles page")</span></span>

9.  <span data-ttu-id="37913-p109">Wählen Sie auf der Seite **Serverrollen diesem Front-End-Pool zuordnen** während einer Pilotpoolbereitstellung nicht die Option **Edgepool zur Verwendung durch die Medienkomponente dieses Front-End-Pools auswählen** aus. Diese Funktion wird in einer späteren Phase der Migration aktiviert und online geschaltet. Lassen Sie diese Einstellung zu diesem Zeitpunkt deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="37913-p109">On the **Associate server roles with this Front End pool** page, during pilot pool deployment, do not choose the **Enable an Edge pool to be used by the media component of this Front End pool** option. This is a feature you will enable and bring online in a later phase of migration. Keep this setting cleared for now.</span></span>
    
    <span data-ttu-id="37913-140">![Zuordnen von Serverrollen zu Front-End-Pool Seite](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Zuordnen von Serverrollen zu Front-End-Pool Seite")</span><span class="sxs-lookup"><span data-stu-id="37913-140">![Associate server roles with Front End pool page](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associate server roles with Front End pool page")</span></span>

10. <span data-ttu-id="37913-141">Klicken Sie auf der Seite **Einen Office Web Apps-Server auswählen** auf **Neu**, und geben Sie den FQDN des Anwendungsservers an.</span><span class="sxs-lookup"><span data-stu-id="37913-141">On the **Select an Office Web Apps Server** page, click **New**, and specify the FQDN of the application server.</span></span>
    
    <span data-ttu-id="37913-142">![Definieren neuer Eigenschaften des Office-webapps-Server-FQDN](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definieren neuer Eigenschaften des Office-webapps-Server-FQDN")</span><span class="sxs-lookup"><span data-stu-id="37913-142">![Define New Office Web Apps Server FQDN properties](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Define New Office Web Apps Server FQDN properties")</span></span>

11. <span data-ttu-id="37913-143">Wählen Sie auf der Seite **Archivierungs SQL Server Speicher definieren** die SQL Server Instanz aus, die zuvor für lync Server 2013 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37913-143">On the **Define the Archiving SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span>
    
    <span data-ttu-id="37913-144">![Seite "Archivierung SQL Server Speicher definieren"](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Seite "Archivierung SQL Server Speicher definieren"")</span><span class="sxs-lookup"><span data-stu-id="37913-144">![Define Archiving SQL Server store page](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Define Archiving SQL Server store page")</span></span>

12. <span data-ttu-id="37913-145">Wählen Sie auf der Seite **Überwachung SQL Server Speicher definieren** die SQL Server Instanz aus, die zuvor für lync Server 2013 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37913-145">On the **Define the Monitoring SQL Server store** page, select the SQL Server instance created earlier for Lync Server 2013.</span></span> <span data-ttu-id="37913-146">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="37913-146">Click **Finish**.</span></span>

13. <span data-ttu-id="37913-p111">Klicken Sie im obersten Knoten des Topologie-Generators mit der rechten Maustaste auf **Lync Server**, und klicken Sie dann auf **Eigenschaften bearbeiten.** Klicken Sie auf **Einfache URLs**.</span><span class="sxs-lookup"><span data-stu-id="37913-p111">From the top node of Topology Builder, right click **Lync Server** and click **Edit Properties.** Click **Simple URLs**.</span></span>

14. <span data-ttu-id="37913-149">Aktualisieren Sie die **URL für administrativen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="37913-149">Update the **Administrative access URL**.</span></span>
    
    <span data-ttu-id="37913-150">![Bearbeiten von Eigenschaften, einfache URLs (Seite)](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Bearbeiten von Eigenschaften, einfache URLs (Seite)")</span><span class="sxs-lookup"><span data-stu-id="37913-150">![Edit Properties, Simple URLs page](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Edit Properties, Simple URLs page")</span></span>
    
    <span data-ttu-id="37913-151">Weitere Informationen zu einfachen URLs finden Sie im Thema [Bearbeiten oder konfigurieren einfacher URLs in lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="37913-151">For additional information on Simple URLs, see the topic [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

15. <span data-ttu-id="37913-152">Klicken Sie unter **Eigenschaften bearbeiten** auf **Zentraler Verwaltungsserver**.</span><span class="sxs-lookup"><span data-stu-id="37913-152">From the **Edit Properties**, click **Central Management Server**.</span></span>

16. <span data-ttu-id="37913-153">Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.</span><span class="sxs-lookup"><span data-stu-id="37913-153">From the drop-down list, select the Lync Server 2013 pool.</span></span>
    
    <span data-ttu-id="37913-154">![Bearbeiten von Eigenschaften, Seite des zentralen Verwaltungsservers](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Bearbeiten von Eigenschaften, Seite des zentralen Verwaltungsservers")</span><span class="sxs-lookup"><span data-stu-id="37913-154">![Edit Properties, Central Management Server page](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Edit Properties, Central Management Server page")</span></span>

17. <span data-ttu-id="37913-155">Klicken Sie auf "OK" um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37913-155">Click OK to close **the Edit Properties** page.</span></span>

18. <span data-ttu-id="37913-156">Wählen Sie im Menü **Aktion** den Eintrag **Topologie veröffentlichen** aus.</span><span class="sxs-lookup"><span data-stu-id="37913-156">From the **Action** menu, select **Publish Topology**.</span></span>

19. <span data-ttu-id="37913-157">Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="37913-157">When the publish process has completed, click **Finish**.</span></span>

20. <span data-ttu-id="37913-158">Wenn Sie zum lync Server 2013-Bereitstellungs-Assistenten zurückkehren, klicken Sie auf **lync Server System installieren oder aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="37913-158">Returning to the Lync Server 2013 Deployment Wizard, click **Install or Update Lync Server System**.</span></span>
    
    <span data-ttu-id="37913-159">![Lync Server 2013-Bereitstellungs-Assistent](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013-Bereitstellungs-Assistent")</span><span class="sxs-lookup"><span data-stu-id="37913-159">![Lync Server 2013 Deployment Wizard](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 Deployment Wizard")</span></span>

<span data-ttu-id="37913-160">Informationen zum Installieren einer lokalen Kopie des Konfigurationsspeichers und zum Starten der erforderlichen Dienste finden Sie unter [Einrichten von Front-End-Servern und Front-End-Pools für lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="37913-160">To install a local copy of the configuration store and start the required services, see [Setting up Front End Servers and Front End pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.</span></span>


</div>

<span> </span>

</div>

</div>

</div>

