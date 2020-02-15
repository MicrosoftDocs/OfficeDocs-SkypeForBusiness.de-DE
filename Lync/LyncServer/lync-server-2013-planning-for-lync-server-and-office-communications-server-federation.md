---
title: Planung für lync Server und Office Communications Server Partnerverbund
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22c94254921e3aa1cde8d93998f8fe5bf122ac92
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a><span data-ttu-id="df446-102">Planung für lync Server 2013 und Office Communications Server Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="df446-102">Planning for Lync Server 2013 and Office Communications Server federation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df446-103">_**Letztes Änderungsstand des Themas:** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="df446-103">_**Topic Last Modified:** 2013-02-13_</span></span>

<span data-ttu-id="df446-104">Partnerverbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server unterstützt Peer-to-Peer-und Mehrparteienkommunikation.</span><span class="sxs-lookup"><span data-stu-id="df446-104">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="df446-105">Peer-zu-Peer-Unterhaltungen können an mehr Parteien Unterhaltungen weitergeleitet werden, sodass Ad-hoc-Besprechungen möglich sind.</span><span class="sxs-lookup"><span data-stu-id="df446-105">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="df446-106">Besprechungen – Webkonferenzen oder Audio/visuelle Konferenzen – können so geplant werden, dass Sie Kontakte in Ihrer Organisation sowie Kontakte in Partnergruppen einbeziehen, mit denen Sie verbündet sind.</span><span class="sxs-lookup"><span data-stu-id="df446-106">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="df446-107">Der Verbund erschien zunächst in Microsoft Office Live Communications Server 2005 und unterstützte eine Art von Verbund, direktem Verbund.</span><span class="sxs-lookup"><span data-stu-id="df446-107">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="df446-108">Für den direkten Verbund mussten Sie die SIP-Domäne (Session Initiation Protocol) des Partnerverbund Partners und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeserver des Partners kennen.</span><span class="sxs-lookup"><span data-stu-id="df446-108">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="df446-109">Live Communications Server 2005 mit SP1 wurden zusätzliche Verbundtypen eingeführt, für die alle DNS-SRV-Einträge (Domain Name System) vom Partnerverbund veröffentlicht werden mussten, um Ihre Edgeserver zu finden.</span><span class="sxs-lookup"><span data-stu-id="df446-109">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="df446-110">Die Terminologie für diese Version lautete:</span><span class="sxs-lookup"><span data-stu-id="df446-110">The terminology for that release was:</span></span>

  - <span data-ttu-id="df446-111">*Open Enhanced Federation*: akzeptieren Sie einen beliebigen SIP-Domänennamen, und verwenden Sie DNS-SRV zum Auffinden der Partner Edgeserver</span><span class="sxs-lookup"><span data-stu-id="df446-111">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="df446-112">*Erweiterter Verbund*: Konfigurieren Sie den SIP-Domänennamen des Partners als Verbundpartner für Ihre Organisation, und verwenden Sie DNS-SRV, um den Partner zu finden Edgeserver</span><span class="sxs-lookup"><span data-stu-id="df446-112">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="df446-113">*Direkter Verbund*: Konfigurieren Sie den SIP-Domänennamen des Partners und den FQDN für den Edgeserver des Partners.</span><span class="sxs-lookup"><span data-stu-id="df446-113">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="df446-114">*Server Zulassungsliste*: akzeptieren einer beliebigen Domäne, verwenden von DNS-SRV zum Auffinden der Edgeserver eines Hostinganbieter oder eines Anbieters für öffentliche Chatnachrichten (Instant Messaging)</span><span class="sxs-lookup"><span data-stu-id="df446-114">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="df446-115">Microsoft Office Communications Server 2007 wurde die aktualisierte Benennung von Verbundtypen eingeführt, um besser zu definieren, was die einzelnen Verbundtypen tatsächlich erreicht haben:</span><span class="sxs-lookup"><span data-stu-id="df446-115">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="df446-116">Open Enhanced Federation wurde als *entdeckte Partner Domäne* bezeichnet</span><span class="sxs-lookup"><span data-stu-id="df446-116">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="df446-117">Erweiterter Verbund wurde als *zugelassene Partner Domäne* bezeichnet</span><span class="sxs-lookup"><span data-stu-id="df446-117">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="df446-118">Der direkte Verbund wurde als *zulässiger Partner Server* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="df446-118">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="df446-119">Server Zulassungsliste wurde als *Hostinganbieter* und *Öffentlicher Chat Anbieter* bezeichnet</span><span class="sxs-lookup"><span data-stu-id="df446-119">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="df446-120">Microsoft lync Server 2010 eine engere Definition des Hostinganbieter in Übereinstimmung mit Microsoft lync Online 2010 und Microsoft Office 365 eingeführt und unterliegt außerdem der gleichen zulässigen Liste, die vom Partner Domänen-Verbundtyp zulässig definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="df446-120">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="df446-121">Das Aktivieren des Verbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server verwendet die Edgeserver und Reverse Proxies, um die von Ihnen definierten Regeln und zulässigen Partnerdomänen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="df446-121">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="df446-122">Aus Planungssicht und Verbund mit anderen lync Server erfordert Office Communications Server Folgendes:</span><span class="sxs-lookup"><span data-stu-id="df446-122">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="df446-123">Aktivieren Sie den Partnerverbund im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="df446-123">Enable federation in Topology Builder.</span></span> <span data-ttu-id="df446-124">Ausführliche Informationen finden Sie im Bereitstellungs Thema [Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und der öffentlichen Sofortnachrichten in lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="df446-124">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="df446-125">Bestimmen der Anforderungen für die Verbunddomänen Ermittlung:</span><span class="sxs-lookup"><span data-stu-id="df446-125">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="df446-126">Für die manuelle Konfiguration des Verbunds benötigen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeserver und Domänennamens des Partners oder den Online Domänennamen, der in den **SIP-Verbunddomänen**lync Server-Systemsteuerung, Partner **Verbund und externer Zugriff**eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="df446-126">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="df446-127">Erstellen Sie eine **neue** Richtlinie, oder **Bearbeiten** Sie eine vorhandene Richtlinie, um Domänen nach FQDN zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="df446-127">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="df446-128">Die manuelle Konfiguration des Edgeserver eines Partnerverbund Partners ist anfällig für den Fall, dass der Partner die IP-Adresse seiner Edgeserver ändert.</span><span class="sxs-lookup"><span data-stu-id="df446-128">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="df446-129">Für <STRONG>neue SIP-Verbunddomänen</STRONG>müssen Sie den <STRONG>Domänennamen (oder FQDN)</STRONG> für Microsoft lync Online Microsoft Office 365 angeben.</span><span class="sxs-lookup"><span data-stu-id="df446-129">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="df446-130">Für Microsoft lync Server 2013, lync Server 2010 und Office Communications Server müssen Sie auch eine <STRONG>Zugriffs-Edgedienst (FQDN)</STRONG> bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="df446-130">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="df446-131">Für entdeckte Partnerverbund, in dem Partner ihre Edgeserver ermitteln können, erstellen Sie einen SRV-Eintrag in Ihrem externen \_DNS-sipfederationtls. \_TCP.contoso.com – der auf den Port 5061 und den Host (A)-Eintrag Ihrer Edgeserver zeigt</span><span class="sxs-lookup"><span data-stu-id="df446-131">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="df446-132">Wenn Sie Microsoft lync Mobile-Clients auf Windows Phone oder Apple iPhone, iPad oder anderen Apple-Geräten unterstützen und den Push-Benachrichtigungsdienst oder den Push-Benachrichtigungsdienst verwenden, müssen Sie _sipfederationtls. _tcp planen.</span><span class="sxs-lookup"><span data-stu-id="df446-132">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="df446-133">&lt;SIP-&gt; Domänen-SRV-Einträge für jede SIP-Domäne, in der Sie lync Mobile-Clients haben.</span><span class="sxs-lookup"><span data-stu-id="df446-133">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="df446-134">Android und Nokia Symbian lync Mobile verwenden keine Push-Benachrichtigung und unterliegen nicht dieser Anforderung.</span><span class="sxs-lookup"><span data-stu-id="df446-134">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="df446-135">Konfigurieren von Richtlinien für den externen Benutzer Zugriff zur Unterstützung von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="df446-135">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="df446-136">Öffnen Sie Firewall-Ports für SIP (Session Initiation Protocol), Webkonferenzen und Audio/visuell, um die zu aktivierende Föderation oder Kontakte aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="df446-136">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="df446-137">Ausführliche Informationen finden Sie unter: [bestimmen der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="df446-137">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="df446-138">Die folgenden Informationen helfen Ihnen beim Definieren der Zertifikate, Port/Protokoll-und DNS-Anforderungen für den Verbund mit Microsoft lync Server 2013 und lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="df446-138">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="df446-139">Die Planung von Zertifikaten, Firewall-und Port/Protocol-Anforderungen und DNS-Anforderungen ist in der Regel ein geradliniger Prozess, wenn Sie die Microsoft lync Server 2013-Edgeserver geplant oder bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="df446-139">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="df446-140">Da es sich bei dem Verbund um ein zusätzliches Feature handelt, das die vorhandenen Edgeserver verwendet, werden die Planungsanforderungen im Allgemeinen von der Edgeserver Planung und Bereitstellung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="df446-140">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="df446-141">Verwenden Sie die folgenden Tabellen, um zu ermitteln, ob Ihre Anforderungen erfüllt sind, und ändern Sie entsprechend Port/Protocol und DNS.</span><span class="sxs-lookup"><span data-stu-id="df446-141">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="df446-142">Wenn Sie einen Pool mit Edgeserver haben und mit lync Server 2013 oder lync Server 2010 Partnern zusammenschließen, können Sie entweder den DNS-Lastenausgleich oder Hardwarelastenausgleichs auf den internen und externen Seiten der Edgeserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="df446-142">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="df446-143">Wenn Sie einen Verbund mit Office Communications Server 2007 oder Office Communications Server 2007 R2 durchführen, bietet der Hardwarelastenausgleich im Fall eines Edgeserver eine Failover-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="df446-143">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="df446-144">Office Communications Server 2007 und Office Communications Server 2007 R2 sind nicht mit dem DNS-Lastenausgleich vertraut.</span><span class="sxs-lookup"><span data-stu-id="df446-144">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="df446-145">Die Partner-Edgeserver stellen die Kommunikation mit dem ersten Edgeserver in Ihrem Pool her, der antwortet.</span><span class="sxs-lookup"><span data-stu-id="df446-145">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="df446-146">Wenn das Edgeserver fehlschlägt, wird bei der Kommunikation nicht automatisch ein Failover ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="df446-146">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="df446-147">Zertifikatanforderungen werden normalerweise durch die Planung von Zertifikaten für den ausgewählten Edgeserver oder den Pooled Edgeserver-Plan erfüllt.</span><span class="sxs-lookup"><span data-stu-id="df446-147">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="df446-148">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="df446-148">In This Section</span></span>

  - [<span data-ttu-id="df446-149">Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-149">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="df446-150">Port Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-150">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [<span data-ttu-id="df446-151">DNS-Zusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-151">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="df446-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df446-152">See Also</span></span>


[<span data-ttu-id="df446-153">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-153">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="df446-154">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="df446-155">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-155">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="df446-156">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-156">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="df446-157">Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-157">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="df446-158">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-158">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="df446-159">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df446-159">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

