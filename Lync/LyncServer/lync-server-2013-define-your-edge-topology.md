---
title: 'Lync Server 2013: Definieren Ihrer Edge-Topologie'
description: 'Lync Server 2013: definieren Sie die Edge-Topologie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define your edge topology
ms:assetid: 787b23f1-8fa0-4c37-abf2-c516c5dd66f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398591(v=OCS.15)
ms:contentKeyID: 48184562
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd4aa16ca23d24f0edd92189216030ef926fc841
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572941"
---
# <a name="define-your-edge-topology-in-lync-server-2013"></a><span data-ttu-id="82c59-103">Definieren Ihrer Edge-Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="82c59-103">Define your edge topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82c59-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="82c59-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="82c59-105">Sie müssen den Topologie-Generator verwenden, um Ihre Topologie zu erstellen, und Sie müssen mindestens eine interne Front-End-Pool oder Standard Edition-Server einrichten, bevor Sie Ihre Edgeserver bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="82c59-105">You must use Topology Builder to build your topology and you must set up at least one internal Front End pool or Standard Edition server before you can deploy your Edge Server.</span></span> <span data-ttu-id="82c59-106">Verwenden Sie das folgende Verfahren, um die Edge-Topologie für einen einzelnen Edgeserver zu definieren, und verwenden Sie dann die Verfahren unter [Veröffentlichen Ihrer Topologie in lync Server 2013](lync-server-2013-publish-your-topology.md) , und [exportieren Sie Ihre lync Server 2013 Topologie, und kopieren Sie Sie in externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) , um die Topologie zu veröffentlichen und Sie für Ihre Edgeserver verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="82c59-106">Use the following procedure to define the edge topology for a single Edge Server, and then use the procedures in [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) to publish the topology and make it available to your Edge Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="82c59-p102">Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c59-p102">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="82c59-109">Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, müssen Sie als Benutzer angemeldet sein, der Mitglied der Gruppe RTCUniversalServerAdmins und Domänenadministratoren ist.</span><span class="sxs-lookup"><span data-stu-id="82c59-109">To successfully publish, enable, or disable a topology when adding or removing a server role, you must be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="82c59-110">Sie können auch die Administratorrechte und-Berechtigungen erteilen, die für das Hinzufügen von Serverrollen zu einem Benutzerkonto erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="82c59-110">You can also grant the administrator rights and permissions required for adding server roles to a user account.</span></span> <span data-ttu-id="82c59-111">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Standard Edition-Server-oder Enterprise Edition-Server-Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="82c59-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="82c59-112">Für andere Konfigurationsänderungen müssen Sie lediglich Mitglied der Gruppe "RTCUniversalServerAdmins" sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-112">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<span data-ttu-id="82c59-113">Wenn Sie die Edge-Topologie bei der Definition und Veröffentlichung ihrer internen Topologie definiert haben und keine Änderungen an der zuvor definierten Edge-Topologie erforderlich sind, müssen Sie Sie nicht definieren und erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="82c59-113">If you defined your edge topology when you defined and published your internal topology, and no changes are required to the edge topology that you previously defined, you do not need to do define it and publish it again.</span></span> <span data-ttu-id="82c59-114">Verwenden Sie das folgende Verfahren nur, wenn Sie Änderungen an ihrer Edge-Topologie vornehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="82c59-114">Use the following procedure only if you need to make changes to your edge topology.</span></span> <span data-ttu-id="82c59-115">Sie müssen die zuvor definierte und veröffentlichte Topologie für Ihre Edgeserver zur Verfügung stellen, und zwar mithilfe des Verfahrens unter [Exportieren Ihrer lync Server 2013 Topologie und Kopieren der Topologie auf externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span><span class="sxs-lookup"><span data-stu-id="82c59-115">You must make the previously defined and published topology available to your Edge Servers, which you do by using the procedure in [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="82c59-116">Sie können den Topologie-Generator nicht aus einem Edgeserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="82c59-116">You cannot run Topology Builder from an Edge Server.</span></span> <span data-ttu-id="82c59-117">Er muss entweder auf dem Front-End-Server oder auf Standard Edition-Servern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="82c59-117">You must run it from your Front End Server or Standard Edition servers.</span></span>



</div>

<span data-ttu-id="82c59-118">Der Vorgang zum Definieren Ihrer Edgeserver Topologie erfolgt im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="82c59-118">The process to define your Edge Server topology is done in Topology Builder.</span></span> <span data-ttu-id="82c59-119">Die drei primären Edgeserver-Topologietypen, die Sie planen und konfigurieren, werden nachfolgend aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="82c59-119">The three primary types of Edge Server topologies that you plan and configure are listed below:</span></span>

  - <span data-ttu-id="82c59-120">So definieren Sie die Topologie für einen einzelnen Edgeserver</span><span class="sxs-lookup"><span data-stu-id="82c59-120">To define the Topology for a Single Edge Server</span></span>

  - <span data-ttu-id="82c59-121">So definieren Sie die Topologie für einen Edgeserverpool mit Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="82c59-121">To define the Topology for a Load Balanced Edge Server Pool</span></span>

  - <span data-ttu-id="82c59-122">So definieren Sie die Topologie für einen Edgeserverpool mit Hardwarelastenausgleich</span><span class="sxs-lookup"><span data-stu-id="82c59-122">To define the Topology for a Hardware Load Balanced Edge Pool</span></span>

<div>

## <a name="to-define-the-topology-for-a-single-edge-server"></a><span data-ttu-id="82c59-123">So definieren Sie die Topologie für einen einzelnen Edgeserver</span><span class="sxs-lookup"><span data-stu-id="82c59-123">To define the topology for a single Edge Server</span></span>

1.  <span data-ttu-id="82c59-124">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="82c59-124">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="82c59-125">Erweitern Sie in der Konsolenstruktur den Standort, an dem ein Edgeserver bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82c59-125">In the console tree, expand the site in which you want to deploy an Edge Server.</span></span>

3.  <span data-ttu-id="82c59-126">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.</span><span class="sxs-lookup"><span data-stu-id="82c59-126">Right-click **Edge pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="82c59-127">Klicken Sie in **Neuen Edgepool definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-127">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="82c59-128">Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-128">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-129">Geben Sie im Feld **Pool-FQDN** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der internen Schnittstelle für den Edgeserver ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-129">In **Pool FQDN**, type the fully qualified domain name (FQDN) of the internal interface for the Edge Server.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="82c59-130">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82c59-130">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="82c59-131">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="82c59-131">By default the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="82c59-132">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="82c59-132">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="82c59-133">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="82c59-133">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="82c59-134">Verwenden Sie beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver und Pools nur Standardzeichen (also A–Z, a–z, 0–9 und Bindestriche).</span><span class="sxs-lookup"><span data-stu-id="82c59-134">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="82c59-135">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="82c59-135">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="82c59-136">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="82c59-136">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="82c59-137">Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="82c59-137">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-138">Klicken Sie auf **Pool mit einem Computer** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-138">Click **Single computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="82c59-139">Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-139">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-140">Wenn Sie einen einzelnen FQDN und eine einzige IP-Adresse für den SIP-Zugriffsdienst, lync Server 2013 Webkonferenzdienst und a/V-Edgedienst verwenden möchten, aktivieren Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .</span><span class="sxs-lookup"><span data-stu-id="82c59-140">If you plan to use a single FQDN and IP address for the SIP Access service, Lync Server 2013 Web Conferencing service, and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="82c59-141">Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="82c59-141">If you plan to enable federation select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-p108">Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise ff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienje einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="82c59-p108">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For example, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-146">Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)**.</span><span class="sxs-lookup"><span data-stu-id="82c59-146">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="82c59-147">Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-147">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-148">**IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-148">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="82c59-149">**IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-149">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="82c59-150">**IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-150">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="82c59-151">**IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-151">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="82c59-152">Sie können die Edgeserver oder Edgepool auch so konfigurieren, dass eine Adresse für die Netzwerkadressübersetzung für die externen IP-Adressen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="82c59-152">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="82c59-153">Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.</span><span class="sxs-lookup"><span data-stu-id="82c59-153">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

8.  <span data-ttu-id="82c59-154">Führen Sie in **Externe FQDNs** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-154">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-155">Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie in **SIP-Zugriff** den externen FQDN ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-155">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-p110">Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061 für den Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z. B. 443) für alle drei Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c59-p110">If you choose this option, you must specify a different port number for each of the edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). Selecting this option can help prevent potential connectivity issues, and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-158">Wenn Sie in **Funktionen auswählen** nicht festgelegt haben, dass ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie die externen FQDNs für **SIP-Zugriff**, **Webkonferenzen** und **Audio/Video** ein. Behalten Sie dabei die Standardports bei.</span><span class="sxs-lookup"><span data-stu-id="82c59-158">If in **Select features** you did not chose to use a single FQDN and IP Address, type the External FQDNs for **SIP Access**, **Web Conferencing** and **Audio Video**, keeping the default ports.</span></span>

9.  <span data-ttu-id="82c59-159">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-159">Click **Next**.</span></span>

10. <span data-ttu-id="82c59-p111">Geben Sie unter **Interne IP-Adresse definieren** in **Interne IPv4-Adresse** bzw. **Interne IPv6-Adresse** die IP-Adresse Ihres Edgeservers ein, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p111">In **Define the Internal IP address**, type the IP address of your Edge Server in **Internal IPv4 address** and **Internal IPv6 address** as is appropriate for your requirements. Click **Next**.</span></span>

11. <span data-ttu-id="82c59-162">Führen Sie in **Externe IP-Adresse definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-162">In **Define the External IP address**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-163">Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv4-Adresse des Edgeservers ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-163">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="82c59-164">Wenn Sie IPv6-Adressen verwenden möchten, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-164">If you chose to use IPv6 addresses, type the external IPv6 address of the Edge Server in **SIP Access**, and then, click **Next**.</span></span>
    
      - <span data-ttu-id="82c59-165">Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff**, **Webkonferenzen** und **A/V-Konferenzen** die externen IPv4-Adressen der Edgeserver ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-165">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="82c59-166">Wenn Sie IPv6-Adressen nutzen möchten und nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff**, **Webkonferenzen** und **A/V-Konferenzen** die externen IPv6-Adressen der Edgeserver ein. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-166">If you chose to use IPv6 addresses and did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 addresses of the Edge Server in **SIP Access**, **Web Conferencing**, and **A/V Conferencing**, and then click **Next**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-167">Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c59-167">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

        
        </div>

12. <span data-ttu-id="82c59-p112">Wenn Sie die Verwendung der Netzwerkadressenübersetzung festgelegt haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IPv4-Adresse des A/V-Edgediensts** die öffentliche IPv4-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p112">If you chose to use NAT, a dialog box appears. In **Public IPv4 address for the A/V Edge service**, type the public IPv4 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-170">Dies muss die externe IP-Adresse des A/V-Edgediensts sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-170">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

13. <span data-ttu-id="82c59-p113">Wenn Sie sich für die Verwendung der Netzwerkadressenübersetzung und IPv6-Adressen entschieden haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IPv6-Adresse des A/V-Edgediensts** die öffentliche IPv6-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p113">If you chose to use NAT and IPv6 addresses, a dialog box appears. In **Public IPv6 address for the A/V Edge service**, type the public IPv6 address to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-173">Dies muss die externe IP-Adresse des A/V-Edgediensts sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-173">This should be the external IP address of the A/V Edge service.</span></span>

    
    </div>

14. <span data-ttu-id="82c59-p114">Wählen Sie in **Nächsten Hop definieren** unter **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Alternativ können Sie, wenn Ihre Bereitstellung einen Director umfasst, den Namen des Directors auswählen. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p114">In **Define the next hop**, in **Next hop pool**, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the Director. Then, click **Next**.</span></span>

15. <span data-ttu-id="82c59-177">Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c59-177">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pools that are to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-p115">Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.</span><span class="sxs-lookup"><span data-stu-id="82c59-p115">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

16. <span data-ttu-id="82c59-181">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="82c59-181">Click **Finish**.</span></span>

17. <span data-ttu-id="82c59-182">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="82c59-182">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-dns-load-balanced-edge-server-pool"></a><span data-ttu-id="82c59-183">So definieren Sie die Topologie für einen Edgeserverpool mit DNS-Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="82c59-183">To define the topology for a DNS load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="82c59-184">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="82c59-184">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="82c59-185">Erweitern Sie in der Konsolenstruktur den Standort, an dem Edgeserver bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="82c59-185">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="82c59-186">Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **Neuer Edgepool**.</span><span class="sxs-lookup"><span data-stu-id="82c59-186">Right-click **Edge Pools**, and then click **New Edge Pool**.</span></span>

4.  <span data-ttu-id="82c59-187">Klicken Sie in **Neuen Edgepool definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-187">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="82c59-188">Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-188">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-189">Geben Sie im Feld **Pool-FQDN** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für die interne Verbindung des Edgepools an.</span><span class="sxs-lookup"><span data-stu-id="82c59-189">In **Pool FQDN**, type the fully qualified domain name (FQDN) for the internal connection of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="82c59-190">Der Name, den Sie für den Pool angeben, muss der interne Name des Edgepools sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-190">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="82c59-191">Dieser muss als vollqualifizierter Domänenname (FQDN) definert sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-191">This must be defined as a FQDN.</span></span> <span data-ttu-id="82c59-192">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="82c59-192">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="82c59-193">Verwenden Sie nur Standardzeichen (also A–Z, a–z, 0–9 und Bindestriche) beim Zuweisen von FQDNs der Lync-Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="82c59-193">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="82c59-194">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="82c59-194">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="82c59-195">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="82c59-195">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-196">Klicken Sie auf **Pool mit mehreren Computern** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-196">Click **Multiple computer pool**, and then click **Next**.</span></span>

6.  <span data-ttu-id="82c59-197">Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-197">In **Select features**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-198">Wenn Sie einen einzelnen FQDN und eine einzige IP-Adresse für den SIP-Zugriff verwenden möchten, aktivieren Sie lync Server 2013 Webkonferenzdienst-und a/V-Edgedienst das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** .</span><span class="sxs-lookup"><span data-stu-id="82c59-198">If you plan to use a single FQDN and IP address for the SIP access, Lync Server 2013 Web Conferencing service and A/V Edge services, select the **Use a single FQDN and IP Address** check box.</span></span>
    
      - <span data-ttu-id="82c59-p117">Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund aktivieren (Port 5061)**. Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p117">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box. Click **Next**</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-p118">Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="82c59-p118">You can select this option, but only one Edge pool or Edge Server in your organization can be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-205">Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)**.</span><span class="sxs-lookup"><span data-stu-id="82c59-205">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="82c59-206">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-206">Click **Next**.</span></span>

8.  <span data-ttu-id="82c59-207">Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-207">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-208">**IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-208">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="82c59-209">**IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-209">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="82c59-210">**IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-210">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="82c59-211">**IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-211">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <span data-ttu-id="82c59-212">Sie können die Edgeserver oder Edgepool auch so konfigurieren, dass eine Adresse für die Netzwerkadressübersetzung für die externen IP-Adressen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="82c59-212">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="82c59-213">Dazu aktivieren Sie einfach das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der Netzwerkadressenübersetzung übersetzt**.</span><span class="sxs-lookup"><span data-stu-id="82c59-213">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>

9.  <span data-ttu-id="82c59-214">Führen Sie in **Externe FQDNs** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-214">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-215">Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** den externen FQDN ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-215">If in **Select features** you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-p120">Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061 für den Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z. B. 443) für alle drei Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c59-p120">If you choose this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-p121">Wenn Sie unter **Funktionen auswählen** nicht festgelegt haben, dass nur ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie den FQDN für die öffentliche Seite des Edgepools in **SIP-Zugriff** ein. Geben Sie in **Webkonferenzen** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **Audio/Video** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Verwenden Sie die Standardports.</span><span class="sxs-lookup"><span data-stu-id="82c59-p121">If in **Select features** you did not chose to use a single FQDN and IP Address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>

10. <span data-ttu-id="82c59-222">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-222">Click **Next**.</span></span>

11. <span data-ttu-id="82c59-223">Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="82c59-223">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="82c59-224">Führen Sie in **Interner FQDN und interne IP-Adresse** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-224">In **Internal FQDN and IP address**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-225">Geben Sie entsprechend Ihren Anforderungen in **Interne IPv4-Adresse** die IPv4-Adresse bzw. in **Interne IPv6-Adresse** die IPv6-Adresse des ersten Edgeservers ein, der in diesem Pool erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82c59-225">In **Internal IPv4 address**, type the IPv4 address and **Internal IPv6 address** as is appropriate for your requirements for the first Edge Server that you want to create in this pool.</span></span>
    
      - <span data-ttu-id="82c59-226">Geben Sie in **Interner FQDN** den FQDN des ersten Edgeservers ein, der in diesem Pool erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82c59-226">In **Internal FQDN**, type the FQDN of the first Edge Server that you want to create in this pool.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-227">Der angegebene Name muss mit dem auf dem Server konfigurierten Computernamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="82c59-227">The name you specify must be identical to the computer name configured on the server.</span></span> <span data-ttu-id="82c59-228">Der Name eines Computers, der nicht Mitglied einer Domäne ist, ist standardmäßig kein FQDN, sondern ein Kurzname.</span><span class="sxs-lookup"><span data-stu-id="82c59-228">By default, the computer name of a computer that is not joined to a domain is a short name, not an FQDN.</span></span> <span data-ttu-id="82c59-229">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="82c59-229">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="82c59-230">Daher müssen Sie ein DNS-Suffix für den Namen des Computers konfigurieren, der als Edgeserver bereitgestellt werden soll und nicht Mitglied einer Domäne ist.</span><span class="sxs-lookup"><span data-stu-id="82c59-230">So, you must configure a DNS suffix on the name of the computer to be deployed as an Edge Server that is not joined to a domain.</span></span> <span data-ttu-id="82c59-231">Verwenden Sie beim Zuweisen von FQDNs der Server mit Lync Server, Edgeserver, Pools und Arrays nur Standardzeichen (A-Z, a-z, 0-9 und Bindestriche).</span><span class="sxs-lookup"><span data-stu-id="82c59-231">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, pools, and arrays.</span></span> <span data-ttu-id="82c59-232">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="82c59-232">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="82c59-233">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="82c59-233">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span> <span data-ttu-id="82c59-234">Ausführliche Informationen zum Hinzufügen eines DNS-Suffix zu einem Computernamen finden Sie unter <A href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="82c59-234">For details about adding a DNS suffix to a computer name, see <A href="lync-server-2013-configure-dns-for-edge-support.md">Configure DNS for edge support in Lync Server 2013</A>.</span></span>

        
        </div>

13. <span data-ttu-id="82c59-235">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-235">Click **Next**.</span></span>

14. <span data-ttu-id="82c59-236">Führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-236">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-237">Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden soll, geben Sie in **SIP-Zugriff** die externe IP-Adresse des Edgeservers ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-237">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="82c59-p123">Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IP-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="82c59-p123">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

15. <span data-ttu-id="82c59-241">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-241">Click **Next**.</span></span>

16. <span data-ttu-id="82c59-242">Wenn Sie IPv6-Adressen aktivieren möchten, führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-242">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-243">Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-243">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="82c59-p124">Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IPv6-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="82c59-p124">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-247">Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c59-247">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

17. <span data-ttu-id="82c59-248">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="82c59-248">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-249">Der erste Edgeserver, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c59-249">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

18. <span data-ttu-id="82c59-250">Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**, und wiederholen Sie die Schritte 11 bis 14 für den zweiten Edgeserver, der zum Edgepool hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82c59-250">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to you Edge pool.</span></span>

19. <span data-ttu-id="82c59-251">Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-251">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-252">Die beiden Edgeserver werden nun in Ihrem Pool angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c59-252">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

20. <span data-ttu-id="82c59-p125">Wenn Sie die Verwendung der Netzwerkadressenübersetzung festgelegt haben, wird ein Dialogfeld angezeigt. Geben Sie in **Öffentliche IP-Adresse** die öffentliche IPv4- bzw. IPv6-Adresse ein, die mithilfe der Netzwerkadressenübersetzung übersetzt werden soll, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p125">If you chose to use NAT, a dialog box appears. In **Public IP address**, type the public IPv4 and IPv6 (as appropriate) addresses to be translated by NAT, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-255">Dies muss die externe IP-Adresse des A/V-Edgeservers sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-255">This should be the external IP Address of the A/V Edge.</span></span>

    
    </div>

21. <span data-ttu-id="82c59-p126">Wählen Sie in **Nächsten Hop definieren** in der Liste **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Oder, wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p126">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

22. <span data-ttu-id="82c59-259">Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c59-259">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-p127">Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.</span><span class="sxs-lookup"><span data-stu-id="82c59-p127">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

23. <span data-ttu-id="82c59-263">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="82c59-263">Click **Finish**.</span></span>

24. <span data-ttu-id="82c59-264">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="82c59-264">Publish your topology.</span></span>

</div>

<div>

## <a name="to-define-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a><span data-ttu-id="82c59-265">So definieren Sie die Topologie für einen Edgeserverpool mit Hardwaregerät zum Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="82c59-265">To define the topology for a hardware load balanced Edge Server pool</span></span>

1.  <span data-ttu-id="82c59-266">Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.</span><span class="sxs-lookup"><span data-stu-id="82c59-266">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="82c59-267">Erweitern Sie in der Konsolenstruktur den Standort, an dem Edgeserver bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="82c59-267">In the console tree, expand the site in which you want to deploy Edge Servers.</span></span>

3.  <span data-ttu-id="82c59-268">Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und wählen Sie dann **neuer Edge-Pool**aus.</span><span class="sxs-lookup"><span data-stu-id="82c59-268">Right-click **Edge Pools**, and then select **New Edge Pool**.</span></span>

4.  <span data-ttu-id="82c59-269">Klicken Sie in **Neuen Edgepool definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-269">In **Define the New Edge Pool**, click **Next**.</span></span>

5.  <span data-ttu-id="82c59-270">Führen Sie in **FQDN für Edgepool definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-270">In **Define the Edge pool FQDN**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-271">Geben Sie in **FQDN** den vollqualifizierten Domänennamen ein, den Sie für die interne Seite des Edgepools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="82c59-271">In **FQDN**, type the fully qualified domain name (FQDN) you have chosen for the internal side of the Edge pool.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="82c59-272">Der Name, den Sie für den Pool angeben, muss der interne Name des Edgepools sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-272">The name you specify for the pool must be the internal edge pool name.</span></span> <span data-ttu-id="82c59-273">Dieser muss als vollqualifizierter Domänenname (FQDN) definert sein.</span><span class="sxs-lookup"><span data-stu-id="82c59-273">This must be defined as a FQDN.</span></span> <span data-ttu-id="82c59-274">Der Topologie-Generator verwendet keine Kurznamen, sondern FQDNs.</span><span class="sxs-lookup"><span data-stu-id="82c59-274">Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="82c59-275">Verwenden Sie nur Standardzeichen (also A–Z, a–z, 0–9 und Bindestriche) beim Zuweisen von FQDNs der Lync-Server, Edgeserver und Pools.</span><span class="sxs-lookup"><span data-stu-id="82c59-275">Use only standard characters (including A–Z, a–z, 0–9, and hyphens) when assigning FQDNs of your Lync Servers, Edge Servers, and pools.</span></span> <span data-ttu-id="82c59-276">Verwenden Sie keine Unicode-Zeichen oder Unterstriche.</span><span class="sxs-lookup"><span data-stu-id="82c59-276">Do not use Unicode characters or underscores.</span></span> <span data-ttu-id="82c59-277">Andere als die genannten Zeichen in einem FQDN werden von externen DNS und öffentlichen Zertifizierungsstellen (wenn der FQDN dem SN im Zertifikat zugewiesen werden muss) häufig nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="82c59-277">Nonstandard characters in an FQDN are often not supported by external DNS and public CAs (when the FQDN must be assigned to the SN in the certificate).</span></span>

        
        </div>
    
    <!-- end list -->
    
      - <span data-ttu-id="82c59-278">Klicken Sie auf **Pool mit mehreren Computern**und dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-278">Click **Multiple computer pool**, and then **Next**.</span></span>

6.  <span data-ttu-id="82c59-279">Führen Sie unter **Funktionen auswählen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-279">In **Select features** do the following:</span></span>
    
      - <span data-ttu-id="82c59-280">Wenn Sie einen einzelnen FQDN und eine einzige IP-Adresse für den SIP-Zugriffsdienst verwenden möchten, aktivieren Sie lync Server Webkonferenzdienst und A/V-Edgedienst das Kontrollkästchen **einen einzelnen FQDN & IP-Adresse verwenden** .</span><span class="sxs-lookup"><span data-stu-id="82c59-280">If you plan to use a single FQDN and IP address for the SIP access service, Lync Server Web Conferencing service, and A/V Edge service, select the **Use a single FQDN & IP Address** check box.</span></span>
    
      - <span data-ttu-id="82c59-281">Wenn der Partnerverbund aktiviert werden soll, aktivieren Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)**.</span><span class="sxs-lookup"><span data-stu-id="82c59-281">If you plan to enable federation, select the **Enable federation for this Edge pool (Port 5061)** check box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-p129">Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzern öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.</span><span class="sxs-lookup"><span data-stu-id="82c59-p129">You can select this option, but only one Edge pool or Edge Server in your organization may be published externally for federation. All access by federated users, including public instant messaging (IM) users, go through the same Edge pool or single Edge Server. For instance, if your deployment includes an Edge pool or single Edge Server deployed in New York and one deployed in London and you enable federation support on the New York Edge pool or single Edge Server, signal traffic for federated users will go through the New York Edge pool or single Edge Server. This is true even for communications with London users, although a London internal user calling a London federated user uses the London pool or Edge Server for A/V traffic.</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-286">Wenn Sie XMPP (Extensible Messaging and Presence Protocol) für Ihre Bereitstellung nutzen möchten, aktivieren Sie das Kontrollkästchen **XMPP-Partnerverbund aktivieren (Port 5269)**.</span><span class="sxs-lookup"><span data-stu-id="82c59-286">If you plan to support the extensible messaging and presence protocol (XMPP) for your deployment, select the **Enable XMPP federation (port 5269)** check box</span></span>

7.  <span data-ttu-id="82c59-287">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-287">Click **Next**.</span></span>

8.  <span data-ttu-id="82c59-288">Führen Sie unter **IP-Optionen auswählen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-288">In **Select IP Options**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-289">**IPv4 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-289">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="82c59-290">**IPv6 für interne Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool interne Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-290">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
      - <span data-ttu-id="82c59-291">**IPv4 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv4-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-291">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
      - <span data-ttu-id="82c59-292">**IPv6 für externe Schnittstelle aktivieren**: Aktivieren Sie das Kontrollkästchen, wenn Sie eine IPv6-Adresse auf die Edgeserver oder Edgepool externe Schnittstelle anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="82c59-292">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="82c59-p130">Aktivieren Sie <STRONG>nicht</STRONG> das Kontrollkästchen <STRONG>Die externe IP-Adresse des Edgepools wird von der Netzwerkadressenübersetzung übersetzt</STRONG>. Die Netzwerkadressenübersetzung wird bei Verwendung eines Hardwaregeräts zum Lastenausgleich nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="82c59-p130"><STRONG>Do Not</STRONG> select the <STRONG>The external IP address of the Edge pool is translated by NAT</STRONG> check box. Network address translation (NAT) is not supported when you are using hardware load balancing.</span></span>

    
    </div>

9.  <span data-ttu-id="82c59-295">Führen Sie in **Externe FQDNs** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-295">In **External FQDNs**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-296">Wenn Sie in **Funktionen auswählen** festlegen, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** den externen FQDN ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-296">If in **Select features** you chose to use a single FQDN and IP address for the SIP access, Web Conferencing service, and A/V Edge service, type the external FQDN in **SIP Access**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-p131">Wenn Sie diese Option aktivieren, müssen Sie für jeden Edgedienst eine andere Portnummer angeben (die empfohlenen Porteinstellungen lauten: 5061 für den Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den A/V-Edgedienst). Durch Auswahl dieser Option können Sie potenzielle Konnektivitätsprobleme verhindern und die Konfiguration vereinfachen, indem Sie dieselbe Portnummer (z. B. 443) für alle drei Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c59-p131">If you choose to select this option, you must specify a different port number for each of the Edge services (recommended port settings: 5061 for Access Edge service, 444 for Web Conferencing Edge service, and 443 for A/V Edge service). By selecting this option, you can help prevent potential connectivity issues and simplify the configuration because you can then use the same port number (for example, 443) for all three services.</span></span>

        
        </div>
    
      - <span data-ttu-id="82c59-p132">Wenn Sie unter **Funktionen auswählen** nicht festgelegt haben, dass nur ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie den FQDN für die öffentliche Seite des Edgepools in **SIP-Zugriff** ein. Geben Sie in **Webkonferenzen** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **Audio/Video** den FQDN ein, den Sie für die öffentliche Seite des Edgepools ausgewählt haben. Verwenden Sie die Standardports.</span><span class="sxs-lookup"><span data-stu-id="82c59-p132">If in **Select features** you did not chose to use a single FQDN and IP address, type the FQDN that you have chosen for your public facing side of the edge pool for in **SIP Access**. In **Web Conferencing**, type the FQDN you have chosen for your public facing side of the Edge pool. In **Audio/Video**, type the FQDN you have chosen for your public facing side of the Edge pool. Use the default ports.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="82c59-303">Dabei handelt es sich um die FQDNs der virtuellen IP-Adressen (VIP) für die öffentliche Seite des Pools.</span><span class="sxs-lookup"><span data-stu-id="82c59-303">These will be the publicly facing virtual IP (VIP) FQDNs for the pool.</span></span>

        
        </div>

10. <span data-ttu-id="82c59-304">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-304">Click **Next**.</span></span>

11. <span data-ttu-id="82c59-305">Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="82c59-305">In **Define the computers in this pool**, click **Add**.</span></span>

12. <span data-ttu-id="82c59-306">Führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-306">In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-307">Wenn Sie festgelegt haben, dass für den **SIP-Zugriff**, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv4-Adresse des Edgeservers ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-307">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv4 address of the Edge Server in **SIP Access**.external IP address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="82c59-p133">Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IP-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IP-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="82c59-p133">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IP address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IP address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IP address you have chosen for your public facing side of this Edge pool server.</span></span>

13. <span data-ttu-id="82c59-311">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-311">Click **Next**.</span></span>

14. <span data-ttu-id="82c59-312">Wenn Sie IPv6-Adressen aktivieren möchten, führen Sie in **Externe IP-Adressen definieren** die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="82c59-312">If you chose to enable IPv6 addresses, In **Define the external IP addresses**, do the following:</span></span>
    
      - <span data-ttu-id="82c59-313">Wenn Sie festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Edgedienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie in **SIP-Zugriff** die externe IPv6-Adresse des Edgeservers ein.</span><span class="sxs-lookup"><span data-stu-id="82c59-313">If you chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Edge service, type the external IPv6 address of the Edge Server in **SIP Access**.</span></span>
    
      - <span data-ttu-id="82c59-p134">Wenn Sie nicht festgelegt haben, dass für den SIP-Zugriff, den Webkonferenzdienst und den A/V-Konferenzdienst ein einziger FQDN und eine einzige IP-Adresse verwendet werden sollen, geben Sie für **SIP-Zugriff** die IPv6-Adresse ein, die Sie für die öffentliche Seite dieses Edgepoolservers ausgewählt haben. Geben Sie in **Webkonferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben. Geben Sie in **A/V-Konferenzen** die IPv6-Adresse ein, die Sie für die öffentliche Seite des Edgepools ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="82c59-p134">If you did not chose to use a single FQDN and IP Address for the SIP access, Web Conferencing service, and A/V Conferencing service, type the IPv6 address that you have chosen for your public facing side of this Edge pool server for **SIP Access**. In **Web Conferencing**, type the IPv6 address that you have chosen for your public facing side of this Edge pool server. In **A/V Conferencing**, type the IPv6 address you have chosen for your public facing side of this Edge pool server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-317">Wenn Sie nicht ausgewählt haben, dass Sie IPv6-Adressen aktivieren und zuweisen möchten, wird dieses Dialogfeld nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c59-317">If you did not choose to enable and assign IPv6 addressing, you will not see this dialog box.</span></span>

    
    </div>

15. <span data-ttu-id="82c59-318">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="82c59-318">Click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-319">Der erste Edgeserver, den Sie in Ihrem Pool erstellt haben, wird nun im Dialogfeld <STRONG>Computer in diesem Pool definieren</STRONG> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c59-319">You will now see the first Edge Server you created in your pool in the <STRONG>Define the computers in this pool</STRONG> dialog box.</span></span>

    
    </div>

16. <span data-ttu-id="82c59-320">Klicken Sie in **Computer in diesem Pool definieren** auf **Hinzufügen**, und wiederholen Sie die Schritte 11 bis 14 für den zweiten Edgeserver, der dem Edgepool hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="82c59-320">In **Define the computers in this pool**, click **Add**, and then repeat steps 11 through 14 for the second Edge Server that you want to add to your Edge pool.</span></span>

17. <span data-ttu-id="82c59-321">Nachdem Sie die Schritte 11 bis 14 wiederholt haben, klicken Sie in **Computer in diesem Pool definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-321">After you repeat steps 11 through 14, click **Next** in **Define the computers in this pool**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-322">Die beiden Edgeserver werden nun in Ihrem Pool angezeigt.</span><span class="sxs-lookup"><span data-stu-id="82c59-322">At this point, you can see both of the Edge Servers in your pool.</span></span>

    
    </div>

18. <span data-ttu-id="82c59-p135">Wählen Sie in **Nächsten Hop definieren** in der Liste **Nächster Hoppool** den Namen des internen Pools aus, bei dem es sich entweder um einen Front-End-Pool oder um einen Standard Edition-Pool handeln kann. Oder, wenn Ihre Bereitstellung einen Director umfasst, wählen Sie den Namen des Directors. Klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="82c59-p135">In **Define the next hop**, in the **Next hop pool** list, select the name of the internal pool, which can be either a Front End pool or a Standard Edition pool. Or, if your deployment includes a Director, select the name of the Director. Then, click **Next**.</span></span>

19. <span data-ttu-id="82c59-326">Geben Sie in **Front-End-Pools zuordnen** einen oder mehrere interne Pools an (diese können Front-End-Pools und Standard Edition-Server umfassen), die diesem Edgeserver zugeordnet werden sollen. Wählen Sie dazu die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden.</span><span class="sxs-lookup"><span data-stu-id="82c59-326">In **Associate Front End pools**, specify one or more internal pools, which can include Front End pools and Standard Edition servers, to be associated with this Edge Server, by selecting the names of the internal pool(s) that is to use this Edge Server for communication with supported external users.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="82c59-p136">Jedem internen Pool kann für A/V-Datenverkehr nur ein Edgepool mit Lastenausgleich oder einzelner Edgeserver zugeordnet werden. Wenn einem internen Pool bereits ein Edgepool oder Edgeserver zugeordnet ist, werden Sie in einer Warnmeldung darüber informiert. Bei Auswahl eines Pools, der bereits einem anderen Edgeserver zugeordnet ist, wird die Zuordnung geändert.</span><span class="sxs-lookup"><span data-stu-id="82c59-p136">Only one load-balanced Edge pool or single Edge Server can be associated with each internal pool for A/V traffic. If you already have an internal pool associated with an Edge pool or Edge Server, a warning appears indicating that the internal pool is already associated an Edge pool or Edge Server. If you select a pool that is already associated with another Edge Server, it will change the association.</span></span>

    
    </div>

20. <span data-ttu-id="82c59-330">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="82c59-330">Click **Finish**.</span></span>

21. <span data-ttu-id="82c59-331">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="82c59-331">Publish your topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

