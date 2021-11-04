---
title: Einstellungen für die Partnerverbundroute – Erweiterung
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FederationRouteSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 22aa11b8-80ba-4c6a-9396-d11166903066
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Zuweisen einer Partnerverbundroute zu einem Standort muss für den Edgeserver bzw. Edgeserverpool der Partnerverbund aktiviert sein. Ist dies nicht der Fall, können die Einstellungen für die Zuweisung einer Partnerverbundroute nicht geändert werden.
ms.openlocfilehash: 565ec7fc5888f6b2a2dbe0c6c63772cbe0863f91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739751"
---
# <a name="federation-route-settings-expander"></a>Einstellungen für die Partnerverbundroute – Erweiterung
 
Zum Zuweisen einer Partnerverbundroute zu einem Standort muss für den Edgeserver bzw. Edgeserverpool der Partnerverbund aktiviert sein. Ist dies nicht der Fall, können die Einstellungen für die Zuweisung einer Partnerverbundroute nicht geändert werden.

Wenn die Partnerverbundeinstellung für den Edgeserver oder -pool konfiguriert wurde, können Sie die folgenden Optionen konfigurieren: 
  
- **Verbundroutenzuweisungen für alle Standorte zulassen** Diese Einstellung wirkt sich auf alle Websites aus. Vergewissern Sie sich, dass die Einstellung, die Sie für diesen Standort konfigurieren, für alle Standorte geeignet ist.
    
- **Aktivieren des SIP-Partnerverbunds** Wählen Sie diese Option aus, um eine SIP-Partnerverbundroute zu aktivieren, und wählen Sie dann einen Director oder Edgepool als Partnerverbundroute aus.
    
- **XMPP-Partnerverbund aktivieren** Wählen Sie diese Option aus, um eine XMPP-Partnerverbundroute zu aktivieren, und wählen Sie dann einen Director- oder Edgepool als Partnerverbundroute aus.
- 
  > [!NOTE]
  > XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds.](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)
    

