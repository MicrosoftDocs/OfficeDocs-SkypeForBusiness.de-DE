---
title: Konfigurieren der medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: Aktivieren Sie die medienumgehung, um den Vermittlungsserver in Skype for Business Server Enterprise Voice immer zu umgehen.
ms.openlocfilehash: 0e45f8ede38411974f9433c17ccd0a0946b427ff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275878"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1a3e9-103">Konfigurieren der medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen</span><span class="sxs-lookup"><span data-stu-id="1a3e9-103">Configure media bypass in Skype for Business Server to always bypass the Mediation Server</span></span>
 
<span data-ttu-id="1a3e9-104">Aktivieren Sie die medienumgehung, um den Vermittlungsserver in Skype for Business Server Enterprise Voice immer zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-104">Enable media bypass to always bypass the Mediation Server in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="1a3e9-105">Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, besteht die Annahme, dass Sie über eine gute Verbindung zwischen den Endpunkten von Skype for Business und allen Peers verfügen, für die Sie die medienumgehung für die trunk-Verbindung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
<span data-ttu-id="1a3e9-106">Wenn Sie keine gute Verbindung zwischen Skype for Business-Endpunkten und allen Peers mit dem Vermittlungs Server haben, deren jeweilige trunk-Verbindungen für die medienumgehung aktiviert wurden, müssen Sie die globalen Einstellungen für die medienumgehung so konfigurieren, dass die Website-und Regionsinformationen verwendet werden. bei Verwendung der medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-106">If you do not have good connectivity between Skype for Business endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="1a3e9-107">Auf diese Weise können Sie festlegen, wann Medien den Vermittlungs Server umgeht.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-107">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="1a3e9-108">Führen Sie dazu die Schritte unter Konfigurieren der [globalen Einstellungen für medienumgehung in Skype for Business Server aus, um Website-und Regionsinformationen zu verwenden](use-site-and-region-information.md) und stattdessen [ein Subnetz mit einer Netzwerk Website zu verknüpfen](deploy-network.md#BKMK_AssociateSubnets) .</span><span class="sxs-lookup"><span data-stu-id="1a3e9-108">To do this, use the steps in [Configure media bypass global settings in Skype for Business Server to use site and region information](use-site-and-region-information.md) and [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) instead.</span></span>
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="1a3e9-109">So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="1a3e9-109">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1. <span data-ttu-id="1a3e9-110">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-110">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1a3e9-111">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-111">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1a3e9-112">Doppelklicken Sie in der Liste auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-112">Double-click the **Global** configuration in the list.</span></span>
    
4. <span data-ttu-id="1a3e9-113">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-113">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="1a3e9-114">Klicken Sie auf **Immer umgehen**.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-114">Click **Always bypass**.</span></span>
    
6. <span data-ttu-id="1a3e9-115">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1a3e9-115">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1a3e9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a3e9-116">See also</span></span>

[<span data-ttu-id="1a3e9-117">Planen der medienumgehung in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1a3e9-117">Plan for media bypass in Skype for Business</span></span>](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[<span data-ttu-id="1a3e9-118">Bereitstellen der medienumgehung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1a3e9-118">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

