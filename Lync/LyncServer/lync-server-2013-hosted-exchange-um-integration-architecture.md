---
title: 'Lync Server 2013: Architektur für die Integration gehosteter Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="436f2-102">Architektur für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="436f2-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="436f2-103">_**Letztes Änderungsdatum des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="436f2-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="436f2-104">Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in eine lokale Exchange Unified Messaging (um)-Bereitstellung, wobei Exchange um von einem Dienstanbieter gehostet wird oder mit einer Kombination der beiden.</span><span class="sxs-lookup"><span data-stu-id="436f2-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="436f2-105">Das folgende Diagramm zeigt alle drei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="436f2-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="436f2-106">**Integration in eine lokale Exchange um-Bereitstellung und zwei gehostete Exchange-Anbieter**</span><span class="sxs-lookup"><span data-stu-id="436f2-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="436f2-107">![Lokale lync Server Exchange um-Bereitstellung] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")</span><span class="sxs-lookup"><span data-stu-id="436f2-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="436f2-108">Die folgenden Modi werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="436f2-108">The following modes are supported:</span></span>

  - <span data-ttu-id="436f2-109">**Lokale Bereitstellung:** Lync Server 2013 und Exchange um sind beide auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="436f2-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="436f2-110">**Standortübergreifende Bereitstellung:** Lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum, gehostet.</span><span class="sxs-lookup"><span data-stu-id="436f2-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="436f2-111">**Gemischte Bereitstellung:** In ihrer lync Server 2013-Bereitstellung sind einige Benutzerpostfächer auf lokalen Exchange-Servern innerhalb Ihres Unternehmens und einige Postfächer in einem gehosteten Exchange-Dienst-Rechenzentrum verwaltet.</span><span class="sxs-lookup"><span data-stu-id="436f2-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="436f2-112">Die gemischte Bereitstellung kann während der Evaluierung und der schrittweisen Migration von Benutzern zu Hosted Exchange um eine Übergangslösung sowie eine dauerhafte Lösung verwendet werden, wenn Sie sich entscheiden, die Exchange-um-Dienste einiger Benutzer nach der Übertragung anderer Personen lokal zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="436f2-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="436f2-113">Freigegebener SIP-Adressraum</span><span class="sxs-lookup"><span data-stu-id="436f2-113">Shared SIP Address Space</span></span>

<span data-ttu-id="436f2-114">Um lync Server 2013 in eine lokale Exchange um-Bereitstellung zu integrieren, erteilen Sie die lync Server 2013-Berechtigung zum Lesen von Exchange um-Active Directory-Domänendienste-Objekten.</span><span class="sxs-lookup"><span data-stu-id="436f2-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="436f2-115">Dieser Ansatz funktioniert jedoch nicht für die Integration in Hosted Exchange um, da lync Server 2013 und Exchange um in getrennten Gesamtstrukturen installiert werden, die keine Vertrauensstellung zwischen Ihnen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="436f2-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="436f2-116">Zum Integrieren von lync Server 2013 in gehostete Exchange um müssen Sie einen *freigegebenen SIP-Adressraum*konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="436f2-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="436f2-117">In dieser Konfiguration steht derselbe SIP-Domänen Adressraum sowohl für lync Server 2013 als auch für den gehosteten Exchange um-Dienstanbieter zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="436f2-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="436f2-118">Die Verwendung des freigegebenen SIP-Adressraums ähnelt dem in einer standortübergreifenden lync Server 2013-Umgebung verwendeten Ansatz, bei dem einige Benutzer in der lokalen Bereitstellung verwaltet werden und einige in einer gehosteten Bereitstellung (wie lync Online) verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="436f2-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="436f2-119">Die SIP-Domäne wird zwischen ihnen aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="436f2-119">The SIP domain is split between them.</span></span> <span data-ttu-id="436f2-120">Wenn Sie lync Server 2013 mit Hosted Exchange um integrieren, stellen Sie sicher, dass Sie den Exchange um-Dienstanbieter in den freigegebenen SIP-Adressraum einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="436f2-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="436f2-121">Wenn Sie den freigegebenen SIP-Adressraum für die Integration in einen Exchange um-Dienstanbieter konfigurieren möchten, müssen Sie den Edgeserver wie folgt konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="436f2-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="436f2-122">Konfigurieren Sie den Edgeserver für Federation, indem Sie das Cmdlet " **festlegen-csaccessedgeconfiguration nicht angeben** " ausführen, um die folgenden Parameter einzurichten:</span><span class="sxs-lookup"><span data-stu-id="436f2-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="436f2-123">**UseDnsSrvRouting** gibt an, dass Edgeserver beim Senden und Empfangen von Partnerverbundanforderungen auf DNS-SRV-Einträge zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="436f2-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="436f2-p105">**AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft legt außerdem fest, ob interne Benutzer mit Benutzern in einem Szenario mit getrennten Domänen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="436f2-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="436f2-126">**EnablePartnerDiscovery** gibt an, ob lync Server 2013 DNS-Einträge verwendet, um zu versuchen, Partnerdomänen zu finden, die nicht in der Liste der zulässigen Domänen für Active Directory aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="436f2-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="436f2-127">Ist der Wert false, wird lync Server 2013 nur mit Domänen zusammen, die in der Liste zugelassene Domänen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="436f2-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="436f2-128">Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="436f2-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="436f2-129">In den meisten Bereitstellungen ist der Wert auf "False" gesetzt, um einen Partnerverbund mit allen Partnern zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="436f2-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="436f2-130">Replizieren Sie den zentralen Verwaltungsspeicher auf den Edgeserver, und überprüfen Sie die Replikation.</span><span class="sxs-lookup"><span data-stu-id="436f2-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="436f2-131">Ausführliche Informationen finden Sie unter [Exportieren Ihrer lync Server 2013-Topologie und Kopieren der Edge-Installation in externe Medien](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="436f2-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="436f2-132">Konfigurieren Sie einen *Hostinganbieter* auf dem Edgeserver, indem Sie das Cmdlet **New-CsHostingProvider** ausführen, um die folgenden Parameter einzurichten:</span><span class="sxs-lookup"><span data-stu-id="436f2-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="436f2-133">**Identity** gibt einen eindeutigen Zeichenfolgenwert Bezeichner für den Hostinganbieter an, den Sie erstellen, beispielsweise " **Hosted Exchange um**".</span><span class="sxs-lookup"><span data-stu-id="436f2-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="436f2-134">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="436f2-134">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="436f2-135">Muss auf " **true**" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="436f2-135">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="436f2-136">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="436f2-136">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="436f2-137">Muss auf " **true**" festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="436f2-137">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="436f2-138">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von lync Server 2013-Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="436f2-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="436f2-139">Muss auf " **false**" festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="436f2-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="436f2-140">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) für den vom Hostinganbieter verwendeten Proxy Server an, beispielsweise **Proxyserver.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="436f2-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="436f2-141">Wenden Sie sich für diese Informationen an Ihren Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="436f2-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="436f2-142">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="436f2-142">This value cannot be modified.</span></span> <span data-ttu-id="436f2-143">Wenn der Hostinganbieter seinen Proxy Server ändert, müssen Sie den Eintrag für diesen Anbieter löschen und dann erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="436f2-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="436f2-144">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server 2013-Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="436f2-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="436f2-145">Muss auf " **false**" festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="436f2-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

