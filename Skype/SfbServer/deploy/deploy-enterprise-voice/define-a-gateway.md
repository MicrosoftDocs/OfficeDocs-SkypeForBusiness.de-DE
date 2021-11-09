---
title: Definieren eines Gateways im Topologie-Generator in Skype for Business Server
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Zusammenfassung: Erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype for Business Server definieren.'
ms.openlocfilehash: 2e8a69fb1a884597f4e6ecde1a3811a88982d13e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857952"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definieren eines Gateways im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype for Business Server definieren.
  
Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen Peer zu definieren, dem Sie einen Vermittlungsserver zuordnen können, um Benutzern, die für Enterprise-VoIP aktiviert sind, verbindungen mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN) bereitzustellen. Ein Peer zum Vermittlungsserver kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein Session Border Controller (SBC) für einen Internettelefoniedienstanbieter (Internet Telephony Service Provider, ITSP) sein, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>So definieren Sie einen Peer für den Vermittlungsserver

1. Topologie-Generator starten: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business Server 2015** und dann auf **Skype for Business Server 2015Topology Builder.**
    
2. Klicken Sie unter Skype for Business Server mit der rechten Maustaste auf den Knoten **"PSTN-Gateways"** und dann auf **"Neues PSTN-Gateway".**
3. Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein, und klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Wenn Sie Tls (Transport Layer Security) als Transporttyp angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers des Vermittlungsservers angeben. 
  
4. Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateway, und klicken Sie auf **Weiter**.

5. Definieren Sie einen Stammtrunk für das PSTN-Gateway. Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway, das vom Tupel eindeutig identifiziert wird.
    
    {Vermittlungsserver-FQDN, Vermittlungsserver-Überwachungsport (TLS oder TCP): Gateway-IP und FQDN, Gateway-Überwachungsport}
    
     - Beim Definieren eines PSTN-Gateways im Topologie-Generator müssen Sie einen Stammtrunk definieren, um das PSTN-Gateway erfolgreich zu Ihrer Topologie hinzuzufügen.
    
     - Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.
    
6. Geben Sie unter **"Überwachungsport für IP/PSTN-Gateway"** den Überwachungsport ein, den das Gateway, die Nebenstellenanlage oder der SBC für SIP-Nachrichten vom Vermittlungsserver verwendet, der dem Stammtrunk des PSTN-Gateways zugeordnet wird. (In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt. In einer Survivable Branch Appliance an einem Zweigstellenstandort sind die Standardports 5081 für TCP und 5082 für TLS.)
    
7. Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll, und klicken Sie dann auf **OK**.
    
    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, einen Peer auf dem Vermittlungsserver bereitzustellen, der TLS verwenden kann. 
  
8. Wählen Sie unter **Zugeordneter Vermittlungsserver** den Vermittlungsserverpool aus, der dem Stammtrunk dieses PSTN-Gateways zugeordnet werden soll.
    
9. Geben Sie unter **zugeordneter Vermittlungsserverport** den Überwachungsport ein, den der Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet.
    
    > [!NOTE]
    > Mit mehreren Trunkunterstützungen in Skype for Business Server können Sie mehrere SIP-Signalisierungsports auf dem Vermittlungsserver für die Kommunikation mit mehreren PSTN-Gateways definieren. Beim Definieren eines Trunks muss sich der Port des **zugeordneten Vermittlungsservers** innerhalb des Bereichs der Überwachungsports für das entsprechende Protokoll befinden, das vom Vermittlungsserver zugelassen wird. Dieser Portbereich ist unter Skype for Business Server und Vermittlungspools definiert. Klicken Sie mit der rechten Maustaste auf den gewünschten Vermittlungsserverpool, und wählen Sie **"Eigenschaften bearbeiten"** aus. Geben Sie den Portbereich im Feld **Überwachungsports** an.
  
10. Stellen Sie sicher, dass der von Ihnen definierte Peer ausgeführt wird und den angegebenen FQDN oder die angegebene IP-Adresse verwendet. Klicken Sie dann auf **Fertig stellen**.
    
11. Klicken Sie mit der rechten Maustaste auf den **Knoten Skype for Business Server,** und klicken Sie dann auf **"Topologie veröffentlichen".**
    

