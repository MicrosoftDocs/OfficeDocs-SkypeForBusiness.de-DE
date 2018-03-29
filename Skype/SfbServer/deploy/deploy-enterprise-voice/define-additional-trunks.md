---
title: Definieren von zusätzlichen Trunks im Topologie-Generator in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer im Topologie-Generator in Skype für Business Server 2015 definieren.'
ms.openlocfilehash: 67d378a794ed6a80b5721f9eb2e9e988ee4db048
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server-2015"></a>Definieren von zusätzlichen Trunks im Topologie-Generator in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer im Topologie-Generator in Skype für Business Server 2015 zu definieren.
  
Befolgen Sie diese Schritte, um einen zusätzlichen Trunk definieren, den einen Peer einen Vermittlungsserver zugeordnet werden können. Ein Peer bietet Benutzern, die mit der Konnektivität zu im Public Switched Telephone Network, (PSTN) für Enterprise Voice aktiviert. Bei einem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.
  
Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway.
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie Setup ein PSTN-Gateway und stammtrunk mit mindestens einem verbundenen oder eigenständigen Vermittlungsserver oder-Pool verfügen, wie in der Dokumentation zur Bereitstellung definieren [eines Gateways im Topologie-Generator in Skype für Business Server 2015](define-a-gateway.md) beschrieben.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>So definieren Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer

1. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.
    
2. Klicken Sie unter Skype für Business Server, Ihr Sitename, **Freigegebene Komponenten**, mit der rechten Maustaste in des Knotens **Trunks** , und klicken Sie dann auf **Neuer Trunk**.
    3. Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    
    > [!NOTE]
    > Wenn Sie Transport Layer Security (TLS) als Transportprotokoll angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers für den Vermittlungsserver angeben. 
  
4. Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    5. Geben Sie unter **Überwachungsport für PSTN-Gateway**, den Überwachungsport ein, dass der Peer (PSTN-Gateways, IP-Nebenstellenanlage oder SBC) vom Vermittlungsserver SIP-Nachrichten erhalten, die mit diesem Trunk zugeordnet werden soll. Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security). Die Survivable Branch Appliance Standardports sind 5081 für TCP und 5082 für TLS.
    
6. Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    
    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann. 
  
7. Wählen Sie unter **Zugeordneter Vermittlungsserver**zu dem stammtrunk dieses Peers zugeordnet Pools für den Vermittlungsserver
    
8. Geben Sie unter **zugeordneter Vermittlungsserver Port**den Überwachungsport, dass der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.
    
    > [!NOTE]
    > Zwei Trunks mit unterschiedlichen trunknamen können nicht mit Unterstützung mehrerer Trunks in Skype für Business Server mit dem gleichen **zugeordneter Vermittlungsserver Port** und **Überwachungsport für IP/PSTN-Gateway** konfiguriert werden
  
    > [!NOTE]
    > Mit Unterstützung mehrerer Trunks in Skype für Business Server kann mehrere SIP-Signalisierung Ports auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden. Wenn Sie einen Trunk zu definieren, muss die Portnummer **Zugeordneter Vermittlungsserver** innerhalb des Bereichs von die Überwachungsports für das jeweilige Protokoll vom Vermittlungsserver zulässig sein. Dieser Portbereich ist unter Skype für Business Server und Vermittlungsserver Pools definiert. Mit der rechten Maustaste in des entsprechenden Vermittlungsserver Pools, und wählen Sie **Eigenschaften bearbeiten**. Geben Sie den Portbereich im Feld **Überwachungsports** an.
  
9. Klicken Sie anschließend auf **OK**. 
    

