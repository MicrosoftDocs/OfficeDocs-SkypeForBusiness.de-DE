---
title: Planen von Edgeserverbereitstellungen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Hybrid
ms.custom: null
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Zusammenfassung: Planen Ihrer Skype for Business Server Edgeumgebung. In diesem Thema werden Die Edge-Konzepte vorgestellt, und Sie können sich mit unseren ausführlicheren Themen organisieren.'
---

# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planen von Edgeserverbereitstellungen in Skype for Business Server
 
**Zusammenfassung:** Planen Sie ihre Skype for Business Server Edgeumgebung. In diesem Thema werden Die Edge-Konzepte vorgestellt, und Sie können sich mit unseren ausführlicheren Themen organisieren.
  
Wenn Sie über eine Skype for Business Server Umgebung verfügen, die intern gut funktioniert, ist der nächste Schritt für Sie möglicherweise die Einführung eines Edgeservers oder eines Edgepools in die Umgebung. Diese Rolle wäre wichtig, wenn die von Skype for Business Server bereitgestellten Dienste von Personen außerhalb Ihres internen Netzwerks verwendet werden sollen. Dies kann potenziell Folgendes umfassen:
  
- Remotebenutzer: Mitarbeiter außerhalb des Standorts, entweder vorübergehend oder fortlaufend.
    
- Verbundbenutzer: Mitarbeiter Ihrer Partnerorganisationen.
    
- Mobile Benutzer.
    
- Potenzielle Kunden, Partner und sogar anonyme Benutzer, die Sie zu Besprechungen und Präsentationen einladen möchten.
    
Der externe Benutzerzugriff, der von Edgeservern bereitgestellt wird, lässt all dies zu. Ihre internen Benutzer können die folgenden Dienste nutzen, die von Ihrer Skype for Business Server Bereitstellung gehostet werden:
  
- Chat und Anwesenheit für die Kommunikation: Autorisierte externe Benutzer können an Chatunterhaltungen und Konferenzen teilnehmen. Sie können Anwesenheitsinformationen für andere Benutzer abrufen (die auch ihre Anwesenheitsinformationen erhalten). Wenn Sie einen öffentlichen Chatanbieter verwenden, ist dies reine Peer-to-Peer-Kommunikation. Es werden jedoch sowohl SIP- als auch XMPP-Protokolle unterstützt.
    
- Audio-/Videokonferenzen (A/V): Autorisierte externe Benutzer können an Ihren Skype for Business Server Audio- und Videokonferenzen teilnehmen.
    
- Webkonferenzen: Ihre autorisierten externen Benutzer können an Ihren Skype for Business Konferenzen teilnehmen. Sie können die Teilnahme auch für Remotebenutzer, Verbundbenutzer und anonyme Benutzer aktivieren, wenn Sie möchten. Benutzer öffentlicher Chatnachrichten können nicht an Konferenzen teilnehmen. Es gibt auch Optionen, mit denen diese Benutzer an der Anwendungs- und Desktopfreigabe teilnehmen und sogar als Besprechungsorganisatoren oder Referenten fungieren können.
    
Der Zugriff auf mobile Geräte wird ebenso wie Enterprise-VoIP unterstützt. Sie können externe Benutzer zu diesen Besprechungen einladen, an denen sie teilnehmen sollen, auch anonyme Benutzer, wenn Sie ihnen Berechtigungen erteilen möchten.
  
Wenn dies nach etwas klingt, das Ihre Organisation benötigt, ist die Planung für eine Edgeumgebung eine große Hilfe bei der Bereitstellung. Weitere Informationen finden Sie in den unten aufgeführten Themen.

> [!NOTE]
> XMPP-Gateways und Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter [Migrieren des XMPP-Partnerverbunds](../../../SfBServer2019/migration/migrating-xmpp-federation.md) . 
  
## <a name="planning-topics"></a>Planungsthemen:

Die Planungsartikel sind:
  
- [Systemanforderungen für Edgeserver in Skype for Business Server 2015](system-requirements.md)
    
- [Edgeserver-Umgebungsanforderungen in Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Edgeserverszenarien in Skype for Business Server 2015](scenarios.md)
    

