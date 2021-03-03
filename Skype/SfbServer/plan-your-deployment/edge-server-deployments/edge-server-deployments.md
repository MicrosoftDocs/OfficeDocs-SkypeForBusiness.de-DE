---
title: Planen von Edgeserverbereitstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Zusammenfassung: Planen Sie Ihre Skype for Business Server-Edgeumgebung. In diesem Thema werden Sie mit den Konzepten von Edge und mit unseren detaillierten Themen organisiert.'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813805"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>Planen von Edgeserverbereitstellungen in Skype for Business Server
 
**Zusammenfassung:** Planen Sie Ihre Skype for Business Server-Edgeumgebung. In diesem Thema werden Sie mit den Konzepten von Edge und mit unseren detaillierten Themen organisiert.
  
Wenn Sie über eine Skype for Business Server-Umgebung verfügen, die intern gut funktioniert, besteht der nächste Schritt möglicherweise in der Einführung eines Edgeservers oder edgepools in der Umgebung. Diese Rolle wäre wichtig, wenn die von Skype for Business Server bereitgestellten Dienste von Personen außerhalb Ihres internen Netzwerks verwendet werden sollen. Dazu können u. a. folgende gehören:
  
- Remotebenutzer: Mitarbeiter, die entweder vorübergehend oder fortlaufend außerhalb des Standorts arbeiten.
    
- Verbundbenutzer: Mitarbeiter Ihrer Partnerorganisationen.
    
- Mobile Benutzer.
    
- Potenzielle Kunden, Partner und sogar anonyme Benutzer, die Sie zu Besprechungen und Präsentationen einladen möchten.
    
Der externe Benutzerzugriff, der von Edgeservern ermöglicht wird, lässt dies zu. Ihre internen Benutzer können die folgenden Dienste nutzen, die von Ihrer Skype for Business Server-Bereitstellung gehostet werden:
  
- Chat und Anwesenheit für die Kommunikation: Autorisierte externe Benutzer können an Chatunterhaltungen und Konferenzen teilnehmen. Sie können Anwesenheitsinformationen für andere Benutzer (die auch ihre Anwesenheitsinformationen erhalten) erhalten. Wenn Sie einen öffentlichen Anbieter für Internetkonferenzen verwenden, können Sie keine Konferenzen mit mehreren Konferenzteil nehmen. Dies ist die reine Peer-zu-Peer-Kommunikation. Es werden jedoch sowohl SIP- als auch XMPP-Protokolle unterstützt.
    
- Audio-/Videokonferenzen (A/V): Autorisierte externe Benutzer können an Ihren Audio- und Videokonferenzen in Skype for Business Server teilnehmen.
    
- Webkonferenzen: Ihre autorisierten externen Benutzer können an Ihren Skype for Business-Konferenzen teilnehmen. Sie können die Teilnahme auch für Remotebenutzer, Partnerbenutzer und anonyme Benutzer aktivieren, wenn Sie möchten. Benutzer von öffentlichen Internetkonferenzen können nicht an Konferenzen teilnehmen. Es gibt auch Optionen, um diesen Benutzern die Teilnahme an der Anwendungs- und Desktopfreigabe zu ermöglichen und sogar als Besprechungsorganisatoren oder Organisator zu fungieren.
    
Der Zugriff auf mobile Geräte wird unterstützt, ebenso wie Enterprise-VoIP. Sie können externe Benutzer zu diesen Besprechungen einladen, an denen sie teilnehmen sollen, auch anonyme Benutzer, wenn Sie ihnen Berechtigungen erteilen möchten.
  
Wenn dies so klingt, als ob Ihre Organisation dies benötigt, ist die Planung einer Edgeumgebung eine wichtige Hilfe bei der Bereitstellung. Weitere Informationen finden Sie in den unten aufgeführten Themen.

> [!NOTE]
> XMPP-Gateways und -Proxys sind in Skype for Business Server 2015 verfügbar, werden jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Weitere Informationen finden Sie unter ["Migrieren des XMPP-Verbunds".](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 
  
## <a name="planning-topics"></a>Planungsthemen:

Die Planungsartikel sind:
  
- [Systemanforderungen für Edgeserver in Skype for Business Server 2015](system-requirements.md)
    
- [Umgebungsanforderungen für Edgeserver in Skype for Business Server 2015](edge-environmental-requirements.md)
    
- [Edgeserverszenarien in Skype for Business Server 2015](scenarios.md)
    

