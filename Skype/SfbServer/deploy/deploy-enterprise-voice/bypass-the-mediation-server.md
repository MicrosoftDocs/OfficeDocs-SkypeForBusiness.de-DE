---
title: Konfigurieren der medienumgehung in Skype für Business Server 2015 zum dauerhaften Umgehung des Vermittlungsservers
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Aktivieren Sie die medienumgehung auf immer Umgehung des Vermittlungsservers in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: d7a80d9fb0365dde437f10696b13262f8667addf
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a><span data-ttu-id="dcdc1-103">Konfigurieren der medienumgehung in Skype für Business Server 2015 zum dauerhaften Umgehung des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="dcdc1-103">Configure media bypass in Skype for Business Server 2015 to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="dcdc1-104">Aktivieren Sie die medienumgehung auf immer Umgehung des Vermittlungsservers in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="dcdc1-105">Wenn Sie die Schritte in diesem Thema zum Konfigurieren der globaler Einstellungen für Medien umgehen, wird davon ausgegangen, dass Sie gute Verbindung zwischen Skype für Business-Endpunkte und alle Peer für die medienumgehung für die trunkverbindung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="dcdc1-106">Wenn Sie keine gute Verbindung zwischen Skype für Business-Endpunkte und alle Peers an den Vermittlungsserver, deren jeweiligen trunkverbindungen für die medienumgehung aktiviert wurden, müssen Sie Einstellungen für globale die medienumgehung Verwendung von Website und Regionsinformationen konfigurieren. Wenn Sie die medienumgehung verwenden.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="dcdc1-107">Dies ermöglicht mehr Kontrolle bei der Bestimmung, wenn Medien für den Vermittlungsserver umgeht.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="dcdc1-108">Zu diesem Zweck verwenden Sie stattdessen die Schritte unter [Configure Media bypass global Settings in Skype für Business Server 2015 Standorten und Regionen verwenden](use-site-and-region-information.md) and [ein Subnetz einem Netzwerkstandort zuzuordnen](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="dcdc1-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server 2015 to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="dcdc1-109">So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="dcdc1-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="dcdc1-110">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="dcdc1-111">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="dcdc1-112">Doppelklicken Sie in der Liste auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="dcdc1-113">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="dcdc1-114">Klicken Sie auf **Immer umgehen**.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="dcdc1-115">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="dcdc1-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="dcdc1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcdc1-116">See also</span></span>

#### 

[<span data-ttu-id="dcdc1-117">Planen Sie für die medienumgehung in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="dcdc1-117">Plan for media bypass in Skype for Business 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="dcdc1-118">Bereitstellen von medienumgehung in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dcdc1-118">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

