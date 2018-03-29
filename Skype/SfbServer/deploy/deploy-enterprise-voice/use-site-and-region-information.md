---
title: Konfigurieren von globalen Einstellungen für die medienumgehung in Skype für Business Server 2015 Standorten und Regionen verwenden
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Konfigurieren der medienumgehung nur für bestimmte Standorte und Regionen in Skype für Business Server Enterprise-VoIP verwendet werden.
ms.openlocfilehash: cebfa9d416fe3e68cd5615ae11616707ba1f60a8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-2015-to-use-site-and-region-information"></a><span data-ttu-id="cb96b-103">Konfigurieren von globalen Einstellungen für die medienumgehung in Skype für Business Server 2015 Standorten und Regionen verwenden</span><span class="sxs-lookup"><span data-stu-id="cb96b-103">Configure media bypass global settings in Skype for Business Server 2015 to use site and region information</span></span>
 
<span data-ttu-id="cb96b-104">Konfigurieren der medienumgehung nur für bestimmte Standorte und Regionen in Skype für Business Server Enterprise-VoIP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb96b-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="cb96b-105">Wenn Sie die Schritte in diesem Thema zum Konfigurieren der globaler Einstellungen für Medien umgehen, wird davon ausgegangen, dass Sie keine gute Verbindung zwischen allen Skype für Business-Endpunkte und alle Peer für die medienumgehung für die trunkverbindung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="cb96b-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cb96b-p101">Die Informationen zu Netzwerkregionen und Netzwerkstandorten werden sowohl für die Anrufsteuerung als auch für die Medienumgehung verwendet, wenn beide der erweiterten Enterprise-VoIP-Funktionen aktiviert sind. Wenn Sie daher die Anrufsteuerung bereits konfiguriert haben, müssen Sie das folgende Verfahren zum Bearbeiten von Standort- und Regioneninformationen nicht speziell für die Medienumgehung ausführen. Führen Sie die Schritte des folgenden Verfahrens aus, wenn Sie noch keine Netzwerkregionen und Standorte für die Anrufsteuerung konfiguriert haben und die Einstellungen für die Medienumgehung ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="cb96b-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="cb96b-109">Vorhanden für die medienumgehung für die Verwendung ordnungsgemäß muss sein Konsistenz zwischen einer Website gemäß Definition im Topologie-Generator, und wie sie beim Konfigurieren von netzwerkregionen und Netzwerkstandorte definiert ist.</span><span class="sxs-lookup"><span data-stu-id="cb96b-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="cb96b-110">Beispielsweise bei einer Zweigniederlassung, die Sie im Topologie-Generator definiert, dass haben nur ein PSTN-Gateway bereitgestellt, und klicken Sie dann, Zweigstellenstandort muss konfiguriert werden, mit einer Enterprise-VoIP-Richtlinie, mit die Benutzer des zweigstellenstandorts ihre PSTN-Anrufe über das PSTN weitergeleitet werden können Gateway am Zweigstellenstandort.</span><span class="sxs-lookup"><span data-stu-id="cb96b-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="cb96b-111">So konfigurieren Sie Informationen zu Standorten und Regionen für die Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="cb96b-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="cb96b-112">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cb96b-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="cb96b-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cb96b-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="cb96b-114">Doppelklicken Sie in der Tabelle auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="cb96b-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="cb96b-115">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="cb96b-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="cb96b-116">Klicken Sie auf **Standort- und Regionskonfiguration verwenden**.</span><span class="sxs-lookup"><span data-stu-id="cb96b-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="cb96b-117">Falls erforderlich, aktivieren Sie das Kontrollkästchen **Umgehung für nicht zugeordnete Standorte aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="cb96b-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cb96b-p103">Aktivieren Sie dieses Kontrollkästchen nur, wenn Sie über einen oder mehrere große Standorte ohne Bandbreiteneinschränkungen verfügen (z. B. ein großer Hauptstandort), die einer bestimmten Region zugeordnet sind, und Sie außerdem über einige Zweigniederlassungen mit Bandbreiteneinschränkungen verfügen, die derselben Region zugeordnet sind. Wenn Sie die Umgehung für nicht zugeordnete Standorte aktivieren, wird die Konfiguration optimiert, da Sie nur die den Zweigniederlassungen zugeordneten Subnetze angeben, statt sämtliche, allen Standorten zugeordnete Subnetze angeben zu müssen. Es wird empfohlen, dieses Kontrollkästchen nicht zu aktivieren, wenn die Anrufsteuerung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="cb96b-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="cb96b-121">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cb96b-121">Click **Commit**.</span></span>
    
<span data-ttu-id="cb96b-p104">Fügen Sie anschließend Subnetze zum Netzwerkstandort hinzu, wie unter [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) beschrieben. Nachdem Sie alle Subnetze zu Netzwerkstandorten zugeordnet haben, ist die Bereitstellung der Medienumgehung abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cb96b-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="cb96b-124">Wenn Sie noch keine Netzwerkregionen und Netzwerkstandorte erstellt haben, müssen Sie dies nachholen, bevor Sie mit der Bereitstellung der Medienumgehung fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="cb96b-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="cb96b-125">Weitere Informationen hierzu finden Sie unter [Bereitstellen von netzwerkregionen, Standorten und Subnetze in Skype für Business 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="cb96b-125">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cb96b-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb96b-126">See also</span></span>

#### 

[<span data-ttu-id="cb96b-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="cb96b-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

