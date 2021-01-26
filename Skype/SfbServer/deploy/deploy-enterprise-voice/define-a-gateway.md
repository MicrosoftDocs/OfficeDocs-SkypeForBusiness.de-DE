---
title: Definieren eines Gateways im Topologie-Generator in Skype for Business Server
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Zusammenfassung: Informationen zum Definieren eines PSTN-Gateways im Topologie-Generator in Skype for Business Server.'
ms.openlocfilehash: be68c853cdcd530b05ad4b0949f722788e77d0df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837025"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definieren eines Gateways im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype for Business Server definieren.
  
Führen Sie die folgenden Schritte aus, um den Topologie-Generator zu verwenden, um einen Peer zu definieren, dem Sie einen Vermittlungsserver zuordnen können, um Benutzern, die für den Zugriff aktiviert sind, eine Verbindung mit dem Telefonnetz (Public Switched Telephone Network, PSTN) Enterprise-VoIP. Ein Peer zum Vermittlungsserver kann ein PSTN-Gateway, eine IP-PBX-Anlage oder ein SBC (Session Border Controller) für einen Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP) sein, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>So definieren Sie einen Peer für den Vermittlungsserver

1. Starten Sie den Topologie-Generator: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business Server 2015"** und dann auf **"Skype for Business Server 2015Topology Builder".**
    
2. Klicken Sie unter Skype for Business Server, Standortname, freigegebene Komponenten mit der rechten Maustaste auf den Knoten **"PSTN-Gateways",** und klicken Sie dann auf **"Neues PSTN-Gateway".**
3. Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein, und klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers des Vermittlungsservers angeben. 
  
4. Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateway, und klicken Sie auf **Weiter**.

5. Definieren Sie einen Stammtrunk für das PSTN-Gateway. Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway, das durch das Tupel eindeutig identifiziert wird.
    
    {Vermittlungsserver-FQDN, Vermittlungsserver-Abhörport (TLS oder TCP): Gateway-IP und FQDN, Gateway-Listening-Port}
    
     - Beim Definieren eines PSTN-Gateways im Topologie-Generator müssen Sie einen Stamm trunk definieren, um das PstN-Gateway erfolgreich zu Ihrer Topologie hinzuzufügen.
    
     - Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.
    
6. Geben Sie unter "Abhörport für **IP/PSTN-Gateway"** den Abhörport ein, den das Gateway, die Nebenstellenanlage oder der SBC für SIP-Nachrichten vom Vermittlungsserver verwendet, die dem Stamm trunk des PSTN-Gateways zugeordnet werden. (In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt. Bei einer Survivable Branch Appliance an einem Zweigstellenstandort sind die Standardports 5081 für TCP und 5082 für TLS.)
    
7. Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll, und klicken Sie dann auf **OK**.
    
    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, dass Sie einen Peer auf dem Vermittlungsserver bereitstellen, der TLS verwenden kann. 
  
8. Wählen **Sie unter Zugeordneter Vermittlungsserver** den Vermittlungsserverpool aus, der dem Stamm trunk dieses PSTN-Gateways zugeordnet werden soll.
    
9. Geben **Sie unter "Zugeordneter Vermittlungsserverport"** den Abhörport ein, den der Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet.
    
    > [!NOTE]
    > Mit der Unterstützung mehrerer Trunks in Skype for Business Server können Sie mehrere SIP-Signalports auf dem Vermittlungsserver für die Kommunikation mit mehreren PSTN-Gateways definieren. Beim Definieren eines Trunks muss sich der **Port** des zugeordneten Vermittlungsservers innerhalb des Bereichs der Abhörports für das entsprechende Protokoll befinden, das vom Vermittlungsserver zugelassen wird. Dieser Portbereich wird unter Skype for Business Server und Vermittlungspools definiert. Klicken Sie mit der rechten Maustaste auf den Vermittlungsserverpool, und wählen Sie **"Eigenschaften bearbeiten" aus.** Geben Sie den Portbereich im Feld **Überwachungsports** an.
  
10. Stellen Sie sicher, dass der von Ihnen definierte Peer ausgeführt wird und den von Ihnen angegebenen FQDN oder die angegebene IP-Adresse verwendet. Klicken Sie dann auf **Fertig stellen**.
    
11. Klicken Sie mit der rechten Maustaste auf den **Knoten "Skype for Business Server",** und klicken Sie dann **auf "Topologie veröffentlichen".**
    

