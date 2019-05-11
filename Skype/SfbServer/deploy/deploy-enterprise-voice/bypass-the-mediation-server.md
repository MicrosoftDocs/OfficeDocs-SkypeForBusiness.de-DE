---
title: Konfigurieren der medienumgehung in Skype für Business Server zum dauerhaften Umgehung des Vermittlungsservers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Aktivieren Sie die medienumgehung auf immer Umgehung des Vermittlungsservers in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: ffefeb9850915f4ac8e4677f1bcf0202c4f29405
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893140"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="053d9-103">Konfigurieren der medienumgehung in Skype für Business Server zum dauerhaften Umgehung des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="053d9-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="053d9-104">Aktivieren Sie die medienumgehung auf immer Umgehung des Vermittlungsservers in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="053d9-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="053d9-105">Wenn Sie die Schritte in diesem Thema zum Konfigurieren der globaler Einstellungen für Medien umgehen, wird davon ausgegangen, dass Sie gute Verbindung zwischen Skype für Business-Endpunkte und alle Peer für die medienumgehung für die trunkverbindung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="053d9-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="053d9-106">Wenn Sie keine gute Verbindung zwischen Skype für Business-Endpunkte und alle Peers an den Vermittlungsserver, deren jeweiligen trunkverbindungen für die medienumgehung aktiviert wurden, müssen Sie Einstellungen für globale die medienumgehung Verwendung von Website und Regionsinformationen konfigurieren. Wenn Sie die medienumgehung verwenden.</span><span class="sxs-lookup"><span data-stu-id="053d9-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="053d9-107">Dies ermöglicht mehr Kontrolle bei der Bestimmung, wenn Medien für den Vermittlungsserver umgeht.</span><span class="sxs-lookup"><span data-stu-id="053d9-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="053d9-108">Zu diesem Zweck verwenden Sie stattdessen die Schritte unter [Configure Media bypass global Settings in Skype für Business Server der Standorte und Regionen verwenden](use-site-and-region-information.md) and [ein Subnetz einem Netzwerkstandort zuzuordnen](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="053d9-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="053d9-109">So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="053d9-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="053d9-110">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="053d9-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="053d9-111">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="053d9-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="053d9-112">Doppelklicken Sie in der Liste auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="053d9-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="053d9-113">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="053d9-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="053d9-114">Klicken Sie auf **Immer umgehen**.</span><span class="sxs-lookup"><span data-stu-id="053d9-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="053d9-115">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="053d9-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="053d9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="053d9-116">See also</span></span>

[<span data-ttu-id="053d9-117">Planen der medienumgehung in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="053d9-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="053d9-118">Die medienumgehung in Skype für Business Server bereitstellen</span><span class="sxs-lookup"><span data-stu-id="053d9-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

