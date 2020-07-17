---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht. Nachdem Sie zu Ihrem Pilot Pool migriert haben, müssen Sie von der Verbund Route ihrer Vorgängerversionen-Edgeserver zur Verbund Route Ihrer Skype for Business Server 2019-Edgeserver wechseln.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754035"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="31486-104">Konfigurieren von Partnerverbundrouten und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="31486-104">Configure federation routes and media traffic</span></span>

<span data-ttu-id="31486-105">Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="31486-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="31486-106">Nachdem Sie zu Ihrem Pilot Pool migriert haben, müssen Sie von der Verbund Route der Edgeserver ihrer Vorgängerversion zur Verbund Route Ihrer Skype for Business Server 2019-Edgeserver wechseln.</span><span class="sxs-lookup"><span data-stu-id="31486-106">After you migrate to your pilot pool, you need to transition from the federation route of your previous version's Edge Servers to the federation route of your Skype for Business Server 2019 Edge Servers.</span></span>
  
<span data-ttu-id="31486-107">Verwenden Sie die folgenden Verfahren, um die partnerverbundroute und die Mediendaten Verkehrsroute von der Edgeserver und dem Director der vorherigen Version auf die Skype for Business Server 2019-Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzustellen.</span><span class="sxs-lookup"><span data-stu-id="31486-107">Use the following procedures to transition the federation route and the media traffic route from your previous version's Edge Server and Director to your Skype for Business Server 2019 Edge Server, for a single-site deployment.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="31486-108">Für das Ändern der Route für partnerverbundroute und Mediendatenverkehr ist es erforderlich, dass Sie Wartungs Ausfälle für die Edgeserver von Skype for Business Server 2019 und früheren Versionen planen.</span><span class="sxs-lookup"><span data-stu-id="31486-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Skype for Business Server 2019 and previous version Edge Servers.</span></span> <span data-ttu-id="31486-109">Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="31486-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="31486-110">Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten.</span><span class="sxs-lookup"><span data-stu-id="31486-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="31486-111">Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren.</span><span class="sxs-lookup"><span data-stu-id="31486-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="31486-112">Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf.</span><span class="sxs-lookup"><span data-stu-id="31486-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="31486-113">Wenn Ihr Legacy Edgeserver für die Verwendung desselben FQDN für die Zugriffs-Edgedienst, Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31486-113">If your legacy Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="31486-114">Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer migrieren und dann die vorherigen Versionen Edgeserver vor dem Aktivieren des Verbund im Skype for Business Server 2019 Edgeserver außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="31486-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="31486-115">Wenn Ihr XMPP-Verbund über eine Skype for Business Server 2019 Edgeserver weitergeleitet wird, können Benutzer der vorherigen Version nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer auf Skype for Business Server 2019 verschoben wurden, XMPP-Richtlinien und Zertifikate konfiguriert wurden, der XMPP-Verbundpartner wurde für Skype for Business Server 2019 konfiguriert. und schließlich wurden die DNS-Einträge aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="31486-115">If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019, and, lastly, the DNS entries have been updated.</span></span> 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a><span data-ttu-id="31486-116">So entfernen Sie die Legacy-Verbund Zuordnung von Skype for Business Server 2019-Websites</span><span class="sxs-lookup"><span data-stu-id="31486-116">To remove the legacy federation association from Skype for Business Server 2019 sites</span></span>

1. <span data-ttu-id="31486-117">Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 die vorhandene Topologie im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="31486-117">On the Skype for Business Server 2019 Front End server, open the existing topology in Topology Builder.</span></span> 
    
2. <span data-ttu-id="31486-118">Navigieren Sie im linken Bereich zum Websiteknoten, der sich direkt unterhalb **Skype for Business Server**befindet.</span><span class="sxs-lookup"><span data-stu-id="31486-118">In the left pane, navigate to the site node, which is located directly below **Skype for Business Server**.</span></span>
    
3. <span data-ttu-id="31486-119">Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31486-119">Right-click the site, and then click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="31486-120">Wählen Sie im linken Bereich die Option **Partnerverbundroute** aus.</span><span class="sxs-lookup"><span data-stu-id="31486-120">In the left pane, select **Federation route**.</span></span> 
    
5. <span data-ttu-id="31486-121">Deaktivieren Sie unter **Standort Verbund-Routen Zuweisung**das Kontrollkästchen SIP-Partner **Verbund aktivieren** , um die partnerverbundroute über die Legacyumgebung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="31486-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy environment.</span></span> 
  
6. <span data-ttu-id="31486-122">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-122">Click **OK** to close the Edit Properties page.</span></span> 
    
7. <span data-ttu-id="31486-123">Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="31486-123">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span>
    
8. <span data-ttu-id="31486-124">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="31486-124">From the **Action** menu, click **Publish Topology**.</span></span>
    
9. <span data-ttu-id="31486-125">Klicken Sie auf **weiter** , um den Veröffentlichungsprozess abzuschließen, und klicken Sie dann auf **Fertig stellen** , wenn der Veröffentlichungsprozess abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="31486-125">Click **Next** to complete the publishing process, and then click **Finish** when the publishing process has completed.</span></span> 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="31486-126">So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="31486-126">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1. <span data-ttu-id="31486-127">Navigieren Sie im linken Bereich zum Knoten Legacy Installation und dann zum Knoten Edge- **Pools** .</span><span class="sxs-lookup"><span data-stu-id="31486-127">In the left pane, navigate to the legacy install node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="31486-128">Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31486-128">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="31486-129">Wählen Sie im linken Bereich **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="31486-129">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="31486-130">Deaktivieren Sie das Kontrollkästchen Partner **Verbund für diese Edgepool aktivieren (Port 5061)** , und wählen Sie **OK** aus, um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-130">Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="31486-131">Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="31486-131">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="31486-132">Nach Abschluss des Veröffentlichungs-Assistenten\*\*\*\* klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-132">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="31486-133">Stellen Sie sicher, dass der Verbund für den Legacy-Edgeserver im Topologie-Generator deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="31486-133">Verify that federation for the legacy Edge server is disabled in Topology Builder.</span></span>
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a><span data-ttu-id="31486-134">So konfigurieren Sie Zertifikate für die Legacy Edgeserver</span><span class="sxs-lookup"><span data-stu-id="31486-134">To configure certificates on the legacy Edge Server</span></span>

1. <span data-ttu-id="31486-135">Exportieren Sie das externe Zugriffs Proxy Zertifikat mit dem privaten Schlüssel aus dem Legacy Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="31486-135">Export the external Access Proxy certificate, with the private key, from the legacy Edge Server.</span></span> 
    
2. <span data-ttu-id="31486-136">Importieren Sie im Skype for Business Server 2019 Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="31486-136">On the Skype for Business Server 2019 Edge Server, and import the Access Proxy external certificate from the previous step.</span></span>
    
3. <span data-ttu-id="31486-137">Weisen Sie das externe Zertifikat des Zugriffsproxys der externen Skype for Business Server 2019-Schnittstelle des Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="31486-137">Assign the Access Proxy external certificate to the Skype for Business Server 2019 external interface of the Edge Server.</span></span>
    
4. <span data-ttu-id="31486-138">Das interne Schnittstellen Zertifikat des Skype for Business Server 2019 Edgeserver sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="31486-138">The internal interface certificate of the Skype for Business Server 2019 Edge Server should be requested from a trusted CA and assigned.</span></span> 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="31486-139">So ändern Sie die partnerverbundroute der Vorgängerversion Skype for Business Server 2019 Edgeserver</span><span class="sxs-lookup"><span data-stu-id="31486-139">To change the previous version's federation route to use Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="31486-140">Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Knoten **Edge-Pools** .</span><span class="sxs-lookup"><span data-stu-id="31486-140">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="31486-141">Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31486-141">Right-click the Edge server, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="31486-142">Wählen Sie im linken Bereich **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="31486-142">Select **General** in the left pane.</span></span> 
    
4. <span data-ttu-id="31486-143">Aktivieren Sie das Kontrollkästchen Partner **Verbund für diesen Edgepool aktivieren (Port 5061)**, und klicken Sie dann auf **OK** , um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-143">Select the check box for **Enable federation for this Edge pool (port 5061)**, and then click **OK** to close the page.</span></span> 
  
5. <span data-ttu-id="31486-144">Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="31486-144">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="31486-145">Nach Abschluss des Veröffentlichungs-Assistenten\*\*\*\* klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-145">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span> 
    
7. <span data-ttu-id="31486-146">Stellen Sie sicher, dass der **Verbund (Port 5061)** im Topologie-Generator auf **aktiviert** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="31486-146">Verify that **Federation (port 5061)** is set to **Enabled** in Topology Builder.</span></span>
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a><span data-ttu-id="31486-147">So aktualisieren Sie den nächsten Hop Skype for Business Server 2019 Edgeserver-Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="31486-147">To update Skype for Business Server 2019 Edge Server federation next hop</span></span>

1. <span data-ttu-id="31486-148">Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Knoten **Edge-Pools** .</span><span class="sxs-lookup"><span data-stu-id="31486-148">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="31486-149">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31486-149">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
3. <span data-ttu-id="31486-150">Wählen Sie auf der Seite **Allgemein** unter **Auswahl für nächsten Hop**in der Dropdownliste den Skype for Business Server Pool 2019 aus.</span><span class="sxs-lookup"><span data-stu-id="31486-150">On the **General** page, under **Next hop selection**, select from the drop-down list the Skype for Business Server 2019 pool.</span></span>
  
4. <span data-ttu-id="31486-151">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-151">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="31486-152">Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="31486-152">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
6. <span data-ttu-id="31486-153">Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="31486-153">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span> 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a><span data-ttu-id="31486-154">So konfigurieren Sie Skype for Business Server 2019 Edgeserver ausgehenden Medienpfad</span><span class="sxs-lookup"><span data-stu-id="31486-154">To configure Skype for Business Server 2019 Edge Server outbound media path</span></span>

1. <span data-ttu-id="31486-155">Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.</span><span class="sxs-lookup"><span data-stu-id="31486-155">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>
    
2. <span data-ttu-id="31486-156">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31486-156">Right-click the pool, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="31486-157">Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="31486-157">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span> 
  
4. <span data-ttu-id="31486-158">Wählen Sie im Dropdownfeld die Skype for Business Server 2019 Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="31486-158">From the drop-down box, select the Skype for Business Server 2019 Edge Server.</span></span>
    
5. <span data-ttu-id="31486-159">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-159">Click **OK** to close the **Edit Properties** page.</span></span> 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a><span data-ttu-id="31486-160">So aktivieren Sie Skype for Business Server 2019 Edgeserver Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="31486-160">To turn on Skype for Business Server 2019 Edge Server federation</span></span>

1. <span data-ttu-id="31486-161">Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **Skype for Business Server 2019** und dann zum Knoten **Edge-Pools** .</span><span class="sxs-lookup"><span data-stu-id="31486-161">From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the **Edge pools** node.</span></span> 
    
2. <span data-ttu-id="31486-162">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31486-162">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="31486-163">Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="31486-163">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="31486-164">Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund-Edgepool verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="31486-164">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span> 
  
3. <span data-ttu-id="31486-165">Stellen Sie auf der Seite **Allgemein** sicher, dass das Kontrollkästchen Partner **Verbund für diese Edgepool aktivieren (Port 5061)** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="31486-165">On the **General** page, verify that the **Enable federation for this Edge pool (Port 5061)** check box is selected.</span></span> 
  
4. <span data-ttu-id="31486-166">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-166">Click **OK** to close the Edit Properties page.</span></span> 
    
5. <span data-ttu-id="31486-167">Navigieren Sie zum Knoten Website.</span><span class="sxs-lookup"><span data-stu-id="31486-167">Navigate to the site node.</span></span> 
    
6. <span data-ttu-id="31486-168">Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31486-168">Right-click the site, and then click **Edit Properties**.</span></span>
    
7. <span data-ttu-id="31486-169">Klicken Sie im linken Bereich auf **Partnerverbundroute**.</span><span class="sxs-lookup"><span data-stu-id="31486-169">In the left pane, click **Federation route**.</span></span>
    
8. <span data-ttu-id="31486-170">Wählen Sie unter **Standort Verbund-Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann in der Liste den aufgelisteten Skype for Business Server 2019 Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="31486-170">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed.</span></span> 
  
9. <span data-ttu-id="31486-171">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-171">Click **OK** to close the **Edit Properties** page.</span></span> 
    
     <span data-ttu-id="31486-172">Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus.</span><span class="sxs-lookup"><span data-stu-id="31486-172">For multi-site deployments, complete this procedure at each site.</span></span> 
    
## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="31486-173">So veröffentlichen Sie Edgeserver-Konfigurationsänderungen</span><span class="sxs-lookup"><span data-stu-id="31486-173">To publish Edge Server configuration changes</span></span>

1. <span data-ttu-id="31486-174">Wählen Sie im **Topologie-Generator**den obersten Knoten **Skype for Business Server**aus.</span><span class="sxs-lookup"><span data-stu-id="31486-174">From **Topology Builder**, select the top node **Skype for Business Server**.</span></span> 
    
2. <span data-ttu-id="31486-175">Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="31486-175">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span> 
    
3. <span data-ttu-id="31486-176">Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.</span><span class="sxs-lookup"><span data-stu-id="31486-176">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="31486-177">Möglicherweise wird die folgende Meldung angezeigt: **Warnung: die Topologie enthält mehr als einen Verbund Edgeserver. Dies kann während der Migration zu einer neueren Version des Produkts passieren. In diesem Fall würde nur ein Edgeserver für den Verbund aktiv verwendet werden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf die richtige Edgeserver verweist. Wenn Sie mehrere Verbund Edgeserver bereitstellen möchten, gleichzeitig aktiv zu sein (also kein Migrationsszenario), überprüfen Sie, ob alle Verbundpartner Skype for Business Server verwenden. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag alle Verbund fähigen Edgeserver auflistet.**</span><span class="sxs-lookup"><span data-stu-id="31486-177">You may see the following message: **Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Skype for Business Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.**</span></span> <span data-ttu-id="31486-178">Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="31486-178">This warning is expected and can be safely ignored.</span></span> 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a><span data-ttu-id="31486-179">So konfigurieren Sie Skype for Business Server 2019 Edgeserver</span><span class="sxs-lookup"><span data-stu-id="31486-179">To configure Skype for Business Server 2019 Edge Server</span></span>

1. <span data-ttu-id="31486-180">Alle Skype for Business Server 2019-Edgeserver online schalten.</span><span class="sxs-lookup"><span data-stu-id="31486-180">Bring all of the Skype for Business Server 2019 Edge Servers online.</span></span> 
    
2. <span data-ttu-id="31486-181">Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, um den SIP-Datenverkehr für den externen Zugriff (in der Regel Port 443) und den Verbund (in der Regel Port 5061) an den Skype for Business Server 2019 Edgeserver anstelle des Legacy Edgeserver zu senden.</span><span class="sxs-lookup"><span data-stu-id="31486-181">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Skype for Business Server 2019 Edge Server, instead of the legacy Edge Server.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="31486-182">Wenn Sie nicht über ein Hardwaregerät zum Lastenausgleich verfügen, müssen Sie den DNS-a-Eintrag für den Verbund so aktualisieren, dass er auf den neuen Skype for Business Server Access-Edgeserver aufgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="31486-182">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server.</span></span> <span data-ttu-id="31486-183">Um dies bei minimaler Unterbrechung zu erreichen, reduzieren Sie den TLL-Wert für den externen Skype for Business Server Zugriffs-Edge-FQDN, sodass beim Aktualisieren von DNS auf den neuen Skype for Business Server Zugriffs-Edge der Verbund und der Remotezugriff schnell aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="31486-183">To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly.</span></span> 
  
3. <span data-ttu-id="31486-184">Beenden Sie die **Skype for Business Server Zugriffs Kante** für jeden Edgeserver Computer.</span><span class="sxs-lookup"><span data-stu-id="31486-184">Stop the **Skype for Business Server Access Edge** from each Edge Server computer.</span></span> 
    
4. <span data-ttu-id="31486-185">Öffnen Sie auf jedem Computer mit Legacy Edgeserver das Applet **Dienste** über die **Verwaltungs Tools**.</span><span class="sxs-lookup"><span data-stu-id="31486-185">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>
    
5. <span data-ttu-id="31486-186">Suchen Sie in der Liste Dienste nach **Skype for Business Server Zugriffs-Edge**.</span><span class="sxs-lookup"><span data-stu-id="31486-186">In the services list, find **Skype for Business Server Access Edge**.</span></span>
    
6. <span data-ttu-id="31486-187">Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden**, um den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="31486-187">Right-click the services name, and then select **Stop** to stop the service.</span></span> 
    
7. <span data-ttu-id="31486-188">Legen Sie als Starttyp **Deaktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="31486-188">Set the Startup type to **Disabled**.</span></span> 
    
8. <span data-ttu-id="31486-189">Klicken Sie auf **OK**, um das Fenster **Eigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="31486-189">Click **OK** to close the **Properties** window.</span></span> 
    

