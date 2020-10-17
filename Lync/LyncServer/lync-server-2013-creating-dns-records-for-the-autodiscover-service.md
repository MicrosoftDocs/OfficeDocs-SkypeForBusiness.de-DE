---
title: 'Lync Server 2013: Erstellen von DNS-Einträgen für den AutoErmittlungsdienst'
description: 'Lync Server 2013: Erstellen von DNS-Einträgen für den AutoErmittlungsdienst.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating DNS records for the Autodiscover Service
ms:assetid: 3756ffe4-c6b1-492d-850e-42a832e06567
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690010(v=OCS.15)
ms:contentKeyID: 48183823
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6903e6b07001289db8b65e8cc962e8d8db4b248b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563101"
---
# <a name="creating-dns-records-for-the-autodiscover-service-in-lync-server-2013"></a><span data-ttu-id="5c275-103">Erstellen von DNS-Einträgen für den AutoErmittlungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c275-103">Creating DNS records for the Autodiscover Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c275-104">_**Letztes Änderungsstand des Themas:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="5c275-104">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="5c275-105">Ihre mobilen lync-Benutzer müssen AutoDiscovery aktivieren, und ein Teil davon umfasst das Erstellen einiger Domain Name System (DNS)er Datensätze.</span><span class="sxs-lookup"><span data-stu-id="5c275-105">Your Lync Mobile users will need you to enable autodiscovery, and a part of that involves creating some Domain Name System (DNS) records.</span></span> <span data-ttu-id="5c275-106">Je nach Ihren Anforderungen benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5c275-106">Depending on your needs, you need the following:</span></span>

  - <span data-ttu-id="5c275-107">Ein interner DNS-Eintrag zur Unterstützung mobiler Benutzer, die im Netzwerk Ihrer Organisation eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="5c275-107">An internal DNS record to support mobile users who’re connecting from within your organization's network.</span></span>

  - <span data-ttu-id="5c275-108">Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung mobiler Benutzer, die eine Verbindung über das Internet herstellen</span><span class="sxs-lookup"><span data-stu-id="5c275-108">An external, or public, DNS record to support mobile users who’re connecting from the Internet</span></span>

<span data-ttu-id="5c275-109">Warum beides?</span><span class="sxs-lookup"><span data-stu-id="5c275-109">Why both?</span></span> <span data-ttu-id="5c275-110">Sie müssen sowohl einen internen DNS-Eintrag als auch einen externen DNS-Eintrag für jede SIP-Domäne erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c275-110">You need to create both an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="5c275-111">Bei den von Ihnen erstellten DNS-Einträgen kann es sich entweder um einen (Host-) Eintrag oder um CNAME-Einträge handeln.</span><span class="sxs-lookup"><span data-stu-id="5c275-111">The DNS records you create can be either A (host) records or CNAME records.</span></span> <span data-ttu-id="5c275-112">Um Ihnen zu helfen, erfahren Sie, wie Sie diese internen und externen DNS-Einträge unten erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c275-112">To help you out, we’ll walk through how to create these internal and external DNS records below.</span></span> <span data-ttu-id="5c275-113">Wenn Sie weitere Informationen zu den DNS-Anforderungen für mobile Benutzer benötigen, können Sie die [technischen Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="5c275-113">If you need to do some further reading about the DNS requirements for mobile users, you can check out [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

<div>

## <a name="creating-an-internal-dns-cname-record"></a><span data-ttu-id="5c275-114">Erstellen eines internen DNS-CNAME-Eintrags</span><span class="sxs-lookup"><span data-stu-id="5c275-114">Creating an internal DNS CNAME record</span></span>

1.  <span data-ttu-id="5c275-115">Um einen internen DNS-Eintrag zu erstellen, müssen Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto anmelden, das entweder Mitglied der Gruppe "Domänen-Admins" oder ein Mitglied der Gruppe "DnsAdmins" ist.</span><span class="sxs-lookup"><span data-stu-id="5c275-115">To make an internal DNS record, you’ll need to log on to a DNS server in your network with a domain account that’s either a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="5c275-116">Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5c275-116">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="5c275-117">Erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory Domäne, in der Ihre lync Server 2013 Directorpool und Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="5c275-117">In the console tree of the DNS server, expand **Forward Lookup Zones** for the Active Directory domain where your Lync Server 2013 Director pool and Front End pool are installed.</span></span> <span data-ttu-id="5c275-118">(beispielsweise "contoso. local").</span><span class="sxs-lookup"><span data-stu-id="5c275-118">(for example, contoso.local).</span></span>

4.  <span data-ttu-id="5c275-119">Prüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Directorpool für einen internen DNS-Eintrag vorhanden ist, sollte ein Host-a-Eintrag für den internen Webdienste vollqualifizierten Domänennamen (FQDN) für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="5c275-119">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="5c275-120">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keinen Directorpool, und Sie müssen den FQDN für Ihren Front-End-Pool oder sogar einen einzelnen Server-FQDN verwenden, falls dies Ihr Setup ist.</span><span class="sxs-lookup"><span data-stu-id="5c275-120">If it’s not here, you may not be using a Director pool, and you’ll need to use the FQDN for your Front End pool or even a single server FQDN, if that’s your setup.</span></span>

5.  <span data-ttu-id="5c275-121">Beachten Sie, dass Sie überprüfen und sehen können, ob ein Host-a-Eintrag (AAAA für IPv6) für die Front-End-Pool eines internen DNS-Eintrags vorhanden ist, dass ein Host-a-Eintrag (oder AAAA) für den internen Webdienste-FQDN für Ihre Front-End-Pool vorhanden sein muss (beispielsweise lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="5c275-121">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="5c275-122">Wenn dies nicht der Fall ist, müssen Sie den FQDN für den Front-End-Server oder Standard Edition-Server notieren.</span><span class="sxs-lookup"><span data-stu-id="5c275-122">If it doesn’t, you’ll need to make note of the FQDN for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="5c275-123">Wenn Sie wissen, welche Host-a-(oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5c275-123">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="5c275-124">Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="5c275-124">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="5c275-125">Geben Sie unter **Aliasname**"lyncdiscoverinternal" als Hostnamen für die interne AutoErmittlungsdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="5c275-125">In **Alias name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="5c275-126">Geben Sie im **vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den Zielhost**den internen Webdienste FQDN für den Directorpool ein (beispielsweise lyncwebdir01. contoso. local), oder klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c275-126">In **Fully qualified domain name (FQDN) for target host**, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local) and then click **OK**.</span></span>

10. <span data-ttu-id="5c275-127">Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013 Umgebung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5c275-127">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-cname-record"></a><span data-ttu-id="5c275-128">Erstellen eines externen DNS-CNAME-Eintrags</span><span class="sxs-lookup"><span data-stu-id="5c275-128">Creating an external DNS CNAME record</span></span>

1.  <span data-ttu-id="5c275-129">Zum Erstellen eines externen DNS-CNAME-Eintrags müssen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter herstellen und dann unsere Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="5c275-129">To create an external DNS CNAME record, you’re going to need to connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="5c275-130">Wir können nicht genau beschreiben, wo Sie in die Umgebung Ihres DNS-Anbieters wechseln, da es unterschiedliche Möglichkeiten zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="5c275-130">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="5c275-131">Melden Sie sich bei Ihrem externen DNS-Anbieter mit einem Konto an, das DNS-Einträge in dieser Umgebung erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="5c275-131">Log into your external DNS provider with an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="5c275-132">Sie sollten bereits eine SIP-Domäne für diese Umgebung erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="5c275-132">You should have a SIP domain created for this environment already.</span></span> <span data-ttu-id="5c275-133">Erweitern Sie die **Forward-Lookupzone** für diese SIP-Domäne, oder wählen Sie Sie auf andere Weise je nach verwendeter externer DNS-Schnittstelle aus.</span><span class="sxs-lookup"><span data-stu-id="5c275-133">Expand the **Forward Lookup Zone** for this SIP domain, or otherwise select it depending on the external DNS interface being used.</span></span>

4.  <span data-ttu-id="5c275-134">Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihre Directorpool (beispielsweise lyncwebexdir01.contoso.com) sehen, also bestätigen Sie, dass dieser vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5c275-134">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there.</span></span> <span data-ttu-id="5c275-135">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keine Directorpool.</span><span class="sxs-lookup"><span data-stu-id="5c275-135">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="5c275-136">Wenn dies der Fall ist, müssen Sie den FQDN des Front-End-Pools verwenden, oder wenn Sie dies für einen einzelnen Server, für Ihren Front-End Server oder Standard Edition-Server tun.</span><span class="sxs-lookup"><span data-stu-id="5c275-136">If that’s the case, you’ll need to use the FQDN of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span>

5.  <span data-ttu-id="5c275-137">Sie müssen außerdem sicherstellen, dass ein Host-a-Eintrag (AAAA für IPv6) für Ihren externen Webdienste vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Ihre Front-End-Pool (beispielsweise lyncwebextpool01.contoso.com) oder ein FQDN für Ihren Einzelserver-FQDN vorhanden ist, wenn Sie über keine Front-End-Pool verfügen.</span><span class="sxs-lookup"><span data-stu-id="5c275-137">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or a FQDN for your single-server FQDN if you have no Front End pool.</span></span> <span data-ttu-id="5c275-138">Wie im vorherigen Schritt erwähnt, benötigen Sie diese weiter unten, wenn Sie keine Directorpool haben.</span><span class="sxs-lookup"><span data-stu-id="5c275-138">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="5c275-139">Wählen Sie nun im entsprechenden Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Alias (CNAME)** (Dies kann eine Menüoption oder ein Link sein, je nach Format des DNS-Anbieters).</span><span class="sxs-lookup"><span data-stu-id="5c275-139">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Alias (CNAME)** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="5c275-140">Es sollte eine Form von **Alias Namen** -Textfeld geben wie beim internen DNS sollten Sie lyncdiscover als Hostnamen für die externe AutoErmittlungsdienst-URL eingeben.</span><span class="sxs-lookup"><span data-stu-id="5c275-140">There should be some form of **Alias name** text box as with the internal DNS, you should enter lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="5c275-141">Es sollte auch eine Form eines **vollqualifizierten Domänennamens (Fully Qualified Domain Name, FQDN) für das Textfeld Zielhost** geben, hier geben Sie den externen Webdienste-FQDN für Ihre Directorpool ein (beispielsweise lyncwebexdir01.contoso.com), und klicken Sie dann auf OK, oder nehmen Sie alle Aktionen im externen DNS vor, um die Erstellung dieses Eintrags zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="5c275-141">There should also be some form of a **Fully qualified domain name (FQDN) for target host** text box, here’s where you’ll enter the external Web Services FQDN for your Director pool (for example, lyncwebexdir01.contoso.com) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="5c275-142">Wie in Schritt 4 oben erwähnt, müssen Sie, wenn Sie nicht über ein Directorpool verfügen, den Front-End-Pool-FQDN oder den FQDN des Einzelservers verwenden, den Sie eingerichtet haben, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5c275-142">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool FQDN or the single-server FQDN you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="5c275-143">Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013 Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5c275-143">You’ll need to make a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

<div>

## <a name="creating-an-internal-dns-a-record"></a><span data-ttu-id="5c275-144">Erstellen eines internen DNS-A-Eintrags</span><span class="sxs-lookup"><span data-stu-id="5c275-144">Creating an internal DNS A record</span></span>

1.  <span data-ttu-id="5c275-145">Um einen internen DNS-Eintrag zu erstellen, melden Sie sich bei einem DNS-Server in Ihrem Netzwerk mit einem Domänenkonto an, das Mitglied der Gruppe "Domänen-Admins" oder ein Mitglied der Gruppe "DnsAdmins" ist.</span><span class="sxs-lookup"><span data-stu-id="5c275-145">To make an internal DNS record, log on to a DNS server in your network with a domain account that’s a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="5c275-146">Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5c275-146">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="5c275-147">Erweitern Sie für einen internen DNS-Eintrag in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre Active Directory Domäne (beispielsweise "contoso. local"), in der Ihre lync Server 2013 Directorpool und Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="5c275-147">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local) where your Lync Server 2013 Director pool and Front End pool are installed.</span></span>

4.  <span data-ttu-id="5c275-148">Prüfen Sie, ob ein Host-a-Eintrag (AAAA für IPv6) für Ihren Directorpool für einen internen DNS-Eintrag vorhanden ist, sollte ein Host-a-Eintrag für den internen Webdienste vollqualifizierten Domänennamen (FQDN) für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="5c275-148">Check and see if a host A (AAAA for IPv6) record exists for your Director pool for an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span> <span data-ttu-id="5c275-149">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keine Directorpool, und Sie müssen die IP-Adresse für Ihre Front-End-Pool oder sogar eine IP-Adresse für einen einzelnen Server verwenden, falls dies Ihr Setup ist.</span><span class="sxs-lookup"><span data-stu-id="5c275-149">If it’s not here, you may not be using a Director pool, and you’ll need to use the IP address for your Front End pool or even a single server IP address, if that’s your setup.</span></span>

5.  <span data-ttu-id="5c275-150">Beachten Sie, dass Sie überprüfen und sehen können, ob ein Host-a-Eintrag (AAAA für IPv6) für die Front-End-Pool eines internen DNS-Eintrags vorhanden ist, dass ein Host-a-Eintrag (oder AAAA) für den internen Webdienste-FQDN für Ihre Front-End-Pool vorhanden sein muss (beispielsweise lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="5c275-150">Keeping that in mind, check and see if a host A (AAAA for IPv6) record exists for your Front End pool for an internal DNS record, a host A (or AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span> <span data-ttu-id="5c275-151">Wenn dies nicht der Fall ist, müssen Sie die IP-Adresse für die Front-End-Server oder Standard Edition-Server notieren.</span><span class="sxs-lookup"><span data-stu-id="5c275-151">If it doesn’t, you’ll need to make note of the IP address for the Front End Server or Standard Edition server.</span></span>

6.  <span data-ttu-id="5c275-152">Wenn Sie wissen, welche Host-a-(oder AAAA)-Einträge vorhanden sind, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für Ihre SIP-Domäne (beispielsweise contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5c275-152">Once you know what host A (or AAAA) records exist, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

7.  <span data-ttu-id="5c275-153">Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="5c275-153">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="5c275-154">Geben Sie unter **Name**den Namen "lyncdiscoverinternal" als Hostnamen für die interne URL des AutoErmittlungsdiensts ein.</span><span class="sxs-lookup"><span data-stu-id="5c275-154">In **Name**, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="5c275-155">Geben Sie unter **IP-Adresse**die interne Webdienste-IP-Adresse des Directors ein (oder geben Sie bei Verwendung eines Lastenausgleichs die virtuelle IP (VIP) des Director-Lastenausgleichs) ein.</span><span class="sxs-lookup"><span data-stu-id="5c275-155">In **IP Address**, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span> <span data-ttu-id="5c275-156">Wie in Schritt 4 oben erwähnt, müssen Sie möglicherweise die IP-Adresse des Front-End-Server oder Standard Edition-Server eingeben oder, wenn Sie einen Lastenausgleichsmodul verwenden, den VIP des Front-End-Pool Lastenausgleichs eingeben.</span><span class="sxs-lookup"><span data-stu-id="5c275-156">As noted in Step 4 above, if you aren’t using a Director, you may need to enter the IP address of the Front End Server or Standard Edition server or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

10. <span data-ttu-id="5c275-157">Klicken Sie auf **Host hinzufügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c275-157">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="5c275-158">Wenn Sie einen zusätzlichen a-oder AAAA-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10, und beachten Sie dabei, dass Sie in der Forward-Lookupzone jeder SIP-Domäne, die in ihrer lync Server 2013 Umgebung unterstützt wird, neue a-oder AAAA-Einträge für die AutoErmittlung erstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="5c275-158">To create an additional A or AAAA record, repeat steps 8 through 10, keeping in mind that you’ll need to create new Autodiscover A or AAAA records in the forward lookup zone of each SIP domain that’s supported in your Lync Server 2013 environment.</span></span>

12. <span data-ttu-id="5c275-159">Klicken Sie auf **Fertig**, wenn Sie das Erstellen von A-Einträgen (für IPv6, AAAA) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="5c275-159">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

<div>

## <a name="creating-an-external-dns-a-record"></a><span data-ttu-id="5c275-160">Erstellen eines externen DNS-A-Eintrags</span><span class="sxs-lookup"><span data-stu-id="5c275-160">Creating an external DNS A record</span></span>

1.  <span data-ttu-id="5c275-161">Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter her, und führen Sie dann die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="5c275-161">To create an external DNS record, connect to your public DNS provider, and then follow our steps.</span></span> <span data-ttu-id="5c275-162">Wir können nicht genau beschreiben, wo Sie in die Umgebung Ihres DNS-Anbieters wechseln, da es unterschiedliche Möglichkeiten zur Verwaltung Ihres externen DNS geben kann, aber wir hoffen, dass diese Schritte hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="5c275-162">We can’t describe exactly where you’re going in your DNS provider’s environment as there may be different ways of managing your external DNS, but we hope these steps help.</span></span>

2.  <span data-ttu-id="5c275-163">Sie müssen als Konto angemeldet sein, das DNS-Einträge in dieser Umgebung erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="5c275-163">You’ll need to be logged in as an account that can create DNS records in that environment.</span></span>

3.  <span data-ttu-id="5c275-164">Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").</span><span class="sxs-lookup"><span data-stu-id="5c275-164">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span> <span data-ttu-id="5c275-165">Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").</span><span class="sxs-lookup"><span data-stu-id="5c275-165">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="5c275-166">Sie sollten bereits einen Host-a-Eintrag (AAAA für IPv6) für Ihre Directorpool (beispielsweise lyncwebexdir01.contoso.com) sehen, also bestätigen Sie, dass er vorhanden ist und was die IP-Adresse ist.</span><span class="sxs-lookup"><span data-stu-id="5c275-166">You should already see a host A (AAAA for IPv6) record for your Director pool (such as lyncwebexdir01.contoso.com), so confirm that it’s there and what the IP address is.</span></span> <span data-ttu-id="5c275-167">Wenn dies nicht der Fall ist, verwenden Sie möglicherweise keine Directorpool.</span><span class="sxs-lookup"><span data-stu-id="5c275-167">If it’s not, then you may not be using a Director pool.</span></span> <span data-ttu-id="5c275-168">Wenn dies der Fall ist, müssen Sie die IP-Adresse des Front-End-Pools verwenden oder wenn Sie dies für einen einzelnen Server, für Ihren Front-End Server oder Standard Edition-Server tun.</span><span class="sxs-lookup"><span data-stu-id="5c275-168">If that’s the case, you’ll need to use the IP address of your Front End Pool, or if you’re doing this for a single server, for your Front-End server or Standard Edition server.</span></span> <span data-ttu-id="5c275-169">Beachten Sie, dass sich Ihre Server möglicherweise auch hinter einem Lastenausgleichsmodul oder einem Reverseproxy befinden.</span><span class="sxs-lookup"><span data-stu-id="5c275-169">Keep in mind that your servers may also be behind a load-balancer, or using a reverse proxy.</span></span> <span data-ttu-id="5c275-170">Notieren Sie sich die IP-Adressen, und führen Sie die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="5c275-170">Make note of the IP addresses as well for following the steps below.</span></span>

5.  <span data-ttu-id="5c275-171">Sie müssen außerdem sicherstellen, dass ein Host-a-Eintrag (AAAA für IPv6) für Ihren externen Webdienste vollqualifizierten Domänennamen (FQDN) für Ihre Front-End-Pool (beispielsweise lyncwebextpool01.contoso.com) oder eine IP-Adresse für die Einzelserver-lync-Installation vorhanden ist, wenn Sie keine Front-End-Pool haben.</span><span class="sxs-lookup"><span data-stu-id="5c275-171">You’ll also need to confirm that a host A (AAAA for IPv6) record exists for your external Web Services Fully Qualified Domain Name (FQDN) for your Front End pool (such as lyncwebextpool01.contoso.com), or an IP address for your single-server Lync installation if you have no Front End pool.</span></span> <span data-ttu-id="5c275-172">Wie im vorherigen Schritt erwähnt, benötigen Sie diese weiter unten, wenn Sie keine Directorpool haben.</span><span class="sxs-lookup"><span data-stu-id="5c275-172">As noted in the previous step, you’ll need this below if you don’t have a Director pool.</span></span>

6.  <span data-ttu-id="5c275-173">Wählen Sie nun im entsprechenden Format für Ihren externen DNS-Anbieter die Option zum Erstellen eines **neuen Hosts a oder AAAA** (Dies kann eine Menüoption oder ein Link sein, je nach Format des DNS-Anbieters).</span><span class="sxs-lookup"><span data-stu-id="5c275-173">Now, in the appropriate format for your external DNS provider, choose the option for creating a **New Host A or AAAA** (this may be a menu option or a link, depending on the format of the DNS provider).</span></span>

7.  <span data-ttu-id="5c275-174">Es sollte einen Ort geben, um einen **Namen**einzugeben, geben Sie lyncdiscover als Hostnamen für die externe AutoErmittlungsdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="5c275-174">There should be a place to enter a **Name**, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

8.  <span data-ttu-id="5c275-175">Es sollte auch ein **IP-Adress** Textfeld vorhanden sein, in dem Sie die IP-Adresse für Ihre Directorpool eingeben (beispielsweise lyncwebexdir01.contoso.com) oder möglicherweise die IP-Adresse des Lastenausgleichs Ihres Pools (oder eine Reverse-Proxy-IP, die dazu führt) und dann auf OK klicken oder eine beliebige Aktion im externen DNS durchführen, um die Erstellung dieses Eintrags zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="5c275-175">There should also be an **IP Address** text box, here’s where you’ll enter the IP for your for your Director pool (for example, lyncwebexdir01.contoso.com) or possibly the IP of your pool’s load balancer (or a reverse proxy IP that leads to the same) and then click OK or take whatever action in the external DNS to accept the creation of this entry.</span></span> <span data-ttu-id="5c275-176">Wie in Schritt 4 oben erwähnt, müssen Sie, wenn Sie nicht über ein Directorpool verfügen, die Front-End-Pool-IP-Adresse oder die IP-Adresse eines einzelnen Servers verwenden, die Sie eingerichtet haben, je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5c275-176">As noted in Step 4, above, if you don’t have a Director pool, you’ll need to use the Front End pool IP address or the single-server IP address you have set up, as appropriate.</span></span>

9.  <span data-ttu-id="5c275-177">Sie müssen einen neuen Auto Ermittlungs Eintrag a oder AAAA in der Forward-Lookupzone jeder SIP-Domäne erstellen, die in ihrer lync 2013 Umgebung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5c275-177">You’ll need to make a new Autodiscover A or AAAA record in the forward lookup zone of each SIP domain that’s supported in your Lync 2013 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

