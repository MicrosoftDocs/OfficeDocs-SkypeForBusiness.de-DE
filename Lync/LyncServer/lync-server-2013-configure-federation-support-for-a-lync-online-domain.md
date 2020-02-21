---
title: 'Lync Server 2013: Konfigurieren der Verbundunterstützung für eine lync Online Domäne'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99c3dd2d1a8ea2027b7007d9a05a4c3ec8357a15
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="c8276-102">Konfigurieren der Verbundunterstützung für eine lync Online Domäne in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8276-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8276-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c8276-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c8276-104">Für die Zusammensetzung mit einem Microsoft lync Online 2010-Kunden müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="c8276-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="c8276-105">Konfigurieren Sie die Unterstützung für die Domäne des lync Online 2010-Kunden (beispielsweise contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="c8276-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="c8276-106">Wie im Abschnitt [Voraussetzungen für die Verbundfunktion mit einem lync Online Kunden in lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) dieser Dokumentation angegeben, sollten Sie den Partnerverbund für Ihre Organisation bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c8276-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="c8276-107">Zum Aktivieren des Partnerverbunds muss die Methode zur Steuerung des Zugriffs durch Partnerdomänen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c8276-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="c8276-108">Wenn in Ihrer Organisation die Ermittlung verwendet wird, kann die Domäne optional der Liste der zugelassenen Domänen Ihrer Organisation hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c8276-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="c8276-109">Wenn Sie die Domänen Ermittlung nicht aktiviert haben, müssen Sie den Domänennamen des lync Online Kunden der Liste der zugelassenen Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8276-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="c8276-110">Sie können einen Domänennamen entweder mithilfe von lync Server-Systemsteuerung oder durch Ausführen des Cmdlets **New-CSAllowedDomain** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c8276-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="c8276-111">Ausführliche Informationen zur Verwendung von lync Server-Systemsteuerung, einschließlich der Aktivierung der Suche von Domänen, finden Sie unter [Manage SIP Federated Providers for your organization in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8276-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="c8276-112">Ausführliche Informationen zur Verwendung des **New-CSAllowedDomain-** Cmdlets zum Hinzufügen einer Domäne finden Sie unter [New-CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8276-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8276-113">Ein lync Online Kunde kann mehrere Domänen haben.</span><span class="sxs-lookup"><span data-stu-id="c8276-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="c8276-114">Wenn Sie eine Föderation mit mehr als einer der Domänen durchsetzen möchten, müssen Sie die Unterstützung für jede einzelne Domäne konfigurieren, für die Sie den Partnerverbund unterstützen möchten, und der Administrator des lync Online-Kunden muss den Partnerverbund für jede der Domänen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c8276-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="c8276-115">Konfigurieren Sie die Unterstützung für den Hostinganbieter der lync Online 2010-Kundendomäne, mit der Sie einen Partnerverbund einrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="c8276-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="c8276-116">Verwenden Sie das Verfahren in diesem Abschnitt, um die Unterstützung für Hostinganbieter zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c8276-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8276-117">Dieser Schritt ist nur für den Verbund mit einer Domäne eines lync Online Kunden erforderlich, nicht für den Verbund mit einer Domäne, die lokal am Standort des Verbundpartners bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c8276-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="c8276-118">So konfigurieren Sie die Unterstützung für einen Hostinganbieter</span><span class="sxs-lookup"><span data-stu-id="c8276-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="c8276-119">Starten Sie in einem Front-End-Server das lync Server-Verwaltungsshell: Klicken Sie auf **Start**, auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="c8276-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="c8276-120">Führen Sie das Cmdlet **New-CsHostingProvider** aus, um den Hostinganbieter zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c8276-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="c8276-121">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c8276-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="c8276-122">Im oben stehenden Beispiel werden folgende Parameter festgelegt:</span><span class="sxs-lookup"><span data-stu-id="c8276-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="c8276-p105">**Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen. Beachten Sie, dass der Befehl nicht erfolgreich ist, wenn bereits ein Anbieter mit dieser Identität konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c8276-p105">**Identity** specifies a unique string value identifier for the hosting provider that you are creating. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="c8276-p106">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Dieser Wert kann nicht geändert werden. Wenn der Hostinganbieter seinen Proxyserver ändert, muss der Eintrag für diesen Anbieter gelöscht und neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c8276-p106">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="c8276-128">**VerificationLevel** gibt an, wie (oder ob) von einem Hostinganbieter gesendete Nachrichten überprüft werden, um sicherzustellen, dass sie tatsächlich von diesem Anbieter stammen.</span><span class="sxs-lookup"><span data-stu-id="c8276-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="c8276-p107">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Der Nachrichtenaustausch zwischen zwei Organisationen ist erst möglich, wenn dieser Wert auf **True** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c8276-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="c8276-131">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum (getrennte Domäne) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8276-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="c8276-132">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von lync Server Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c8276-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="c8276-133">Der Wert **False** gibt an, dass der Anbieter andere Kontotypen (z. B. Microsoft Exchange-Konten) hostet.</span><span class="sxs-lookup"><span data-stu-id="c8276-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="c8276-134">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c8276-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="c8276-135">Ausführliche Informationen zur Verwendung dieses Cmdlets finden Sie unter [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="c8276-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

