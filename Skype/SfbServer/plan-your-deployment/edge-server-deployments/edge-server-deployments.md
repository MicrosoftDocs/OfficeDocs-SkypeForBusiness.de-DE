---
title: Planen von Edge-Server-Bereitstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Zusammenfassung: Planen Sie Ihre Skype for Business Server-Edge-Umgebung. Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277160"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planen von Edge-Server-Bereitstellungen in Skype for Business Server
 
**Zusammenfassung:** Planen Sie Ihre Skype for Business Server-Edge-Umgebung. Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.
  
Wenn Sie über eine Skype for Business Server-Umgebung verfügen, die intern gut funktioniert, besteht der nächste Schritt darin, einen Edgeserver oder einen Edge-Pool für die Umgebung einzuführen. Diese Rolle wäre von entscheidender Bedeutung, wenn Sie möchten, dass die von Skype for Business Server bereitgestellten Dienste von Personen verwendet werden, die sich außerhalb Ihres internen Netzwerks befinden. Zu diesen können folgende gehören:
  
- Remotebenutzer: Mitarbeiter, die vorübergehend oder längerfristig standortextern arbeiten.
    
- Federated-Benutzer: Mitarbeiter Ihrer Partnerorganisationen.
    
- Mobile Benutzer.
    
- Potenzielle Kunden, Partner und sogar anonyme Benutzer, die Sie zu Meetings und Präsentationen einladen möchten.
    
Der Zugriff externer Benutzer, was von Edge-Servern bereitgestellt wird, ermöglicht dies. Ihre internen Benutzer können die folgenden Dienste nutzen, die von Ihrer Skype for Business Server-Bereitstellung gehostet werden:
  
- Chat und Anwesenheitsinformationen für die Kommunikation: autorisierte externe Benutzer können an Chat Unterhaltungen und Konferenzen teilnehmen. Sie können Anwesenheitsinformationen für andere Benutzer erhalten (die auch ihre Anwesenheitsinformationen erhalten). Wenn Sie einen öffentlichen Chat-Anbieter verwenden, sind Sie nicht in der Lage, mehrteilige Konferenzen zu Unternehmen, da es sich um eine strikte Peer-to-Peer-Kommunikation handelt. Es werden jedoch sowohl SIP-als auch XMPP-Protokolle unterstützt.
    
- Audio/Video-Konferenzen (A/V): autorisierte externe Benutzer können an Ihren Skype for Business Server-Audio-und Videokonferenzen teilnehmen.
    
- Webkonferenzen: ihre autorisierten externen Benutzer können an Ihren Skype for Business-Konferenzen teilnehmen. Sie können auch die Teilnahme an Remotebenutzern, Verbundbenutzern und anonymen Benutzern aktivieren, wenn Sie möchten. Öffentliche Chat-Benutzer können nicht an Konferenzen teilnehmen. Darüber hinaus gibt es Optionen, mit denen diese Benutzer an der Anwendungs-und Desktopfreigabe teilnehmen und sogar als Besprechungsorganisatoren oder Referenten fungieren können.
    
Der Zugriff auf mobile Geräte wird ebenso wie Enterprise-VoIP unterstützt. Sie können externe Benutzer zu Besprechungen einladen, an denen diese teilnehmen sollen, und sogar anonyme Benutzer, wenn Sie diesen die Berechtigungen geben möchten.
  
Wenn dies sinnvoll für Ihr Unternehmen erscheint, wird die Planung einer Edge-Umgebung eine große Hilfe für die Bereitstellung sein. Weitere Themen können Sie nachfolgend lesen.

> [!NOTE]
> XMPP-Gateways und-Proxies sind in Skype for Business Server 2015 verfügbar, werden aber in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren der XMPP-Föderation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Themen für die Planung:

Zu den Artikeln für die Planung gehören folgende:
  
- [Systemanforderungen des Edgeservers in Skype for Business Server 2015](system-requirements.md)
    
- [Umgebungsanforderungen des Edgeservers in Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Edgeserver-Szenarien in Skype for Business Server 2015](scenarios.md)
    

