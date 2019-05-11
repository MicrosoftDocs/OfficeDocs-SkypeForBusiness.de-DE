---
title: Definieren von zusätzlichen Trunks im Topologie-Generator in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer im Topologie-Generator in Skype für Business Server definieren.'
ms.openlocfilehash: 308cd200af2ee046a3e2bcc84815d3755cea932f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892860"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definieren von zusätzlichen Trunks im Topologie-Generator in Skype für Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer im Topologie-Generator in Skype für Business Server definieren.
  
Befolgen Sie diese Schritte, um einen zusätzlichen Trunk definieren, den einen Peer einen Vermittlungsserver zugeordnet werden können. Ein Peer bietet Benutzern, die mit der Konnektivität zu im Public Switched Telephone Network, (PSTN) für Enterprise Voice aktiviert. Bei einem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.
  
Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway.
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie Setup ein PSTN-Gateway und stammtrunk mit mindestens einem verbundenen oder eigenständigen Vermittlungsserver oder-Pool verfügen, wie in der Dokumentation zur Bereitstellung definieren [eines Gateways im Topologie-Generator in Skype für Business Server](define-a-gateway.md) beschrieben.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>So definieren Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem gatewaypeer

1. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.
    
2. Klicken Sie unter Skype für Business Server, Ihr Sitename, **Freigegebene Komponenten**, mit der rechten Maustaste in des Knotens **Trunks** , und klicken Sie dann auf **Neuer Trunk**.
   1. Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    
      > [!NOTE]
      > Wenn Sie Transport Layer Security (TLS) als Transportprotokoll angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers für den Vermittlungsserver angeben. 
  
3. Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    5. Geben Sie unter **Überwachungsport für PSTN-Gateway**, den Überwachungsport ein, dass der Peer (PSTN-Gateways, IP-Nebenstellenanlage oder SBC) vom Vermittlungsserver SIP-Nachrichten erhalten, die mit diesem Trunk zugeordnet werden soll. Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security). Die Survivable Branch Appliance Standardports sind 5081 für TCP und 5082 für TLS.
    
4. Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    
    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann. 
  
5. Wählen Sie unter **Zugeordneter Vermittlungsserver**zu dem stammtrunk dieses Peers zugeordnet Pools für den Vermittlungsserver
    
6. Geben Sie unter **zugeordneter Vermittlungsserver Port**den Überwachungsport, dass der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.
    
    > [!NOTE]
    > Zwei Trunks mit unterschiedlichen trunknamen können nicht mit Unterstützung mehrerer Trunks in Skype für Business Server mit dem gleichen **zugeordneter Vermittlungsserver Port** und **Überwachungsport für IP/PSTN-Gateway** konfiguriert werden
  
    > [!NOTE]
    > Mit Unterstützung mehrerer Trunks in Skype für Business Server kann mehrere SIP-Signalisierung Ports auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden. Wenn Sie einen Trunk zu definieren, muss die Portnummer **Zugeordneter Vermittlungsserver** innerhalb des Bereichs von die Überwachungsports für das jeweilige Protokoll vom Vermittlungsserver zulässig sein. Dieser Portbereich ist unter Skype für Business Server und Vermittlungsserver Pools definiert. Mit der rechten Maustaste in des entsprechenden Vermittlungsserver Pools, und wählen Sie **Eigenschaften bearbeiten**. Specify the port range in the **Listening ports** field.
  
7. Klicken Sie anschließend auf **OK**. 
    

