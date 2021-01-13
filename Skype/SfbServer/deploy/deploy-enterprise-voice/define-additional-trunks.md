---
title: Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server
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
ms.assetid: e68b8377-50a2-452a-bf5c-910929e34236
description: 'Zusammenfassung: Informationen zum Definieren eines zusätzlichen Trunks zwischen einem Vermittlungsserver und einem Gateway-Peer im Topologie-Generator in Skype for Business Server.'
ms.openlocfilehash: 3aab744761420ab631f17e6b56391f1fab120ccf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836995"
---
# <a name="define-additional-trunks-in-topology-builder-in-skype-for-business-server"></a>Definieren zusätzlicher Trunks im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem Gateway-Peer im Topologie-Generator in Skype for Business Server definieren.
  
Führen Sie die folgenden Schritte aus, um einen zusätzlichen Trunk zu definieren, dem Sie einen Peer einem Vermittlungsserver zuordnen können. Ein Peer stellt Benutzern, die für Enterprise-VoIP aktiviert sind, eine Verbindung mit dem Telefonnetz (Public Switched Telephone Network, PSTN) zur Verfügung. Bei dem Peer kann es sich um ein PSTN-Gateway, eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten handeln.
  
Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway.
  
> [!NOTE]
> In diesem Thema wird davon ausgegangen, dass Sie ein PSTN-Gateway und einen Stamm trunk mit mindestens einem verbindenden oder eigenständigen Vermittlungsserver oder -pool eingerichtet haben, wie in "Definieren eines Gateways im [Topologie-Generator in Skype for Business Server" in](define-a-gateway.md) der Bereitstellungsdokumentation beschrieben.
  
### <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>So definieren Sie einen zusätzlichen Trunk zwischen einem Vermittlungsserver und einem Gateway-Peer

1. Starten Sie den Topologie-Generator: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business Server 2015"** und dann auf **"Skype for Business Server 2015Topology Builder".**
    
2. Klicken Sie unter Skype for Business Server, **Standortname,** freigegebene Komponenten mit der rechten Maustaste auf den Knoten **Trunks,** und klicken Sie dann auf **"Neuer Trunk".**
   1. Geben Sie in **Neuen Trunk definieren** einen Anzeigenamen ein, um den Trunk eindeutig zu identifizieren. Zwei Trunks mit demselben Namen sind nicht zulässig.
    
      > [!NOTE]
      > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers des Vermittlungsservers angeben. 
  
3. Wählen Sie unter **Zugeordnetes PSTN-Gateway** den PSTN-Gatewaypeer aus, der diesem Trunk zugeordnet werden soll.
    5. Geben Sie unter "Abhörport für **PSTN-Gateway"** den Abhörport ein, den der Peer (PSTN-Gateway, IP-PBX oder SBC) vom Vermittlungsserver erhält, der diesem Trunk zugeordnet werden soll. Die Standardmäßigen Peerports sind 5066 für TCP (Transmission Control Protocol) und 5067 für TLS (Transport Layer Security). Die standardmäßigen Survivable Branch Appliance-Ports sind 5081 für TCP und 5082 für TLS.
    
4. Klicken Sie unter **SIP-Transportprotokoll** auf den vom Peer verwendeten Transporttyp.
    
    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, dass Sie einen Peer auf dem Vermittlungsserver bereitstellen, der TLS verwenden kann. 
  
5. Wählen **Sie unter Zugeordneter Vermittlungsserver** den Vermittlungsserverpool aus, der dem Stamm trunk dieses Peers zugeordnet werden soll.
    
6. Geben **Sie unter "Zugeordneter Vermittlungsserverport"** den Abhörport ein, den der Vermittlungsserver vom Peer erhält.
    
    > [!NOTE]
    > Bei der Unterstützung mehrerer Trunks in Skype for Business Server können zwei  Trunks mit unterschiedlichen Trunknamen nicht mit demselben Port für den zugeordneten Vermittlungsserver und dem gleichen Abhörport für **IP-/PSTN-Gateways** konfiguriert werden.
  
    > [!NOTE]
    > Bei der Unterstützung mehrerer Trunks in Skype for Business Server können auf dem Vermittlungsserver mehrere SIP-Signalports für die Kommunikation mit mehreren Peers definiert werden. Beim Definieren eines  Trunks muss sich die Portnummer des zugeordneten Vermittlungsservers innerhalb des Bereichs der vom Vermittlungsserver zulässigen Abhörports für das entsprechende Protokoll befinden. Dieser Portbereich wird unter Skype for Business Server- und Vermittlungsserverpools definiert. Klicken Sie mit der rechten Maustaste auf den entsprechenden Vermittlungsserverpool, und wählen **Sie "Eigenschaften bearbeiten" aus.** Geben Sie den Portbereich im Feld **Überwachungsports** an.
  
7. Klicken Sie auf **OK**. 
    

