---
title: 'Lync Server 2013: DNS-Anforderungen für die automatische Clientanmeldung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b022d9780d1498f70fd5918894a1412996731004
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="71c98-102">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c98-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c98-103">_**Letztes Änderungsstand des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="71c98-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="71c98-104">In diesem Abschnitt wird erläutert, welche DNS-Einträge (Domain Name System) für die automatische Clientanmeldung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="71c98-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="71c98-105">Wenn Sie Standard Edition-Server oder Front-End-Pools bereitstellen, können Sie Ihre Clients zur automatischen Ermittlung von und Anmeldung am geeigneten Standard Edition-Server oder Front-End-Pool konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="71c98-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="71c98-106">Wenn Sie planen, dass Ihre Clients manuell mit lync Server 2013 eine Verbindung herstellen müssen, können Sie dieses Thema überspringen.</span><span class="sxs-lookup"><span data-stu-id="71c98-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="71c98-107">Zur Unterstützung der automatischen Clientanmeldung müssen Sie folgende Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="71c98-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="71c98-p102">Legen Sie einen einzelnen Server oder Pool für die Verteilung und Authentifizierung von Clientanmeldeanforderungen fest. Hierbei kann es sich um einen vorhandenen Server oder Pool handeln, der Benutzer hostet, oder Sie können zu diesem Zweck einen dedizierten Server oder Pool zuweisen, der keine Benutzer hostet. Um eine hohe Verfügbarkeit sicherzustellen, wird empfohlen, einen Front-End-Pool für diese Funktion zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="71c98-p102">Designate a single server or pool to distribute and authenticate client sign-in requests. This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users. For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="71c98-111">Erstellen Sie einen internen DNS-SRV-Eintrag zur Unterstützung der automatischen Clientanmeldung für diesen Server oder Pool.</span><span class="sxs-lookup"><span data-stu-id="71c98-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="71c98-p103">In den folgenden Eintragsanforderungen bezieht sich die SIP-Domäne auf den Hostabschnitt der SIP-URIs, die Benutzern zugewiesen sind. Wenn die SIP-URIs beispielsweise das Format "\*@contoso.com" aufweisen, bezeichnet "contoso.com" die SIP-Domäne. Die SIP-Domäne unterscheidet sich häufig von der internen Active Directory-Domäne. In einer Organisation können auch mehrere SIP-Domänen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="71c98-p103">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users. For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain. The SIP domain is often different from the internal Active Directory domain. An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="71c98-116">Um die automatische Konfiguration für Ihre Clients zu aktivieren, müssen Sie einen internen DNS-SRV-Eintrag erstellen, der einen der folgenden Einträge dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pool oder Standard Edition-Server zuordnet, der Anmeldeanforderungen von lync verteilt. Clients</span><span class="sxs-lookup"><span data-stu-id="71c98-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="71c98-117">\_sipinternaltls. \_TCP. \<Domäne\> – für interne TLS-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="71c98-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="71c98-118">Sie müssen für den Front-End-Pool oder Standard Edition-Server, der die Anmeldeanforderungen verteilt, nur einen einzigen SRV-Eintrag erstellen.</span><span class="sxs-lookup"><span data-stu-id="71c98-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="71c98-119">Die folgende Tabelle enthält einige der erforderlichen Beispieleinträge für das fiktive Unternehmen Contoso, das die SIP-Domänen "contoso.com" und "retail.contoso.com" unterstützt.</span><span class="sxs-lookup"><span data-stu-id="71c98-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="71c98-120">Beispiele für erforderliche DNS-Einträge für die automatische Clientanmeldung bei mehreren SIP-Domänen</span><span class="sxs-lookup"><span data-stu-id="71c98-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71c98-121">FQDN des Front-End-Pools für die Verteilung von Anmeldeanforderungen</span><span class="sxs-lookup"><span data-stu-id="71c98-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="71c98-122">SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="71c98-122">SIP domain</span></span></th>
<th><span data-ttu-id="71c98-123">DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="71c98-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c98-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71c98-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="71c98-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="71c98-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="71c98-126">Ein SRV-Eintrag für die Domäne "_sipinternaltls._tcp.contoso.com" über Port 5061, der "pool01.contoso.com" zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="71c98-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c98-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71c98-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="71c98-128">retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="71c98-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="71c98-129">Ein SRV-Eintrag für die Domäne "_sipinternaltls._tcp.retail.contoso.com" über Port 5061, der "pool01.contoso.com" zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="71c98-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="71c98-130">In der Standardeinstellung müssen bei Abfragen für DNS-Einträge die Domänennamen im Benutzernamen und im SRV-Eintrag genau übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="71c98-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="71c98-131">Wenn bei DNS-Abfragen des Clients stattdessen die Suffixe verglichen werden sollen, können Sie die Gruppenrichtlinie "DisableStrictDNSNaming" konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="71c98-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="71c98-132">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for Clients and Devices in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="71c98-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="71c98-133">Beispiele für erforderliche Zertifikate und DNS-Einträge für die automatische Clientanmeldung</span><span class="sxs-lookup"><span data-stu-id="71c98-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="71c98-p105">In diesem Beispiel werden dieselben Beispiele wie in der oben gezeigten Tabelle verwendet. Das Unternehmen Contoso unterstützt die SIP-Domänen "contoso.com" und "retail.contoso.com", und alle Benutzer des Unternehmens verfügen über einen SIP-URI in einem der folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="71c98-p105">This example uses the same example names in the preceding table. The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="71c98-136">\<Benutzer\>@Retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="71c98-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="71c98-137">\<Benutzer\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="71c98-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

