---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Föderation ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die es Benutzern in separaten Organisationen ermöglicht, über Netzwerkgrenzen hinweg zu kommunizieren. Nachdem Sie die Migration zu Ihrem Pilot Pool durchgeführt haben, müssen Sie von der Föderations Route ihrer Vorgängerversionen-Edgeserver zur Föderations Route Ihrer Skype for Business Server 2019 Edge-Server wechseln.
ms.openlocfilehash: 71417307fd46c2c29535cea3a52f0286ad6dc951
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813813"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="dc025-104">Konfigurieren von Partnerverbundrouten und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="dc025-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="dc025-105">Föderation ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die es Benutzern in separaten Organisationen ermöglicht, über Netzwerkgrenzen hinweg zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="dc025-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="dc025-106">Nachdem Sie die Migration zu Ihrem Pilot Pool durchgeführt haben, müssen Sie von der Föderations Route der Edgeserver Ihrer vorherigen Version zur Föderations Route Ihrer Skype for Business Server 2019 Edge-Server wechseln.</span><span class="sxs-lookup"><span data-stu-id="dc025-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="dc025-107">Führen Sie die folgenden Verfahren aus, um die Föderations Route und die Mediendaten Verkehrsroute vom Edgeserver und Director der vorherigen Version zu Ihrem Skype for Business Server 2019 Edge-Server für eine Bereitstellung mit einem einzelnen Standort zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="dc025-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dc025-108">Für das Ändern der Route für die Föderations Route und den Mediendatenverkehr müssen Sie Wartungs Ausfälle für die Edgeserver von Skype for Business Server 2019 und früheren Versionen planen.</span><span class="sxs-lookup"><span data-stu-id="dc025-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="dc025-109">Dieser gesamte Übergangsprozess bedeutet auch, dass der Verbundzugriff für die Dauer des Ausfalls nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="dc025-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="dc025-110">Sie sollten die Downtime für eine Zeit planen, wenn Sie eine minimale Benutzeraktivität erwarten.</span><span class="sxs-lookup"><span data-stu-id="dc025-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="dc025-111">Darüber hinaus sollten Sie den Endbenutzern eine ausreichende Benachrichtigung senden.</span><span class="sxs-lookup"><span data-stu-id="dc025-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="dc025-112">Planen Sie für diesen Ausfall entsprechend, und setzen Sie in Ihrer Organisation angemessene Erwartungen.</span><span class="sxs-lookup"><span data-stu-id="dc025-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dc025-113">Wenn Ihr Legacy-Edgeserver für die Verwendung desselben FQDN für den Access-Edgedienst, den Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dc025-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="dc025-114">Wenn die Legacy Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Benutzer migrieren und dann den Edgeserver für frühere Versionen außer Betrieb setzen, bevor Sie den Verbund auf dem Skype for Business Server 2019 Edge-Server aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc025-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dc025-115">Wenn Ihr XMPP-Verbund über einen Skype for Business Server 2019 Edge-Server weitergeleitet wird, können Benutzer der vorherigen Version nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in Skype for Business Server 2019, XMPP-Richtlinien und Es wurden Zertifikate konfiguriert, der XMPP-Verbundpartner wurde in Skype for Business Server 2019 konfiguriert, und schließlich wurden die DNS-Einträge aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="dc025-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="dc025-116">So entfernen Sie die Legacy Federation Association von den Skype for Business Server 2019-Websites</span><span class="sxs-lookup"><span data-stu-id="dc025-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="dc025-117">Öffnen Sie auf dem Front-End-Server von Skype for Business Server 2019 die vorhandene Topologie im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="dc025-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="dc025-118">Navigieren Sie im linken Bereich zum Websiteknoten, der sich direkt unter **Skype for Business Server**befindet.</span><span class="sxs-lookup"><span data-stu-id="dc025-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="dc025-119">Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc025-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="dc025-120">Wählen Sie im linken Bereich **Föderations Route**aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="dc025-121">Deaktivieren Sie unter **Standort Verbund-Routen Zuweisung**das Kontrollkästchen **SIP-Verbund aktivieren** , um die Föderations Route über die Legacyumgebung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="dc025-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="dc025-122">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="dc025-123">Wählen Sie im **Topologie-Generator**den obersten Knoten von **Skype for Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="dc025-124">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="dc025-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="dc025-125">Klicken Sie auf **weiter** , um den Veröffentlichungsvorgang abzuschließen, und klicken Sie dann auf **Fertig stellen** , wenn der Veröffentlichungsvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="dc025-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="dc025-126">So konfigurieren Sie den Legacy-Edgeserver als nicht-Föderations-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="dc025-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="dc025-127">Navigieren Sie im linken Bereich zum Legacy Installations Knoten und dann zum Knoten Edge- **Pools** .</span><span class="sxs-lookup"><span data-stu-id="dc025-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="dc025-128">Klicken Sie mit der rechten Maustaste auf den Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc025-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="dc025-129">Wählen Sie im linken Bereich die Option **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="dc025-130">Deaktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** , und wählen Sie **OK** aus, um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="dc025-131">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc025-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="dc025-132">Klicken Sie nach Abschluss des **Veröffentlichungs-Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="dc025-133">Überprüfen Sie, ob der Verbund für den Legacy-Edgeserver im Topologie-Generator deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dc025-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="dc025-134">So konfigurieren Sie Zertifikate auf dem Legacy-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="dc025-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="dc025-135">Exportieren Sie das Proxy Zertifikat für den externen Zugriff mit dem privaten Schlüssel vom Legacy-Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="dc025-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="dc025-136">Klicken Sie auf dem Skype for Business Server 2019-Edgeserver, und importieren Sie das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="dc025-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="dc025-137">Weisen Sie das externe Zertifikat des Zugriffsproxys der externen Skype for Business Server 2019-Schnittstelle des Edge-Servers zu.</span><span class="sxs-lookup"><span data-stu-id="dc025-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="dc025-138">Das interne Schnittstellen Zertifikat des Skype for Business Server 2019 Edge-Servers sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="dc025-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="dc025-139">So ändern Sie die Föderations Route der vorherigen Version zur Verwendung von Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="dc025-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="dc025-140">Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum Knoten Edge- **Pools** .</span><span class="sxs-lookup"><span data-stu-id="dc025-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="dc025-141">Klicken Sie mit der rechten Maustaste auf den Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc025-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="dc025-142">Wählen Sie im linken Bereich die Option **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="dc025-143">Aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)**, und klicken Sie dann auf **OK** , um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="dc025-144">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen**aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc025-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="dc025-145">Klicken Sie nach Abschluss des **Veröffentlichungs-Assistenten** auf **Fertig stellen** , um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="dc025-146">Überprüfen Sie, ob der **Verbund (Port 5061)** im Topologie-Generator auf **aktiviert** festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="dc025-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="dc025-147">So aktualisieren Sie den nächsten Hop von Skype for Business Server 2019 Edge Server Federation</span><span class="sxs-lookup"><span data-stu-id="dc025-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="dc025-148">Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum Knoten Edge- **Pools** .</span><span class="sxs-lookup"><span data-stu-id="dc025-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="dc025-149">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc025-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="dc025-150">Wählen Sie auf der Seite **Allgemein** unter **Auswahl des nächsten Hop**in der Dropdownliste den Skype for Business Server 2019-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="dc025-151">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="dc025-152">Wählen Sie im **Topologie-Generator**den obersten Knoten von **Skype for Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="dc025-153">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="dc025-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="dc025-154">So konfigurieren Sie den ausgehenden Medienpfad für Skype for Business Server 2019 Edge Server</span><span class="sxs-lookup"><span data-stu-id="dc025-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="dc025-155">Navigieren Sie im linken Bereich des Topologie-Generators zum **Skype for Business Server 2019** -Knoten, und klicken Sie dann auf den Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.</span><span class="sxs-lookup"><span data-stu-id="dc025-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="dc025-156">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc025-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="dc025-157">Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edge-Pool zuordnen (für Medienkomponenten)** .</span><span class="sxs-lookup"><span data-stu-id="dc025-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="dc025-158">Wählen Sie im Dropdownfeld den Skype for Business Server 2019 Edge-Server aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="dc025-159">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="dc025-160">So aktivieren Sie den Skype for Business Server 2019 Edge Server-Verbund</span><span class="sxs-lookup"><span data-stu-id="dc025-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="dc025-161">Navigieren Sie vom Topologie-Generator im linken Bereich zum Knoten **Skype for Business Server 2019** und dann zum Knoten Edge- **Pools** .</span><span class="sxs-lookup"><span data-stu-id="dc025-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="dc025-162">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc025-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="dc025-163">Der Verbund kann nur für einen einzelnen Edge-Pool aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="dc025-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="dc025-164">Wenn Sie über mehrere Edge-Pools verfügen, wählen Sie eine aus, die Sie als Föderations-Edge-Pool verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="dc025-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="dc025-165">Überprüfen Sie auf der Seite **Allgemein** , ob das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="dc025-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="dc025-166">Klicken Sie auf **OK** , um die Seite Eigenschaften bearbeiten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="dc025-167">Navigieren Sie zum Websiteknoten.</span><span class="sxs-lookup"><span data-stu-id="dc025-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="dc025-168">Klicken Sie mit der rechten Maustaste auf die Website, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc025-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="dc025-169">Klicken Sie im linken Bereich auf **Föderations Route**.</span><span class="sxs-lookup"><span data-stu-id="dc025-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="dc025-170">Wählen Sie unter **Website Verbund-Routenzuordnung**die Option **SIP-Verbund aktivieren**aus, und wählen Sie dann in der Liste den Eintrag Skype for Business Server 2019 Edge Server aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="dc025-171">Klicken Sie auf **OK** , um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="dc025-172">Führen Sie für die Bereitstellung mehrerer Websites dieses Verfahren an jedem Standort aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="dc025-173">So veröffentlichen Sie Änderungen an Edge-Server-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="dc025-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="dc025-174">Wählen Sie im **Topologie-Generator**den obersten Knoten von **Skype for Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="dc025-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="dc025-175">Wählen Sie im Menü **Aktion** die Option **Topologie veröffentlichen** aus, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="dc025-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="dc025-176">Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="dc025-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc025-177">Möglicherweise wird die folgende Meldung angezeigt: **Warnung: die Topologie enthält mehr als einen Federated Edge-Server. Dies kann während der Migration zu einer neueren Version des Produkts auftreten. In diesem Fall würde nur ein Edgeserver für den Verbund aktiv verwendet. Überprüfen Sie, ob der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Verbund-Edgeserver bereitstellen möchten, um gleichzeitig aktiv zu sein (also kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Skype for Business Server verwenden. Überprüfen Sie, ob der externe DNS-SRV-Eintrag alle Verbund fähigen Edgeserver auflistet.**</span><span class="sxs-lookup"><span data-stu-id="dc025-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="dc025-178">Diese Warnung wird erwartet und kann bedenkenlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="dc025-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="dc025-179">So konfigurieren Sie den Edge-Server für Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="dc025-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="dc025-180">Bringen Sie alle Skype for Business Server 2019 Edge-Server online.</span><span class="sxs-lookup"><span data-stu-id="dc025-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="dc025-181">Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardware-Lastenausgleichsmodul, um SIP-Datenverkehr für externen Zugriff (in der Regel Port 443) und Föderation (in der Regel Port 5061) an den Edgeserver von Skype for Business Server 2019 zu senden, statt auf den Legacy Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="dc025-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dc025-182">Wenn Sie nicht über ein Hardware-Lastenausgleichsmodul verfügen, müssen Sie den DNS-a-Eintrag für Federation aktualisieren, damit er auf den neuen Skype for Business Server Access-Edgeserver aufgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="dc025-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="dc025-183">Um dies bei minimaler Unterbrechung zu erreichen, sollten Sie den TLL-Wert für den externen Skype for Business Server Access Edge-FQDN reduzieren, damit die DNS-Aktualisierung so aktualisiert wird, dass Sie auf den neuen Skype for Business Server Access-Edge verweist, Föderation und RAS schnell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc025-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="dc025-184">Beenden Sie den **Skype for Business Server Access-Edge** von jedem Edge-Server-Computer.</span><span class="sxs-lookup"><span data-stu-id="dc025-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="dc025-185">Öffnen Sie auf jedem Legacy-Edgeserver-Computer das Applet **Dienste** in den **Verwaltungs Tools**.</span><span class="sxs-lookup"><span data-stu-id="dc025-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="dc025-186">Suchen Sie in der Liste "Dienste" **nach Skype for Business Server Access Edge**.</span><span class="sxs-lookup"><span data-stu-id="dc025-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="dc025-187">Klicken Sie mit der rechten Maustaste auf den Namen der Dienste, und wählen Sie dann **Beenden** aus, um den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="dc025-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="dc025-188">Setzen Sie den Starttyp auf **disabled**.</span><span class="sxs-lookup"><span data-stu-id="dc025-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="dc025-189">Klicken Sie auf **OK** , um das **Eigenschaften** Fenster zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dc025-189">Click **OK** to close the **Properties** window.</span></span> 
    

