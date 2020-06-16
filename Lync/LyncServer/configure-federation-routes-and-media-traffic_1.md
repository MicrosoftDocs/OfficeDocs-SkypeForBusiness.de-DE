---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: ed6cb922-7863-453a-adce-2ce0ba761d74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721925(v=OCS.15)
ms:contentKeyID: 49733860
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d6af77188809b092050629c1b74cdab8b20a2cc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754961"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="5c422-102">Konfigurieren von Partnerverbundrouten und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="5c422-102">Configure federation routes and media traffic</span></span>

 


<span data-ttu-id="5c422-103">Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5c422-103">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="5c422-104">Nachdem Sie zu Ihrem lync Server 2013 Pilot-Pool migriert haben, müssen Sie von der Verbund Route Ihrer Microsoft Office Communications Server 2007 R2-Edgeserver zur Verbund Route ihrer lync Server 2013 Edgeserver wechseln.</span><span class="sxs-lookup"><span data-stu-id="5c422-104">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Microsoft Office Communications Server 2007 R2 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="5c422-105">Führen Sie die folgenden Verfahren aus, um die partnerverbundroute und die Mediendaten Verkehrsroute von Ihrem Office Communications Server 2007 R2 Edgeserver und Directors zu Ihrem lync Server 2013 Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="5c422-105">Use the procedures that follow to transition the federation route and the media traffic route from your Office Communications Server 2007 R2 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>


> [!IMPORTANT]  
> <span data-ttu-id="5c422-106">Zum Ändern der Route für partnerverbundroute und Mediendatenverkehr müssen Sie Wartungs Ausfälle für die lync Server 2013-und Office Communications Server 2007 R2-Edgeserver planen.</span><span class="sxs-lookup"><span data-stu-id="5c422-106">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Office Communications Server 2007 R2 Edge Servers.</span></span> <span data-ttu-id="5c422-107">Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5c422-107">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="5c422-108">Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten.</span><span class="sxs-lookup"><span data-stu-id="5c422-108">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="5c422-109">Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren.</span><span class="sxs-lookup"><span data-stu-id="5c422-109">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="5c422-110">Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf.</span><span class="sxs-lookup"><span data-stu-id="5c422-110">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>




> [!IMPORTANT]  
> <span data-ttu-id="5c422-111">Wenn Ihr Legacy Office Communications Server 2007 R2 Edgeserver für die Verwendung desselben FQDN für die Zugriffs-Edgedienst, Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt zum Übergang der Verbund Einstellung zu einem lync Server 2013 Edgeserver nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5c422-111">If your legacy Office Communications Server 2007 R2 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section to transition the federation setting to a Lync Server 2013 Edge Server are not supported.</span></span> <span data-ttu-id="5c422-112">Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer von Office Communications Server 2007 R2 zu lync Server 2013 migrieren und dann die Office Communications Server 2007 R2 Edgeserver vor dem Aktivieren des partnerverbunds auf dem lync Server 2013 Edgeserver außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="5c422-112">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Office Communications Server 2007 R2 to Lync Server 2013, then decommission the Office Communications Server 2007 R2 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="5c422-113">Weitere Informationen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="5c422-113">For details, see the following topics:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="5c422-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Verbleibenden Benutzer in lync Server 2013 verlagern</A></span><span class="sxs-lookup"><span data-stu-id="5c422-114"><A href="move-remaining-users-to-lync-server-2013_1.md">Move remaining users to Lync Server 2013</A></span></span></P>
> <LI>
> <P><span data-ttu-id="5c422-115">"Entfernen von Servern und Serverrollen" unter<A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span><span class="sxs-lookup"><span data-stu-id="5c422-115">"Remove Servers and Server Roles" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268790">https://go.microsoft.com/fwlink/p/?LinkId=268790</A></span></span></P></LI></UL>




> [!IMPORTANT]  
> <span data-ttu-id="5c422-116">Wenn Ihr XMPP-Verbund über eine lync Server 2013 Edgeserver weitergeleitet wird, können Legacy Office Communications Server 2007 R2 Benutzer nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in lync Server 2013 verschoben wurden, XMPP-Richtlinien und Zertifikate konfiguriert wurden, der XMPP-Verbundpartner für lync Server 2013 konfiguriert wurde und schließlich die DNS-Einträge aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="5c422-116">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Office Communications Server 2007 R2 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



<span data-ttu-id="5c422-117">Für eine erfolgreiche Veröffentlichung, Aktivierung oder Deaktivierung einer Topologie beim Hinzufügen oder Entfernen einer Serverrolle müssen Sie als Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="5c422-117">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="5c422-118">Es ist auch möglich, die geeigneten Benutzerrechte und -berechtigungen für das Hinzufügen von Serverrollen zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="5c422-118">It is also possible to delegate the proper user rights and permissions for adding server roles.</span></span> <span data-ttu-id="5c422-119">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Standard Edition-Server-oder Enterprise Edition-Server-Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="5c422-119">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="5c422-120">Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.</span><span class="sxs-lookup"><span data-stu-id="5c422-120">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="5c422-121">So entfernen Sie die Partnerverbundzuordnung der Vorversion von Lync Server 2013-Standorten</span><span class="sxs-lookup"><span data-stu-id="5c422-121">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="5c422-122">Öffnen Sie mithilfe des Topologie-Generators die Pilotpooltopologie.</span><span class="sxs-lookup"><span data-stu-id="5c422-122">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="5c422-123">Navigieren Sie im linken Bereich zum Knoten Standort.</span><span class="sxs-lookup"><span data-stu-id="5c422-123">In the left pane, navigate to the site node.</span></span>

3.  <span data-ttu-id="5c422-124">Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5c422-124">Right-click the site, and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="5c422-125">Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.</span><span class="sxs-lookup"><span data-stu-id="5c422-125">Select **Federation route** in the left pane.</span></span>

5.  <span data-ttu-id="5c422-126">Deaktivieren Sie unter Standort Verbund Routen Zuweisung das Kontrollkästchen neben SIP-Partner **Verbund aktivieren** , um die partnerverbundroute über das **BackCompatSite**zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5c422-126">Under Site federation route assignment, clear the check box next to **Enable SIP federation** to disable the federation route through the **BackCompatSite**.</span></span>
    
    <span data-ttu-id="5c422-127">![Dialogfeld "Eigenschaften bearbeiten", Verbund Route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Verbund Route")</span><span class="sxs-lookup"><span data-stu-id="5c422-127">![Edit Properties dialog, Federation route](images/JJ721925.2a80c103-c0cc-43ed-ba00-420f9add006a(OCS.15).jpg "Edit Properties dialog, Federation route")</span></span>

6.  <span data-ttu-id="5c422-128">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c422-128">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="5c422-129">Wählen Sie im Topologie-Generator\*\*\*\* den obersten Knoten **Lync Server** aus.</span><span class="sxs-lookup"><span data-stu-id="5c422-129">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="5c422-130">Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="5c422-130">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="5c422-131">So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5c422-131">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="5c422-132">Klicken Sie im Topologie-Generator im Menü \*\*\*\*\*\*Aktionen\*\* auf **Office Communications Server 2007 R2-Topologie zusammenführen**.</span><span class="sxs-lookup"><span data-stu-id="5c422-132">From **Topology Builder**, from the **Action** menu click **Merge Office Communications Server 2007 R2 Topology**.</span></span>

2.  <span data-ttu-id="5c422-133">Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="5c422-133">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="5c422-134">Wählen Sie auf der Seite **Edgesetup angeben** unter **Interner FQDN des Edgeservers** den vollqualifizierten Domänennamen (FQDN) aus, der aktuell für den Partnerverbund konfiguriert ist, und klicken Sie dann auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="5c422-134">On the **Specify Edge Setup**, select the **Edge Server Internal FQDN** that is currently configured for federation, and then click **Change**.</span></span>
    
    <span data-ttu-id="5c422-135">![Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Zusammenführen der OCS 2007 R2-Topologie, angeben des Edge-Setups")</span><span class="sxs-lookup"><span data-stu-id="5c422-135">![Merge OCS 2007 R2 Topology, Specify Edge Setup](images/JJ721925.42c15aaf-c1ac-4fb1-a086-665835c57b23(OCS.15).jpg "Merge OCS 2007 R2 Topology, Specify Edge Setup")</span></span>

4.  <span data-ttu-id="5c422-136">Klicken Sie auf **Weiter**, und akzeptieren Sie die Standardeinstellungen, bis Sie zur Seite **Externen Edge angeben** gelangen:</span><span class="sxs-lookup"><span data-stu-id="5c422-136">Click **Next** and accept the default settings until you get to the **Specify External Edge** page:</span></span>
    
    <span data-ttu-id="5c422-137">![Topologie-Generator: Seite "externer Edge" angeben](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topologie-Generator: Seite "externer Edge" angeben")</span><span class="sxs-lookup"><span data-stu-id="5c422-137">![Topology Builder Specify External Edge page](images/JJ721925.e36f3a1f-3655-456e-9e6d-4814c37da0bf(OCS.15).jpg "Topology Builder Specify External Edge page")</span></span>

5.  <span data-ttu-id="5c422-138">Deaktivieren Sie unter **externer Edge angeben**das Kontrollkästchen **diese Edgepool wird für Verbund-und öffentliche Chat Verbindungen verwendet** .</span><span class="sxs-lookup"><span data-stu-id="5c422-138">In **Specify External Edge**, clear the **This Edge pool is used for federation and public IM connectivity** check box.</span></span> <span data-ttu-id="5c422-139">Dadurch wird die Verbund Zuordnung mit dem BackCompatSite entfernt.</span><span class="sxs-lookup"><span data-stu-id="5c422-139">This will remove the federation association with the BackCompatSite.</span></span>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5c422-140">This step is important.</span><span class="sxs-lookup"><span data-stu-id="5c422-140">This step is important.</span></span> <span data-ttu-id="5c422-141">You must clear this option to remove the legacy federation association.</span><span class="sxs-lookup"><span data-stu-id="5c422-141">You must clear this option to remove the legacy federation association.</span></span>



6.  <span data-ttu-id="5c422-142">Klicken Sie auf **Weiter**, und akzeptieren Sie die Standardeinstellungen der restlichen Seiten des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="5c422-142">Click **Next** and accept the default settings of the remaining pages of the wizard.</span></span>

7.  <span data-ttu-id="5c422-143">Klicken Sie auf der Seite **Zusammenfassung** auf **Weiter**, um mit dem Zusammenführen der Topologien zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="5c422-143">In **Summary**, click **Next** to begin merging the topologies.</span></span>

8.  <span data-ttu-id="5c422-144">Überprüfen Sie in der Spalte **Status** , ob der Wert **Erfolg**lautet, und klicken Sie dann auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c422-144">In the **Status** column, verify that the value is **Success**, and then click **Finish** to close the wizard.</span></span>

9.  <span data-ttu-id="5c422-145">Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5c422-145">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

10. <span data-ttu-id="5c422-146">Nach Abschluss des Veröffentlichungs-Assistenten\*\*\*\* klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c422-146">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>
    
    <span data-ttu-id="5c422-147">![Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topologie-Generator mit Website, die nach dem Zusammenführen angezeigt wird")</span><span class="sxs-lookup"><span data-stu-id="5c422-147">![Topology Builder with site displayed after merge](images/JJ721925.92b679ad-332f-49aa-b4e2-19f939b711ca(OCS.15).jpg "Topology Builder with site displayed after merge")</span></span>
    
    <span data-ttu-id="5c422-148">Wie in der vorherigen Abbildung gezeigt, ist der **SIP-Partnerverbund** unter **Zuweisung der Partnerverbundroute des Standorts** auf **Deaktiviert** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5c422-148">As shown in the previous figure, the **SIP federation** located under **Site federation route assignment** is set to **Disabled**.</span></span>

## <a name="to-configure-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="5c422-149">So konfigurieren Sie Zertifikate auf dem Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5c422-149">To configure certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="5c422-150">Exportieren Sie das externe Zugriffs Proxy Zertifikat mit dem privaten Schlüssel aus dem Legacy Office Communications Server 2007 R2 Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="5c422-150">Export the external Access Proxy certificate, with the private key, from the legacy Office Communications Server 2007 R2 Edge Server.</span></span>

2.  <span data-ttu-id="5c422-151">Importieren Sie im lync Server 2013 Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="5c422-151">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="5c422-152">Weisen Sie das externe Zertifikat des Zugriffsproxys der externen lync Server 2013-Schnittstelle des Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="5c422-152">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="5c422-153">Das interne Schnittstellen Zertifikat des lync Server 2013 Edgeserver sollte nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5c422-153">The internal interface certificate of the Lync Server 2013 Edge Server should not be changed.</span></span>

## <a name="to-change-office-communications-server-2007-r2-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="5c422-154">So legen Sie für die Office Communications Server 2007 R2-Partnerverbundroute die Verwendung des Lync Server 2013-Edgeservers fest</span><span class="sxs-lookup"><span data-stu-id="5c422-154">To change Office Communications Server 2007 R2 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="5c422-155">Öffnen Sie im Office Communications Server 2007 R2 Standard Edition-Server oder Front-End-Server das Office Communications Server 2007 R2 Verwaltungstool.</span><span class="sxs-lookup"><span data-stu-id="5c422-155">On the Office Communications Server 2007 R2 Standard Edition server or Front End Server, open the Office Communications Server 2007 R2 Administrative tool.</span></span>

2.  <span data-ttu-id="5c422-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span><span class="sxs-lookup"><span data-stu-id="5c422-156">In the left pane, expand the top node, and then right-click the **Forest** node.</span></span> <span data-ttu-id="5c422-157">Select **Properties**, and then click **Global Properties**.</span><span class="sxs-lookup"><span data-stu-id="5c422-157">Select **Properties**, and then click **Global Properties**.</span></span>

3.  <span data-ttu-id="5c422-158">Klicken Sie auf die Registerkarte **Partnerverbund**.</span><span class="sxs-lookup"><span data-stu-id="5c422-158">Click the **Federation** tab.</span></span>

4.  <span data-ttu-id="5c422-159">Aktivieren Sie das Kontrollkästchen Verbund und Verbindung mit öffentlichen Instant Messaging-Diensten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5c422-159">Select the check box to enable federation and Public IM connectivity.</span></span>

5.  <span data-ttu-id="5c422-160">Geben Sie den FQDN des lync Server 2013 Edgeserver ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c422-160">Enter the FQDN of the Lync Server 2013 Edge Server, and then click **OK**.</span></span>
    
    <span data-ttu-id="5c422-161">![Globale OCS-Eigenschaften, Registerkarte "Verbund"](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "Globale OCS-Eigenschaften, Registerkarte "Verbund"")</span><span class="sxs-lookup"><span data-stu-id="5c422-161">![OCS Global Properties, Federation tab](images/JJ721925.da633f72-43c6-4dac-8d37-ccd0dcde79c9(OCS.15).jpg "OCS Global Properties, Federation tab")</span></span>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="5c422-162">So aktivieren Sie den Partnerverbund für den Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5c422-162">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="5c422-163">Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten lync Server 2013- **Edge-Pools** .</span><span class="sxs-lookup"><span data-stu-id="5c422-163">From Topology Builder, in the left pane, navigate to the Lync Server 2013 **Edge pools** node.</span></span>

2.  <span data-ttu-id="5c422-164">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5c422-164">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="5c422-165">Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5c422-165">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="5c422-166">Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund-Edgepool verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="5c422-166">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>



3.  <span data-ttu-id="5c422-167">Aktivieren Sie auf der Seite **Allgemein** das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="5c422-167">On the **General** page, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
    
    <span data-ttu-id="5c422-168">![Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, Edge-Verbund aktivieren")</span><span class="sxs-lookup"><span data-stu-id="5c422-168">![Edit Properties, General, Enable Edge Federation](images/JJ721925.2aeb5958-da55-4910-b3d7-2124e144a2f0(OCS.15).jpg "Edit Properties, General, Enable Edge Federation")</span></span>

4.  <span data-ttu-id="5c422-169">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c422-169">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="5c422-170">Navigieren Sie anschließend zum Knoten Standort.</span><span class="sxs-lookup"><span data-stu-id="5c422-170">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="5c422-171">Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5c422-171">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="5c422-172">Klicken Sie im linken Bereich auf **Partnerverbundroute**.</span><span class="sxs-lookup"><span data-stu-id="5c422-172">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="5c422-173">Wählen Sie unter **Standort Verbund-Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann in der Liste den aufgelisteten lync Server 2013 Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="5c422-173">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>

9.  <span data-ttu-id="5c422-174">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c422-174">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="5c422-175">![Eigenschaften bearbeiten, allgemein, zuordnen Edgepool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, zuordnen Edgepool")</span><span class="sxs-lookup"><span data-stu-id="5c422-175">![Edit Properties, General, Associate Edge pool](images/JJ721925.33d43297-10cd-412e-bf4a-a1d9a84b9009(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>
    
    <span data-ttu-id="5c422-176">Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus.</span><span class="sxs-lookup"><span data-stu-id="5c422-176">For multi-site deployments, complete this procedure at each site.</span></span>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="5c422-177">So konfigurieren Sie den ausgehenden Medienpfad für den Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5c422-177">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="5c422-178">Navigieren Sie im **Topologie-Generator**zum lync Server 2013 Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.</span><span class="sxs-lookup"><span data-stu-id="5c422-178">From **Topology Builder**, navigate to the Lync Server 2013 pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="5c422-179">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5c422-179">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="5c422-180">Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="5c422-180">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>

4.  <span data-ttu-id="5c422-181">Wählen Sie im Dropdownfeld die lync Server 2013 Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="5c422-181">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>
    
    <span data-ttu-id="5c422-182">![Dialogfeld "Eigenschaften bearbeiten", "Edge-Pool zuordnen"](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", "Edge-Pool zuordnen"")</span><span class="sxs-lookup"><span data-stu-id="5c422-182">![Edit Properties dialog, Associate Edge Pool](images/JJ721925.0cb76b08-5923-4972-8d7a-a829cb77136b(OCS.15).jpg "Edit Properties dialog, Associate Edge Pool")</span></span>

5.  <span data-ttu-id="5c422-183">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c422-183">Click **OK** to close the **Edit Properties** page.</span></span>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="5c422-184">So veröffentlichen Sie Edgeserver-Konfigurationsänderungen</span><span class="sxs-lookup"><span data-stu-id="5c422-184">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="5c422-185">Wählen Sie im \*\*\*\* Topologie-Generator den obersten Knoten aus, **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5c422-185">From **Topology Builder**, select the top node **Lync Server**.</span></span>

2.  <span data-ttu-id="5c422-186">Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="5c422-186">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="5c422-187">Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.</span><span class="sxs-lookup"><span data-stu-id="5c422-187">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="5c422-188">Möglicherweise wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5c422-188">You may see the following message:</span></span><BR><span data-ttu-id="5c422-189"><STRONG>Warnung: Die Topologie enthält mehrere Partner-Edgeserver. Dies kann während der Migration auf eine höhere Version des Produkts geschehen. In diesem Fall wird nur ein Edgeserver aktiv für den Partnerverbund verwendet. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Partnerverbund-Edgeserver bereitstellen möchten, die gleichzeitig aktiv sind (kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Office Communications Server 2007 R2 oder höher verwenden. Stellen Sie außerdem sicher, dass der externe DNS-SRV-Eintrag alle partnerverbundfähigen Edgeserver auflistet.</STRONG></span><span class="sxs-lookup"><span data-stu-id="5c422-189"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Office Communications Server 2007 R2 or Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="5c422-190">Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="5c422-190">This warning is expected and can be safely ignored.</span></span>



## <a name="to-verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="5c422-191">So überprüfen Sie den Partnerverbund und den Remotezugriff für externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="5c422-191">To verify federation and remote access for external users</span></span>

1.  <span data-ttu-id="5c422-192">Öffnen Sie im lync Server 2013 Front-End-Server die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="5c422-192">From the Lync Server 2013 Front End Server, open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="5c422-193">Zum Überprüfen des Status des Partnerverbunds und des Remotezugriffs geben Sie an der Befehlszeile folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="5c422-193">To verify the status of federation and remote access, from the command line, type the following:</span></span>
    
        Get-CsAccessEdgeConfiguration

3.  <span data-ttu-id="5c422-194">Zum Aktivieren des Partnerverbunds und des Remotezugriffs geben Sie an der Befehlszeile folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="5c422-194">To enable federation and remote access, from the command line, type the following:</span></span>
    
        Set-CsAccessEdgeConfiguration
    
    <span data-ttu-id="5c422-195">Weitere Informationen zu diesen Cmdlets finden Sie in den folgenden Themen: [Get-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) und [Sets-csaccessedgeconfiguration nicht angeben](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="5c422-195">For more information on these cmdlets, see the following topics: [Get-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg398574\(v=ocs.15\)) and [Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/library/gg413017\(v=ocs.15\)).</span></span>

4.  <span data-ttu-id="5c422-196">Warten Sie, bis die Replikation abgeschlossen ist, bevor Sie die lync Server 2013-Edgeserver online schalten und den Partnerverbund und den externen Zugriff testen.</span><span class="sxs-lookup"><span data-stu-id="5c422-196">Wait until replication has completed before bringing the Lync Server 2013 Edge servers online, and testing federation and external access.</span></span>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="5c422-197">So konfigurieren Sie Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="5c422-197">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="5c422-198">Alle lync Server 2013-Edgeserver online schalten.</span><span class="sxs-lookup"><span data-stu-id="5c422-198">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="5c422-199">Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, um den SIP-Datenverkehr für den externen Zugriff (in der Regel Port 443) und den Verbund (in der Regel Port 5061) an die lync Server 2013 Edgeserver anstelle des Legacy Edgeserver zu senden.</span><span class="sxs-lookup"><span data-stu-id="5c422-199">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="5c422-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span><span class="sxs-lookup"><span data-stu-id="5c422-200">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve the new Lync Server Access Edge server.</span></span> <span data-ttu-id="5c422-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span><span class="sxs-lookup"><span data-stu-id="5c422-201">To accomplish this with minimum disruption, reduce the TTL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge server, federation and remote access will be updated quickly.</span></span>



3.  <span data-ttu-id="5c422-202">Beenden Sie als nächstes die **lync Server Zugriffs Kante** für jeden Edgeserver Computer.</span><span class="sxs-lookup"><span data-stu-id="5c422-202">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="5c422-203">Öffnen Sie auf jedem Computer mit Legacy Edgeserver das Applet **Dienste** über die **Verwaltungs Tools**.</span><span class="sxs-lookup"><span data-stu-id="5c422-203">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="5c422-204">Suchen Sie in der Liste mit den Diensten nach **Office Communications Server-Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="5c422-204">In the services list, find **Office Communications Server Access Edge**.</span></span>

6.  <span data-ttu-id="5c422-205">Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden**, um den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="5c422-205">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="5c422-206">Legen Sie als Starttyp **Deaktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="5c422-206">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="5c422-207">Klicken Sie auf **OK**, um das Fenster **Eigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5c422-207">Click **OK** to close the **Properties** window.</span></span>

## <a name="to-test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="5c422-208">So testen Sie die Anbindung externer Benutzer und den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="5c422-208">To Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="5c422-209">Benutzer aus mindestens einer Verbunddomäne, einem internen Benutzer auf lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="5c422-209">Users from at least one federated domain, an internal user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="5c422-210">Testen von Chatnachrichten, Anwesenheit, Audio/Video (A/V) und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="5c422-210">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="5c422-211">Benutzer aller öffentlichen Sofortnachrichten-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für die die Bereitstellung abgeschlossen ist), die mit einem Benutzer auf lync Server 2013 und einem Benutzer in Office Communications Server 2007 R2 kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="5c422-211">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="5c422-212">Überprüfen Sie, ob anonyme Benutzer in der Lage sind, an Konferenzen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="5c422-212">Verify anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="5c422-213">Ein Benutzer, der auf Office Communications Server 2007 R2 unter Verwendung des Remotebenutzerzugriffs (Anmeldung bei Office Communications Server 2007 R2 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="5c422-213">A user hosted on Office Communications Server 2007 R2 using remote user access (logging into Office Communications Server 2007 R2 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="5c422-214">Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="5c422-214">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="5c422-215">Ein Benutzer, der auf lync Server 2013 unter Verwendung des Remotebenutzerzugriffs (Anmeldung bei lync Server 2013 von außerhalb des Intranets, aber ohne VPN) mit einem Benutzer in lync Server 2013 und einem Benutzer auf Office Communications Server 2007 R2 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="5c422-215">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Office Communications Server 2007 R2.</span></span> <span data-ttu-id="5c422-216">Testen Sie Sofortnachrichten, Anwesenheit, A/V und Desktopfreigabe.</span><span class="sxs-lookup"><span data-stu-id="5c422-216">Test IM, presence, A/V, and desktop sharing.</span></span>

