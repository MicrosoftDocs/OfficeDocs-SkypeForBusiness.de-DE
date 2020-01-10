---
title: Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Zusammenfassung: erfahren Sie mehr über die Schritte, die Sie ausführen müssen, um Skype-Live Konferenz für Ihre lokale Skype for Business Server-hybridbereitstellung zu konfigurieren.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002805"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="c91d9-103">Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz</span><span class="sxs-lookup"><span data-stu-id="c91d9-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="c91d9-104">**Zusammenfassung:** Informieren Sie sich über die Schritte, die Sie ausführen müssen, um Skype-Live Konferenz für Ihre lokale Skype for Business Server-hybridbereitstellung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c91d9-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="c91d9-105">Skype-Live Konferenz ist ein Onlinedienst, der Teil von Office 365 ist.</span><span class="sxs-lookup"><span data-stu-id="c91d9-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="c91d9-106">Wenn Sie Skype for Business Server lokal ausführen und die Skype-Live Konferenz in Ihrer Umgebung verwenden möchten, müssen Sie die Konfigurationsschritte in diesem Thema befolgen.</span><span class="sxs-lookup"><span data-stu-id="c91d9-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="c91d9-107">Bevor Sie beginnen, muss Ihre Umgebung für hybride mit Skype for Business Online konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="c91d9-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="c91d9-108">Weitere Informationen finden Sie unter [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) und [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="c91d9-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="c91d9-109">Konfigurieren der Hybridumgebung für Skype-Live Konferenz</span><span class="sxs-lookup"><span data-stu-id="c91d9-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="c91d9-110">Sie müssen die folgenden Schritte ausführen, um Ihre Umgebung für die Skype-Live Konferenz vorzubereiten:</span><span class="sxs-lookup"><span data-stu-id="c91d9-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="c91d9-111">Konfigurieren des Verbunds mit Skype for Business Online-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c91d9-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="c91d9-112">Konfigurieren von SIP-Partnerverbunddomänen</span><span class="sxs-lookup"><span data-stu-id="c91d9-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="c91d9-113">Konfigurieren des Verbunds mit Skype for Business Online-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c91d9-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="c91d9-114">Um die Föderation mit Skype for Business Online-Ressourcen zu aktivieren, müssen Sie den externen Zugriff für einen SIP-Verbund Anbieter konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c91d9-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="c91d9-115">Führen Sie dazu die folgenden Schritte aus, indem Sie das Skype for Business Server Control Panel verwenden:</span><span class="sxs-lookup"><span data-stu-id="c91d9-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="c91d9-116">Starten Sie die Skype for Business Server-Systemsteuerung, und wählen Sie auf der linken Seite **externen Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="c91d9-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="c91d9-117">Wählen Sie **SIP-Partnerverbundanbieter** und klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="c91d9-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="c91d9-118">Konfigurieren Sie den neuen Anbieter mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c91d9-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="c91d9-119">**Aktivieren der Kommunikation mit diesem Anbieter:**</span><span class="sxs-lookup"><span data-stu-id="c91d9-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="c91d9-120">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="c91d9-120">Selected</span></span>  <br/> |
|<span data-ttu-id="c91d9-121">**Anbietername:**</span><span class="sxs-lookup"><span data-stu-id="c91d9-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="c91d9-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="c91d9-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="c91d9-123">**Zugriffs-Edgedienst (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="c91d9-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="c91d9-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="c91d9-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="c91d9-125">**Standardüberprüfungsstufe:**</span><span class="sxs-lookup"><span data-stu-id="c91d9-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="c91d9-126">Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet</span><span class="sxs-lookup"><span data-stu-id="c91d9-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="c91d9-127">Sie können auch den Verbund mit Skype for Business Online-Ressourcen aktivieren, indem Sie in der Skype for Business Server-Verwaltungsshell das folgende Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="c91d9-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="c91d9-128">Konfigurieren von SIP-Partnerverbunddomänen</span><span class="sxs-lookup"><span data-stu-id="c91d9-128">Configure SIP federated domains</span></span>

<span data-ttu-id="c91d9-129">Als nächstes müssen Sie SIP-Verbunddomänen zur Liste der zulässigen Domänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c91d9-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="c91d9-130">Wiederholen Sie diese Schritte für alle aufgeführten Domänen und erstellen Sie so vier neue SIP-Partnerverbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="c91d9-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="c91d9-131">Zu diesen Domänen gehören die regionalen Rechenzentren, die in Skype for Business Online verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c91d9-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="c91d9-132">Starten Sie die Skype for Business Server-Systemsteuerung, und wählen Sie auf der linken Seite **externen Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="c91d9-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="c91d9-133">Wählen Sie **SIP-Partnerverbunddomänen** und klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="c91d9-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="c91d9-134">Geben Sie als **Domänenname (oder FQDN):** die Domäne ein und wiederholen Sie diese Vorgehensweise für alle folgenden Domänen:</span><span class="sxs-lookup"><span data-stu-id="c91d9-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="c91d9-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c91d9-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="c91d9-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c91d9-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="c91d9-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c91d9-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="c91d9-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="c91d9-138">resources.lync.com</span></span>
    
<span data-ttu-id="c91d9-139">Sie können den externen Zugriff für SIP-Verbunddomänen auch konfigurieren, indem Sie die folgenden Cmdlets in der Skype for Business Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="c91d9-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="c91d9-140">Nachdem Sie diese Konfigurationsschritte abgeschlossen haben, können Sie Skype-Live Konferenz in Ihrer Bereitstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="c91d9-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="c91d9-141">Weitere Informationen zu Skype-Live Konferenz finden Sie unter [Was ist eine Skype-Live Konferenz?](https://go.microsoft.com/fwlink/?LinkId=617071) und [Skype-Live Konferenz-Administratorhandbuch](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="c91d9-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

