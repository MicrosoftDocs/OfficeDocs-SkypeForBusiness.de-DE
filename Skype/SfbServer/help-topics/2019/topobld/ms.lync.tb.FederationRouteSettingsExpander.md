---
title: Einstellungen für die Partnerverbundroute – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Wenn eine Zuweisung der partnerverbundroute Route festlegen möchten, müssen Sie zuerst den Verbund aktiviert werden, auf dem Edge-Server oder Pool für Edge-Server verfügen. Wenn auf dem Edge-Server oder Pool nicht den Verbund aktiviert ist, werden die Federation Route Zuordnung Einstellungen für die Website nicht geändert.
ms.openlocfilehash: 49709f5c4a91e25efb14cc4b2c321c99fec89b68
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873338"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="c9922-104">Einstellungen für die Partnerverbundroute – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="c9922-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="c9922-105">Wenn eine Zuweisung der partnerverbundroute Route festlegen möchten, müssen Sie zuerst den Verbund aktiviert werden, auf dem Edge-Server oder Pool für Edge-Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="c9922-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="c9922-106">Wenn auf dem Edge-Server oder Pool nicht den Verbund aktiviert ist, werden die Federation Route Zuordnung Einstellungen für die Website nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="c9922-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="c9922-107">Wenn die partnerverbundeinstellung für den Edge-Server oder Pool konfiguriert wurde, können Sie die folgenden Optionen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="c9922-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="c9922-108">**Zulassen Federation Route Zuordnungen für alle Websites** Diese Einstellung wirkt sich auf alle Websites.</span><span class="sxs-lookup"><span data-stu-id="c9922-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="c9922-109">Stellen Sie sicher, dass die Einstellung, die Sie an diesem Standort konfigurieren für alle Websites geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="c9922-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="c9922-110">**SIP-Partnerverbund aktivieren** Wählen Sie diese Option, um eine SIP-partnerverbundroute zu aktivieren, und wählen Sie dann einen Director- oder Edgepool als partnerverbundroute.</span><span class="sxs-lookup"><span data-stu-id="c9922-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="c9922-111">**Aktivieren von XMPP-Verbund** Wählen Sie diese Option, um eine XMPP-partnerverbundroute zu aktivieren, und wählen Sie dann einen Director- oder Edgepool als partnerverbundroute.</span><span class="sxs-lookup"><span data-stu-id="c9922-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="c9922-112">XMPP-Gateways und -Proxys werden stehen in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="c9922-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="c9922-113">Weitere Informationen finden Sie unter [Migrieren von XMPP-Verbund](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="c9922-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

