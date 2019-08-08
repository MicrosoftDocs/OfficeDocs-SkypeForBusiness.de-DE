---
title: Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer im Topologie-Generator in Skype for Business Server definieren.'
ms.openlocfilehash: eeaddf6b5b150298e7a77b819464b3c0ef653b70
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245610"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer im Topologie-Generator in Skype for Business Server definieren.
  
Führen Sie die folgenden Schritte aus, um einen zusätzlichen trunk zu definieren, dem Sie einen Peer einem Vermittlungs Server zuordnen können. Ein Peer bietet Benutzern, die für Enterprise-VoIP aktiviert sind, Verbindungen mit dem öffentlich geschalteten Telefonnetz (PSTN). Bei einem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.
  
Ein trunk ist eine logische Verbindung zwischen einem Vermittlungs Server und einem Gateway.
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stamm Stamm mit mindestens einem zusammengefassten oder eigenständigen Vermittlungs Server oder-Pool eingerichtet haben, wie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server](define-a-gateway.md) in der Bereitstellungsdokumentation beschrieben.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>So definieren Sie einen zusätzlichen trunk zwischen einem Vermittlungs Server und einem Gateway-Peer

1. Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.
    
2. Klicken Sie unter Skype for Business Server, Name Ihrer Website, **freigegebene Komponenten**, mit der rechten Maustaste auf den Knoten **Trunks** , und klicken Sie dann auf **neuer trunk**.
   1. Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    
      > [!NOTE]
      > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsservers den FQDN angeben. 
  
3. Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    5. Geben Sie unter **Abhör-Port für PSTN-Gateway**den Abhör-Port ein, mit dem der Peer (PSTN-Gateway, IP-PBX oder SBC) SIP-Nachrichten vom Vermittlungs Server empfängt, der diesem trunk zugeordnet werden soll. Die standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security). Die Standardanschlüsse für Survivable Branch-Appliances sind 5081 für TCP und 5082 für TLS.
    
4. Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    
    > [!NOTE]
    > Aus Sicherheitsgründen empfehlen wir dringend, einen Peer auf dem Vermittlungs Server bereitzustellen, der TLS verwenden kann. 
  
5. Wählen Sie unter **zugeordneter Vermittlungsserver**den vermittlungsserverpool aus, der dem Stamm Stamm dieses Peers zugeordnet werden soll.
    
6. Geben Sie unter **zugeordneter Vermittlungsserver-Port**den Abhör-Port ein, auf dem der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.
    
    > [!NOTE]
    > Mit mehreren trunk-Unterstützung in Skype for Business Server können zwei Trunks mit unterschiedlichen trunk-Namen nicht mit dem gleichen **zugehörigen Vermittlungs Server-Port** und **Abhör-Port für IP/PSTN-Gateway** konfiguriert werden.
  
    > [!NOTE]
    > Mit mehreren trunk-Unterstützung in Skype for Business Server können mehrere SIP-Signalisierungs Anschlüsse auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden. Wenn Sie einen trunk definieren, muss sich die **zugeordnete Vermittlungsserver-Port** Nummer innerhalb des Bereichs der Abhör Anschlüsse für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden. Dieser Portbereich wird unter Skype for Business Server-und Mediation Server-Pools definiert. Klicken Sie mit der rechten Maustaste auf den entsprechenden Vermittlungs Server Pool, und wählen Sie **Eigenschaften bearbeiten**aus. Specify the port range in the **Listening ports** field.
  
7. Klicken Sie anschließend auf **OK**. 
    

