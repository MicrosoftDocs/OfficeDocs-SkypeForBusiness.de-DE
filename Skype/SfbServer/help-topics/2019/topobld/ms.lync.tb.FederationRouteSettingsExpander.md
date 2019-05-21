---
title: Einstellungen für die Partnerverbundroute – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Einrichten einer Standort Verbund-Routenzuordnung müssen Sie zuerst den Verbund auf dem Edgeserver oder Edgeserver-Pool aktivieren. Wenn der Verbund auf dem Edgeserver oder Pool nicht aktiviert ist, stehen die Zuordnungseinstellungen für die Verbund Route für die Website nicht zur Änderung zur Verfügung.
ms.openlocfilehash: 6e68bc7cb2f5a9f04e208dc2f27ce7724aa7e793
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292724"
---
# <a name="federation-route-settings-expander"></a><span data-ttu-id="cb1d0-104">Einstellungen für die Partnerverbundroute – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="cb1d0-104">Federation Route Settings Expander</span></span>
 
<span data-ttu-id="cb1d0-105">Zum Einrichten einer Standort Verbund-Routenzuordnung müssen Sie zuerst den Verbund auf dem Edgeserver oder Edgeserver-Pool aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-105">To set a site federation route assignment, you must first have federation enabled on the Edge Server or Edge Server pool.</span></span> <span data-ttu-id="cb1d0-106">Wenn der Verbund auf dem Edgeserver oder Pool nicht aktiviert ist, stehen die Zuordnungseinstellungen für die Verbund Route für die Website nicht zur Änderung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-106">If federation is not enabled on the Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="cb1d0-107">Wenn die Verbund Einstellung auf dem Edgeserver oder Pool konfiguriert wurde, können Sie die folgenden Optionen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="cb1d0-107">If the federation setting at the Edge Server or pool has been configured, you can configure the following options:</span></span> 
  
- <span data-ttu-id="cb1d0-108">**Zuordnungen von Verbund Routen zu allen Websites zulassen** Diese Einstellung wirkt sich auf alle Websites aus.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-108">**Allow federation route assignments to all sites** This setting will affect all sites.</span></span> <span data-ttu-id="cb1d0-109">Stellen Sie sicher, dass die Einstellungen, die Sie auf dieser Website konfigurieren, für alle Websites geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-109">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>
    
- <span data-ttu-id="cb1d0-110">**SIP-Verbund aktivieren** Wählen Sie diese Option aus, um eine SIP-Föderations Route zu aktivieren, und wählen Sie dann einen Director oder einen Edge-Pool als Verbund Route aus.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-110">**Enable SIP federation** Select this option to enable a SIP federation route, and then select a Director or Edge pool as the federation route.</span></span>
    
- <span data-ttu-id="cb1d0-111">**Aktivieren der XMPP-Föderation** Wählen Sie diese Option aus, um eine XMPP-Föderations Route zu aktivieren, und wählen Sie dann einen Director oder einen Edge-Pool als Verbund Route aus.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-111">**Enable XMPP federation** Select this option to enable an XMPP federation route, and then select a Director or Edge pool as the federation route.</span></span>
- 
  > [!NOTE]
  > <span data-ttu-id="cb1d0-112">XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb1d0-112">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="cb1d0-113">Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="cb1d0-113">See [Migrating XMPP federation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span>
    

