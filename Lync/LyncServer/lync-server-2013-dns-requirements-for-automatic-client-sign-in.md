---
title: 'Lync Server 2013: DNS-Anforderungen für die automatische Clientanmeldung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afd8ac315222a5582bde9802c22ab7b4911ddfe3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a><span data-ttu-id="a7d59-102">DNS-Anforderungen für die automatische Clientanmeldung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7d59-102">DNS requirements for automatic client sign-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7d59-103">_**Letztes Änderungsdatum des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="a7d59-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="a7d59-104">In diesem Abschnitt werden die DNS-Einträge (Domain Name System) erläutert, die für die automatische Clientanmeldung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a7d59-104">This section explains the Domain Name System (DNS) records that are required for automatic client sign-in.</span></span> <span data-ttu-id="a7d59-105">Wenn Sie Ihre Standard Edition-Server oder Front-End-Pools bereitstellen, können Sie Ihre Clients so konfigurieren, dass die automatische Ermittlung für die Anmeldung beim entsprechenden Standard Edition-Server oder Front-End-Pool verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a7d59-105">When you deploy your Standard Edition servers or Front End pools, you can configure your clients to use automatic discovery to sign in to the appropriate Standard Edition server or Front End pool.</span></span> <span data-ttu-id="a7d59-106">Wenn Sie planen, dass Ihre Clients eine Verbindung mit lync Server 2013 manuell herstellen müssen, können Sie dieses Thema überspringen.</span><span class="sxs-lookup"><span data-stu-id="a7d59-106">If you plan to require your clients to connect manually to Lync Server 2013, you can skip this topic.</span></span>

<span data-ttu-id="a7d59-107">Um die automatische Clientanmeldung zu unterstützen, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="a7d59-107">To support automatic client sign-in, you must:</span></span>

  - <span data-ttu-id="a7d59-108">Festlegen eines einzelnen Servers oder Pools zum Verteilen und Authentifizieren von Clientanmeldeanforderungen</span><span class="sxs-lookup"><span data-stu-id="a7d59-108">Designate a single server or pool to distribute and authenticate client sign-in requests.</span></span> <span data-ttu-id="a7d59-109">Hierbei kann es sich um einen vorhandenen Server oder Pool in Ihrer Organisation handeln, der Benutzer hostet, oder Sie können einen dedizierten Server oder Pool für diesen Zweck festlegen, der keine Benutzer hostet.</span><span class="sxs-lookup"><span data-stu-id="a7d59-109">This can be an existing server or pool in your organization that hosts users, or you can designate a dedicated server or pool for this purpose that hosts no users.</span></span> <span data-ttu-id="a7d59-110">Für eine höhere Verfügbarkeit empfehlen wir, einen Front-End-Pool für diese Funktion festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a7d59-110">For high availability, we recommend that you designate a Front End pool for this function.</span></span>

  - <span data-ttu-id="a7d59-111">Erstellen Sie einen internen DNS-SRV-Eintrag, um die automatische Clientanmeldung für diesen Server oder Pool zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a7d59-111">Create an internal DNS SRV record to support automatic client sign-in for this server or pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a7d59-112">In den folgenden Daten Satz Anforderungen bezieht sich die SIP-Domäne auf den Hostbereich der SIP-URIs, die Benutzern zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a7d59-112">In the following record requirements, SIP domain refers to the host portion of the SIP URIs assigned to users.</span></span> <span data-ttu-id="a7d59-113">Wenn beispielsweise SIP-URIs die Form \* @contoso. com aufweisen, ist contoso.com die SIP-Domäne.</span><span class="sxs-lookup"><span data-stu-id="a7d59-113">For example, if SIP URIs are of the form \*@contoso.com, contoso.com is the SIP domain.</span></span> <span data-ttu-id="a7d59-114">Die SIP-Domäne unterscheidet sich häufig von der internen Active Directory-Domäne.</span><span class="sxs-lookup"><span data-stu-id="a7d59-114">The SIP domain is often different from the internal Active Directory domain.</span></span> <span data-ttu-id="a7d59-115">Eine Organisation kann auch mehrere SIP-Domänen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a7d59-115">An organization can also support multiple SIP domains.</span></span>

    
    </div>

<span data-ttu-id="a7d59-116">Wenn Sie die automatische Konfiguration für Ihre Clients aktivieren möchten, müssen Sie einen internen DNS-SRV-Eintrag erstellen, der einen der folgenden Einträge dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Front-End-Pools oder Standard Edition-Servers zuordnet, der Anmeldeanforderungen von lync verteilt. Clients</span><span class="sxs-lookup"><span data-stu-id="a7d59-116">To enable automatic configuration for your clients, you must create an internal DNS SRV record that maps one of the following records to the fully qualified domain name (FQDN) of the Front End pool or Standard Edition server that distributes sign-in requests from Lync clients:</span></span>

  - <span data-ttu-id="a7d59-117">\_sipinternaltls. \_TCP. \<Domäne\> – für interne TLS-Verbindungen</span><span class="sxs-lookup"><span data-stu-id="a7d59-117">\_sipinternaltls.\_tcp.\<domain\> - for internal TLS connections</span></span>

<span data-ttu-id="a7d59-118">Sie müssen nur einen einzelnen SRV-Eintrag für den Front-End-Pool oder Standard Edition-Server erstellen oder die Anmeldeanforderungen verteilen.</span><span class="sxs-lookup"><span data-stu-id="a7d59-118">You only need to create a single SRV record for the Front End pool or Standard Edition server or that will distribute sign-in requests.</span></span>

<span data-ttu-id="a7d59-119">In der folgenden Tabelle sind einige Beispieldatensätze aufgeführt, die für das fiktive Unternehmen Contoso erforderlich sind, das SIP-Domänen von contoso.com und Retail.contoso.com unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a7d59-119">The following table shows some example records required for the fictitious company Contoso, which supports SIP domains of contoso.com and retail.contoso.com.</span></span>

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a><span data-ttu-id="a7d59-120">Beispiel für DNS-Einträge, die für die automatische Client Anmeldung mit mehreren SIP-Domänen erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="a7d59-120">Example of DNS Records Required for Automatic Client Sign-in with Multiple SIP Domains</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7d59-121">FQDN des Front-End-Pools, der zum Verteilen von Anmeldeanforderungen verwendet wird</span><span class="sxs-lookup"><span data-stu-id="a7d59-121">FQDN of Front End pool used to distribute sign-in requests</span></span></th>
<th><span data-ttu-id="a7d59-122">SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="a7d59-122">SIP domain</span></span></th>
<th><span data-ttu-id="a7d59-123">DNS-SRV-Eintrag</span><span class="sxs-lookup"><span data-stu-id="a7d59-123">DNS SRV record</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7d59-124">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7d59-124">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a7d59-125">contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7d59-125">contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a7d59-126">Ein SRV-Eintrag für _sipinternaltls. _tcp. contoso. com-Domäne über Port 5061, der pool01.contoso.com zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="a7d59-126">An SRV record for _sipinternaltls._tcp.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7d59-127">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7d59-127">pool01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a7d59-128">Retail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7d59-128">retail.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="a7d59-129">Ein SRV-Eintrag für _sipinternaltls. _tcp. Retail. contoso. com-Domäne über Port 5061, der pool01.contoso.com zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="a7d59-129">An SRV record for _sipinternaltls._tcp.retail.contoso.com domain over port 5061 that maps to pool01.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a7d59-130">Standardmäßig befolgen Abfragen für DNS-Einträge den strikten Domänennamen Abgleich zwischen der Domäne im Benutzernamen und dem SRV-Eintrag.</span><span class="sxs-lookup"><span data-stu-id="a7d59-130">By default, queries for DNS records adhere to strict domain name matching between the domain in the user name and the SRV record.</span></span> <span data-ttu-id="a7d59-131">Wenn Sie es vorziehen, dass Client-DNS-Abfragen stattdessen Suffix-Abgleich verwenden, können Sie die DisableStrictDNSNaming-Gruppenrichtlinie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a7d59-131">If you prefer that client DNS queries use suffix matching instead, you can configure the DisableStrictDNSNaming Group Policy.</span></span> <span data-ttu-id="a7d59-132">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planen von Clients und Geräten in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a7d59-132">For details, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a><span data-ttu-id="a7d59-133">Beispiel für die für die automatische Client Anmeldung erforderlichen Zertifikate und DNS-Einträge</span><span class="sxs-lookup"><span data-stu-id="a7d59-133">Example of the Certificates and DNS Records Required for Automatic Client Sign-In</span></span>

<span data-ttu-id="a7d59-134">In diesem Beispiel werden die gleichen Beispiel Namen in der vorhergehenden Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7d59-134">This example uses the same example names in the preceding table.</span></span> <span data-ttu-id="a7d59-135">Die Contoso-Organisation unterstützt die SIP-Domänen von contoso.com und Retail.contoso.com, und alle Benutzer verfügen über einen SIP-URI in einem der folgenden Formate:</span><span class="sxs-lookup"><span data-stu-id="a7d59-135">The Contoso organization supports the SIP domains of contoso.com and retail.contoso.com, and all of its users have a SIP URI in one of the following forms:</span></span>

  - <span data-ttu-id="a7d59-136">\<Benutzer\>@Retail. contoso.com</span><span class="sxs-lookup"><span data-stu-id="a7d59-136">\<user\>@retail.contoso.com</span></span>

  - <span data-ttu-id="a7d59-137">\<Benutzer\>@contoso. com</span><span class="sxs-lookup"><span data-stu-id="a7d59-137">\<user\>@contoso.com</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

