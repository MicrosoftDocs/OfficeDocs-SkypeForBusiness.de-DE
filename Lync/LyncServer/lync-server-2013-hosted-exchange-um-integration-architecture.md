---
title: 'Lync Server 2013: Hosted Exchange um Integration Architecture'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb0e195b10f5c368e2b12d2dfdc00be0fa1b3da2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="14c3f-102">Gehostete Exchange um Integrationsarchitektur in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14c3f-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14c3f-103">_**Letztes Änderungsstand des Themas:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="14c3f-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="14c3f-104">Die lync Server 2013 ExUM-Routing Anwendung unterstützt die Integration in eine lokale Exchange Unified Messaging (um)-Bereitstellung, wobei Exchange um von einem Dienstanbieter gehostet wird, oder mit einer Kombination aus beiden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="14c3f-105">Im nachfolgenden Diagramm werden alle drei Möglichkeiten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="14c3f-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="14c3f-106">**Integration in eine Umgebung mit lokaler Exchange UM-Bereitstellung und zwei Anbietern für gehostete Exchange-Dienste**</span><span class="sxs-lookup"><span data-stu-id="14c3f-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="14c3f-107">![Lokale lync Server Exchange um-Bereitstellung](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Lokale lync Server Exchange um-Bereitstellung")</span><span class="sxs-lookup"><span data-stu-id="14c3f-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="14c3f-108">Die folgenden Modi werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="14c3f-108">The following modes are supported:</span></span>

  - <span data-ttu-id="14c3f-109">**Lokale Bereitstellung:** Lync Server 2013 und Exchange um werden auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="14c3f-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="14c3f-110">**Standortübergreifende Bereitstellung:** Lync Server 2013 wird auf lokalen Servern innerhalb Ihres Unternehmens bereitgestellt, und Exchange um wird in der Einrichtung eines Onlinedienstanbieters gehostet, beispielsweise in einem Microsoft Exchange Online-Rechenzentrum.</span><span class="sxs-lookup"><span data-stu-id="14c3f-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="14c3f-111">**Gemischte Bereitstellung:** Bei ihrer lync Server 2013-Bereitstellung befinden sich einige Benutzerpostfächer auf lokalen Exchange-Servern innerhalb Ihres Unternehmens und einige Postfächer, die in einem gehosteten Exchange-Dienst Datencenter verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14c3f-112">Die gemischte Bereitstellung kann als Übergangslösung bei der Evaluierung und bei einer in Phasen durchgeführten Migration von Benutzern zu gehosteten Exchange UM-Diensten oder als dauerhafte Lösung eingesetzt werden, wenn Sie einige Exchange UM-Dienste nach der Migration weiterhin lokal verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="14c3f-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="14c3f-113">Freigegebener SIP-Adressraum</span><span class="sxs-lookup"><span data-stu-id="14c3f-113">Shared SIP Address Space</span></span>

<span data-ttu-id="14c3f-114">Zum Integrieren von lync Server 2013 in eine lokale Exchange um-Bereitstellung erteilen Sie lync Server 2013 Berechtigung zum Lesen Exchange um Active Directory-Domänendienste-Objekten.</span><span class="sxs-lookup"><span data-stu-id="14c3f-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="14c3f-115">Diese Vorgehensweise funktioniert jedoch nicht für die Integration in gehostete Exchange um, da lync Server 2013 und Exchange um in getrennten Gesamtstrukturen installiert werden, ohne dass diese vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="14c3f-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="14c3f-116">Um lync Server 2013 mit gehosteten Exchange um zu integrieren, müssen Sie einen *freigegebenen SIP-Adressraum*konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="14c3f-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="14c3f-117">In dieser Konfiguration ist derselbe SIP-Domänen Adressraum sowohl für lync Server 2013 als auch für den gehosteten Exchange um Dienstanbieter verfügbar.</span><span class="sxs-lookup"><span data-stu-id="14c3f-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="14c3f-118">Die Verwendung des freigegebenen SIP-Adressraums ähnelt dem in einer standortübergreifenden lync Server 2013 Umgebung verwendeten Ansatz, bei dem einige Benutzer in der lokalen Bereitstellung verwaltet werden und einige in einer gehosteten Bereitstellung (beispielsweise lync Online) verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="14c3f-119">Die SIP-Domäne wird zwischen den Umgebungen aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="14c3f-119">The SIP domain is split between them.</span></span> <span data-ttu-id="14c3f-120">Wenn Sie lync Server 2013 mit gehosteten Exchange um integrieren, stellen Sie sicher, dass Sie den Exchange um Dienstanbieter in den freigegebenen SIP-Adressraum einschließen.</span><span class="sxs-lookup"><span data-stu-id="14c3f-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="14c3f-121">Zum Konfigurieren des freigegebenen SIP-Adressraums für die Integration in eine Umgebung mit einem Exchange UM-Dienstanbieter müssen Sie Ihren Edgeserver folgendermaßen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="14c3f-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="14c3f-122">Konfigurieren Sie den Edgeserver für den Partnerverbund, indem Sie mit dem **Set-CsAccessEdgeConfiguration**-Cmdlet die folgenden Parameter festlegen:</span><span class="sxs-lookup"><span data-stu-id="14c3f-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="14c3f-123">**UseDnsSrvRouting** gibt an, dass Edgeserver beim Senden und Empfangen von Partnerverbundanforderungen auf DNS-SRV-Einträge zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="14c3f-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="14c3f-p105">**AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft legt außerdem fest, ob interne Benutzer mit Benutzern in einem Szenario mit getrennten Domänen kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="14c3f-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="14c3f-126">**EnablePartnerDiscovery** gibt an, ob lync Server 2013 DNS-Einträge verwenden, um Partnerdomänen zu ermitteln, die nicht in der Liste zugelassene Domänen Active Directory aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="14c3f-127">Wenn false, werden lync Server 2013 nur mit Domänen zusammenfassen, die in der Liste zugelassene Domänen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="14c3f-128">Dieser Parameter ist für die Verwendung von DNS-Dienstrouting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="14c3f-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="14c3f-129">In den meisten Bereitstellungen ist der Wert auf "False" gesetzt, um einen Partnerverbund mit allen Partnern zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="14c3f-130">Replizieren Sie den zentralen Verwaltungsspeicher in den Edgeserver, und überprüfen Sie die Replikation.</span><span class="sxs-lookup"><span data-stu-id="14c3f-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="14c3f-131">Ausführliche Informationen finden Sie unter [Exportieren Ihrer lync Server 2013 Topologie und Kopieren dieser auf externe Medien für die Edge-Installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="14c3f-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="14c3f-132">Konfigurieren Sie einen *Hostinganbieter* auf dem Edgeserver, indem Sie mit dem Cmdlet **New-CsHostingProvider** die folgenden Parameter festlegen:</span><span class="sxs-lookup"><span data-stu-id="14c3f-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="14c3f-133">**Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen, beispielsweise **Hosted Exchange UM**.</span><span class="sxs-lookup"><span data-stu-id="14c3f-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="14c3f-p108">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf **True** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="14c3f-p109">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf **True** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-p109">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="14c3f-138">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von lync Server 2013 Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="14c3f-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="14c3f-139">Dieser Parameter muss auf **False** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="14c3f-140">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an, z. B. **proxyserver.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="14c3f-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="14c3f-141">Sie erhalten diese Information von Ihrem Hostinganbieter.</span><span class="sxs-lookup"><span data-stu-id="14c3f-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="14c3f-142">Dieser Wert kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-142">This value cannot be modified.</span></span> <span data-ttu-id="14c3f-143">Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="14c3f-144">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server 2013 Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="14c3f-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="14c3f-145">Dieser Parameter muss auf **False** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="14c3f-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

