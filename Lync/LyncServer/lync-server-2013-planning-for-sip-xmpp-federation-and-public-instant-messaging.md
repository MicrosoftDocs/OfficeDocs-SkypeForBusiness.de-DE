---
title: Planen von SIP, XMPP Federation und Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="8acc4-102">Planen von SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-102">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8acc4-103">_**Letztes Änderungsdatum des Themas:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="8acc4-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="8acc4-104">Edgeserver können so konfiguriert werden, dass Sie Ihren internen und externen Benutzern den Zugriff auf Kontakte in Partnerorganisationen oder-Diensten gestatten.</span><span class="sxs-lookup"><span data-stu-id="8acc4-104">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="8acc4-105">Föderationen können, wie diese Partnervereinbarungen bekannt sind, den Kontakten in Ihrer Organisation im Partnerverbund oder Kontakten in der Partner Föderation eine oder alle folgenden Informationen zur Verfügung stellen:</span><span class="sxs-lookup"><span data-stu-id="8acc4-105">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="8acc4-106">Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="8acc4-106">Instant messaging and presence</span></span>

  - <span data-ttu-id="8acc4-107">Zusammenarbeit und Konferenz, beispielsweise Web-Conferencing</span><span class="sxs-lookup"><span data-stu-id="8acc4-107">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="8acc4-108">Audiokonferenzen, Videokonferenzen oder beides</span><span class="sxs-lookup"><span data-stu-id="8acc4-108">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="8acc4-109">In einigen Fällen ist die Kommunikation, beispielsweise Instant Messaging (im) und Anwesenheitsinformationen zwischen einem Microsoft lync Server 2013 und einem Kontakt mit einem erweiterbaren Messaging-und Anwesenheits Protokoll (XMPP), nur Peer-to-Peer-Unterstützung nur von Ihnen und dem Kontakt im Verbund Partner.</span><span class="sxs-lookup"><span data-stu-id="8acc4-109">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="8acc4-110">In anderen Fällen, wie lync Server, lync Server 2010, lync Server 2013 Federation können mehrere Teilnehmer eingeladen werden, an der Unterhaltung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-110">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="8acc4-111">Lync Server und Office Communications Server-Föderation</span><span class="sxs-lookup"><span data-stu-id="8acc4-111">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="8acc4-112">Der Verbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server unterstützt Peer-to-Peer-und Mehrparteienkommunikation.</span><span class="sxs-lookup"><span data-stu-id="8acc4-112">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="8acc4-113">Peer-to-Peer-Unterhaltungen können an mehr Parteien Unterhaltungen eskaliert werden, was zu Ad-hoc-Besprechungen führt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-113">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="8acc4-114">Besprechungen – Webkonferenzen oder Audio/visuelle Konferenzen – können so geplant werden, dass Sie Kontakte innerhalb Ihrer Organisation sowie Kontakte in Partner einbeziehen, mit denen Sie eine Föderation aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-114">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="8acc4-115">Federation erschien zunächst in Microsoft Office Live Communications Server 2005 und unterstützte eine Art von Föderation, direkte Föderation.</span><span class="sxs-lookup"><span data-stu-id="8acc4-115">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="8acc4-116">Für den direkten Verbund mussten Sie die SIP-Domäne (Session Initiation Protocol) des Partner Verbandes und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edge-Servers des Partners kennen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-116">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="8acc4-117">Mit Live Communications Server 2005 mit SP1 wurden zusätzliche Föderations Typen eingeführt, die alle DNS-SRV-Einträge (Domain Name System) benötigten, die von dem Partnerverbund zum Auffinden des Edgeserver veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="8acc4-117">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="8acc4-118">Die Terminologie für diese Version lautete:</span><span class="sxs-lookup"><span data-stu-id="8acc4-118">The terminology for that release was:</span></span>

  - <span data-ttu-id="8acc4-119">*Erweiterte Föderation öffnen*: akzeptieren Sie einen beliebigen SIP-Domänennamen, und verwenden Sie DNS SRV zum Auffinden des Partner-Edge-Servers.</span><span class="sxs-lookup"><span data-stu-id="8acc4-119">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="8acc4-120">*Erweiterte Föderation*: Konfigurieren Sie den SIP-Domänennamen des Partners als Verbundpartner für Ihre Organisation, und verwenden Sie DNS SRV zum Auffinden des Partner-Edge-Servers.</span><span class="sxs-lookup"><span data-stu-id="8acc4-120">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="8acc4-121">*Direkter Verbund*: Konfigurieren Sie den SIP-Domänennamen und den FQDN des Partners auf dem Edgeserver des Partners.</span><span class="sxs-lookup"><span data-stu-id="8acc4-121">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="8acc4-122">*Server Zulassungsliste*: akzeptieren einer beliebigen Domäne, verwenden von DNS SRV zum Auffinden des Edgeserver eines Hostinganbieter oder eines öffentlichen Instant Messaging (im)-Verbindungs Anbieters</span><span class="sxs-lookup"><span data-stu-id="8acc4-122">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="8acc4-123">Microsoft Office Communications Server 2007 hat aktualisierte Namen für Verbundtypen eingeführt, um besser zu definieren, was die einzelnen Föderations Typen tatsächlich erreicht haben:</span><span class="sxs-lookup"><span data-stu-id="8acc4-123">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="8acc4-124">Open Enhanced Federation wurde als *erkannte Partner Domäne* bekannt</span><span class="sxs-lookup"><span data-stu-id="8acc4-124">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="8acc4-125">Erweiterte Föderation wurde als *zugelassene Partner Domäne* bekannt</span><span class="sxs-lookup"><span data-stu-id="8acc4-125">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="8acc4-126">Der direkte Verbund wurde als *zugelassener Partner Server* bekannt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-126">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="8acc4-127">Server Zulassungsliste wurde als *Hostinganbieter* und *Öffentlicher Chat Anbieter* bekannt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-127">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="8acc4-128">Microsoft lync Server 2010 hat eine schmalere Definition des Hostinganbieter-Anbieters in Übereinstimmung mit Microsoft lync Online 2010 und Microsoft Office 365 eingeführt und außerdem der gleichen zulässigen Liste unterzogen, die durch den Föderations zugelassene Partner Domäne definiert ist.</span><span class="sxs-lookup"><span data-stu-id="8acc4-128">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="8acc4-129">Wenn Sie den Verbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server aktivieren, werden die Edgeserver und Reverse Proxys verwendet, um die von Ihnen definierten Regeln und zulässigen Partnerdomänen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-129">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="8acc4-130">Aus Planungssicht erfordert die Zusammenarbeit mit anderen lync-Servern in Office Communications Server Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8acc4-130">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="8acc4-131">Aktivieren der Föderation im Topologie-Generator</span><span class="sxs-lookup"><span data-stu-id="8acc4-131">Enable federation in Topology Builder.</span></span> <span data-ttu-id="8acc4-132">Ausführliche Informationen finden Sie im Bereitstellungs Thema [Konfigurieren von SIP Federation, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="8acc4-132">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="8acc4-133">Ermitteln Sie Ihre Anforderungen für die Föderationsdomänen Ermittlung:</span><span class="sxs-lookup"><span data-stu-id="8acc4-133">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="8acc4-134">Für die manuelle Konfiguration von Federation müssen Sie über den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edge-Servers des Partners und des Domänennamens oder des Online Domänennamens verfügen, der in der lync Server-Systemsteuerung, in der **Föderation und im externen Zugriff**, SIP eingegeben wird. \*\* Föderationsdomänen\*\*.</span><span class="sxs-lookup"><span data-stu-id="8acc4-134">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="8acc4-135">Erstellen Sie eine **neue** Richtlinie, oder **Bearbeiten** Sie eine vorhandene Richtlinie, damit Domänen nach FQDN zugelassen oder blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="8acc4-135">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="8acc4-136">Die manuelle Konfiguration des Edge-Servers eines Verbundpartners ist für den Fall anfällig, dass der Partner die IP-Adresse seines Edge-Servers ändert.</span><span class="sxs-lookup"><span data-stu-id="8acc4-136">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="8acc4-137">Für <STRONG>neue SIP-Verbunddomänen</STRONG>müssen Sie den <STRONG>Domänennamen (oder den FQDN)</STRONG> für Microsoft lync Online, Microsoft Office 365, angeben.</span><span class="sxs-lookup"><span data-stu-id="8acc4-137">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online, Microsoft Office 365.</span></span> <span data-ttu-id="8acc4-138">Für Microsoft lync Server 2013, lync Server 2010 und Office Communications Server müssen Sie auch einen <STRONG>Access Edge Service (FQDN)</STRONG> bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-138">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="8acc4-139">Für entdeckten Partnerverbund, in dem Partner ihren Edgeserver entdecken können, erstellen Sie einen SRV-Eintrag in Ihrem \_externen DNS-sipfederationtls. \_TCP.contoso.com – verweist auf den Port 5061 und den Host (A)-Eintrag Ihres Edge-Servers</span><span class="sxs-lookup"><span data-stu-id="8acc4-139">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="8acc4-140">Wenn Sie Microsoft lync Mobile-Clients auf Windows Phone oder Apple iPhone, iPad oder anderen Apple-Geräten unterstützen und den Push-Benachrichtigungsdienst oder den Push-Benachrichtigungsdienst verwenden, müssen Sie _sipfederationtls. _tcp planen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-140">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="8acc4-141">&lt;SIP-&gt; Domänen-SRV-Einträge für jede SIP-Domäne, auf der Sie lync Mobile-Clients haben.</span><span class="sxs-lookup"><span data-stu-id="8acc4-141">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="8acc4-142">Android und Nokia Symbian lync Mobile verwenden keine Push-Benachrichtigung und unterliegen nicht dieser Anforderung.</span><span class="sxs-lookup"><span data-stu-id="8acc4-142">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="8acc4-143">Konfigurieren von Richtlinien für den externen Benutzer Zugriff zur Unterstützung von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="8acc4-143">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="8acc4-144">Öffnen Sie die Firewall-Ports für SIP (Session Initiation Protocol), Webkonferenzen und Audio/visuell, um die von Ihnen aktivierte Föderation oder Kontakte aufnehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="8acc4-144">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="8acc4-145">Ausführliche Informationen finden Sie unter: [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="8acc4-145">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="8acc4-146">Die folgenden Informationen unterstützen Sie bei der Definition der Zertifikat-, Port/Protokoll-und DNS-Anforderungen für den Verbund mit Microsoft lync Server 2013 und lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8acc4-146">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="8acc4-147">Die Planung für Zertifikate, Firewall-und Port/Protocol-Anforderungen und DNS-Anforderungen ist in der Regel ein geradliniger Prozess, wenn Sie Ihre Microsoft lync Server 2013-Edgeserver geplant oder bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="8acc4-147">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="8acc4-148">Da es sich bei der Föderation um ein zusätzliches Feature handelt, das den vorhandenen Edgeserver verwendet, werden die Planungsanforderungen in der Regel von der Planung und Bereitstellung des Edge-Servers erfüllt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-148">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="8acc4-149">Verwenden Sie die folgenden Tabellen, um festzustellen, ob Ihre Anforderungen erfüllt sind, und nehmen Sie dementsprechend Änderungen an Port/Protokoll und DNS vor.</span><span class="sxs-lookup"><span data-stu-id="8acc4-149">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8acc4-150">Wenn Sie über einen Pool von Edge-Servern verfügen und mit lync Server 2013-oder lync Server 2010-Partnern zusammenarbeiten, können Sie entweder den DNS-Lastenausgleich oder Hardwarelastenausgleichs auf der internen und externen Seite der Edgeserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="8acc4-150">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="8acc4-151">Wenn Sie mit Office Communications Server 2007 oder Office Communications Server 2007 R2 eine Föderation durchführen, bietet der Hardwarelastenausgleich eine Failover-Unterstützung für den Fall eines Edgeserver.</span><span class="sxs-lookup"><span data-stu-id="8acc4-151">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="8acc4-152">Office Communications Server 2007 und Office Communications Server 2007 R2 sind nicht für den DNS-Lastenausgleich bekannt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-152">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="8acc4-153">Die Partner-Edgeserver richten die Kommunikation mit dem ersten Edgeserver in Ihrem Pool ein, der antwortet.</span><span class="sxs-lookup"><span data-stu-id="8acc4-153">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="8acc4-154">Wenn dieser Edge-Server ausfällt, wird die Kommunikation nicht automatisch Failover.</span><span class="sxs-lookup"><span data-stu-id="8acc4-154">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="8acc4-155">Die Zertifikatanforderungen werden in der Regel durch die Planung von Zertifikaten für den ausgewählten Edgeserver oder den Pooled Edge Server-Plan erfüllt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-155">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="8acc4-156">Öffentliche Instant Messaging-Konnektivität</span><span class="sxs-lookup"><span data-stu-id="8acc4-156">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="8acc4-157">Die öffentliche Instant Messaging-Konnektivität ist eine Klasse des Föderations-und ist so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden hinzufügen können:</span><span class="sxs-lookup"><span data-stu-id="8acc4-157">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="8acc4-158">Messenger-Kontakte</span><span class="sxs-lookup"><span data-stu-id="8acc4-158">Messenger contacts</span></span>

  - <span data-ttu-id="8acc4-159">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="8acc4-159">Yahoo\!</span></span> <span data-ttu-id="8acc4-160">Kontakte</span><span class="sxs-lookup"><span data-stu-id="8acc4-160">contacts</span></span>

  - <span data-ttu-id="8acc4-161">America Online (AOL)-Kontakte</span><span class="sxs-lookup"><span data-stu-id="8acc4-161">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="8acc4-162">Ab dem 1. September, 2012, ist die Microsoft lync Public Chat-Benutzerabonnementlizenz (PIC USL) nicht mehr für den Kauf für neue oder erneuernde Vereinbarungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8acc4-162">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="8acc4-163">Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden</span><span class="sxs-lookup"><span data-stu-id="8acc4-163">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8acc4-164">Messenger bis zum Shutdown-Datum des Diensts (das genaue Datum wird noch entschieden, aber frühestens Juni 2013).</span><span class="sxs-lookup"><span data-stu-id="8acc4-164">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="8acc4-165">Bei der PIC-USL handelt es sich um eine pro Benutzer/Monat-Abonnementlizenz, die für lync Server oder Office Communications Server für die Föderation mit Yahoo! erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8acc4-165">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8acc4-166">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8acc4-166">Messenger.</span></span> <span data-ttu-id="8acc4-167">Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung nicht verlängert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8acc4-167">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="8acc4-168">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-168">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8acc4-169">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8acc4-169">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8acc4-170">Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen über Chat und Sprache zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-170">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="8acc4-171">Für diese Föderations Klasse sind die folgenden Planungsüberlegungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="8acc4-171">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="8acc4-172">Benutzer von Windows Live Messenger können neben Instant Messaging auch eine Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern führen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-172">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="8acc4-173">Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-173">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="8acc4-174">Ausführliche Informationen finden Sie unter [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8acc4-174">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="8acc4-175">Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die normalerweise bei der Planung und Bereitstellung des typischen Edgeserver verwendet werden, der Föderation bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-175">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="8acc4-176">Für America Online ist es erforderlich, dass Ihr Edge-Server-Zertifikat, das dem Access-Edgedienst zugewiesen ist, über eine erweiterte Client-Schlüsselverwendung verfügt.</span><span class="sxs-lookup"><span data-stu-id="8acc4-176">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="8acc4-177">Extensible Messaging and Presence Protocol (XMPP)-Föderation</span><span class="sxs-lookup"><span data-stu-id="8acc4-177">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="8acc4-178">In früheren Versionen von lync Server und Office Communications Server wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Server Rolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-178">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="8acc4-179">In Microsoft lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8acc4-179">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="8acc4-180">Die XMPP-Funktionalität ist in zwei Teilen installiert: ein XMPP-Proxy, der auf dem Edgeserver ausgeführt wird, und das XMPP-Gateway, das auf den Front-End-Servern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8acc4-180">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="8acc4-181">Die Bereitstellung und Konfiguration von XMPP wird unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) , die Sie zur Unterstützung von xmpp in Ihrer Organisation planen, durch Definieren von Port-und Protokollregeln für Ihre Firewall, Konfiguration von Zertifikaten und Hinzufügen von DNS abgedeckt. Einträge.</span><span class="sxs-lookup"><span data-stu-id="8acc4-181">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="8acc4-182">In den folgenden Themen in diesem Abschnitt werden die Informationen zusammengefasst, die Sie benötigen, um die XMPP-Föderation für Ihre Bereitstellung erfolgreich zu planen.</span><span class="sxs-lookup"><span data-stu-id="8acc4-182">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8acc4-p120">Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8acc4-p120">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8acc4-185">Die XMPP-Föderation wird für Benutzer nicht unterstützt, die sich auf Überlebenden Branch-Appliances befinden.</span><span class="sxs-lookup"><span data-stu-id="8acc4-185">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="8acc4-186">Dies gilt sowohl für das Anzeigen von Anwesenheitsinformationen als auch für den Austausch von Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="8acc4-186">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="8acc4-187">In den folgenden Themen finden Sie Anleitungen zum Definieren von Zertifikaten, Firewall-Ports und DNS-Einträgen für die Typen unterstützter Verbundszenarien.</span><span class="sxs-lookup"><span data-stu-id="8acc4-187">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="8acc4-188">Zusammenfassung des Zertifikats – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-188">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="8acc4-189">Port Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-189">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="8acc4-190">DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-190">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8acc4-191">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8acc4-191">See Also</span></span>


[<span data-ttu-id="8acc4-192">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-192">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="8acc4-193">Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-193">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="8acc4-194">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-194">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="8acc4-195">Ermitteln von DNS-Anforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-195">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="8acc4-196">Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-196">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="8acc4-197">Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-197">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="8acc4-198">Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acc4-198">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

