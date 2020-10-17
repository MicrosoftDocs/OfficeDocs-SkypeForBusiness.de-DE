---
title: Planung für SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
description: Planung für SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c28c9c75310c884ea00117be2458384d408daae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564061"
---
# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="1b697-103">Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-103">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b697-104">_**Letztes Änderungsstand des Themas:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="1b697-104">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="1b697-105">Edgeserver können so konfiguriert werden, dass ihren internen und externen Benutzern der Zugriff auf Kontakte in Partnerorganisationen oder-Diensten ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="1b697-105">Edge Servers can be configured to allow your internal and external users access to contacts at partner organizations or services.</span></span> <span data-ttu-id="1b697-106">Diese Partnervereinbarung wird als Partnerverbund bezeichnet und stellt für Kontakte in Ihrer Organisation oder für Kontakte in der Partnerorganisation, die zum Partnerverbund gehören, beliebige oder alle der folgenden Funktionen bereit:</span><span class="sxs-lookup"><span data-stu-id="1b697-106">Federations, as these partner agreements are known, can provide any or all of the following to the contacts in your organization on the partner federation or contacts in the partner federation to yours:</span></span>

  - <span data-ttu-id="1b697-107">Chat und Anwesenheit</span><span class="sxs-lookup"><span data-stu-id="1b697-107">Instant messaging and presence</span></span>

  - <span data-ttu-id="1b697-108">Zusammenarbeit und Konferenzen, z. B. Webkonferenz</span><span class="sxs-lookup"><span data-stu-id="1b697-108">Collaboration and conferencing, for example – Web conferencing</span></span>

  - <span data-ttu-id="1b697-109">Audiokonferenz, Videokonferenz oder beides</span><span class="sxs-lookup"><span data-stu-id="1b697-109">Audio conferencing, video conferencing, or both</span></span>

<span data-ttu-id="1b697-110">In einigen Fällen ist die Kommunikation, beispielsweise Instant Messaging (im) und Anwesenheitsinformationen zwischen einem Microsoft lync Server 2013 und einem XMPP-Kontakt (Extensible Messaging and Presence Protocol) nur Peer-zu-Peer-Unterstützung nur Sie und der Kontakt beim Verbundpartner.</span><span class="sxs-lookup"><span data-stu-id="1b697-110">In some cases the communication, for example instant messaging (IM) and presence between a Microsoft Lync Server 2013 and an extensible messaging and presence protocol (XMPP) contact, is peer-to-peer only - supporting only you and the contact at the federated partner.</span></span> <span data-ttu-id="1b697-111">In anderen Fällen, beispielsweise in einer lync Server, lync Server 2010 lync Server 2013 Partnerverbund können mehrere Teilnehmer eingeladen werden, um an der Unterhaltung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1b697-111">In other cases, such as a Lync Server, Lync Server 2010 to Lync Server 2013 federation, multiple participants can be invited to join into the conversation.</span></span>

<div>

## <a name="lync-server-and-office-communications-server-federation"></a><span data-ttu-id="1b697-112">Lync Server und Office Communications Server Partnerverbund</span><span class="sxs-lookup"><span data-stu-id="1b697-112">Lync Server and Office Communications Server Federation</span></span>

<span data-ttu-id="1b697-113">Partnerverbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server unterstützt Peer-to-Peer-und Mehrparteienkommunikation.</span><span class="sxs-lookup"><span data-stu-id="1b697-113">Federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server supports peer-to-peer and multi-party communications.</span></span> <span data-ttu-id="1b697-114">Peer-zu-Peer-Unterhaltungen können an mehr Parteien Unterhaltungen weitergeleitet werden, sodass Ad-hoc-Besprechungen möglich sind.</span><span class="sxs-lookup"><span data-stu-id="1b697-114">Peer-to-peer conversations can be escalated to multi-party conversations, allowing for ad hoc meetings.</span></span> <span data-ttu-id="1b697-115">Besprechungen – Webkonferenzen oder Audio/visuelle Konferenzen – können so geplant werden, dass Sie Kontakte in Ihrer Organisation sowie Kontakte in Partnergruppen einbeziehen, mit denen Sie verbündet sind.</span><span class="sxs-lookup"><span data-stu-id="1b697-115">Meetings – Web conferencing or audio/visual conferences – can be scheduled to include contacts inside your organization as well as contacts in partners that you federate with.</span></span>

<span data-ttu-id="1b697-116">Der Verbund erschien zunächst in Microsoft Office Live Communications Server 2005 und unterstützte eine Art von Verbund, direktem Verbund.</span><span class="sxs-lookup"><span data-stu-id="1b697-116">Federation first appeared in Microsoft Office Live Communications Server 2005 and supported one kind of federation, Direct Federation.</span></span> <span data-ttu-id="1b697-117">Für den direkten Verbund mussten Sie die SIP-Domäne (Session Initiation Protocol) des Partnerverbund Partners und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeserver des Partners kennen.</span><span class="sxs-lookup"><span data-stu-id="1b697-117">Direct Federation required you to know the federation partner’s session initiation protocol (SIP) domain and the fully qualified domain name (FQDN) of the partner’s Edge Server.</span></span> <span data-ttu-id="1b697-118">Live Communications Server 2005 mit SP1 wurden zusätzliche Verbundtypen eingeführt, für die alle DNS-SRV-Einträge (Domain Name System) vom Partnerverbund veröffentlicht werden mussten, um Ihre Edgeserver zu finden.</span><span class="sxs-lookup"><span data-stu-id="1b697-118">Live Communications Server 2005 with SP1 introduced additional federation types, all of which required domain name system (DNS) SRV records to be published by the federated partner to locate their Edge Server.</span></span> <span data-ttu-id="1b697-119">Die Terminologie für diese Version lautete:</span><span class="sxs-lookup"><span data-stu-id="1b697-119">The terminology for that release was:</span></span>

  - <span data-ttu-id="1b697-120">*Open Enhanced Federation*: akzeptieren Sie einen beliebigen SIP-Domänennamen, und verwenden Sie DNS-SRV zum Auffinden der Partner Edgeserver</span><span class="sxs-lookup"><span data-stu-id="1b697-120">*Open Enhanced Federation*: Accept any SIP domain name and use DNS SRV to locate the partner Edge Server</span></span>

  - <span data-ttu-id="1b697-121">*Erweiterter Verbund*: Konfigurieren Sie den SIP-Domänennamen des Partners als Verbundpartner für Ihre Organisation, und verwenden Sie DNS-SRV, um den Partner zu finden Edgeserver</span><span class="sxs-lookup"><span data-stu-id="1b697-121">*Enhanced Federation*: Configure the partner’s SIP domain name as a federation partner for your organization and use DNS SRV to find the partner Edge Server</span></span>

  - <span data-ttu-id="1b697-122">*Direkter Verbund*: Konfigurieren Sie den SIP-Domänennamen des Partners und den FQDN für den Edgeserver des Partners.</span><span class="sxs-lookup"><span data-stu-id="1b697-122">*Direct Federation*: Configure the partner’s SIP domain name and the FQDN to the partner’s Edge Server</span></span>

  - <span data-ttu-id="1b697-123">*Server Zulassungsliste*: akzeptieren einer beliebigen Domäne, verwenden von DNS-SRV zum Auffinden der Edgeserver eines Hostinganbieter oder eines Anbieters für öffentliche Chatnachrichten (Instant Messaging)</span><span class="sxs-lookup"><span data-stu-id="1b697-123">*Server Allow List*: Accept any domain, use DNS SRV to find the Edge Server of a hosting provider or a public instant messaging (IM) connectivity provider</span></span>

<span data-ttu-id="1b697-124">Microsoft Office Communications Server 2007 wurde die aktualisierte Benennung von Verbundtypen eingeführt, um besser zu definieren, was die einzelnen Verbundtypen tatsächlich erreicht haben:</span><span class="sxs-lookup"><span data-stu-id="1b697-124">Microsoft Office Communications Server 2007 introduced updated naming for federation types to better define what each federation type actually accomplished:</span></span>

  - <span data-ttu-id="1b697-125">Open Enhanced Federation wurde als *entdeckte Partner Domäne* bezeichnet</span><span class="sxs-lookup"><span data-stu-id="1b697-125">Open Enhanced Federation became known as *Discovered Partner Domain*</span></span>

  - <span data-ttu-id="1b697-126">Erweiterter Verbund wurde als *zugelassene Partner Domäne* bezeichnet</span><span class="sxs-lookup"><span data-stu-id="1b697-126">Enhanced Federation became known as *Allowed Partner Domain*</span></span>

  - <span data-ttu-id="1b697-127">Der direkte Verbund wurde als *zulässiger Partner Server* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1b697-127">Direct Federation became known as *Allowed Partner Server*</span></span>

  - <span data-ttu-id="1b697-128">Server Zulassungsliste wurde als *Hostinganbieter* und *Öffentlicher Chat Anbieter* bezeichnet</span><span class="sxs-lookup"><span data-stu-id="1b697-128">Server Allow List became known as *Hosting Provider* and *Public IM Provider*</span></span>

<span data-ttu-id="1b697-129">Microsoft lync Server 2010 eine engere Definition des Hostinganbieter in Übereinstimmung mit Microsoft lync Online 2010 und Microsoft Office 365 eingeführt und unterliegt außerdem der gleichen zulässigen Liste, die vom Partner Domänen-Verbundtyp zulässig definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b697-129">Microsoft Lync Server 2010 introduced a narrower definition of Hosting Provider in accordance with Microsoft Lync Online 2010 and Microsoft Office 365 and also made it subject to the same allowed list defined by the Allowed Partner Domain federation type.</span></span>

<span data-ttu-id="1b697-130">Das Aktivieren des Verbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server verwendet die Edgeserver und Reverse Proxies, um die von Ihnen definierten Regeln und zulässigen Partnerdomänen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="1b697-130">Enabling federation between Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server uses the Edge Servers and reverse proxies to enforce the rules and allowed partner domains that you define.</span></span> <span data-ttu-id="1b697-131">Aus Planungssicht und Verbund mit anderen lync Server erfordert Office Communications Server Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1b697-131">From a planning perspective, federating with other Lync Server, Office Communications Server requires the following:</span></span>

  - <span data-ttu-id="1b697-132">Aktivieren Sie den Partnerverbund im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="1b697-132">Enable federation in Topology Builder.</span></span> <span data-ttu-id="1b697-133">Ausführliche Informationen finden Sie im Bereitstellungs Thema [Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und der öffentlichen Sofortnachrichten in lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="1b697-133">For details, see the Deployment topic [Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).</span></span>

  - <span data-ttu-id="1b697-134">Bestimmen der Anforderungen für die Verbunddomänen Ermittlung:</span><span class="sxs-lookup"><span data-stu-id="1b697-134">Determine your requirements for federated domain discovery:</span></span>
    
      - <span></span>  
        <span data-ttu-id="1b697-135">Für die manuelle Konfiguration des Verbunds benötigen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeserver und Domänennamens des Partners oder den Online Domänennamen, der in den **SIP-Verbunddomänen**lync Server-Systemsteuerung, Partner **Verbund und externer Zugriff**eingegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1b697-135">For manual configuration of federation, you must have the fully qualified domain name (FQDN) of the partner’s Edge Server and domain name, or online domain name, which is entered in the Lync Server Control Panel, **Federation and External Access**, **SIP Federated Domains**.</span></span> <span data-ttu-id="1b697-136">Erstellen Sie eine **neue** Richtlinie, oder **Bearbeiten** Sie eine vorhandene Richtlinie, um Domänen nach FQDN zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="1b697-136">Create a **New** policy or **Edit** an existing policy to either allow or block domains by FQDN.</span></span>
        
        <div>
        

        > [!WARNING]
        > <span data-ttu-id="1b697-137">Die manuelle Konfiguration des Edgeserver eines Partnerverbund Partners ist anfällig für den Fall, dass der Partner die IP-Adresse seiner Edgeserver ändert.</span><span class="sxs-lookup"><span data-stu-id="1b697-137">Manual configuration of a federation partner’s Edge Server is prone to failure in the event that the partner changes the IP address of their Edge Server.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="1b697-138">Für <STRONG>neue SIP-Verbunddomänen</STRONG>müssen Sie den <STRONG>Domänennamen (oder FQDN)</STRONG> für Microsoft lync Online und Microsoft 365 oder Office 365 angeben.</span><span class="sxs-lookup"><span data-stu-id="1b697-138">For <STRONG>New SIP Federated Domains</STRONG>, you must provide the <STRONG>Domain name (or FQDN)</STRONG> for Microsoft Lync Online and Microsoft 365 or Office 365.</span></span> <span data-ttu-id="1b697-139">Für Microsoft lync Server 2013, lync Server 2010 und Office Communications Server müssen Sie auch eine <STRONG>Zugriffs-Edgedienst (FQDN)</STRONG> bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1b697-139">For Microsoft Lync Server 2013, Lync Server 2010 and Office Communications Server you must also provide an <STRONG>Access Edge service (FQDN)</STRONG></span></span>

        
        </div>
    
      - <span></span>  
        <span data-ttu-id="1b697-140">Für entdeckte Partnerverbund, in dem Partner ihre Edgeserver ermitteln können, erstellen Sie einen SRV-Eintrag in Ihrem externen DNS- \_ sipfederationtls. \_ TCP.contoso.com – der auf den Port 5061 und den Host (A)-Eintrag Ihrer Edgeserver zeigt</span><span class="sxs-lookup"><span data-stu-id="1b697-140">For discovered partner federation, where partners can discover your Edge Server, you create an SRV record in your external DNS - \_sipfederationtls.\_tcp.contoso.com – which points to the port 5061 and the host (A) record of your Edge Server</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="1b697-141">Wenn Sie Microsoft lync Mobile-Clients auf Windows Phone oder Apple iPhone, iPad oder anderen Apple-Geräten unterstützen und den Push-Benachrichtigungsdienst oder den Push-Benachrichtigungsdienst verwenden, müssen Sie _sipfederationtls. _tcp planen.</span><span class="sxs-lookup"><span data-stu-id="1b697-141">If you are supporting Microsoft Lync Mobile clients on either Windows Phone or Apple iPhone, iPad, or other Apple devices and are using the Push Notification Service or Push Notification Service, you must plan for _sipfederationtls._tcp.</span></span> <span data-ttu-id="1b697-142">&lt;SIP &gt; -Domänen-SRV-Einträge für jede SIP-Domäne, in der Sie lync Mobile-Clients haben.</span><span class="sxs-lookup"><span data-stu-id="1b697-142">&lt;SIP domain&gt; SRV records for each SIP domain that you have Lync Mobile clients.</span></span> <span data-ttu-id="1b697-143">Android und Nokia Symbian lync Mobile verwenden keine Push-Benachrichtigung und unterliegen nicht dieser Anforderung.</span><span class="sxs-lookup"><span data-stu-id="1b697-143">Android and Nokia Symbian Lync Mobile do not use push notification and are not subject to this requirement.</span></span>

        
        </div>

  - <span data-ttu-id="1b697-144">Konfigurieren von Richtlinien für den externen Benutzer Zugriff zur Unterstützung von Verbunddomänen</span><span class="sxs-lookup"><span data-stu-id="1b697-144">Configure external user access policies to support federated domains</span></span>

  - <span data-ttu-id="1b697-145">Öffnen Sie Firewall-Ports für SIP (Session Initiation Protocol), Webkonferenzen und Audio/visuell, um die zu aktivierende Föderation oder Kontakte aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1b697-145">Open firewall ports for session initiation protocol (SIP), web conferencing and audio/visual to accommodate the federation or contacts that you are enabling.</span></span> <span data-ttu-id="1b697-146">Ausführliche Informationen finden Sie unter: [bestimmen der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="1b697-146">For details, see: [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)</span></span>

<span data-ttu-id="1b697-147">Die folgenden Informationen helfen Ihnen beim Definieren der Zertifikate, Port/Protokoll-und DNS-Anforderungen für den Verbund mit Microsoft lync Server 2013 und lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1b697-147">The following information will aid you in defining the certificate, port/protocol and DNS requirements for federation with Microsoft Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="1b697-148">Die Planung von Zertifikaten, Firewall-und Port/Protocol-Anforderungen und DNS-Anforderungen ist in der Regel ein geradliniger Prozess, wenn Sie die Microsoft lync Server 2013-Edgeserver geplant oder bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="1b697-148">Planning for certificates, firewall and port/protocol requirements and DNS requirements is generally a straight forward process if you have planned or deployed your Microsoft Lync Server 2013 Edge Servers.</span></span> <span data-ttu-id="1b697-149">Da es sich bei dem Verbund um ein zusätzliches Feature handelt, das die vorhandenen Edgeserver verwendet, werden die Planungsanforderungen im Allgemeinen von der Edgeserver Planung und Bereitstellung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="1b697-149">Because federation is an additional feature that uses the existing Edge Server, the planning requirements are generally met by the Edge Server planning and deployment.</span></span> <span data-ttu-id="1b697-150">Verwenden Sie die folgenden Tabellen, um zu ermitteln, ob Ihre Anforderungen erfüllt sind, und ändern Sie entsprechend Port/Protocol und DNS.</span><span class="sxs-lookup"><span data-stu-id="1b697-150">You should use the following tables to determine that your requirements are met and make changes in port/protocol and DNS accordingly.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1b697-151">Wenn Sie einen Pool mit Edgeserver haben und mit lync Server 2013 oder lync Server 2010 Partnern zusammenschließen, können Sie entweder den DNS-Lastenausgleich oder Hardwarelastenausgleichs auf den internen und externen Seiten der Edgeserver verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b697-151">If you have a pool of Edge Servers and are federating with Lync Server 2013 or Lync Server 2010 partners, then you can use either DNS load balancing or hardware load balancers on the internal and external facing sides of the Edge Servers.</span></span> <span data-ttu-id="1b697-152">Wenn Sie einen Verbund mit Office Communications Server 2007 oder Office Communications Server 2007 R2 durchführen, bietet der Hardwarelastenausgleich im Fall eines Edgeserver eine Failover-Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="1b697-152">If you are federating with Office Communications Server 2007 or Office Communications Server 2007 R2, hardware load balancing will provide failover support in the event of an Edge Server.</span></span> <span data-ttu-id="1b697-153">Office Communications Server 2007 und Office Communications Server 2007 R2 sind nicht mit dem DNS-Lastenausgleich vertraut.</span><span class="sxs-lookup"><span data-stu-id="1b697-153">Office Communications Server 2007 and Office Communications Server 2007 R2 are not DNS load balancing aware.</span></span> <span data-ttu-id="1b697-154">Die Partner-Edgeserver stellen die Kommunikation mit dem ersten Edgeserver in Ihrem Pool her, der antwortet.</span><span class="sxs-lookup"><span data-stu-id="1b697-154">The partner Edge Servers will establish communication with the first Edge Server in your pool that responds.</span></span> <span data-ttu-id="1b697-155">Wenn das Edgeserver fehlschlägt, wird bei der Kommunikation nicht automatisch ein Failover ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b697-155">If that Edge Server fails, communication does not automatically failover.</span></span>



</div>

<span data-ttu-id="1b697-156">Zertifikatanforderungen werden normalerweise durch die Planung von Zertifikaten für den ausgewählten Edgeserver oder den Pooled Edgeserver-Plan erfüllt.</span><span class="sxs-lookup"><span data-stu-id="1b697-156">Certificate requirements are typically met through the planning of certificates for your chosen Edge Server or pooled Edge Server plan.</span></span>

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a><span data-ttu-id="1b697-157">Verbindung mit öffentlichen Instant Messaging-Diensten</span><span class="sxs-lookup"><span data-stu-id="1b697-157">Public Instant Messaging Connectivity</span></span>

<span data-ttu-id="1b697-158">Die Verbindung mit öffentlichen Instant Messaging-Diensten ist eine Klasse von Verbund und wird so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden Elemente hinzufügen können:</span><span class="sxs-lookup"><span data-stu-id="1b697-158">Public Instant Messaging Connectivity is a class of federation, and is configured to allow your internal and external Lync Server 2013 users to add contacts from any of the following:</span></span>

  - <span data-ttu-id="1b697-159">Messenger-Kontakte</span><span class="sxs-lookup"><span data-stu-id="1b697-159">Messenger contacts</span></span>

  - <span data-ttu-id="1b697-160">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="1b697-160">Yahoo\!</span></span> <span data-ttu-id="1b697-161">contacts</span><span class="sxs-lookup"><span data-stu-id="1b697-161">contacts</span></span>

  - <span data-ttu-id="1b697-162">America Online (AOL)-Kontakte</span><span class="sxs-lookup"><span data-stu-id="1b697-162">America Online (AOL) contacts</span></span>

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P><span data-ttu-id="1b697-163">Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity User Subscription License (PIC USL) nicht mehr für den Kauf für neue oder erneuerte Verträge verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1b697-163">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (PIC USL) is no longer available for the purchase for new or renewing agreements.</span></span> <span data-ttu-id="1b697-164">Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1b697-164">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="1b697-165">Messenger bis zum Datum des Herunterfahrens des Diensts (das genaue Datum muss noch festgelegt werden, frühestens jedoch im Juni 2013).</span><span class="sxs-lookup"><span data-stu-id="1b697-165">Messenger until the service shutdown date (exact date is still to be decided, but no sooner than June 2013).</span></span></P>
> <LI>
> <P><span data-ttu-id="1b697-166">Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server erforderlich ist, um mit Yahoo! zu verbünden.</span><span class="sxs-lookup"><span data-stu-id="1b697-166">The PIC USL is a per-user, per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="1b697-167">Messenger.</span><span class="sxs-lookup"><span data-stu-id="1b697-167">Messenger.</span></span> <span data-ttu-id="1b697-168">Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die nicht erneuert wird.</span><span class="sxs-lookup"><span data-stu-id="1b697-168">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which will not be renewed.</span></span></P>
> <LI>
> <P><span data-ttu-id="1b697-169">Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt.</span><span class="sxs-lookup"><span data-stu-id="1b697-169">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="1b697-170">Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b697-170">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="1b697-171">Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer über Chat und Voice Hunderte von Millionen von Benutzern erreichen können.</span><span class="sxs-lookup"><span data-stu-id="1b697-171">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people through IM and voice.</span></span></P></LI></UL>



</div>

<span data-ttu-id="1b697-172">Für diese Partnerverbundklasse sind die folgenden Planungsüberlegungen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="1b697-172">This class of federation requires the following planning considerations:</span></span>

  - <span data-ttu-id="1b697-173">Windows Live Messenger-Benutzer können über Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern sowie Chatnachrichten verfügen.</span><span class="sxs-lookup"><span data-stu-id="1b697-173">Windows Live Messenger users can have peer-to-peer audio/visual communication with Lync Server 2013 users, in addition to instant messaging.</span></span> <span data-ttu-id="1b697-174">Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="1b697-174">Your Edge Servers must meet specific port and protocol requirements.</span></span> <span data-ttu-id="1b697-175">Ausführliche Informationen finden Sie unter [bestimmen der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b697-175">For details, see [Determine external A/V firewall and port requirements for Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).</span></span>

  - <span data-ttu-id="1b697-176">Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die in der Regel für die Planung und Bereitstellung der typischen Edgeserver verwendet werden, die den Verbund bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="1b697-176">Yahoo instant messaging has no unique requirements, other than those typically used in the planning and deployment of the typical Edge Server that is providing federation.</span></span>

  - <span data-ttu-id="1b697-177">Für America Online ist es erforderlich, dass Ihr Edgeserver Zertifikat, das dem Zugriffs-Edgedienst zugewiesen ist, über eine verstärkte Schlüsselverwendung für Clients verfügt (EKU).</span><span class="sxs-lookup"><span data-stu-id="1b697-177">America Online requires that your Edge Server certificate assigned to the Access Edge service has a client enhanced key usage (EKU).</span></span>

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a><span data-ttu-id="1b697-178">XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="1b697-178">Extensible Messaging and Presence Protocol (XMPP) Federation</span></span>

<span data-ttu-id="1b697-179">In früheren Versionen von lync Server und Office Communications Server wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Server Rolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1b697-179">Previous versions of Lync Server and Office Communications Server provided an extensible messaging and presence protocol (XMPP) gateway that could be deployed as a separate server role to allow federating with XMPP deployments.</span></span> <span data-ttu-id="1b697-180">In Microsoft lync Server 2013 kann die XMPP-Funktionalität als Feature bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1b697-180">In Microsoft Lync Server 2013, the XMPP functionality can be deployed as a feature.</span></span> <span data-ttu-id="1b697-181">Die XMPP-Funktionalität wird in zwei Teilen installiert: einem XMPP-Proxy, der auf dem Edgeserver und dem XMPP-Gateway ausgeführt wird, das auf den Front-End-Servern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1b697-181">XMPP functionality is installed in two parts: an XMPP proxy that runs on the Edge Server and the XMPP gateway that runs on the Front End Servers.</span></span>

<span data-ttu-id="1b697-182">Die Bereitstellung und Konfiguration von XMPP wird unter [Bereitstellen von externem Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md) behandelt, in dem xmpp in Ihrer Organisation unterstützt werden soll, indem Sie Port-und Protokollregeln für Ihre Firewall, die Konfiguration von Zertifikaten und das Hinzufügen von DNS-Einträgen definieren.</span><span class="sxs-lookup"><span data-stu-id="1b697-182">Deployment and configuration of XMPP is covered in [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) You plan for supporting XMPP in your organization by defining port and protocol rules on your firewall, configuration of certificates, and adding DNS records.</span></span> <span data-ttu-id="1b697-183">In den folgenden Themen in diesem Abschnitt werden die Informationen zusammengefasst, die Sie benötigen, um den XMPP-Partnerverbund für Ihre Bereitstellung erfolgreich zu planen.</span><span class="sxs-lookup"><span data-stu-id="1b697-183">The following topics in this section summarize the information that you will need to successfully plan XMPP federation for your deployment.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1b697-184">Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b697-184">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="1b697-185">Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1b697-185">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>


> [!IMPORTANT]
> <span data-ttu-id="1b697-186">Der XMPP-Verbund wird für Benutzer, die in Survivable Branch Appliances verwaltet werden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b697-186">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="1b697-187">Dies gilt sowohl für das Anzeigen von Anwesenheitsinformationen als auch für den Austausch von Chatnachrichten.</span><span class="sxs-lookup"><span data-stu-id="1b697-187">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

</div>

<div id="sectionSection3" class="section">

<span data-ttu-id="1b697-188">In den folgenden Themen finden Sie Anleitungen zum Definieren von Zertifikaten, Firewall-Ports und DNS-Einträgen für die Typen unterstützter Verbundszenarien.</span><span class="sxs-lookup"><span data-stu-id="1b697-188">In the following topics contain guidance for defining certificates, firewall ports and DNS entries for the types of supported federation scenarios.</span></span>

  - <span></span>  
    [<span data-ttu-id="1b697-189">Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-189">Certificate summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="1b697-190">Port Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-190">Port summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [<span data-ttu-id="1b697-191">DNS-Zusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-191">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b697-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b697-192">See Also</span></span>


[<span data-ttu-id="1b697-193">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-193">Configure policies to control federated user access in Lync Server 2013</span></span>](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[<span data-ttu-id="1b697-194">Szenarien für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-194">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="1b697-195">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-195">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[<span data-ttu-id="1b697-196">Bestimmen der DNS-Anforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-196">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="1b697-197">Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-197">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[<span data-ttu-id="1b697-198">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-198">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[<span data-ttu-id="1b697-199">Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b697-199">Manage SIP federated providers for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

