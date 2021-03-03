---
title: Einstellungen für die Partnerverbundroute – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Zum Zuweisen einer Partnerverbundroute zu einem Standort muss für den Edgeserver bzw. Edgeserverpool der Partnerverbund aktiviert sein. Ist dies nicht der Fall, können die Einstellungen für die Zuweisung einer Partnerverbundroute nicht geändert werden.
ms.openlocfilehash: 9e453eae2ca44b0e6f406aa6767bc44b741bd3b6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819465"
---
# <a name="federation-route-settings-expander"></a>Einstellungen für die Partnerverbundroute – Erweiterung
 
Zum Zuweisen einer Partnerverbundroute zu einem Standort muss für den Edgeserver bzw. Edgeserverpool der Partnerverbund aktiviert sein. Ist dies nicht der Fall, können die Einstellungen für die Zuweisung einer Partnerverbundroute nicht geändert werden.

Wenn die Partnerverbundeinstellung für den Edgeserver oder -pool konfiguriert wurde, können Sie die folgenden Optionen konfigurieren: 
  
- **Zulassen von Zuweisungen von Verbundrouten zu allen Standorten** Diese Einstellung wirkt sich auf alle Websites aus. Vergewissern Sie sich, dass die Einstellung, die Sie für diesen Standort konfigurieren, für alle Standorte geeignet ist.
    
- **Aktivieren des SIP-Verbunds** Wählen Sie diese Option aus, um eine SIP-Verbundroute zu aktivieren, und wählen Sie dann einen Director oder Edgepool als Verbundroute aus.
    
- **Aktivieren des XMPP-Verbunds** Wählen Sie diese Option aus, um eine XMPP-Verbundroute zu aktivieren, und wählen Sie dann einen Director oder Edgepool als Verbundroute aus.
- 
  > [!NOTE]
  > XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../../../../SfBServer2019/migration/migrating-xmpp-federation.md)
    

