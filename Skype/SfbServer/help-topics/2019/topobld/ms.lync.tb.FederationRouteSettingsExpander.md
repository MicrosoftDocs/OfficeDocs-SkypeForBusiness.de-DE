---
title: Federation Route Einstellungen – Erweiterung
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
ms.openlocfilehash: 989ebd13e4491e7b4c28bb936795f9532d7fe88f
ms.sourcegitcommit: 905ba61de9622dd485ff375fa75bb0d76bac0b55
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "22196041"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="dd939-104">Federation Route Einstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="dd939-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="dd939-105">Wenn eine Zuweisung der partnerverbundroute Route festlegen möchten, müssen Sie zuerst den Verbund aktiviert werden, auf dem Edge-Server oder Pool für Edge-Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="dd939-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="dd939-106">Wenn auf dem Edge-Server oder Pool nicht den Verbund aktiviert ist, werden die Federation Route Zuordnung Einstellungen für die Website nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="dd939-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="dd939-107">Wenn die partnerverbundeinstellung für den Edge-Server oder Pool konfiguriert wurde, können Sie die folgenden Optionen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="dd939-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="dd939-108">**Zulassen Federation Route Zuordnungen für alle Websites** Diese Einstellung wirkt sich auf alle Websites.</span><span class="sxs-lookup"><span data-stu-id="dd939-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="dd939-109">Stellen Sie sicher, dass die Einstellung, die Sie an diesem Standort konfigurieren für alle Websites geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="dd939-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="dd939-110">**SIP-Partnerverbund aktivieren** Wählen Sie diese Option, um eine SIP-partnerverbundroute zu aktivieren, und wählen Sie dann einen Director- oder Edgepool als partnerverbundroute.</span><span class="sxs-lookup"><span data-stu-id="dd939-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="dd939-111">**Aktivieren von XMPP-Verbund** Wählen Sie diese Option, um eine XMPP-partnerverbundroute zu aktivieren, und wählen Sie dann einen Director- oder Edgepool als partnerverbundroute.</span><span class="sxs-lookup"><span data-stu-id="dd939-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
> [!NOTE]
> <span data-ttu-id="dd939-112">XMPP-Gateways und -Proxys werden stehen in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype für Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dd939-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="dd939-113">Weitere Informationen finden Sie unter [Migrieren von XMPP-Verbund](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="dd939-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

