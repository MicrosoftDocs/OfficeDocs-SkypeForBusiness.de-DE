---
title: Konfigurieren von Trunks in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Zusammenfassung: Informationen zum Konfigurieren eines Trunks zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype for Business Server.'
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824955"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>Konfigurieren von Trunks in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie einen Trunk zwischen einem Vermittlungsserver und Peers für Enterprise-VoIP in Skype for Business Server konfigurieren.
  
Im Rahmen der Enterprise-VoIP können Sie einen Trunk zwischen einem Vermittlungsserver und einem oder mehreren der folgenden Peers konfigurieren, um Konnektivität über das Telefonnetz (Public Switched Telephone Network, PSTN) für Enterprise-VoIP-Clients und -Geräte in Ihrer Organisation zu ermöglichen:
  
- SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten
    
- PSTN-Gateway
    
- Nebenstellenanlage (Private Branch Exchange, PBX)
    
Weitere Informationen finden Sie unter [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).
  
Die Skype for Business Server-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks vorgenommen, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungsserverpool und einem PSTN-Gateway, einem SBC (Session Border Controller) oder einer IP-PBX-Anlage handelt. Verwenden Sie den Topologie-Generator, um Gateways Vermittlungsservern (d. h. Trunks) zuzuordnen.
  
- Zum Zuweisen oder Entfernen eines Trunks in Skype for Business Server müssen Sie zunächst einen Trunk im Topologie-Generator definieren. Ein Trunk besteht aus der folgenden Zuordnung: Vollqualifizierter Domänenname (FQDN) des Vermittlungsservers, Abhörport des Vermittlungsservers, Gateway-FQDN und Gateway-Listening-Port.
    
- Zum Konfigurieren mehrerer Trunks können Sie mehrere Zuordnungen zwischen demselben Gateway und dem Vermittlungsserver erstellen. Dies bietet zusätzliche Resilienz für die Enterprise-VoIP, was besonders in Interoperationsszenarien mit Nebenstellenanlagen (Private Branch Exchange, PBX) hilfreich ist. 
    
Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Zum Zuordnen eines Trunks zu einer Route definieren Sie einen einfachen Namen für den Trunk im Topologie-Generator. Dieser einfache Name wird als Trunkname in der Skype for Business Server-Systemsteuerung verwendet, in der Trunks Routen zugeordnet werden können. Der einfache Trunkname wird als Gatewayname aus der Skype for Business Server-Verwaltungsshell verwendet. 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungsserver zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugeordneten Vermittlungsserver, und klicken Sie dann auf **Eigenschaften**. Geben Sie das Standardgateway für den Vermittlungsserver an. 
  

