---
title: 'Lync Server 2013: Konfigurieren von DNS für die AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring DNS for Autodiscover
ms:assetid: f07a634c-3cf3-4958-8556-84596319ef54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945656(v=OCS.15)
ms:contentKeyID: 51541528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 249993e68930db1eb5dd5159633a73f80cef8c05
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520052"
---
# <a name="configuring-dns-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="aa3c8-102">Konfigurieren von DNS für die AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa3c8-102">Configuring DNS for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa3c8-103">_**Letztes Änderungsstand des Themas:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="aa3c8-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="aa3c8-104">Um die AutoErmittlung für lync-Clients zu unterstützen, müssen Sie die folgenden Domain Name System (DNS)-Einträge erstellen:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-104">To support autodiscovery for Lync clients, you need to create the following Domain Name System (DNS) records:</span></span>

  - <span data-ttu-id="aa3c8-105">Ein interner DNS-Eintrag zur Unterstützung von lync-Clients, die im Netzwerk Ihrer Organisation eine Verbindung herstellen</span><span class="sxs-lookup"><span data-stu-id="aa3c8-105">An internal DNS record to support Lync clients who connect from within your organization's network</span></span>

  - <span data-ttu-id="aa3c8-106">Einen externen oder öffentlichen DNS-Eintrag zur Unterstützung von lync-Clients, die eine Verbindung über das Internet herstellen</span><span class="sxs-lookup"><span data-stu-id="aa3c8-106">An external, or public, DNS record to support Lync clients who connect from the Internet</span></span>

<span data-ttu-id="aa3c8-107">Für jede SIP-Domäne muss ein interner DNS-Eintrag und ein externer DNS-Eintrag erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-107">You must create an internal DNS record and an external DNS record for each SIP domain.</span></span>

<span data-ttu-id="aa3c8-108">Bei den DNS-Einträgen kann es sich entweder um einen (Host-) Eintrag oder um CNAME-Einträge handeln, basierend auf ihrer Fähigkeit, neue Zertifikate mit dem zusätzlichen Antragstellernamen (San) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-108">The DNS records can be either A (host) records or CNAME records, based on your ability to create new certificates with the additional subject alternate name (SAN).</span></span> <span data-ttu-id="aa3c8-109">Wenn Sie kein neues externes (öffentliches) Zertifikat mit dem lyncdiscover anfordern und bereitstellen können.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="aa3c8-109">If you are not able to request and deploy a new external (public) certificate with the lyncdiscover.\<domain name\></span></span> <span data-ttu-id="aa3c8-110">San verwenden Sie das Verfahren für die Verwendung von http/TCP-Port 80.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-110">SAN, use the procedure for using HTTP/TCP port 80.</span></span> <span data-ttu-id="aa3c8-111">Die folgenden Vorgehensweisen beschreiben, wie interne und externe DNS-Einträge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-111">The following procedures describe how to create internal and external DNS records.</span></span>

<div>

## <a name="to-create-dns-cname-records"></a><span data-ttu-id="aa3c8-112">So erstellen Sie DNS-CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="aa3c8-112">To create DNS CNAME records</span></span>

1.  <span data-ttu-id="aa3c8-113">Melden Sie sich wie folgt an einem DNS-Server an:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-113">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-114">Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich an einem DNS-Server in Ihrem Netzwerk als Mitglied der Domänenadministratorgruppe oder der DnsAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-114">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="aa3c8-115">Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit dem öffentlichen DNS-Anbieter her.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-115">To create an external DNS record, connect to your public DNS provider.</span></span>

2.  <span data-ttu-id="aa3c8-116">Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-116">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="aa3c8-117">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="aa3c8-118">Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne (z. B. "contoso.local").</span><span class="sxs-lookup"><span data-stu-id="aa3c8-118">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aa3c8-119">Diese Domäne ist die Active Directory Domäne, in der Ihre lync Server 2013 &nbsp; Directorpool und Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-119">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="aa3c8-120">Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").</span><span class="sxs-lookup"><span data-stu-id="aa3c8-120">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="aa3c8-121">Stellen Sie sicher, dass ein Host-a-Eintrag für Ihre Directorpool wie folgt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-121">Verify that a host A record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-122">Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag für den internen Webdienste vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-122">For an internal DNS record, a host A record should exist for the internal Web Services fully qualified domain name (FQDN) for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="aa3c8-123">Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag für den externen Webdienste-FQDN für Ihre Directorpool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-123">For an external DNS record, a host A record should exist for the external web services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="aa3c8-124">Stellen Sie sicher, dass ein Host-a-Eintrag für Ihre Front-End-Pool wie folgt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-124">Verify that a host A record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-125">Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag für den internen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-125">For an internal DNS record, a host A record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="aa3c8-126">Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag für den externen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-126">For an external DNS record, a host A record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="aa3c8-127">Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").</span><span class="sxs-lookup"><span data-stu-id="aa3c8-127">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa3c8-128">Wenn Sie einen externen DNS-Eintrag erstellen, ist <STRONG>Forward-Lookupzonen</STRONG> bereits für die SIP-Domäne aus Schritt 3 erweitert.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-128">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="aa3c8-129">Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Alias (CNAME)**.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-129">Right-click the SIP domain name, and then click **New Alias (CNAME)**.</span></span>

8.  <span data-ttu-id="aa3c8-130">Nehmen Sie im Feld **Aliasname** eine der folgenden Eingaben vor:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-130">In **Alias name**, type one of the following:</span></span>
    
      - <span data-ttu-id="aa3c8-131">Geben Sie für einen internen DNS-Eintrag "lyncdiscoverinternal" als den Hostnamen für die interne AutoErmittlungdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-131">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="aa3c8-132">Geben Sie für einen externen DNS-Eintrag "lyncdiscover" als den Hostnamen für die externe AutoErmittlungdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-132">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>

9.  <span data-ttu-id="aa3c8-133">Führen Sie in **Vollqualifizierter Domänenname des Zielhosts** einen der folgenden Schritte durch:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-133">In **Fully qualified domain name (FQDN) for target host**, do one of the following:</span></span>
    
      - <span data-ttu-id="aa3c8-134">Geben Sie für einen internen DNS-Eintrag den internen Webdienste-FQDN für Ihre Directorpool ein (beispielsweise lyncwebdir01. contoso. local), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-134">For an internal DNS record, type or browse to the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local), and then click **OK**.</span></span>
    
      - <span data-ttu-id="aa3c8-135">Geben Sie für einen externen DNS-Eintrag den FQDN des externen Webdienste für die Directorpool ein (beispielsweise lyncwebextdir.contoso.com), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-135">For an external DNS record, type or browse to the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa3c8-136">Wenn Sie keinen Director verwenden, verwenden Sie den internen und externen Webdienste-FQDN für den Front-End-Pool oder für einen einzelnen Server den FQDN für die Front-End-Server oder Standard Edition-Server.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-136">If you do not use a Director, use the internal and external Web Services FQDN for the Front End pool, or, for a single server, the FQDN for the Front End Server or Standard Edition server.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aa3c8-137">Sie müssen einen neuen CNAME-Eintrag für die AutoErmittlung in der Forward-Lookupzone jeder SIP-Domäne erstellen, die Sie in ihrer lync Server 2013 Umgebung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-137">You must create a new Autodiscover CNAME record in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

</div>

<div>

## <a name="to-create-dns-a-records"></a><span data-ttu-id="aa3c8-138">So erstellen Sie DNS-A-Einträge</span><span class="sxs-lookup"><span data-stu-id="aa3c8-138">To create DNS A records</span></span>

1.  <span data-ttu-id="aa3c8-139">Melden Sie sich wie folgt an einem DNS-Server an:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-139">Log on to a DNS server as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-140">Wenn Sie einen internen DNS-Eintrag erstellen möchten, melden Sie sich an einem DNS-Server in Ihrem Netzwerk als Mitglied der Domänenadministratorgruppe oder der DnsAdmins-Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-140">To create an internal DNS record, log on to a DNS server in your network as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
    
      - <span data-ttu-id="aa3c8-141">Wenn Sie einen externen DNS-Eintrag erstellen möchten, stellen Sie eine Verbindung mit Ihrem öffentlichen DNS-Anbieter oder externen DNS-Server her.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-141">To create an external DNS record, connect to your public DNS provider or external DNS server.</span></span>

2.  <span data-ttu-id="aa3c8-142">Öffnen Sie das DNS-Verwaltungs-Snap-In: Klicken Sie auf **Start**, auf **Verwaltung** und dann auf **DNS**.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-142">Open the DNS administrative snap-in: Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="aa3c8-143">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-143">Do one of the following:</span></span>
    
      - <span data-ttu-id="aa3c8-144">Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die Active Directory-Domäne (z. B. "contoso.local").</span><span class="sxs-lookup"><span data-stu-id="aa3c8-144">For an internal DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your Active Directory domain (for example, contoso.local).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aa3c8-145">Diese Domäne ist die Active Directory Domäne, in der Ihre lync Server 2013 &nbsp; Directorpool und Front-End-Pool installiert sind.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-145">This domain is the Active Directory domain where your Lync Server 2013&nbsp;Director pool and Front End pool are installed.</span></span>

        
        </div>
    
      - <span data-ttu-id="aa3c8-146">Wenn Sie einen externen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").</span><span class="sxs-lookup"><span data-stu-id="aa3c8-146">For an external DNS record, in the console tree of the DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>

4.  <span data-ttu-id="aa3c8-147">Stellen Sie sicher, dass ein Host-a-Eintrag (für IPv6, AAAA) für Ihre Directorpool wie folgt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-147">Verify that a host A (for IPv6, AAAA) record exists for your Director pool as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-148">Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienste FQDN für Ihre Directorpool vorhanden sein (beispielsweise lyncwebdir01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-148">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Director pool (for example, lyncwebdir01.contoso.local).</span></span>
    
      - <span data-ttu-id="aa3c8-149">Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den externen Webdienste-FQDN für Ihre Directorpool vorhanden sein (beispielsweise lyncwebextdir.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-149">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Director pool (for example, lyncwebextdir.contoso.com).</span></span>

5.  <span data-ttu-id="aa3c8-150">Stellen Sie sicher, dass ein Host-a-Eintrag (für IPv6, AAAA) für Ihre Front-End-Pool wie folgt vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-150">Verify that a host A (for IPv6, AAAA) record exists for your Front End pool as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-151">Für einen internen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den internen Webdienste FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebpool01. contoso. local).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-151">For an internal DNS record, a host A (for IPv6, AAAA) record should exist for the internal Web Services FQDN for your Front End pool (for example, lyncwebpool01.contoso.local).</span></span>
    
      - <span data-ttu-id="aa3c8-152">Für einen externen DNS-Eintrag sollte ein Host-a-Eintrag (für IPv6, AAAA) für den externen Webdienste-FQDN für Ihre Front-End-Pool vorhanden sein (beispielsweise lyncwebextpool01.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aa3c8-152">For an external DNS record, a host A (for IPv6, AAAA) record should exist for the external Web Services FQDN for your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>

6.  <span data-ttu-id="aa3c8-153">Wenn Sie einen internen DNS-Eintrag erstellen, erweitern Sie in der Konsolenstruktur des DNS-Servers **Forward-Lookupzonen** für die SIP-Domäne (z. B. "contoso.com").</span><span class="sxs-lookup"><span data-stu-id="aa3c8-153">For an internal DNS record, in the console tree of your DNS server, expand **Forward Lookup Zones** for your SIP domain (for example, contoso.com).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa3c8-154">Wenn Sie einen externen DNS-Eintrag erstellen, ist <STRONG>Forward-Lookupzonen</STRONG> bereits für die SIP-Domäne aus Schritt 3 erweitert.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-154">If you are creating an external DNS record, <STRONG>Forward Lookup Zones</STRONG> is already expanded for your SIP domain from step 3.</span></span>

    
    </div>

7.  <span data-ttu-id="aa3c8-155">Klicken Sie mit der rechten Maustaste auf den Namen der SIP-Domäne, und klicken Sie dann auf **Neuer Host (A oder AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-155">Right-click the SIP domain name, and then click **New Host (A or AAAA)**.</span></span>

8.  <span data-ttu-id="aa3c8-156">Geben Sie im Feld **Name** den Hostnamen wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-156">In **Name**, type the host name as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-157">Geben Sie für einen internen DNS-Eintrag "lyncdiscoverinternal" als den Hostnamen für die interne AutoErmittlungdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-157">For an internal DNS record, type lyncdiscoverinternal as the host name for the internal Autodiscover Service URL.</span></span>
    
      - <span data-ttu-id="aa3c8-158">Geben Sie für einen externen DNS-Eintrag "lyncdiscover" als den Hostnamen für die externe AutoErmittlungdienst-URL ein.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-158">For an external DNS record, type lyncdiscover as the host name for the external Autodiscover Service URL.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="aa3c8-159">Der Domänenname wird von der Zone abgeleitet, in welcher der Eintrag definiert ist, und muss daher nicht als Teil des A-Eintrags eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-159">The domain name is assumed from the zone in which the record is defined and, therefore, does not need to be entered as part of the A record.</span></span>

    
    </div>

9.  <span data-ttu-id="aa3c8-160">Geben Sie im Feld **IP-Adresse** die IP-Adresse wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="aa3c8-160">In **IP Address**, type the IP address as follows:</span></span>
    
      - <span data-ttu-id="aa3c8-161">Geben Sie für einen internen DNS-Eintrag die interne Webdienste-IP-Adresse des Directors ein (oder geben Sie bei Verwendung eines Lastenausgleichs die virtuelle IP (VIP) des Director-Lastenausgleichs) ein.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-161">For an internal DNS record, type the internal Web Services IP address of the Director (or, if you use a load balancer, type the virtual IP (VIP) of the Director load balancer).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="aa3c8-162">Wenn Sie keinen Director verwenden, geben Sie die IP-Adresse des Front-End-Server oder Standard Edition-Server ein, oder geben Sie bei Verwendung eines Lastenausgleichs den VIP des Front-End-Pool Lastenausgleichs ein.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-162">If you do not use a Director, type the IP address of the Front End Server or Standard Edition server, or, if you use a load balancer, type the VIP of the Front End pool load balancer.</span></span>

        
        </div>
    
      - <span data-ttu-id="aa3c8-163">Geben Sie für einen externen DNS-Eintrag die externe oder öffentliche IP-Adresse des Reverseproxys ein.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-163">For an external DNS record, type the external or public IP address of the reverse proxy.</span></span>

10. <span data-ttu-id="aa3c8-164">Klicken Sie auf **Host hinzufügen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-164">Click **Add Host**, and then click **OK**.</span></span>

11. <span data-ttu-id="aa3c8-165">Wenn Sie einen zusätzlichen A-Eintrag erstellen möchten, wiederholen Sie die Schritte 8 bis 10.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-165">To create an additional A record, repeat steps 8 through 10.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aa3c8-166">Sie müssen eine neue lyncdiscover erstellen und "lyncdiscoverinternal" eine Datensätze in der Forward-Lookupzone jeder SIP-Domäne, die Sie in ihrer lync Server 2013 Umgebung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-166">You must create a new lyncdiscover and lyncdiscoverinternal A records in the forward lookup zone of each SIP domain that you support in your Lync Server 2013 environment.</span></span>

    
    </div>

12. <span data-ttu-id="aa3c8-167">Klicken Sie auf **Fertig**, wenn Sie das Erstellen von A-Einträgen (für IPv6, AAAA) abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="aa3c8-167">When you are finished creating A (for IPv6, AAAA) records, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

