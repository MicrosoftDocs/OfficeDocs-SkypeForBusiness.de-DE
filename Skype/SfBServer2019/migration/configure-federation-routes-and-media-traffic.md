---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Verbund bezeichnet eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nach der Migration zum pilotpool müssen Sie für den Übergang von der partnerverbundroute Ihrer früherer Versionen Edge-Servern auf die partnerverbundroute von Ihrer Skype für Business Server 2019 Edge-Server.
ms.openlocfilehash: 607d98c3c831ae9fd911b9fd2782490dcfb0e4f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238744"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="81165-104">Konfigurieren von Partnerverbundrouten und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="81165-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="81165-105">Verbund bezeichnet eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="81165-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="81165-106">Nach der Migration zum pilotpool müssen Sie für den Übergang von der partnerverbundroute des Edge-Server der Vorversion auf die partnerverbundroute von Ihrer Skype für Business Server 2019 Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="81165-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="81165-107">Verwenden Sie die folgenden Verfahren, um die partnerverbundroute und die mediendatenverkehrsroute aus der vorherigen Version Edge-Server und Director auf Ihre Skype für Business Server 2019 Edge-Server für die Bereitstellung mit einem einzigen Standort umzustellen.</span><span class="sxs-lookup"><span data-stu-id="81165-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="81165-108">Ändern die partnerverbundroute und die mediendatenverkehrsroute erfordert, dass Sie Ausfallzeiten Wartung für die Skype für Business Server 2019 und die vorherige Version Edge-Servern planen.</span><span class="sxs-lookup"><span data-stu-id="81165-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="81165-109">Dieser Übergangsprozess für die gesamte bedeutet auch, dass federated Zugriff für die Dauer des Ausfalls verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="81165-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="81165-110">Sie sollten die Downtime für einen Zeitraum planen, wenn Sie eine minimale Benutzeraktivität erwarten.</span><span class="sxs-lookup"><span data-stu-id="81165-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="81165-111">Sie sollten auch über ausreichende Benachrichtigung für die Endbenutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="81165-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="81165-112">Planen Sie entsprechend für diese Ausfall und Festlegen der entsprechenden erwartet innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="81165-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="81165-113">Wenn Ihrem älteren Edge-Server, zum Verwenden von des FQDN für Zugriffs-edgedienst, Webkonferenz-edgedienst und A konfiguriert ist / V-Edgeserver die Verfahren in diesem Abschnitt werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81165-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="81165-114">Wenn die legacy-Edge-Diensten für die Verwendung von des FQDN konfiguriert sind, müssen Sie zuerst alle Ihre Benutzer migrieren dann außer Betrieb nehmen die früheren Versionen Edge-Server, bevor Sie auf die Skype-Verbund für Business Server 2019 Edge-Server aktivieren.</span><span class="sxs-lookup"><span data-stu-id="81165-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="81165-115">Wenn Sie über einen Skype XMPP-Verbund für Business Server 2019 Edge-Server weitergeleitet wird, Benutzer auf die vorherige Version werden nicht mit den XMPP-Verbundpartner zu kommunizieren, bis alle Benutzer zu Skype für Business Server 2019, XMPP-Richtlinien verschoben wurden und Zertifikate konfiguriert wurden, der XMPP-Verbundpartner auf Skype für Business Server 2019 konfiguriert wurde und, schließlich die DNS-Einträge wurden aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="81165-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="81165-116">Um die partnerverbundzuordnung der Vorversion aus Skype für Business Server 2019 Websites zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="81165-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="81165-117">Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server die bestehende Topologie im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="81165-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="81165-118">Navigieren Sie im linken Bereich zum Standortknoten, die sich direkt unterhalb **Skype für Business Server**befindet.</span><span class="sxs-lookup"><span data-stu-id="81165-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="81165-119">Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81165-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="81165-120">Wählen Sie im linken Bereich die Option **partnerverbundroute**aus.</span><span class="sxs-lookup"><span data-stu-id="81165-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="81165-121">Deaktivieren Sie das Kontrollkästchen **SIP-Partnerverbund aktivieren** , um die partnerverbundroute über die legacy-Umgebung zu deaktivieren, klicken Sie unter **Zuweisung der partnerverbundroute Route**.</span><span class="sxs-lookup"><span data-stu-id="81165-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="81165-122">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="81165-123">Wählen Sie **Topologie-Generator**den obersten Knoten **Skype für Business Server**ein.</span><span class="sxs-lookup"><span data-stu-id="81165-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="81165-124">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="81165-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="81165-125">Klicken Sie auf **Weiter** , um die Veröffentlichung abzuschließen, und klicken Sie dann auf **Fertig stellen** , wenn der Veröffentlichungsvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="81165-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="81165-126">So konfigurieren Sie die Edgeserver der Vorversion als nicht-Partnerverbund-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="81165-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="81165-127">Navigieren Sie im linken Bereich auf den Knoten legacy installieren und dann auf den Knoten **Edge-Pools** .</span><span class="sxs-lookup"><span data-stu-id="81165-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="81165-128">Maustaste auf den Edge-Server, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81165-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="81165-129">Wählen Sie im linken Bereich **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="81165-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="81165-130">Deaktivieren Sie das Kontrollkästchen **Partnerverbund für diesen edgepool (Port 5061) aktivieren** , und wählen Sie **OK** , um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="81165-131">Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="81165-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="81165-132">Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="81165-133">Stellen Sie sicher, dass im Topologie-Generator-Verbund für Edgeserver der Vorversion deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="81165-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="81165-134">So konfigurieren Sie Zertifikate auf dem Edgeserver der Vorversion</span><span class="sxs-lookup"><span data-stu-id="81165-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="81165-135">Exportieren Sie das externe zugriffsproxyzertifikat, mit dem privaten Schlüssel, aus dem legacy-Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="81165-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="81165-136">Auf der Skype für Business Server 2019 Edge-Server und importieren die Zugriffsproxy externe Zertifikat aus dem vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="81165-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="81165-137">Weisen Sie das externe zugriffsproxyzertifikat der Skype für Business Server 2019 externe Schnittstelle des Edgeservers.</span><span class="sxs-lookup"><span data-stu-id="81165-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="81165-138">Das interne schnittstellenzertifikat des der Skype für Business Server 2019 Edge-Server sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="81165-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="81165-139">So ändern Sie die vorherige Version partnerverbundroute die Verwendung Skype für Business Server 2019 Edge-Server verwenden</span><span class="sxs-lookup"><span data-stu-id="81165-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="81165-140">Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Knoten **edgepools** .</span><span class="sxs-lookup"><span data-stu-id="81165-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="81165-141">Maustaste auf den Edge-Server, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81165-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="81165-142">Wählen Sie im linken Bereich **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="81165-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="81165-143">Aktivieren Sie das Kontrollkästchen für **Partnerverbund für diesen edgepool (Port 5061) aktivieren**, und klicken Sie dann auf **OK** , um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="81165-144">Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="81165-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="81165-145">Wenn der **Veröffentlichen-Assistent** abgeschlossen ist, klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="81165-146">Stellen Sie sicher, dass **Partnerverbund (Port 5061)** **aktiviert** im Topologie-Generator ist.</span><span class="sxs-lookup"><span data-stu-id="81165-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="81165-147">So aktualisieren Sie Skype für Business Server 2019 Edge-Server den nächsten partnerverbundhop</span><span class="sxs-lookup"><span data-stu-id="81165-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="81165-148">Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Knoten **edgepools** .</span><span class="sxs-lookup"><span data-stu-id="81165-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="81165-149">Erweitern Sie den Knoten rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81165-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="81165-150">Wählen Sie auf der Seite **Allgemein** unter **Auswahl für nächsten Hop**aus der Dropdown Liste der Skype für Business Server 2019 Pool.</span><span class="sxs-lookup"><span data-stu-id="81165-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="81165-151">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="81165-152">Wählen Sie **Topologie-Generator**den obersten Knoten **Skype für Business Server**ein.</span><span class="sxs-lookup"><span data-stu-id="81165-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="81165-153">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="81165-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="81165-154">So konfigurieren Sie Skype für ausgehenden Medienpfad Business Server 2019 Edge-Server</span><span class="sxs-lookup"><span data-stu-id="81165-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="81165-155">Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**aus.</span><span class="sxs-lookup"><span data-stu-id="81165-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="81165-156">Mit der rechten Maustaste in des Pools, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81165-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="81165-157">Wählen Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **edgepool zuordnen (für Medienkomponenten)** .</span><span class="sxs-lookup"><span data-stu-id="81165-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="81165-158">Wählen Sie aus dem Dropdown-Feld die Skype für Business Server 2019 Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="81165-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="81165-159">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="81165-160">So aktivieren Sie Skype für den Verbund Business Server 2019 Edge-Server</span><span class="sxs-lookup"><span data-stu-id="81165-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="81165-161">Navigieren Sie Topologie-Generator im linken Bereich zum Knoten **Skype für Business Server 2019** , und klicken Sie dann zum Knoten **edgepools** .</span><span class="sxs-lookup"><span data-stu-id="81165-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="81165-162">Erweitern Sie den Knoten rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81165-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="81165-163">Verbund kann nur für einen einzelnen edgepool aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="81165-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="81165-164">Wenn Sie mehrere edgepools haben, wählen Sie eine als der Föderationspartner Edge-Pool verwenden.</span><span class="sxs-lookup"><span data-stu-id="81165-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="81165-165">Stellen Sie auf der Seite **Allgemein** sicher, dass das Kontrollkästchen **Partnerverbund für diesen edgepool (Port 5061) aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="81165-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="81165-166">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="81165-167">Navigieren Sie zum Standortknoten.</span><span class="sxs-lookup"><span data-stu-id="81165-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="81165-168">Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="81165-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="81165-169">Klicken Sie im linken Bereich auf **partnerverbundroute**.</span><span class="sxs-lookup"><span data-stu-id="81165-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="81165-170">Klicken Sie unter **Zuweisung der partnerverbundroute Route**wählen Sie **SIP-Partnerverbund aktivieren**aus, und wählen Sie dann in der Liste der Skype für Business Server 2019 Edge-Server aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="81165-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="81165-171">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="81165-172">Führen Sie für Bereitstellungen mit mehreren Standorten dieses Verfahren an jedem Standort.</span><span class="sxs-lookup"><span data-stu-id="81165-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="81165-173">So veröffentlichen Edgeserver-konfigurationsänderungen</span><span class="sxs-lookup"><span data-stu-id="81165-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="81165-174">Wählen Sie **Topologie-Generator**den obersten Knoten **Skype für Business Server**ein.</span><span class="sxs-lookup"><span data-stu-id="81165-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="81165-175">Klicken Sie im Menü **Aktion** wählen Sie **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="81165-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="81165-176">Warten Sie Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="81165-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81165-177">Sie können die folgende Meldung angezeigt: **Warnung: die Topologie enthält mehr als eine Federated Edge-Server. Dies kann vorkommen, während der Migration zu einer neueren Version des Produkts. In diesem Fall würde nur einen Edge-Server aktiv für den Verbund verwendet werden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den entsprechenden Edge-Server verweist. Wenn Sie mehrere Verbund Edge-Server bereitstellen möchten gleichzeitig aktiv (d. h., keinem Migrationsszenario), stellen Sie sicher, dass alle Verbundpartnern Skype für Business Server verwenden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag alle Edgeserver für den Verbund aktiviert sind.**</span><span class="sxs-lookup"><span data-stu-id="81165-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="81165-178">Diese Warnung entspricht der Erwartung und kann ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="81165-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="81165-179">So konfigurieren Sie Skype für Business Server 2019 Edge-Server</span><span class="sxs-lookup"><span data-stu-id="81165-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="81165-180">Schalten Sie alle die Skype online für Business Server 2019 Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="81165-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="81165-181">Aktualisieren der externen Firewall Routingregeln oder die Hardware Load Balancer Einstellungen zum Senden von SIP-Datenverkehr für den externen Zugriff (normalerweise port 443) und Verbund (normalerweise port 5061), der Skype für Business Server 2019 Edge-Server, anstatt Edgeserver der Vorversion.</span><span class="sxs-lookup"><span data-stu-id="81165-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="81165-182">Wenn Sie nicht über ein Hardwaregerät zum Lastenausgleich verfügen, müssen Sie den DNS-A-Eintrag für den Verbund zum Auflösen in die neue Skype für Business Server-Zugriffs-Edgeserver zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="81165-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="81165-183">Zu diesem Zweck mit minimaler Beeinträchtigung verringern Sie den Wert TLL für die externe Skype für Business Server Access Edge-FQDN, so, dass bei einer Aktualisierung DNS so zeigen Sie auf die neue Skype für Business Server-Zugriffsedge partnerverbunds und Remotezugriffs schnell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="81165-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="81165-184">Beenden Sie die **Skype für Business Server-Zugriffsedge** auf jedem Computer mit Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="81165-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="81165-185">Öffnen Sie auf jedem Computer mit älteren Edge-Server das Applet **Dienste** in **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="81165-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="81165-186">Suchen Sie in der Dienstliste **Skype für Business Server-Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="81165-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="81165-187">Maustaste auf die Dienste, und wählen Sie dann auf **Beenden** , um den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="81165-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="81165-188">Legen Sie den Starttyp auf **deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="81165-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="81165-189">Klicken Sie auf **OK** , um **das Eigenschaftenfenster** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="81165-189">Click **OK** to close the **Properties** window.</span></span> 
    

