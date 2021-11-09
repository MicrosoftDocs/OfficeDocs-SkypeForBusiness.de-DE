---
title: Konfigurieren von Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen Trunk zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype for Business Server konfigurieren.'
ms.openlocfilehash: f2d88d71476e428230aac0298cb0445844757e1c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839107"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie einen Trunk zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype for Business Server konfigurieren.
  
Im Rahmen Enterprise-VoIP Bereitstellung können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren der folgenden Peers konfigurieren, um PSTN-Verbindungen (Public Switched Telephone Network) für Enterprise-VoIP Clients und Geräte in Ihrer Organisation bereitzustellen:
  
- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
    
- PSTN-Gateway
    
- Nebenstellenanlage (Private Branch Exchange, PBX)
    
Weitere Informationen finden Sie unter [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Skype for Business Server Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks vorgenommen, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungsserverpool und einem PSTN-Gateway, session Border Controller (SBC) oder einer IP-Nebenstellenanlage handelt. Verwenden Sie den Topologie-Generator, um Gateways Vermittlungsservern (d. a. Trunks) zuzuordnen.
  
- Um einen Trunk in Skype for Business Server zuzuweisen oder zu entfernen, müssen Sie zuerst einen Trunk im Topologie-Generator definieren. Ein Trunk besteht aus der folgenden Zuordnung: Vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Vermittlungsservers, Gateway-FQDN und Gateway-Überwachungsport.
    
- Um mehrere Trunks zu konfigurieren, können Sie mehrere Zuordnungen zwischen demselben Gateway und dem Vermittlungsserver erstellen. Dies bietet zusätzliche Resilienz für die Enterprise-VoIP-Infrastruktur, was besonders in Interoperationsszenarien mit Nebenstellenanlagen (Private Branch Exchange, PBX) nützlich ist. 
    
Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Um einen Trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den Trunk im Topologie-Generator. Dieser einfache Name wird als Trunkname in der Skype for Business Server Systemsteuerung verwendet, wobei Trunks Routen zugeordnet werden können. Der einfache Trunkname wird als Gatewayname aus der Skype for Business Server Verwaltungsshell verwendet. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

Der Administrator muss einen Standardtrunk auswählen, der einem Vermittlungsserver zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugeordneten Vermittlungsserver, und klicken Sie dann auf **"Eigenschaften".** Geben Sie das Standardgateway für den Vermittlungsserver an. 
  

