---
title: Konfigurieren von Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen trunk zwischen einem Vermittlungs Server und Peers für Enterprise-VoIP in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 9bd285f1364d54940afd827858248656a6bb9f00
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001235"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen trunk zwischen einem Vermittlungs Server und Peers für Enterprise-VoIP in Skype for Business Server konfigurieren.
  
Im Rahmen der Enterprise-VoIP-Bereitstellung können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren der folgenden Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen:
  
- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
    
- PSTN-Gateway
    
- Nebenstellenanlage (Private Branch Exchange, PBX)
    
Weitere Informationen finden Sie unter [Planen der PSTN-Konnektivität in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Die Skype for Business Server-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks erstellt, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungs Server Pool und einem PSTN-Gateway (Public Switched Telephone Network), Sitzungs Grenz Controller (SBC) oder IP-PBX handelt. Verwenden Sie den Topologie-Generator, um Gateways mit Vermittlungsservern (also Trunks) zu verknüpfen.
  
- Um einen trunk in Skype for Business Server zuzuweisen oder zu entfernen, müssen Sie zuerst einen trunk in Topology Builder definieren. Ein trunk besteht aus der folgenden Zuordnung: vollständig qualifizierter Domänenname (Fully Qualified Domain Name, FQDN), Mediation Server-Abhör Port, Gateway-FQDN und Gateway-Abhör Port.
    
- Zum Konfigurieren mehrerer Trunks können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungs Server erstellen. Dies bietet zusätzliche Widerstandsfähigkeit für die Enterprise-VoIP-Infrastruktur, die besonders in interoperational-Szenarien (Private Branch Exchange) verwendet werden kann. 
    
Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Um einen trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den trunk im Topologie-Generator. Dieser einfache Name wird als trunk-Name in der Skype for Business Server-Systemsteuerung verwendet, in der Trunks mit Routen verknüpft werden können. Der einfache trunk-Name wird als Gateway-Name aus der Skype for Business Server-Verwaltungsshell verwendet. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungs Server zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugehörigen Vermittlungs Server, und klicken Sie dann auf **Eigenschaften**. Geben Sie das Standardgateway für den Vermittlungs Server an. 
  

