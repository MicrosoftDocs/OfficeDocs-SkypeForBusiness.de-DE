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
ms.openlocfilehash: 201fa7b556cc3a12c422145cf46c844faafb1cb4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371781"
---
# <a name="federation-route-settings-expander"></a>Federation Route Einstellungen – Erweiterung
 
Wenn eine Zuweisung der partnerverbundroute Route festlegen möchten, müssen Sie zuerst den Verbund aktiviert werden, auf dem Edge-Server oder Pool für Edge-Server verfügen. Wenn auf dem Edge-Server oder Pool nicht den Verbund aktiviert ist, werden die Federation Route Zuordnung Einstellungen für die Website nicht geändert.

Wenn die partnerverbundeinstellung für den Edge-Server oder Pool konfiguriert wurde, können Sie die folgenden Optionen konfigurieren: 
  
- **Zulassen Federation Route Zuordnungen für alle Websites** Diese Einstellung wirkt sich auf alle Websites. Stellen Sie sicher, dass die Einstellung, die Sie an diesem Standort konfigurieren für alle Websites geeignet ist.
    
- **SIP-Partnerverbund aktivieren** Wählen Sie diese Option, um eine SIP-partnerverbundroute zu aktivieren, und wählen Sie dann einen Director- oder Edgepool als partnerverbundroute.
    
- **Aktivieren von XMPP-Verbund** Wählen Sie diese Option, um eine XMPP-partnerverbundroute zu aktivieren, und wählen Sie dann einen Director- oder Edgepool als partnerverbundroute.
- 
  > [!NOTE]
  > XMPP-Gateways und -Proxys werden stehen in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype für Business Server 2019. Weitere Informationen finden Sie unter [Migrieren von XMPP-Verbund](../../../../SfBServer2019/migration/migrating-xmpp-federation.md) .
    

