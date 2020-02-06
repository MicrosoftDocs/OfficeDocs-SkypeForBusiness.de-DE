---
title: Einstellungen für die Partnerverbundroute – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Einrichten einer Standort Verbund-Routenzuordnung müssen Sie zuerst den Verbund auf dem Edgeserver oder Edgeserver-Pool aktivieren. Wenn der Verbund auf dem Edgeserver oder Pool nicht aktiviert ist, stehen die Zuordnungseinstellungen für die Verbund Route für die Website nicht zur Änderung zur Verfügung.
ms.openlocfilehash: fafc576e3fd3a3c33d17728437c8472eaf1a57e9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793693"
---
# <a name="federation-route-settings-expander"></a>Einstellungen für die Partnerverbundroute – Erweiterung
 
Zum Einrichten einer Standort Verbund-Routenzuordnung müssen Sie zuerst den Verbund auf dem Edgeserver oder Edgeserver-Pool aktivieren. Wenn der Verbund auf dem Edgeserver oder Pool nicht aktiviert ist, stehen die Zuordnungseinstellungen für die Verbund Route für die Website nicht zur Änderung zur Verfügung.

Wenn die Verbund Einstellung auf dem Edgeserver oder Pool konfiguriert wurde, können Sie die folgenden Optionen konfigurieren: 
  
- **Zuordnungen von Verbund Routen zu allen Websites zulassen** Diese Einstellung wirkt sich auf alle Websites aus. Stellen Sie sicher, dass die Einstellungen, die Sie auf dieser Website konfigurieren, für alle Websites geeignet sind.
    
- **SIP-Verbund aktivieren** Wählen Sie diese Option aus, um eine SIP-Föderations Route zu aktivieren, und wählen Sie dann einen Director oder einen Edge-Pool als Verbund Route aus.
    
- **Aktivieren der XMPP-Föderation** Wählen Sie diese Option aus, um eine XMPP-Föderations Route zu aktivieren, und wählen Sie dann einen Director oder einen Edge-Pool als Verbund Route aus.
- 
  > [!NOTE]
  > XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    

