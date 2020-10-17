---
title: Konfigurieren der lokalen lync Server Integration in Exchange Online
description: Konfigurieren der lokalen lync Server Integration in Exchange Online.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59c612bcdcdf4803bd6f9f2b38f1f9bb7dbad016
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553936"
---
# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a><span data-ttu-id="40ce9-103">Konfigurieren der lokalen lync Server 2013 Integration in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="40ce9-103">Configuring on-premises Lync Server 2013 integration with Exchange Online</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40ce9-104">_**Letztes Änderungsstand des Themas:** 2018-03-30_</span><span class="sxs-lookup"><span data-stu-id="40ce9-104">_**Topic Last Modified:** 2018-03-30_</span></span>

<span data-ttu-id="40ce9-105">Kunden, die lokale lync Server 2013-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online im Hybrid Bereitstellungsmodus konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="40ce9-105">Customers who are using on-premises Lync Server 2013 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="40ce9-106">Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="40ce9-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="40ce9-107">Um diese Integration zu ermöglichen, müssen Sie die Edgeserver in Ihrer lokalen lync Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="40ce9-107">To enable this integration, you must configure the Edge Server in your on-premises Lync Server deployment by completing the following tasks:</span></span>

  - <span data-ttu-id="40ce9-108">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="40ce9-108">Configure a shared SIP address space</span></span>

  - <span data-ttu-id="40ce9-109">Konfigurieren eines Host Anbieters im Edgeserver</span><span class="sxs-lookup"><span data-stu-id="40ce9-109">Configure a hosting provider on the Edge Server</span></span>

  - <span data-ttu-id="40ce9-110">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="40ce9-110">Verify replication of the updated Central Management store</span></span>

<span data-ttu-id="40ce9-111">Wenn lync Server 2013 in Exchange Online integriert ist, wird ein Benutzer, der sich bei OWA anmeldet, als ein Remote-oder externer Benutzer betrachtet.</span><span class="sxs-lookup"><span data-stu-id="40ce9-111">If Lync Server 2013 is integrated with Exchange Online, a user who is trying to sign in to IM from OWA is considered a remote or external user.</span></span> <span data-ttu-id="40ce9-112">In diesem Szenario muss dem Benutzer eine externe Zugriffsrichtlinie zugewiesen sein, für die die folgende Option ausgewählt ist:</span><span class="sxs-lookup"><span data-stu-id="40ce9-112">In this scenario, this user must have an external access policy assigned that has the following option selected:</span></span>

<span data-ttu-id="40ce9-113">**Aktivieren der Kommunikation mit Remotebenutzern**</span><span class="sxs-lookup"><span data-stu-id="40ce9-113">**Enable communications with remote users**</span></span>

<span data-ttu-id="40ce9-114">Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie etwa Telearbeiter und Benutzer, die sich auf Reisen befinden, eine Verbindung mit lync Server über das Internet herstellen können sollen.</span><span class="sxs-lookup"><span data-stu-id="40ce9-114">Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server over the Internet.</span></span>

<span data-ttu-id="40ce9-115">Weitere Informationen finden Sie unter [Verwalten von Richtlinien für den externen Zugriff in lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="40ce9-115">For more information, see [Manage external access policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).</span></span>

<div>

## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="40ce9-116">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="40ce9-116">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="40ce9-117">Um lokale lync Server 2013 mit Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="40ce9-117">To integrate on-premises Lync Server 2013 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="40ce9-118">Derselbe SIP-Domänen Adressraum wird sowohl von lync Server als auch vom Exchange Online Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="40ce9-118">The same SIP domain address space is supported by both Lync Server and the Exchange Online service.</span></span>

<span data-ttu-id="40ce9-119">Konfigurieren Sie mithilfe der lync Server-Verwaltungsshell den Edgeserver für den Verbund, indem Sie das Cmdlet " **csaccessedgeconfiguration nicht angeben** " mit den im folgenden Beispiel angezeigten Parametern ausführen:</span><span class="sxs-lookup"><span data-stu-id="40ce9-119">Using the Lync Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters that are displayed in the following example:</span></span>

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - <span data-ttu-id="40ce9-120">**AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="40ce9-120">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="40ce9-121">Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adressraum Szenario mit lync Server und Exchange Online kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="40ce9-121">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Lync Server and Exchange Online.</span></span>

<span data-ttu-id="40ce9-122">Ausführliche Informationen zur Verwendung des lync Server-Verwaltungsshell finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="40ce9-122">For details about how to use the Lync Server Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="40ce9-123">Konfigurieren eines Hostinganbieters auf dem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="40ce9-123">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="40ce9-124">Verwenden Sie die lync Server-Verwaltungsshell, um einen Hostinganbieter im Edgeserver zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="40ce9-124">Use the Lync Server Management Shell to configure a hosting provider on the Edge Server.</span></span> <span data-ttu-id="40ce9-125">Führen Sie dazu das Cmdlet **New-CsHostingProvider** mit den Parametern im folgenden Beispiel aus:</span><span class="sxs-lookup"><span data-stu-id="40ce9-125">To do this, run the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> <span data-ttu-id="40ce9-126">Wenn Sie Office 365 betrieben von 21Vianet in China verwenden, ersetzen Sie den Wert für den Parameter <STRONG>ProxyFqdn</STRONG> in diesem Beispiel ("exap.um.Outlook.com") durch den FQDN für den Dienst, der von 21Vianet verwaltet wird: "exap.um.Partner.Outlook.cn".</span><span class="sxs-lookup"><span data-stu-id="40ce9-126">If you are using Office 365 operated by 21Vianet in China, replace the value for the <STRONG>ProxyFqdn</STRONG> parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>



</div>

  - <span data-ttu-id="40ce9-127">**Identity** gibt einen eindeutigen Bezeichner für den Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="40ce9-127">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="40ce9-128">Werte, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-128">Values that contain spaces must be in double quotation marks.</span></span>

  - <span data-ttu-id="40ce9-129">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="40ce9-129">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="40ce9-130">Dies muss auf **true**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-130">This must be set to **True**.</span></span>

  - <span data-ttu-id="40ce9-131">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40ce9-131">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="40ce9-132">Dies muss auf **true**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-132">This must be set to **True**.</span></span>

  - <span data-ttu-id="40ce9-133">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder lync Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40ce9-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Lync Server.</span></span> <span data-ttu-id="40ce9-134">Dies muss auf **false**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-134">This must be set to **False**.</span></span>

  - <span data-ttu-id="40ce9-135">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an.</span><span class="sxs-lookup"><span data-stu-id="40ce9-135">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="40ce9-136">Für Exchange Online ist der FQDN "exap.um.outlook.com".</span><span class="sxs-lookup"><span data-stu-id="40ce9-136">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>

  - <span data-ttu-id="40ce9-137">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="40ce9-137">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span> <span data-ttu-id="40ce9-138">Dies muss auf **false**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-138">This must be set to **False**.</span></span>

  - <span data-ttu-id="40ce9-139">**"Verificationlevel"** gibt die zulässige Überprüfungsebene für Nachrichten an, die vom gehosteten Anbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-139">**VerificationLevel** indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="40ce9-140">Geben Sie **UseSourceVerification**an.</span><span class="sxs-lookup"><span data-stu-id="40ce9-140">Specify **UseSourceVerification**.</span></span> <span data-ttu-id="40ce9-141">Diese Option beruht auf der Überprüfungsebene, die in Nachrichten enthalten ist, die vom Hostinganbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-141">This option relies on the verification level that is included in messages that are sent from the hosting provider.</span></span> <span data-ttu-id="40ce9-142">Wenn diese Ebene nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="40ce9-142">If this level is not specified, the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="40ce9-143">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="40ce9-143">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="40ce9-144">Die Änderungen, die Sie mit den Cmdlets in den vorhergehenden Abschnitten vorgenommen haben, werden automatisch auf die Edgeserver angewendet und dauern in der Regel weniger als eine Minute, um repliziert zu werden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-144">The changes that you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than one minute to replicate.</span></span> <span data-ttu-id="40ce9-145">Sie können den Replikationsstatus überprüfen und die Änderungen mithilfe der folgenden Cmdlets auf Ihre Edgeserver anwenden.</span><span class="sxs-lookup"><span data-stu-id="40ce9-145">You can verify the replication status and that the changes were applied to your Edge Server by using the following cmdlets.</span></span>

<span data-ttu-id="40ce9-146">Führen Sie das folgende Cmdlet aus, um Replikationsupdates auf einem internen Server in ihrer lync Server-Bereitstellung zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="40ce9-146">To verify replication updates on a server internal in your Lync Server deployment, run the following cmdlet:</span></span>

    Get-CsManagementStoreReplicationStatus

<span data-ttu-id="40ce9-147">Führen Sie das folgende Cmdlet auf dem Edgeserver aus, um sicherzustellen, dass die Änderungen übernommen wurden:</span><span class="sxs-lookup"><span data-stu-id="40ce9-147">To verify that the changes were applied, run the following cmdlet on the Edge Server:</span></span>

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40ce9-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40ce9-148">See Also</span></span>


[<span data-ttu-id="40ce9-149">Bereitstellen von Voicemail für lync Server 2013-Benutzer in gehosteten Exchange um</span><span class="sxs-lookup"><span data-stu-id="40ce9-149">Providing Lync Server 2013 users voice mail on hosted Exchange UM</span></span>](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[<span data-ttu-id="40ce9-150">Hosted Exchange Unified Messaging-Integration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40ce9-150">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
