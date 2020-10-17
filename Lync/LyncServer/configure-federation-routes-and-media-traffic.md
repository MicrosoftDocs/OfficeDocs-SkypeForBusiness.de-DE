---
title: Konfigurieren von Partnerverbundrouten und Mediendatenverkehr
description: Konfigurieren Sie Verbund Routen und den Mediendatenverkehr.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure federation routes and media traffic
ms:assetid: 8b2f5f81-a955-4ad1-ad74-397322ff9521
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688121(v=OCS.15)
ms:contentKeyID: 49733720
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de26f472bddc504ff79e427b5243587f27020c3d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542981"
---
# <a name="configure-federation-routes-and-media-traffic"></a><span data-ttu-id="37f33-103">Konfigurieren von Partnerverbundrouten und Mediendatenverkehr</span><span class="sxs-lookup"><span data-stu-id="37f33-103">Configure federation routes and media traffic</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37f33-104">_**Letztes Änderungsstand des Themas:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="37f33-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="37f33-105">Ein Partnerverbund ist eine Vertrauensstellung zwischen zwei oder mehr SIP-Domänen, die Benutzern in unterschiedlichen Organisationen die Kommunikation über Netzwerkgrenzen hinweg ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="37f33-105">Federation is a trust relationship between two or more SIP domains that permits users in separate organizations to communicate across network boundaries.</span></span> <span data-ttu-id="37f33-106">Nachdem Sie zu Ihrem lync Server 2013 Pilot-Pool migriert haben, müssen Sie von der Verbund Route ihrer lync Server 2010-Edgeserver zur Verbund Route ihrer lync Server 2013 Edgeserver wechseln.</span><span class="sxs-lookup"><span data-stu-id="37f33-106">After you migrate to your Lync Server 2013 pilot pool, you need to transition from the federation route of your Lync Server 2010 Edge Servers to the federation route of your Lync Server 2013 Edge Servers.</span></span>

<span data-ttu-id="37f33-107">Führen Sie die folgenden Verfahren aus, um die partnerverbundroute und die Mediendaten Verkehrsroute von Ihrem lync Server 2010 Edgeserver und Director zu Ihrem lync Server 2013 Edgeserver für eine Bereitstellung mit einem einzelnen Standort umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="37f33-107">Use the following procedures to transition the federation route and the media traffic route from your Lync Server 2010 Edge Server and Director to your Lync Server 2013 Edge Server, for a single-site deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37f33-108">Zum Ändern der Route für partnerverbundroute und Mediendatenverkehr müssen Sie Wartungs Ausfälle für die lync Server 2013-und lync Server 2010-Edgeserver planen.</span><span class="sxs-lookup"><span data-stu-id="37f33-108">Changing the federation route and media traffic route requires that you schedule maintenance downtime for the Lync Server 2013 and Lync Server 2010 Edge Servers.</span></span> <span data-ttu-id="37f33-109">Der gesamte Umstellungsprozess bedeutet auch, dass der Verbundzugriff für die Dauer der Downtime nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="37f33-109">This entire transition process also means that federated access will be unavailable for the duration of the outage.</span></span> <span data-ttu-id="37f33-110">Sie sollten die Downtime für einen Zeitraum einplanen, in dem Sie minimale Benutzeraktivität erwarten.</span><span class="sxs-lookup"><span data-stu-id="37f33-110">You should schedule the downtime for a time when you expect minimal user activity.</span></span> <span data-ttu-id="37f33-111">Darüber hinaus sollten Sie die Endbenutzer rechtzeitig informieren.</span><span class="sxs-lookup"><span data-stu-id="37f33-111">You should also provide sufficient notification to your end users.</span></span> <span data-ttu-id="37f33-112">Planen Sie diese Downtime sorgfältig, und stellen Sie innerhalb Ihrer Organisation entsprechende Ziele auf.</span><span class="sxs-lookup"><span data-stu-id="37f33-112">Plan accordingly for this outage and set appropriate expectations within your organization.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37f33-113">Wenn Ihr Legacy lync Server 2010 Edgeserver für die Verwendung desselben FQDN für die Zugriffs-Edgedienst, Webkonferenz-Edgedienst und den A/V-Edgedienst konfiguriert ist, werden die Verfahren in diesem Abschnitt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37f33-113">If your legacy Lync Server 2010 Edge Server is configured to use the same FQDN for the Access Edge service, Web Conferencing Edge service, and the A/V Edge service, the procedures in this section are not supported.</span></span> <span data-ttu-id="37f33-114">Wenn die Legacy-Edge-Dienste für die Verwendung desselben FQDN konfiguriert sind, müssen Sie zunächst alle Ihre Benutzer von lync Server 2010 zu lync Server 2013 migrieren und dann die lync Server 2010 Edgeserver vor dem Aktivieren des partnerverbunds auf dem lync Server 2013 Edgeserver außer Betrieb nehmen.</span><span class="sxs-lookup"><span data-stu-id="37f33-114">If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users from Lync Server 2010 to Lync Server 2013, then decommission the Lync Server 2010 Edge Server before enabling federation on the Lync Server 2013 Edge Server.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="37f33-115">Wenn Ihr XMPP-Verbund über eine lync Server 2013 Edgeserver weitergeleitet wird, können Legacy lync Server 2010 Benutzer nicht mit dem XMPP-Verbundpartner kommunizieren, bis alle Benutzer in lync Server 2013 verschoben wurden, XMPP-Richtlinien und Zertifikate konfiguriert wurden, der XMPP-Verbundpartner für lync Server 2013 konfiguriert wurde und schließlich die DNS-Einträge aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="37f33-115">If your XMPP federation is routed through a Lync Server 2013 Edge Server, legacy Lync Server 2010 users will not be able to communicate with the XMPP federated partner until all users have been moved to Lync Server 2013, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Lync Server 2013, and lastly the DNS entries have been updated.</span></span>



</div>

<div>

## <a name="to-remove-the-legacy-federation-association-from-lync-server-2013-sites"></a><span data-ttu-id="37f33-116">So entfernen Sie die Partnerverbundzuordnung der Vorversion von Lync Server 2013-Standorten</span><span class="sxs-lookup"><span data-stu-id="37f33-116">To remove the legacy federation association from Lync Server 2013 sites</span></span>

1.  <span data-ttu-id="37f33-117">Öffnen Sie auf dem lync Server 2013-Front-End-Server die vorhandene Topologie im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="37f33-117">On the Lync Server 2013 Front End server, open the existing topology in Topology Builder.</span></span>

2.  <span data-ttu-id="37f33-118">Navigieren Sie im linken Bereich zum Knoten "Standort", der sich direkt unter dem **Lync Server** befindet.</span><span class="sxs-lookup"><span data-stu-id="37f33-118">In the left pane, navigate to the site node, which is located directly below **Lync Server**.</span></span>

3.  <span data-ttu-id="37f33-119">Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37f33-119">Right-click the site and then click **Edit Properties**.</span></span>

4.  <span data-ttu-id="37f33-120">Wählen Sie im linken Bereich **Partnerverbundroute** aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-120">In the left pane, select **Federation route**.</span></span>

5.  <span data-ttu-id="37f33-121">Deaktivieren Sie unter **Standort Verbund-Routen Zuweisung**das Kontrollkästchen SIP-Partner **Verbund aktivieren** , um die partnerverbundroute über die Legacy lync Server 2010 Umgebung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="37f33-121">Under **Site federation route assignment**, clear the **Enable SIP federation** check box to disable the federation route through the legacy Lync Server 2010 environment.</span></span>
    
    <span data-ttu-id="37f33-122">![Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Verbund Route"")</span><span class="sxs-lookup"><span data-stu-id="37f33-122">![Edit Properties dialog, Federation route page](images/JJ688121.8d755ae0-fc7d-4253-b0db-0cf31b863c55(OCS.15).jpg "Edit Properties dialog, Federation route page")</span></span>

6.  <span data-ttu-id="37f33-123">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-123">Click **OK** to close the Edit Properties page.</span></span>

7.  <span data-ttu-id="37f33-124">Wählen Sie im Topologie-Generator\*\*\*\* den obersten Knoten **Lync Server** aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-124">From **Topology Builder**, select the top node **Lync Server**.</span></span>

8.  <span data-ttu-id="37f33-125">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="37f33-125">From the **Action** menu, click **Publish Topology**.</span></span>

9.  <span data-ttu-id="37f33-126">Klicken Sie auf **Weiter**, um den Veröffentlichungsvorgang zu beenden, und klicken Sie dann auf **Fertig stellen**, wenn der Veröffentlichungsvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="37f33-126">Click **Next** to complete the publishing process and then click **Finish** when the publishing process has completed.</span></span>

</div>

<div>

## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a><span data-ttu-id="37f33-127">So konfigurieren Sie den Edgeserver der Vorversion als Nicht-Partnerverbund-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="37f33-127">To configure the legacy Edge Server as a non-federating Edge Server</span></span>

1.  <span data-ttu-id="37f33-128">Navigieren Sie im linken Bereich zum Knoten **Lync Server 2010** und dann zum Knoten **Edgepools**.</span><span class="sxs-lookup"><span data-stu-id="37f33-128">In the left pane, navigate to the **Lync Server 2010** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="37f33-129">Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37f33-129">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="37f33-130">Wählen Sie im linken Bereich **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-130">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="37f33-131">Deaktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**, und wählen Sie **OK** aus, um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-131">Clear the **Enable federation for this Edge pool (port 5061)** check box entry and select **OK** to close the page.</span></span>
    
    <span data-ttu-id="37f33-132">![Eigenschaften bearbeiten, allgemein, Clear Federation aktivieren](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, Clear Federation aktivieren")</span><span class="sxs-lookup"><span data-stu-id="37f33-132">![Edit Properties, General, clear Enable federation](images/JJ688121.3be2c8c0-9ed9-4544-bafd-b7694271fafc(OCS.15).jpg "Edit Properties, General, clear Enable federation")</span></span>

5.  <span data-ttu-id="37f33-133">Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37f33-133">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="37f33-134">Nach Abschluss des Veröffentlichungs-Assistenten\*\*\*\* klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-134">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="37f33-135">Stellen Sie sicher, dass der Partnerverbund für die Edgeserver der Vorversion deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="37f33-135">Verify federation for the legacy Edge server is disabled.</span></span>
    
    <span data-ttu-id="37f33-136">![Topologie-Generator, Edgepool, Verbund deaktiviert](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topologie-Generator, Edgepool, Verbund deaktiviert")</span><span class="sxs-lookup"><span data-stu-id="37f33-136">![Topology Builder, Edge pool, federation disabled](images/JJ688121.a2948438-d51a-4aeb-9eaa-d899ca950758(OCS.15).jpg "Topology Builder, Edge pool, federation disabled")</span></span>

</div>

<div>

## <a name="to-configure-certificates-on-the-lync-server-2010-edge-server"></a><span data-ttu-id="37f33-137">So konfigurieren Sie Zertifikate auf dem Lync Server 2010-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="37f33-137">To configure certificates on the Lync Server 2010 Edge Server</span></span>

1.  <span data-ttu-id="37f33-138">Exportieren Sie das externe Zugriffs Proxy Zertifikat mit dem privaten Schlüssel aus dem Legacy lync Server 2010 Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="37f33-138">Export the external Access Proxy certificate, with the private key, from the legacy Lync Server 2010 Edge Server.</span></span>

2.  <span data-ttu-id="37f33-139">Importieren Sie im lync Server 2013 Edgeserver das externe Zugriffs Proxy Zertifikat aus dem vorherigen Schritt.</span><span class="sxs-lookup"><span data-stu-id="37f33-139">On the Lync Server 2013 Edge Server, import the Access Proxy external certificate from the previous step.</span></span>

3.  <span data-ttu-id="37f33-140">Weisen Sie das externe Zertifikat des Zugriffsproxys der externen lync Server 2013-Schnittstelle des Edgeserver zu.</span><span class="sxs-lookup"><span data-stu-id="37f33-140">Assign the Access Proxy external certificate to the Lync Server 2013 external interface of the Edge Server.</span></span>

4.  <span data-ttu-id="37f33-141">Das interne Schnittstellen Zertifikat des lync Server 2013 Edgeserver sollte von einer vertrauenswürdigen Zertifizierungsstelle angefordert und zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="37f33-141">The internal interface certificate of the Lync Server 2013 Edge Server should be requested from a trusted CA and assigned.</span></span>

</div>

<div>

## <a name="to-change-lync-server-2010-federation-route-to-use-lync-server-2013-edge-server"></a><span data-ttu-id="37f33-142">So legen Sie für die Lync Server 2010-Partnerverbundroute die Verwendung des Lync Server 2013-Edgeservers fest</span><span class="sxs-lookup"><span data-stu-id="37f33-142">To change Lync Server 2010 federation route to use Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="37f33-143">Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten \*\*Lync Server 2013 \*\* und dann zum Knoten **Edgepools**.</span><span class="sxs-lookup"><span data-stu-id="37f33-143">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="37f33-144">Klicken Sie mit der rechten Maustaste auf den Edgeserver und anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37f33-144">Right-click the Edge server, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="37f33-145">Wählen Sie im linken Bereich **Allgemein** aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-145">Select **General** in the left pane.</span></span>

4.  <span data-ttu-id="37f33-146">Aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**, und klicken Sie dann auf **OK**, um die Seite zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-146">Select the check box entry for **Enable federation for this Edge pool (port 5061)** and then click **OK** to close the page.</span></span>
    
    <span data-ttu-id="37f33-147">![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")</span><span class="sxs-lookup"><span data-stu-id="37f33-147">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

5.  <span data-ttu-id="37f33-148">Wählen Sie im Menü **Aktionen** die Option **Topologie veröffentlichen** aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="37f33-148">From the **Action** menu, select **Publish Topology**, and then click **Next**.</span></span>

6.  <span data-ttu-id="37f33-149">Nach Abschluss des Veröffentlichungs-Assistenten\*\*\*\* klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-149">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

7.  <span data-ttu-id="37f33-150">Stellen Sie sicher, dass die Option **Partnerverbund (Port 5061)** auf **Aktiviert** festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="37f33-150">Verify **Federation (port 5061)** is set to **Enabled**.</span></span>
    
    <span data-ttu-id="37f33-151">![Topologie-Generator, Edgepool, Verbund aktiviert](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topologie-Generator, Edgepool, Verbund aktiviert")</span><span class="sxs-lookup"><span data-stu-id="37f33-151">![Topology Builder, Edge pool, Federation enabled](images/JJ688121.e8ccdada-23f4-47e5-a99d-5bf795fefc48(OCS.15).jpg "Topology Builder, Edge pool, Federation enabled")</span></span>

</div>

<div>

## <a name="to-update-lync-server-2013-edge-server-federation-next-hop"></a><span data-ttu-id="37f33-152">So aktualisieren Sie den nächsten Partnerverbundhop für den Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="37f33-152">To update Lync Server 2013 Edge Server federation next hop</span></span>

1.  <span data-ttu-id="37f33-153">Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten \*\*Lync Server 2013 \*\* und dann zum Knoten **Edgepools**.</span><span class="sxs-lookup"><span data-stu-id="37f33-153">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="37f33-154">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37f33-154">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="37f33-155">Wählen Sie auf der Seite **Allgemein** unter **Auswahl für nächsten Hop**in der Dropdownliste den lync Server 2013 Pool aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-155">On the **General** page, under **Next hop selection**, select from the drop-down list the Lync Server 2013  pool.</span></span>
    
    <span data-ttu-id="37f33-156">![Dialogfeld "Eigenschaften bearbeiten", Seite "Nächster Abschnitt"](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Nächster Abschnitt"")</span><span class="sxs-lookup"><span data-stu-id="37f33-156">![Edit Properties dialog, Next hop page](images/JJ688121.5741b9a8-e729-4457-9f62-38f08a2c5b02(OCS.15).jpg "Edit Properties dialog, Next hop page")</span></span>

4.  <span data-ttu-id="37f33-157">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-157">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="37f33-158">Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server** aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-158">From **Topology Builder**, select the top node **Lync Server** .</span></span>

6.  <span data-ttu-id="37f33-159">Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="37f33-159">From the **Action** menu, click **Publish Topology** and complete the wizard.</span></span>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server-outbound-media-path"></a><span data-ttu-id="37f33-160">So konfigurieren Sie den ausgehenden Medienpfad für den Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="37f33-160">To configure Lync Server 2013 Edge Server outbound media path</span></span>

1.  <span data-ttu-id="37f33-161">Navigieren Sie im linken Bereich des Topologie-Generators zum Knoten **lync Server 2013** und dann zum Pool unter **Standard Edition-Front-End-Server** oder **Enterprise Edition-Front-End-Pools**.</span><span class="sxs-lookup"><span data-stu-id="37f33-161">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the pool below **Standard Edition Front End Servers** or **Enterprise Edition Front End pools**.</span></span>

2.  <span data-ttu-id="37f33-162">Klicken Sie mit der rechten Maustaste auf den Pool, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37f33-162">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="37f33-163">Aktivieren Sie im Abschnitt **Zuordnungen** das Kontrollkästchen **Edgepool zuordnen (für Medienkomponenten)**.</span><span class="sxs-lookup"><span data-stu-id="37f33-163">In the **Associations** section, select the **Associate Edge pool (for media components)** check box.</span></span>
    
    <span data-ttu-id="37f33-164">![Eigenschaften bearbeiten, allgemein, zuordnen Edgepool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Eigenschaften bearbeiten, allgemein, zuordnen Edgepool")</span><span class="sxs-lookup"><span data-stu-id="37f33-164">![Edit Properties, General, Associate Edge pool](images/JJ688121.fd9b18ca-fda2-4764-9bf0-726bf39f6a12(OCS.15).jpg "Edit Properties, General, Associate Edge pool")</span></span>

4.  <span data-ttu-id="37f33-165">Wählen Sie im Dropdownfeld die lync Server 2013 Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-165">From the drop down box, select the Lync Server 2013 Edge Server.</span></span>

5.  <span data-ttu-id="37f33-166">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-166">Click **OK** to close the **Edit Properties** page.</span></span>

</div>

<div>

## <a name="to-turn-on-lync-server-2013-edge-server-federation"></a><span data-ttu-id="37f33-167">So aktivieren Sie den Partnerverbund für den Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="37f33-167">To turn on Lync Server 2013 Edge Server federation</span></span>

1.  <span data-ttu-id="37f33-168">Navigieren Sie im Topologie-Generator im linken Bereich zum Knoten \*\*Lync Server 2013 \*\* und dann zum Knoten **Edgepools**.</span><span class="sxs-lookup"><span data-stu-id="37f33-168">From Topology Builder, in the left pane, navigate to the **Lync Server 2013** node and then to the **Edge pools** node.</span></span>

2.  <span data-ttu-id="37f33-169">Erweitern Sie den Knoten, klicken Sie mit der rechten Maustaste auf den aufgelisteten Edgeserver, und klicken Sie anschließend auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37f33-169">Expand the node, right-click the Edge Server listed, and then click **Edit Properties**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37f33-170">Der Partnerverbund kann nur für einen einzelnen Edgepool aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="37f33-170">Federation can only be enabled for a single Edge pool.</span></span> <span data-ttu-id="37f33-171">Wählen Sie bei mehreren Edgepools den Edgepool aus, den Sie als Partnerverbund-Edgepool verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="37f33-171">If you have multiple Edge pools, select one to use as the federating Edge pool.</span></span>

    
    </div>

3.  <span data-ttu-id="37f33-172">Stellen Sie auf der Seite **Allgemein** sicher, dass die Einstellung **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="37f33-172">On the **General** page, verify the **Enable federation for this Edge pool (Port 5061)** setting is checked.</span></span>
    
    <span data-ttu-id="37f33-173">![Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Dialogfeld "Eigenschaften bearbeiten", Seite "Allgemein"")</span><span class="sxs-lookup"><span data-stu-id="37f33-173">![Edit Properties dialog, General page](images/JJ688121.cc79a88c-cce4-4cab-80ad-4f70325dc7c4(OCS.15).jpg "Edit Properties dialog, General page")</span></span>

4.  <span data-ttu-id="37f33-174">Klicken Sie auf **OK**, um die Seite "Eigenschaften bearbeiten" zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-174">Click **OK** to close the Edit Properties page.</span></span>

5.  <span data-ttu-id="37f33-175">Navigieren Sie anschließend zum Knoten Standort.</span><span class="sxs-lookup"><span data-stu-id="37f33-175">Next, navigate to the site node.</span></span>

6.  <span data-ttu-id="37f33-176">Klicken Sie mit der rechten Maustaste auf den Standort, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="37f33-176">Right-click the site, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="37f33-177">Klicken Sie im linken Bereich auf **Partnerverbundroute**.</span><span class="sxs-lookup"><span data-stu-id="37f33-177">In the left pane, click **Federation route**.</span></span>

8.  <span data-ttu-id="37f33-178">Wählen Sie unter **Standort Verbund-Routen Zuweisung**die Option SIP-Partner **Verbund aktivieren**aus, und wählen Sie dann in der Liste den aufgelisteten lync Server 2013 Edgeserver aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-178">Under **Site federation route assignment**, select **Enable SIP federation**, and then from the list select the Lync Server 2013 Edge Server listed.</span></span>
    
    <span data-ttu-id="37f33-179">![Eigenschaften bearbeiten, Verbund Route (Seite)](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Eigenschaften bearbeiten, Verbund Route (Seite)")</span><span class="sxs-lookup"><span data-stu-id="37f33-179">![Edit Properties, Federation route page](images/JJ688121.c50c13b8-0859-4e3e-8793-45c431a5b4b5(OCS.15).jpg "Edit Properties, Federation route page")</span></span>

9.  <span data-ttu-id="37f33-180">Klicken Sie auf **OK**, um die Seite **Eigenschaften bearbeiten** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-180">Click **OK** to close the **Edit Properties** page.</span></span>
    
    <span data-ttu-id="37f33-181">Für Bereitstellungen mit mehreren Standorten führen Sie dieses Verfahren an jedem Standort aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-181">For multi-site deployments, complete this procedure at each site.</span></span>

</div>

<div>

## <a name="to-publish-edge-server-configuration-changes"></a><span data-ttu-id="37f33-182">So veröffentlichen Sie Edgeserver-Konfigurationsänderungen</span><span class="sxs-lookup"><span data-stu-id="37f33-182">To publish Edge Server configuration changes</span></span>

1.  <span data-ttu-id="37f33-183">Wählen Sie im **Topologie-Generator**den obersten Knoten **lync Server** aus.</span><span class="sxs-lookup"><span data-stu-id="37f33-183">From **Topology Builder**, select the top node **Lync Server** .</span></span>

2.  <span data-ttu-id="37f33-184">Klicken Sie im Menü **Aktionen** auf **Topologie veröffentlichen**, und schließen Sie den Assistenten ab.</span><span class="sxs-lookup"><span data-stu-id="37f33-184">From the **Action** menu, select **Publish Topology** and complete the wizard.</span></span>

3.  <span data-ttu-id="37f33-185">Warten Sie, bis die Active Directory-Replikation für alle Pools in der Bereitstellung ausgeführt worden ist.</span><span class="sxs-lookup"><span data-stu-id="37f33-185">Wait for Active Directory replication to occur to all pools in the deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37f33-186">Möglicherweise wird die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="37f33-186">You may see the following message:</span></span><BR><span data-ttu-id="37f33-187"><STRONG>Warnung: Die Topologie enthält mehrere Partner-Edgeserver. Dies kann während der Migration zu einer höheren Version des Produkts geschehen. In diesem Fall wird nur ein Edgeserver aktiv für den Partnerverbund verwendet. Stellen Sie sicher, dass der externe DNS-SRV-Eintrag auf den richtigen Edgeserver verweist. Wenn Sie mehrere Partnerverbund-Edgeserver bereitstellen möchten, die gleichzeitig aktiv sind (kein Migrationsszenario), stellen Sie sicher, dass alle Verbundpartner Lync Server verwenden. Stellen Sie außerdem sicher, dass der externe DNS-SRV-Eintrag alle partnerverbundfähigen Edgeserver auflistet.</STRONG></span><span class="sxs-lookup"><span data-stu-id="37f33-187"><STRONG>Warning: The topology contains more than one Federated Edge Server. This can occur during migration to a more recent version of the product. In that case, only one Edge Server would be actively used for federation. Verify that the external DNS SRV record points to the correct Edge Server. If you want to deploy multiple federation Edge Server to be active concurrently (that is, not a migration scenario), verify that all federated partners are using Lync Server. Verify that the external DNS SRV record lists all federation enabled Edge Servers.</STRONG></span></span><BR><span data-ttu-id="37f33-188">Diese Warnung entspricht der Erwartung und kann problemlos ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="37f33-188">This warning is expected and can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-configure-lync-server-2013-edge-server"></a><span data-ttu-id="37f33-189">So konfigurieren Sie Lync Server 2013-Edgeserver</span><span class="sxs-lookup"><span data-stu-id="37f33-189">To configure Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="37f33-190">Alle lync Server 2013-Edgeserver online schalten.</span><span class="sxs-lookup"><span data-stu-id="37f33-190">Bring all of the Lync Server 2013 Edge Servers online.</span></span>

2.  <span data-ttu-id="37f33-191">Aktualisieren Sie die Routingregeln für externe Firewalls oder die Einstellungen für das Hardwaregerät zum Lastenausgleich, um den SIP-Datenverkehr für den externen Zugriff (in der Regel Port 443) und den Verbund (in der Regel Port 5061) an die lync Server 2013 Edgeserver anstelle des Legacy Edgeserver zu senden.</span><span class="sxs-lookup"><span data-stu-id="37f33-191">Update the external firewall routing rules or the hardware load balancer settings to send SIP traffic for external access (usually port 443) and federation (usually port 5061) to the Lync Server 2013 Edge Server, instead of the legacy Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37f33-p105">Wenn Sie kein Hardwaregerät zum Lastenausgleich zur Verfügung haben, müssen Sie den DNS-A-Eintrag für den Partnerverbund aktualisieren, um das Problem für den neuen Lync Server-Zugriffs-Edgeserver zu lösen. Damit es mit geringstmöglicher Störung abgeschlossen werden kann, sollte Sie den TLL-Wert für den externen FQDN des Lync Server-Zugriffsedge reduzieren, sodass der Partnerverbund und der Remotezugriff schnell aktualisiert werden können, wenn die DNS aktualisiert wird, damit auf den neuen Lync Server-Zugriffsedge verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="37f33-p105">If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Lync Server Access Edge server. To accomplish this with minimum disruption, reduce the TLL value for the external Lync Server Access Edge FQDN so that when DNS is updated to point to the new Lync Server Access Edge, federation and remote access will be updated quickly.</span></span>

    
    </div>

3.  <span data-ttu-id="37f33-194">Beenden Sie als nächstes die **lync Server Zugriffs Kante** für jeden Edgeserver Computer.</span><span class="sxs-lookup"><span data-stu-id="37f33-194">Next, stop the **Lync Server Access Edge** from each Edge Server computer.</span></span>

4.  <span data-ttu-id="37f33-195">Öffnen Sie auf jedem Computer mit Legacy Edgeserver das Applet **Dienste** über die **Verwaltungs Tools**.</span><span class="sxs-lookup"><span data-stu-id="37f33-195">From each legacy Edge Server computer, open the **Services** applet from the **Administrative Tools**.</span></span>

5.  <span data-ttu-id="37f33-196">Suchen Sie in der Liste mit den Diensten nach **Lync Server-Zugriffsedge**.</span><span class="sxs-lookup"><span data-stu-id="37f33-196">In the services list, find **Lync Server Access Edge**.</span></span>

6.  <span data-ttu-id="37f33-197">Klicken Sie mit der rechten Maustaste auf den Namen des Diensts, und klicken Sie dann auf **Beenden**, um den Dienst zu beenden.</span><span class="sxs-lookup"><span data-stu-id="37f33-197">Right-click the services name, and then select **Stop** to stop the service.</span></span>

7.  <span data-ttu-id="37f33-198">Legen Sie als Starttyp **Deaktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="37f33-198">Set the Startup type to **Disabled**.</span></span>

8.  <span data-ttu-id="37f33-199">Klicken Sie auf **OK**, um das Fenster **Eigenschaften** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="37f33-199">Click **OK** to close the **Properties** window.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

