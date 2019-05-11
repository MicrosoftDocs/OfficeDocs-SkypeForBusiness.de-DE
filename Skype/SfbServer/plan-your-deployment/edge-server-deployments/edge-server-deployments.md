---
title: Planen von Edge-Server-Bereitstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Zusammenfassung: Planen Sie für Ihre Skype für Business Server Edge-Umgebung. Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.'
ms.openlocfilehash: 4c4348d0d3aa56aa82b8ea8930176d9d135a64f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885075"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planen von Edge-Server-Bereitstellungen in Skype für Business Server
 
**Zusammenfassung:** Planen Sie Ihre Skype für Business Server Edge-Umgebung aus. Mit diesem Thema werden Sie in die Edge-Konzepte eingeführt und es hilft Ihnen bei der Organisation von unseren ausführlicheren Themenbereichen.
  
Wenn Sie einen Skype für Business Server-Umgebung, die auch intern funktionsfähig ist können Sie, möglicherweise für Sie im nächsten Schritt ein Edge-Server oder einem edgepool für die Umgebung einführen. Diese Rolle wäre wichtiger, wenn der Dienste von Skype für Business Server von Personen, die sich außerhalb des internen Netzwerks befinden, verwendet werden soll. Zu diesen können folgende gehören:
  
- Remotebenutzer: Mitarbeiter, die vorübergehend oder längerfristig standortextern arbeiten.
    
- Partnerbenutzer: Der Partnerorganisation Mitarbeiter.
    
- Mobile Benutzer.
    
- Potenzielle Kunden, Partner und sogar anonyme Benutzer, die Sie zu Meetings und Präsentationen einladen möchten.
    
Zugriff durch externe Benutzer, die ist, was Edge-Server bereitstellen, können all dies geschieht. Internen Benutzern werden die folgenden Dienste nutzen zu können, die von Ihrer Skype für Business Server-Bereitstellung gehostet werden:
  
- Instant Messaging und Anwesenheit für die Kommunikation: autorisierte externe Benutzer können in Sofortnachrichtenunterhaltungen und Konferenzen teilnehmen. Sie können Anwesenheitsinformationen für andere Benutzer abrufen (, wer ihre Anwesenheitsinformationen zu abrufen). Nicht möglich, Konferenzen mit mehreren Teilnehmern ist, wenn Sie einen öffentlichen IM-Dienstanbieter verwenden, der streng Peer-zu-Peer-Kommunikation ist. Aber SIP- und XMPP-Protokolle werden unterstützt.
    
- Audio/Video (A / V) Konferenzen: autorisierte externe Benutzer können Ihre Skype für Business Server audio und video-Konferenzen teilnehmen.
    
- Webkonferenzen: Ihre autorisierte externe Benutzer in Ihrer Skype für Business-Konferenzen teilnehmen können. Wenn Sie möchten, können Sie auch Teilnahme für Remotebenutzer, Verbundbenutzer und anonyme Benutzer aktivieren. Öffentliche Instant Messaging-Benutzer können nicht an Konferenzen teilnehmen. Es gibt auch Optionen, um Benutzern Anwendungs- und Desktopfreigabe teilnehmen, und auch als Besprechungsorganisatoren oder Referenten fungieren.
    
Wie Enterprise-VoIP ist wird, den Zugriff durch Mobile Geräte unterstützt. Sie können externe Benutzer zu Besprechungen einladen, an denen diese teilnehmen sollen, und sogar anonyme Benutzer, wenn Sie diesen die Berechtigungen geben möchten.
  
Wenn dies sinnvoll für Ihr Unternehmen erscheint, wird die Planung einer Edge-Umgebung eine große Hilfe für die Bereitstellung sein. Weitere Themen können Sie nachfolgend lesen.

> [!NOTE]
> XMPP-Gateways und -Proxys werden stehen in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype für Business Server 2019. Weitere Informationen finden Sie unter [Migrieren von XMPP-Verbund](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Themen für die Planung:

Zu den Artikeln für die Planung gehören folgende:
  
- [Systemanforderungen des Edgeservers in Skype for Business Server 2015](system-requirements.md)
    
- [Umgebungsanforderungen des Edgeservers in Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Edgeserver-Szenarien in Skype for Business Server 2015](scenarios.md)
    

