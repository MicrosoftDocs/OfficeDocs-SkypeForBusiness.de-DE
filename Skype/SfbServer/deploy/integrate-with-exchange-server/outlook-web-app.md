---
title: Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Zusammenfassung: Integrieren von Skype für Business Server und Outlook Web App.'
ms.openlocfilehash: 4ac4d6a71f8006e813d09631f8ccf28742940ff2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-2015-and-outlook-web-app"></a><span data-ttu-id="615ac-103">Konfigurieren der Integration zwischen lokalen Skype für Business Server 2015 und Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="615ac-103">Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App</span></span>
 
<span data-ttu-id="615ac-104">**Zusammenfassung:** Integrieren von Skype für Business Server und Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="615ac-104">**Summary:** Integrate Skype for Business Server and Outlook Web App.</span></span>
  
<span data-ttu-id="615ac-105">Kunden, die für die Business Server 2015 Bereitstellungen lokalen Skype verwenden können Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online in einer hybriden Bereitstellung-Modus konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="615ac-105">Customers who are using on-premises Skype for Business Server 2015 deployments can configure interoperability with Microsoft Outlook Web App in Microsoft Exchange Online in a hybrid deployment mode.</span></span> <span data-ttu-id="615ac-106">Zu den Interoperabilitätsfunktionen gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="615ac-106">Interoperability features include single sign on and instant messaging (IM) and presence integration with the Outlook Web App interface.</span></span> <span data-ttu-id="615ac-107">Um diese Integration aktivieren, müssen Sie den Edge-Server in Ihrer lokalen Skype für Business Server-Bereitstellung konfigurieren, durch die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="615ac-107">To enable this integration, you must configure the Edge Server in your on-premises Skype for Business Server deployment by completing the following tasks:</span></span> 
  
- <span data-ttu-id="615ac-108">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="615ac-108">Configure a shared SIP address space</span></span>
    
- <span data-ttu-id="615ac-109">Konfigurieren eines Hostinganbieters auf dem Edge-Server</span><span class="sxs-lookup"><span data-stu-id="615ac-109">Configure a hosting provider on the Edge Server</span></span>
    
- <span data-ttu-id="615ac-110">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="615ac-110">Verify replication of the updated Central Management store</span></span>
    
## <a name="configure-a-shared-sip-address-space"></a><span data-ttu-id="615ac-111">Konfigurieren eines freigegebenen SIP-Adressraums</span><span class="sxs-lookup"><span data-stu-id="615ac-111">Configure a Shared SIP Address Space</span></span>

<span data-ttu-id="615ac-112">Um lokale Skype für Business Server 2015 mit Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="615ac-112">To integrate on-premises Skype for Business Server 2015 with Exchange Online, you must configure a shared SIP address space.</span></span> <span data-ttu-id="615ac-113">Demselben Adressraum für SIP-Domäne wird von Skype für Business Server und Exchange Online-Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="615ac-113">The same SIP domain address space is supported by both Skype for Business Server and the Exchange Online service.</span></span>
  
<span data-ttu-id="615ac-114">Verwenden die Skype als Business Server-Verwaltungsshell, Konfigurieren der Edge-Server für den Verbund durch das **Set-CSAccessEdgeConfiguration** -Cmdlet mit den im folgenden Beispiel angezeigten Parametern ausführen:</span><span class="sxs-lookup"><span data-stu-id="615ac-114">Using the Skype for Business Server Management Shell, configure the Edge Server for federation by running the **Set-CSAccessEdgeConfiguration** cmdlet, using the parameters displayed in the following example:</span></span>
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- <span data-ttu-id="615ac-115">**AllowFederatedUsers** -Parameter gibt an, ob interne Benutzer zur Kommunikation mit Benutzern von Partnerdomänen zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="615ac-115">**AllowFederatedUsers** parameter specifies whether internal users are allowed to communicate with users from federated domains.</span></span> <span data-ttu-id="615ac-116">Diese Eigenschaft bestimmt zudem, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adresse Speicherplatz Szenario mit Skype für Business Server und Exchange Online kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="615ac-116">This property also determines whether internal users can communicate with users in a shared SIP address space scenario with Skype for Business Server and Exchange Online.</span></span>
    
<span data-ttu-id="615ac-117">Weitere Informationen zur Verwendung der Skype für Business Server-Verwaltungsshell finden Sie unter [Skype für Business Server 2015-Verwaltungsshell](../../manage/management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="615ac-117">For details about using the Skype for Business Server Management Shell, see [Skype for Business Server 2015 Management Shell](../../manage/management-shell.md).</span></span>
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="615ac-118">Konfigurieren eines Hostinganbieters auf dem Edgeserver</span><span class="sxs-lookup"><span data-stu-id="615ac-118">Configure a Hosting Provider on the Edge Server</span></span>

<span data-ttu-id="615ac-119">Konfigurieren Sie mit der Skype für Business Server-Verwaltungsshell, einen Hostinganbieter auf dem Edgeserver durch das **New-CsHostingProvider** -Cmdlet mit den Parametern im folgenden Beispiel ausführen:</span><span class="sxs-lookup"><span data-stu-id="615ac-119">Using the Skype for Business Server Management Shell, configure a hosting provider on the Edge Server by running the **New-CsHostingProvider** cmdlet, using the parameters in the following example:</span></span>
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> <span data-ttu-id="615ac-120">Wenn Sie Office 365 über 21Vianet in China nutzen, ersetzen Sie den Wert für den Parameter **ProxyFqdn** in diesem Beispiel („exap.um.outlook.com“) mit dem FQDN für den Dienst, der in China von 21Vianet bereitgestellt wird: „exap.um.partner.outlook.cn“.</span><span class="sxs-lookup"><span data-stu-id="615ac-120">If you are using Office 365 operated by 21Vianet in China, replace the value for the **ProxyFqdn** parameter in this example ("exap.um.outlook.com") with the FQDN for the service operated by 21Vianet: "exap.um.partner.outlook.cn".</span></span>
  
- <span data-ttu-id="615ac-121">**Identität** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter, den Sie erstellen (z. B. "Exchange Online").</span><span class="sxs-lookup"><span data-stu-id="615ac-121">**Identity** specifies a unique string value identifier for the hosting provider that you are creating (for example, "Exchange Online").</span></span> <span data-ttu-id="615ac-122">Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="615ac-122">Values that contain spaces must be in double quotes.</span></span>
    
- <span data-ttu-id="615ac-123">**Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="615ac-123">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="615ac-124">Dieser Parameter muss auf TRUE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="615ac-124">This must be set to True.</span></span>
    
- <span data-ttu-id="615ac-125">**EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem freigegebenen SIP-Adresse Speicherplatz Szenario verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="615ac-125">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="615ac-126">Dieser Parameter muss auf TRUE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="615ac-126">This must be set to True.</span></span>
    
- <span data-ttu-id="615ac-127">**HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Skype für Business Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="615ac-127">**HostsOCSUsers** indicates whether the hosting provider is used to host Office Communications Server or Skype for Business Server.</span></span> <span data-ttu-id="615ac-128">Dieser Parameter muss auf FALSE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="615ac-128">This must be set to False.</span></span>
    
- <span data-ttu-id="615ac-129">**ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) für die vom Hostinganbieter verwendete Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="615ac-129">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="615ac-130">Für Exchange Online ist der FQDN „exap.um.outlook.com“.</span><span class="sxs-lookup"><span data-stu-id="615ac-130">For Exchange Online, the FQDN is exap.um.outlook.com.</span></span>
    
- <span data-ttu-id="615ac-131">**IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype für Business Server-Topologie enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="615ac-131">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="615ac-132">Dieser Parameter muss auf FALSE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="615ac-132">This must be set to False.</span></span>
    
- <span data-ttu-id="615ac-133">**"Verificationlevel"** Gibt die Überprüfung zulässig für Nachrichten, die an und von der gehosteten Anbieter gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="615ac-133">**VerificationLevel** Indicates the verification level allowed for messages that are sent to and from the hosted provider.</span></span> <span data-ttu-id="615ac-134">Geben Sie **"usesourceverification"**, die den Überprüfungsstufen Hostinganbieter gesendeten Nachrichten enthalten benötigt.</span><span class="sxs-lookup"><span data-stu-id="615ac-134">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="615ac-135">Wenn dieser Ebene nicht angegeben ist, wird die Meldung als nicht überprüfbar abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="615ac-135">If this level is not specified, the message will be rejected as being unverifiable.</span></span>
    
## <a name="verify-replication-of-the-updated-central-management-store"></a><span data-ttu-id="615ac-136">Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers</span><span class="sxs-lookup"><span data-stu-id="615ac-136">Verify Replication of the Updated Central Management Store</span></span>

<span data-ttu-id="615ac-137">Die mithilfe der Cmdlets in den vorherigen Abschnitten vorgenommenen Änderungen werden automatisch auf dem Edge-Server angewendet, und im Allgemeinen zum Replizieren von weniger als eine Minute dauern.</span><span class="sxs-lookup"><span data-stu-id="615ac-137">The changes you made by using the cmdlets in the preceding sections are automatically applied to the Edge Server, and generally take less than a minute to replicate.</span></span> <span data-ttu-id="615ac-138">Sie können überprüfen Sie den Replikationsstatus, und stellen dann sicher, dass die Änderungen an den Edge-Server mithilfe der folgenden Cmdlets angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="615ac-138">You can validate replication status, and then confirm that the changes were applied to your Edge Server by using the following cmdlets.</span></span>
  
<span data-ttu-id="615ac-139">Führen Sie zum Überprüfen der Replikation-Updates auf einem Server in Ihrer Skype für Business Server-Bereitstellung das folgende Cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="615ac-139">To verify replication updates, on a server internal in your Skype for Business Server deployment, run the following cmdlet:</span></span>
  
```
Get-CsManagementStoreReplicationStatus
```

<span data-ttu-id="615ac-140">Führen Sie das folgende Cmdlet aus, um zu bestätigen, dass die Änderungen auf dem Edgeserver angewendet wurden:</span><span class="sxs-lookup"><span data-stu-id="615ac-140">To confirm that the changes were applied, on the Edge Server, run the following cmdlet:</span></span>
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a><span data-ttu-id="615ac-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="615ac-141">See also</span></span>

#### 

[<span data-ttu-id="615ac-142">Bereitstellen von Skype für Business Server 2015 Voicemail Benutzer-auf gehostete Exchange um-Dienste</span><span class="sxs-lookup"><span data-stu-id="615ac-142">Providing Skype for Business Server 2015 users voice mail on hosted Exchange UM</span></span>](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[<span data-ttu-id="615ac-143">Gehostete Exchange Unified Messaging Integration in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="615ac-143">Hosted Exchange Unified Messaging integration in Skype for Business Server 2015</span></span>](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)

