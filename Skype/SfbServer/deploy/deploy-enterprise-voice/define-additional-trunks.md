---
title: Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Zusammenfassung: Erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem Gatewaypeer im Topologie-Generator in Skype for Business Server definieren.'
---

# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem Gatewaypeer im Topologie-Generator in Skype for Business Server definieren.
  
Führen Sie die folgenden Schritte aus, um einen zusätzlichen Trunk zu definieren, dem Sie einen Peer einem Vermittlungsserver zuordnen können. Ein Peer stellt Benutzern, die für Enterprise-VoIP aktiviert sind, eine Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) zur Verfügung. Bei dem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.
  
Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway.
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stammtrunk mit mindestens einem verbundenen oder eigenständigen Vermittlungsserver oder -pool eingerichtet haben, wie unter [Definieren eines Gateways im Topologie-Generator in Skype for Business Server](define-a-gateway.md) in der Bereitstellungsdokumentation beschrieben.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>So definieren Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem Gatewaypeer

1. Topologie-Generator starten: Klicken Sie auf **"Start**", auf **"Alle Programme**", auf **Skype for Business Server 2015** und dann auf **Skype for Business Server 2015Topology Builder**.
    
2. Klicken Sie unter Skype for Business Server mit der rechten Maustaste auf den Knoten "**Trunks**" und dann auf "**Neuer Trunk**".
   1. Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    
      > [!NOTE]
      > Wenn Sie Tls (Transport Layer Security) als Transporttyp angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers des Vermittlungsservers angeben. 
  
3. Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    5. Geben Sie unter **"Überwachungsport für PSTN-Gateway**" den Überwachungsport ein, den der Peer (PSTN-Gateway, IP-Nebenstellenanlage oder SBC) SIP-Nachrichten vom Vermittlungsserver empfängt, der diesem Trunk zugeordnet werden soll. Die Standardpeerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für Transport Layer Security (TLS). Die Standardmäßigen Survivable Branch Appliance-Ports sind 5081 für TCP und 5082 für TLS.
    
4. Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    
    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, einen Peer auf dem Vermittlungsserver bereitzustellen, der TLS verwenden kann. 
  
5. Wählen Sie unter **Zugeordneter Vermittlungsserver** den Vermittlungsserverpool aus, der dem Stammtrunk dieses Peers zugeordnet werden soll.
    
6. Geben Sie unter **zugeordneter Vermittlungsserverport** den Überwachungsport ein, den der Vermittlungsserver SIP-Nachrichten vom Peer empfängt.
    
    > [!NOTE]
    > Bei unterstützung mehrerer Trunks in Skype for Business Server können zwei Trunks mit unterschiedlichen Trunknamen nicht mit demselben **Zugeordneten Vermittlungsserverport** und **Überwachungsport für IP/PSTN-Gateway** konfiguriert werden.
  
    > [!NOTE]
    > Mit mehreren Trunkunterstützungen in Skype for Business Server können mehrere SIP-Signalports auf dem Vermittlungsserver für die Kommunikation mit mehreren Peers definiert werden. Beim Definieren eines Trunks muss sich die **Portnummer des zugeordneten Vermittlungsservers** innerhalb des Bereichs der Überwachungsports für das entsprechende Protokoll befinden, das vom Vermittlungsserver zugelassen wird. Dieser Portbereich ist unter Skype for Business Server und Vermittlungsserverpools definiert. Klicken Sie mit der rechten Maustaste auf den entsprechenden Vermittlungsserverpool, und wählen Sie **"Eigenschaften bearbeiten" aus**. Geben Sie den Portbereich im Feld **Überwachungsports** an.
  
7. Klicken Sie auf **OK**. 
    

