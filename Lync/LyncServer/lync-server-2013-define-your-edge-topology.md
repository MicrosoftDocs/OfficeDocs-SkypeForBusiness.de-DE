---
title: 'Lync Server 2013: Definieren der Edgetopologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8364d2167b719e020ecebc3808c2ca850d14bc0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="a67ef-102">Definieren der Edgetopologie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a67ef-102">Define your edge topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a67ef-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a67ef-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a67ef-104">Sie müssen den Topologie-Generator verwenden, um Ihre Topologie zu erstellen, und Sie müssen mindestens einen internen Front-End-Pool oder Standard Edition-Server einrichten, bevor Sie den Edgeserver bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="a67ef-104">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="a67ef-105">Gehen Sie wie folgt vor, um die Edge-Topologie für einen einzelnen Edgeserver zu definieren, und verwenden Sie dann die Verfahren unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md) , und [exportieren Sie Ihre lync Server 2013-Topologie, und kopieren Sie Sie für die Edge-Installation auf externe Medien](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) . , um die Topologie zu veröffentlichen und für Ihren Edgeserver verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-105">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a67ef-106">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-106">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="a67ef-107">Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-107">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="a67ef-108">Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, müssen Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="a67ef-108">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="a67ef-109">Sie können auch die Administratorrechte und-Berechtigungen erteilen, die für das Hinzufügen von Serverrollen zu einem Benutzerkonto erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a67ef-109">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="a67ef-110">Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Dokumentation zur Standard Edition-Server-oder Enterprise Edition-Server Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a67ef-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="a67ef-111">Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a67ef-111">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="a67ef-112">Wenn Sie Ihre Edge-Topologie beim Definieren und Veröffentlichen Ihrer internen Topologie definiert haben und für die zuvor definierte Edge-Topologie keine Änderungen erforderlich sind, müssen Sie Sie nicht definieren und erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-112">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="a67ef-113">Führen Sie das folgende Verfahren nur aus, wenn Sie Änderungen an ihrer Edge-Topologie vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-113">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="a67ef-114">Sie müssen die zuvor definierte und veröffentlichte Topologie für Ihre Edgeserver verfügbar machen, indem Sie das Verfahren zum [Exportieren Ihrer lync Server 2013-Topologie verwenden und Sie für die Edge-Installation auf externe Medien kopieren](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="a67ef-114">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a67ef-115">Sie können den Topology Builder nicht auf einem Edgeserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-115">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="a67ef-116">Sie müssen es auf dem Front-End-Server oder auf Standard Edition-Servern ausführen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-116">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="a67ef-117">Der Prozess zum Definieren Ihrer Edge-Server-Topologie erfolgt im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="a67ef-117">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="a67ef-118">Die drei Haupttypen von Edge-Server-Topologien, die Sie planen und konfigurieren, sind nachfolgend aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a67ef-118">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="a67ef-119">So definieren Sie die Topologie für einen einzelnen Edgeserver</span><span class="sxs-lookup"><span data-stu-id="a67ef-119">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="a67ef-120">So definieren Sie die Topologie für einen Lastenausgleichs-Edge-Server Pool</span><span class="sxs-lookup"><span data-stu-id="a67ef-120">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="a67ef-121">So definieren Sie die Topologie für einen Hardware Lastenausgleich-Edge-Pool</span><span class="sxs-lookup"><span data-stu-id="a67ef-121">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="a67ef-122">So definieren Sie die Topologie für einen einzelnen Edgeserver</span><span class="sxs-lookup"><span data-stu-id="a67ef-122">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="a67ef-123">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-123">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a67ef-124">Erweitern Sie in der Konsolenstruktur die Website, auf der Sie einen Edgeserver bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-124">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="a67ef-125">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-125">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a67ef-126">Klicken Sie unter **neuen Edge-Pool definieren**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-126">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a67ef-127">Gehen Sie unter **Definieren des FQDN des Edge-Pools**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-127">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-128">Geben Sie in **Pool FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Schnittstelle für den Edgeserver ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-128">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a67ef-129">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-129">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a67ef-130">Standardmäßig ist der Computername eines Computers, der nicht zu einer Domäne gehört, ein kurzer Name und kein FQDN.</span><span class="sxs-lookup"><span data-stu-id="a67ef-130">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a67ef-131">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="a67ef-131">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a67ef-132">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="a67ef-132">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a67ef-133">Verwenden Sie nur Standardzeichen (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="a67ef-133">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a67ef-134">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="a67ef-134">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a67ef-135">Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).</span><span class="sxs-lookup"><span data-stu-id="a67ef-135">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="a67ef-136">Details zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a67ef-136">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-137">Klicken Sie auf **Einzelcomputer Pool**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-137">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a67ef-138">Gehen **Sie unter Features auswählen**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-138">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-139">Wenn Sie einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriffsdienst, den lync Server 2013-Webkonferenzdienst und a/V-Edgedienst verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-139">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="a67ef-140">Wenn Sie beabsichtigen, die Föderation zu aktivieren, aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-140">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-141">Sie können diese Option auswählen, aber nur ein Edge-Pool oder Edgeserver in Ihrer Organisation kann extern für den Verbund veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-141">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="a67ef-142">Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="a67ef-142">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="a67ef-143">Wenn Ihre Bereitstellung beispielsweise einen Edge-Pool oder einen einzelnen Edgeserver umfasst, der in New York bereitgestellt und in London bereitgestellt wurde, und Sie die Unterstützung der Föderation auf dem New York Edge-Pool oder einem Single Edge-Server aktivieren, wird der Signal Verkehr für verbundene Benutzer durch das New York durchlaufen. Edge-Pool oder Single Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="a67ef-143">For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="a67ef-144">Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="a67ef-144">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-145">Wenn Sie beabsichtigen, das Extensible Messaging and Presence Protocol (XMPP) für Ihre Bereitstellung zu unterstützen, aktivieren Sie das Kontrollkästchen **XMPP-Föderation aktivieren (Port 5269)** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-145">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a67ef-146">Gehen **Sie unter IP-Optionen auswählen**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-146">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-147">**Aktivieren von IPv4 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-147">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a67ef-148">**Aktivieren von IPv6 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-148">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a67ef-149">**Aktivieren von IPv4 auf externer Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-149">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a67ef-150">**Aktivieren von IPv6 auf einer externen Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-150">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="a67ef-151">Sie können auch den Edgeserver oder den Edge-Pool so konfigurieren, dass für die externen IP-Adressen eine Adresse für die Netzwerkadressübersetzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a67ef-151">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a67ef-152">Aktivieren Sie dazu das Kontrollkästchen, um **die externe IP-Adresse dieses Edge-Pools von NAT zu übersetzen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-152">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="a67ef-153">Führen Sie in **externen FQDNs**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a67ef-153">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-154">Wenn Sie in **ausgewählte Features** einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriff, den Webkonferenzdienst und einen/V-Edgedienst verwenden möchten, geben Sie den externen FQDN in **SIP Access**ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-154">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-155">Wenn Sie diese Option auswählen, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (empfohlene Porteinstellungen: 5061 für Access-Edgedienst, 444 für Webkonferenz-Edgedienst und 443 für a/V-Edgedienst).</span><span class="sxs-lookup"><span data-stu-id="a67ef-155">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="a67ef-156">Wenn Sie diese Option auswählen, können Sie mögliche Verbindungsprobleme verhindern und die Konfiguration vereinfachen, da Sie dann dieselbe Portnummer (beispielsweise 443) für alle drei Dienste verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a67ef-156">Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-157">Wenn Sie in **"Features auswählen"** nicht die Verwendung eines einzelnen FQDN und einer IP-Adresse gewählt haben, geben Sie die externen FQDNs für **SIP-Zugriff**, Webkonferenz und Audiovideo ein, wobei die Standardanschlüsse beizubehalten sind. \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="a67ef-157">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="a67ef-158">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-158">Click **Next**.</span></span>

10. <span data-ttu-id="a67ef-159">Geben Sie unter interne **IP-Adresse definieren**die IP-Adresse Ihres Edge-Servers unter **interner IPv4-Adresse** und **interner IPv6** -Adresse ein, wie dies für Ihre Anforderungen angemessen ist.</span><span class="sxs-lookup"><span data-stu-id="a67ef-159">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements.</span></span> <span data-ttu-id="a67ef-160">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-160">Click **Next**.</span></span>

11. <span data-ttu-id="a67ef-161">Gehen Sie unter **externe IP-Adresse definieren**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-161">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-162">Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenzdienst und a/V-Edgedienst entschieden haben, geben Sie die externe IPv4-Adresse des Edgeserver in **SIP Access**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-162">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="a67ef-163">Wenn Sie sich für die Verwendung von IPv6-Adressen entschieden haben, geben Sie die externe IPv6-Adresse des Edge-Servers in **SIP Access**ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-163">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="a67ef-164">Wenn Sie keinen einzelnen FQDN und keine IP-Adresse für den SIP Access-, Webkonferenzdienst und a/v-Edgedienst verwendet haben, geben Sie die externen IPv4-Adressen des Edgeserver in **SIP Access**, **Web Conferencing**und **a/v Conferencing ein**, und Klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-164">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="a67ef-165">Wenn Sie sich für die Verwendung von IPv6-Adressen entschieden haben und nicht die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenzdienst und a/V-Edgedienst entschieden haben, geben Sie die externen IPv6 \*\*\*\*-Adressen des Edgeserver in **SIP Access**, Webkonferenzen und **a/ V Conferencing**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-165">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-166">Wenn Sie sich nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entschieden haben, wird dieses Dialogfeld nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-166">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="a67ef-167">Wenn Sie sich für die Verwendung von NAT entschieden haben, wird ein Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-167">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="a67ef-168">Geben Sie unter **öffentliche IPv4-Adresse für den A/V**-Edgedienst die öffentliche IPv4-Adresse ein, die von NAT übersetzt werden soll, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-168">In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-169">Dies sollte die externe IP-Adresse des A/V-Edgedienst sein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-169">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="a67ef-170">Wenn Sie sich für die Verwendung von NAT-und IPv6-Adressen entschieden haben, wird ein Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-170">If you chose to use NAT and IPv6 addresses, a dialog box appears.</span></span> <span data-ttu-id="a67ef-171">Geben Sie in **der öffentlichen IPv6-Adresse für den A/V**-Edgedienst die öffentliche IPv6-Adresse ein, die von NAT übersetzt werden soll, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-171">In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-172">Dies sollte die externe IP-Adresse des A/V-Edgedienst sein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-172">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="a67ef-173">Wählen Sie im Bereich "nächsten Hop **definieren**" im Pool für den **nächsten Hop**den Namen des internen Pools aus, der entweder ein Front-End-Pool oder ein Standard Edition-Pool sein kann.</span><span class="sxs-lookup"><span data-stu-id="a67ef-173">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="a67ef-174">Wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Director aus.</span><span class="sxs-lookup"><span data-stu-id="a67ef-174">Or, if your deployment includes a Director, select the Director.</span></span> <span data-ttu-id="a67ef-175">Klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-175">Then, click **Next**.</span></span>

15. <span data-ttu-id="a67ef-176">Geben Sie in **Front-End-Pools zuordnen**einen oder mehrere interne Pools an, die Front-End-Pools und Standard Edition-Server enthalten können, die diesem Edgeserver zugeordnet werden sollen, indem Sie die Namen der internen Pools auswählen, für die dieser Edgeserver verwendet werden soll. Kommunikation mit unterstützten externen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="a67ef-176">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-177">Jedem internen Pool für A/V-Datenverkehr kann nur ein Edge-Pool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-177">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="a67ef-178">Wenn Sie bereits über einen internen Pool verfügen, der einem Edge-Pool oder Edgeserver zugeordnet ist, wird eine Warnung angezeigt, die besagt, dass dem internen Pool bereits ein Edge-Pool oder ein Edgeserver zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a67ef-178">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="a67ef-179">Wenn Sie einen Pool auswählen, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.</span><span class="sxs-lookup"><span data-stu-id="a67ef-179">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="a67ef-180">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-180">Click **Finish**.</span></span>

17. <span data-ttu-id="a67ef-181">Veröffentlichen Sie Ihre Topologie.</span><span class="sxs-lookup"><span data-stu-id="a67ef-181">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="a67ef-182">So definieren Sie die Topologie für einen DNS Load Balancing Edge-Server Pool</span><span class="sxs-lookup"><span data-stu-id="a67ef-182">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="a67ef-183">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-183">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a67ef-184">Erweitern Sie in der Konsolenstruktur die Website, auf der Sie Edgeserver bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-184">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="a67ef-185">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-185">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a67ef-186">Klicken Sie unter **neuen Edge-Pool definieren**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-186">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a67ef-187">Gehen Sie unter **Definieren des FQDN des Edge-Pools**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-187">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-188">Geben Sie in **Pool FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die interne Verbindung des Edge-Pools ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-188">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a67ef-189">Der Name, den Sie für den Pool angeben, muss der Name des internen Edge-Pools sein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-189">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="a67ef-190">Dieser muss als FQDN definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-190">This must be defined as a FQDN.</span></span> <span data-ttu-id="a67ef-191">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="a67ef-191">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a67ef-192">Verwenden Sie nur Standardzeichen (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="a67ef-192">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a67ef-193">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="a67ef-193">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a67ef-194">Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).</span><span class="sxs-lookup"><span data-stu-id="a67ef-194">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-195">Klicken Sie auf **Pool mit mehreren Computern**, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-195">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="a67ef-196">Gehen **Sie unter Features auswählen**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-196">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-197">Wenn Sie einen einzelnen FQDN und eine IP-Adresse für den SIP Access, lync Server 2013 Web Conferencing Service und a/V Edge Services verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-197">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="a67ef-198">Wenn Sie beabsichtigen, die Föderation zu aktivieren, aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-198">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span> <span data-ttu-id="a67ef-199">Klicken Sie auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-199">Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-200">Sie können diese Option auswählen, aber nur ein Edge-Pool oder Edgeserver in Ihrer Organisation kann extern für den Verbund veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-200">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation.</span></span> <span data-ttu-id="a67ef-201">Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="a67ef-201">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="a67ef-202">Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder den einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder den einzelnen Edgeserver in New York.</span><span class="sxs-lookup"><span data-stu-id="a67ef-202">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="a67ef-203">Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="a67ef-203">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-204">Wenn Sie beabsichtigen, das Extensible Messaging and Presence Protocol (XMPP) für Ihre Bereitstellung zu unterstützen, aktivieren Sie das Kontrollkästchen **XMPP-Föderation aktivieren (Port 5269)** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-204">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a67ef-205">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-205">Click **Next**.</span></span>

8.  <span data-ttu-id="a67ef-206">Gehen **Sie unter IP-Optionen auswählen**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-206">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-207">**Aktivieren von IPv4 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-207">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a67ef-208">**Aktivieren von IPv6 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-208">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a67ef-209">**Aktivieren von IPv4 auf externer Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-209">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a67ef-210">**Aktivieren von IPv6 auf einer externen Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-210">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="a67ef-211">Sie können auch den Edgeserver oder den Edge-Pool so konfigurieren, dass für die externen IP-Adressen eine Adresse für die Netzwerkadressübersetzung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a67ef-211">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a67ef-212">Aktivieren Sie dazu das Kontrollkästchen, um **die externe IP-Adresse dieses Edge-Pools von NAT zu übersetzen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-212">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="a67ef-213">Führen Sie in **externen FQDNs**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a67ef-213">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-214">Wenn Sie in **ausgewählte Features** einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriff, den Webkonferenzdienst und einen/V-Edgedienst verwenden möchten, geben Sie den externen FQDN in **SIP Access**ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-214">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-215">Wenn Sie diese Option auswählen, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (empfohlene Porteinstellungen: 5061 für Access-Edgedienst, 444 für Webkonferenz-Edgedienst und 443 für a/V-Edgedienst).</span><span class="sxs-lookup"><span data-stu-id="a67ef-215">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="a67ef-216">Wenn Sie diese Option auswählen, können Sie mögliche Verbindungsprobleme verhindern und die Konfiguration vereinfachen, da Sie dann dieselbe Portnummer (beispielsweise 443) für alle drei Dienste verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a67ef-216">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-217">Wenn Sie in **"Features auswählen"** nicht die Verwendung eines einzelnen FQDN und einer IP-Adresse gewählt haben, geben Sie den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools für den **SIP-Zugriff**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-217">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="a67ef-218">Geben \*\*\*\* Sie in Webkonferenzen den FQDN ein, den Sie für die öffentlich zugängliche Seite des Edge-Pools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-218">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a67ef-219">Geben Sie in **Audio/Video**den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-219">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a67ef-220">Verwenden Sie die Standardanschlüsse.</span><span class="sxs-lookup"><span data-stu-id="a67ef-220">Use the default ports.</span></span>

10. <span data-ttu-id="a67ef-221">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-221">Click **Next**.</span></span>

11. <span data-ttu-id="a67ef-222">Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-222">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="a67ef-223">Gehen Sie unter **Interner FQDN und IP-Adresse**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-223">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-224">Geben Sie unter **interne IPv4-Adresse**die IPv4-Adresse und die **interne IPv6-Adresse** ein, die für Ihre Anforderungen für den ersten Edgeserver, den Sie in diesem Pool erstellen möchten, geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="a67ef-224">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="a67ef-225">Geben Sie im **internen FQDN**den FQDN des ersten Edge-Servers ein, den Sie in diesem Pool erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-225">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-226">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-226">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="a67ef-227">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="a67ef-227">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="a67ef-228">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="a67ef-228">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a67ef-229">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="a67ef-229">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="a67ef-230">Verwenden Sie beim Zuweisen von FQDNs ihrer lync-Server,-Edgeserver,-Pools und-Arrays nur Standardzeichen (einschließlich a – z, a – z, 0 – 9 und Bindestriche).</span><span class="sxs-lookup"><span data-stu-id="a67ef-230">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="a67ef-231">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="a67ef-231">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a67ef-232">Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).</span><span class="sxs-lookup"><span data-stu-id="a67ef-232">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="a67ef-233">Details zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a67ef-233">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="a67ef-234">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-234">Click **Next**.</span></span>

14. <span data-ttu-id="a67ef-235">Gehen Sie unter **externe IP-Adressen definieren**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-235">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-236">Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Edgedienst entschieden haben, geben Sie die externe IP-Adresse des Edgeserver in **SIP Access**ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-236">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a67ef-237">Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-237">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a67ef-238">Geben \*\*\*\* Sie in Webkonferenzen die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-238">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a67ef-239">Geben Sie in **A/V-Konferenzen**die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-239">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="a67ef-240">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-240">Click **Next**.</span></span>

16. <span data-ttu-id="a67ef-241">Wenn Sie sich für die Aktivierung von IPv6-Adressen entschieden haben, gehen Sie unter **definieren externer IP-Adressen**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-241">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-242">Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Edgedienst entschieden haben, geben Sie die externe IPv6-Adresse des Edgeserver in **SIP Access**ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-242">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a67ef-243">Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-243">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a67ef-244">Geben \*\*\*\* Sie in Webkonferenzen die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-244">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a67ef-245">Geben Sie in **A/V-Konferenzen**die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-245">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-246">Wenn Sie sich nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entschieden haben, wird dieses Dialogfeld nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-246">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="a67ef-247">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-247">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-248">Der erste Edge-Server, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-248">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="a67ef-249">Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**, und wiederholen Sie dann die Schritte 11 bis 14 für den zweiten Edgeserver, den Sie dem Edge-Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-249">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="a67ef-250">Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie unter **Definieren der Computer in diesem Pool**auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-250">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-251">An dieser Stelle können Sie die beiden Edgeserver in Ihrem Pool sehen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-251">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="a67ef-252">Wenn Sie sich für die Verwendung von NAT entschieden haben, wird ein Dialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-252">If you chose to use NAT, a dialog box appears.</span></span> <span data-ttu-id="a67ef-253">Geben Sie unter **öffentliche IP-Adresse**die öffentlichen IPv4-und IPv6-Adressen (sofern erforderlich) ein, die von NAT übersetzt werden sollen, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-253">In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-254">Dies sollte die externe IP-Adresse der A/V-Kante sein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-254">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="a67ef-255">Wählen Sie im **Feld nächsten Hop definieren**in der Liste **Nächster Hop-Pool** den Namen des internen Pools aus, der entweder ein Front-End-Pool oder ein Standard Edition-Pool sein kann.</span><span class="sxs-lookup"><span data-stu-id="a67ef-255">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="a67ef-256">Wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors aus.</span><span class="sxs-lookup"><span data-stu-id="a67ef-256">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="a67ef-257">Klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-257">Then, click **Next**.</span></span>

22. <span data-ttu-id="a67ef-258">Geben Sie in **Front-End-Pools zuordnen**einen oder mehrere interne Pools an, die Front-End-Pools und Standard Edition-Server enthalten können, die diesem Edgeserver zugeordnet werden sollen, indem Sie die Namen der internen Pools auswählen, für die dieser Edgeserver verwendet werden soll. Kommunikation mit unterstützten externen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="a67ef-258">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-259">Jedem internen Pool für A/V-Datenverkehr kann nur ein Edge-Pool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-259">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="a67ef-260">Wenn Sie bereits über einen internen Pool verfügen, der einem Edge-Pool oder Edgeserver zugeordnet ist, wird eine Warnung angezeigt, die besagt, dass dem internen Pool bereits ein Edge-Pool oder ein Edgeserver zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a67ef-260">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="a67ef-261">Wenn Sie einen Pool auswählen, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.</span><span class="sxs-lookup"><span data-stu-id="a67ef-261">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="a67ef-262">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-262">Click **Finish**.</span></span>

24. <span data-ttu-id="a67ef-263">Veröffentlichen Sie Ihre Topologie.</span><span class="sxs-lookup"><span data-stu-id="a67ef-263">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="a67ef-264">So definieren Sie die Topologie für einen Hardwarelastenausgleich-Edgeserver-Pool</span><span class="sxs-lookup"><span data-stu-id="a67ef-264">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="a67ef-265">Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-265">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a67ef-266">Erweitern Sie in der Konsolenstruktur die Website, auf der Sie Edgeserver bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-266">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="a67ef-267">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und wählen Sie dann **neuer Edge-Pool**aus.</span><span class="sxs-lookup"><span data-stu-id="a67ef-267">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="a67ef-268">Klicken Sie unter **neuen Edge-Pool definieren**auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-268">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="a67ef-269">Gehen Sie unter **Definieren des FQDN des Edge-Pools**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-269">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-270">Geben Sie in **FQDN**den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den Sie für die interne Seite des Edge-Pools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-270">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a67ef-271">Der Name, den Sie für den Pool angeben, muss der Name des internen Edge-Pools sein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-271">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="a67ef-272">Dieser muss als FQDN definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-272">This must be defined as a FQDN.</span></span> <span data-ttu-id="a67ef-273">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="a67ef-273">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="a67ef-274">Verwenden Sie nur Standardzeichen (also A – Z, a – z, 0 – 9 und Bindestriche) beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="a67ef-274">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="a67ef-275">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="a67ef-275">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="a67ef-276">Nicht standardmäßige Zeichen in einem FQDN werden häufig nicht von externen DNS-und öffentlichen CAS unterstützt (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss).</span><span class="sxs-lookup"><span data-stu-id="a67ef-276">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="a67ef-277">Klicken Sie auf **Pool für mehrere Computer**und dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-277">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="a67ef-278">Gehen **Sie unter Features auswählen** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-278">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="a67ef-279">Wenn Sie einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriffsdienst, den lync Server-Webkonferenzdienst und den a/V-Edgedienst verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN #a0 IP-Adresse verwenden** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-279">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="a67ef-280">Wenn Sie beabsichtigen, die Föderation zu aktivieren, aktivieren Sie das Kontrollkästchen **Föderation für diesen Edge-Pool aktivieren (Port 5061)** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-280">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-281">Sie können diese Option auswählen, es kann jedoch nur ein Edge-Pool oder ein Edgeserver in Ihrer Organisation extern für den Verbund veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-281">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation.</span></span> <span data-ttu-id="a67ef-282">Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server.</span><span class="sxs-lookup"><span data-stu-id="a67ef-282">All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server.</span></span> <span data-ttu-id="a67ef-283">Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder den einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder den einzelnen Edgeserver in New York.</span><span class="sxs-lookup"><span data-stu-id="a67ef-283">For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server.</span></span> <span data-ttu-id="a67ef-284">Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="a67ef-284">This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-285">Wenn Sie beabsichtigen, das Extensible Messaging and Presence Protocol (XMPP) für Ihre Bereitstellung zu unterstützen, aktivieren Sie das Kontrollkästchen **XMPP-Föderation aktivieren (Port 5269)** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-285">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="a67ef-286">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-286">Click **Next**.</span></span>

8.  <span data-ttu-id="a67ef-287">Gehen **Sie unter IP-Optionen auswählen**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-287">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-288">**Aktivieren von IPv4 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-288">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a67ef-289">**Aktivieren von IPv6 auf interner Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die interne Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-289">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="a67ef-290">**Aktivieren von IPv4 auf externer Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-290">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="a67ef-291">**Aktivieren von IPv6 auf einer externen Schnittstelle**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die externe Schnittstelle des Edge-Servers oder des Edge-Pools anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-291">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a67ef-292">Aktivieren Sie <STRONG>nicht</STRONG> das Kontrollkästchen <STRONG>externe IP-Adresse des Edge-Pools, der von NAT übersetzt wird</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="a67ef-292"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box.</span></span> <span data-ttu-id="a67ef-293">Netzwerkadressübersetzung (Network Address Translation, NAT) wird nicht unterstützt, wenn Sie den Hardwarelastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-293">Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="a67ef-294">Führen Sie in **externen FQDNs**die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a67ef-294">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-295">Wenn Sie in **ausgewählte Features** einen einzelnen FQDN und eine IP-Adresse für den SIP-Zugriff, den Webkonferenzdienst und einen/V-Edgedienst verwenden möchten, geben Sie den externen FQDN in **SIP Access**ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-295">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-296">Wenn Sie diese Option auswählen, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (empfohlene Porteinstellungen: 5061 für Access-Edgedienst, 444 für Webkonferenz-Edgedienst und 443 für a/V-Edgedienst).</span><span class="sxs-lookup"><span data-stu-id="a67ef-296">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="a67ef-297">Wenn Sie diese Option auswählen, können Sie mögliche Verbindungsprobleme verhindern und die Konfiguration vereinfachen, da Sie dann dieselbe Portnummer (beispielsweise 443) für alle drei Dienste verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a67ef-297">By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="a67ef-298">Wenn Sie in **"Features auswählen"** nicht die Verwendung eines einzelnen FQDN und einer IP-Adresse gewählt haben, geben Sie den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools für den **SIP-Zugriff**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-298">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**.</span></span> <span data-ttu-id="a67ef-299">Geben \*\*\*\* Sie in Webkonferenzen den FQDN ein, den Sie für die öffentlich zugängliche Seite des Edge-Pools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-299">In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a67ef-300">Geben Sie in **Audio/Video**den FQDN ein, den Sie für die öffentliche Seite des Edge-Pools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-300">In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool.</span></span> <span data-ttu-id="a67ef-301">Verwenden Sie die Standardanschlüsse.</span><span class="sxs-lookup"><span data-stu-id="a67ef-301">Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="a67ef-302">Hierbei handelt es sich um die öffentlich zugänglichen VIP-FQDNs (Virtual IP) für den Pool.</span><span class="sxs-lookup"><span data-stu-id="a67ef-302">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="a67ef-303">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-303">Click **Next**.</span></span>

11. <span data-ttu-id="a67ef-304">Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-304">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="a67ef-305">Gehen Sie unter **externe IP-Adressen definieren**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-305">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-306">Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenzdienst und a/V-Edgedienst entschieden haben, geben Sie die externe IPv4-Adresse des Edgeserver in **SIP Access**ein. externe IP-Adresse des Edge-Servers in **SIP Access**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-306">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a67ef-307">Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-307">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a67ef-308">Geben \*\*\*\* Sie in Webkonferenzen die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-308">In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a67ef-309">Geben Sie in **A/V-Konferenzen**die IP-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-309">In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="a67ef-310">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-310">Click **Next**.</span></span>

14. <span data-ttu-id="a67ef-311">Wenn Sie sich für die Aktivierung von IPv6-Adressen entschieden haben, gehen Sie unter **definieren externer IP-Adressen**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="a67ef-311">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="a67ef-312">Wenn Sie sich für die Verwendung eines einzelnen FQDN und einer IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Edgedienst entschieden haben, geben Sie die externe IPv6-Adresse des Edgeserver in **SIP Access**ein.</span><span class="sxs-lookup"><span data-stu-id="a67ef-312">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="a67ef-313">Wenn Sie nicht entschieden haben, einen einzelnen FQDN und eine IP-Adresse für den SIP Access-, Webkonferenz-und a/V-Konferenzdienst zu verwenden, geben Sie die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers für den **SIP-Zugriff**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-313">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**.</span></span> <span data-ttu-id="a67ef-314">Geben \*\*\*\* Sie in Webkonferenzen die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-314">In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server.</span></span> <span data-ttu-id="a67ef-315">Geben Sie in **A/V-Konferenzen**die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edge-Pool-Servers gewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a67ef-315">In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-316">Wenn Sie sich nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entschieden haben, wird dieses Dialogfeld nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-316">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="a67ef-317">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-317">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-318">Der erste Edge-Server, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a67ef-318">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="a67ef-319">Klicken Sie unter **Computer in diesem Pool definieren**auf **Hinzufügen**, und wiederholen Sie dann die Schritte 11 bis 14 für den zweiten Edgeserver, den Sie Ihrem Edge-Pool hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="a67ef-319">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="a67ef-320">Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie unter **Definieren der Computer in diesem Pool**auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="a67ef-320">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-321">An dieser Stelle können Sie die beiden Edgeserver in Ihrem Pool sehen.</span><span class="sxs-lookup"><span data-stu-id="a67ef-321">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="a67ef-322">Wählen Sie im **Feld nächsten Hop definieren**in der Liste **Nächster Hop-Pool** den Namen des internen Pools aus, der entweder ein Front-End-Pool oder ein Standard Edition-Pool sein kann.</span><span class="sxs-lookup"><span data-stu-id="a67ef-322">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool.</span></span> <span data-ttu-id="a67ef-323">Wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors aus.</span><span class="sxs-lookup"><span data-stu-id="a67ef-323">Or, if your deployment includes a Director, select the name of the Director.</span></span> <span data-ttu-id="a67ef-324">Klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-324">Then, click **Next**.</span></span>

19. <span data-ttu-id="a67ef-325">Geben Sie in **Front-End-Pools zuordnen**einen oder mehrere interne Pools an, die Front-End-Pools und Standard Edition-Server enthalten können, die diesem Edgeserver zugeordnet werden sollen, indem Sie die Namen der internen Pools auswählen, für die dieser Edgeserver verwendet werden soll. Kommunikation mit unterstützten externen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="a67ef-325">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a67ef-326">Jedem internen Pool für A/V-Datenverkehr kann nur ein Edge-Pool mit Lastenausgleich oder ein einzelner Edgeserver zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="a67ef-326">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic.</span></span> <span data-ttu-id="a67ef-327">Wenn Sie bereits über einen internen Pool verfügen, der einem Edge-Pool oder Edgeserver zugeordnet ist, wird eine Warnung angezeigt, die besagt, dass dem internen Pool bereits ein Edge-Pool oder ein Edgeserver zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a67ef-327">If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server.</span></span> <span data-ttu-id="a67ef-328">Wenn Sie einen Pool auswählen, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.</span><span class="sxs-lookup"><span data-stu-id="a67ef-328">If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="a67ef-329">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="a67ef-329">Click **Finish**.</span></span>

21. <span data-ttu-id="a67ef-330">Veröffentlichen Sie Ihre Topologie.</span><span class="sxs-lookup"><span data-stu-id="a67ef-330">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

