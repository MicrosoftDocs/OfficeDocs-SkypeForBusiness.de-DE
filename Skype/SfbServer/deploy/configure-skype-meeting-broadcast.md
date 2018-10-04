---
title: Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Zusammenfassung: Erfahren Sie mehr über die Schritte, die Sie zum Konfigurieren von Skype Besprechung übertragen für Ihre lokale Skype für Business Server hybridbereitstellung ausführen müssen.'
ms.openlocfilehash: bae25dae268dd5ad3b3ab7862feb1156df850953
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371394"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="56369-103">Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz</span><span class="sxs-lookup"><span data-stu-id="56369-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="56369-104">**Zusammenfassung:** Informationen Sie zu den Schritten, die Sie zum Konfigurieren von Skype Besprechung übertragen für Ihre lokale Skype für Business Server hybridbereitstellung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="56369-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="56369-105">Skype Besprechung übertragen ist ein Onlinedienst, der Teil von Office 365 ist.</span><span class="sxs-lookup"><span data-stu-id="56369-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="56369-106">Wenn Sie Skype für Business Server lokal ausgeführt werden und Skype Besprechung übertragen in Ihrer Umgebung verwenden möchten, müssen Sie die Konfiguration Schritte in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="56369-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="56369-107">Bevor Sie beginnen, muss Ihre Umgebung für hybride mit Skype für Business Online konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="56369-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="56369-108">Weitere Informationen finden Sie unter [hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online planen](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) und [Bereitstellen von hybridkonnektivität zwischen Skype für Business Server und Skype für Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="56369-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="56369-109">Konfigurieren der hybridumgebung für Skype Besprechung übertragen</span><span class="sxs-lookup"><span data-stu-id="56369-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="56369-110">Sie müssen Folgendes tun, um die Vorbereitung Ihrer Umgebung Skype Besprechung übertragen werden:</span><span class="sxs-lookup"><span data-stu-id="56369-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="56369-111">Konfigurieren des Verbunds mit Skype für Business Onlineressourcen</span><span class="sxs-lookup"><span data-stu-id="56369-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="56369-112">Konfigurieren von SIP-Partnerverbunddomänen</span><span class="sxs-lookup"><span data-stu-id="56369-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="56369-113">Konfigurieren des Verbunds mit Skype für Business Onlineressourcen</span><span class="sxs-lookup"><span data-stu-id="56369-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="56369-114">Um den Verbund mit Skype für Business Onlineressourcen zu aktivieren, müssen Sie für einen SIP-Partnerverbundanbieter externen Zugriff konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="56369-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="56369-115">Hierzu dies mithilfe der Skype für Business Server-Systemsteuerung gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="56369-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="56369-116">Starten Sie die Skype für Business Server-Systemsteuerung, und wählen Sie **Externen Zugriff** auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="56369-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="56369-117">Wählen Sie **SIP-Partnerverbundanbieter** und klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="56369-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="56369-118">Konfigurieren Sie den neuen Anbieter mit den folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="56369-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="56369-119">**Aktivieren Sie Kommunikation mit diesem Anbieter:**</span><span class="sxs-lookup"><span data-stu-id="56369-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="56369-120">Ausgewählt</span><span class="sxs-lookup"><span data-stu-id="56369-120">Selected</span></span>  <br/> |
|<span data-ttu-id="56369-121">**Anbietername:**</span><span class="sxs-lookup"><span data-stu-id="56369-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="56369-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="56369-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="56369-123">**Zugriffs-Edgedienst (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="56369-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="56369-124">sipfed.Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="56369-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="56369-125">**Standardüberprüfungsstufe:**</span><span class="sxs-lookup"><span data-stu-id="56369-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="56369-126">Benutzern die Kommunikation mit jedem erlauben, der diesen Anbieter verwendet</span><span class="sxs-lookup"><span data-stu-id="56369-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="56369-127">Sie können auch mit Skype-Verbund für Business Onlineressourcen aktivieren, indem Sie das folgende Cmdlet in der Skype für Business Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="56369-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="56369-128">Konfigurieren von SIP-Partnerverbunddomänen</span><span class="sxs-lookup"><span data-stu-id="56369-128">Configure SIP federated domains</span></span>

<span data-ttu-id="56369-129">Im nächsten Schritt müssen Sie SIP Federated Domains die Liste der zulässigen Domänen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="56369-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="56369-130">Wiederholen Sie diese Schritte für alle aufgeführten Domänen und erstellen Sie so vier neue SIP-Partnerverbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="56369-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="56369-131">Diese Domänen enthalten sind für die regionalen Daten verwendeten in Skype für Business Online zentriert.</span><span class="sxs-lookup"><span data-stu-id="56369-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="56369-132">Starten Sie die Skype für Business Server-Systemsteuerung, und wählen Sie **Externen Zugriff** auf der linken Seite.</span><span class="sxs-lookup"><span data-stu-id="56369-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="56369-133">Wählen Sie **SIP-Partnerverbunddomänen** und klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="56369-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="56369-134">Geben Sie als **Domänenname (oder FQDN):** die Domäne ein und wiederholen Sie diese Vorgehensweise für alle folgenden Domänen:</span><span class="sxs-lookup"><span data-stu-id="56369-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="56369-135">noammeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="56369-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="56369-136">emeameetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="56369-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="56369-137">apacmeetings.Lync.com</span><span class="sxs-lookup"><span data-stu-id="56369-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="56369-138">Resources.Lync.com</span><span class="sxs-lookup"><span data-stu-id="56369-138">resources.lync.com</span></span>
    
<span data-ttu-id="56369-139">Sie können auch den externen Zugriff für SIP-Verbund Domänen konfigurieren, indem Sie die folgenden Cmdlets in der Skype für Business Server-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="56369-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="56369-140">Wenn Sie diese Konfigurationsschritte abgeschlossen haben können Sie beginnen, in Ihrer Bereitstellung mit Skype Besprechung übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="56369-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="56369-141">Weitere Informationen zu Skype Besprechung übertragen werden, finden Sie unter [Was ist eine Skype Besprechung übertragen?](https://go.microsoft.com/fwlink/?LinkId=617071) und [Skype-Besprechung übertragen Administratorhandbuch](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="56369-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

