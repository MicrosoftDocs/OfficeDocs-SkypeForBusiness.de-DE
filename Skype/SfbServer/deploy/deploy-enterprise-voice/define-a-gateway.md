---
title: Definieren eines Gateways im Topologie-Generator in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Zusammenfassung: Erfahren Sie, wie ein PSTN-Gateway im Topologie-Generator in Skype für Business Server 2015 zu definieren.'
ms.openlocfilehash: ae8656d60d819a92a22db6e97f83ea847ee15765
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server-2015"></a>Definieren eines Gateways im Topologie-Generator in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype für Business Server 2015 definieren.
  
Befolgen Sie diese Schritte, um die Topologie-Generator verwenden, um einen Peer zu definieren, mit dem Sie einen Vermittlungsserver zum Bereitstellen der Verbindung mit dem öffentlichen Telefonfestnetz (PSTN) für Benutzer für Enterprise Voice aktiviert zuordnen können. Ein Peer für den Vermittlungsserver kann ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein Session Border Controller (SBC) für einen Internet Telefonie Service Provider (ITSP), die durch konfigurieren einen SIP-Trunk verbunden.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>So definieren Sie einen Peer für den Vermittlungsserver

1. Starten des Topologie-Generators: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business Server 2015**, und klicken Sie dann auf **Skype für Business Server 2015Topology-Generator**.
    
2. Klicken Sie unter Skype für Business Server, Ihr Sitename, freigegebene Komponenten, Maustaste auf den Knoten **PSTN-Gateways** , und klicken Sie dann auf **Neues PSTN-Gateway**.
3. Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein und klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Wenn Sie Transport Layer Security (TLS) als Transportprotokoll angeben, müssen Sie den FQDN anstelle der IP-Adresse des Peers für den Vermittlungsserver angeben. 
  
4. Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateways und klicken Sie auf **Weiter**.

5. Definieren Sie einen stammtrunk für die PSTN-Gateway. Ein Trunk ist eine logische Verbindung zwischen einem Vermittlungsserver und einem Gateway durch Folgendes Tupel eindeutig identifiziert.
    
    {Mediation Server-FQDN, Vermittlungsserver Überwachungsport (TLS oder TCP): Gateway-IP und FQDN, gatewayüberwachungsport}
    
     - Wenn Sie ein PSTN-Gateway im Topologie-Generator zu definieren, müssen Sie einen stammtrunk, um das PSTN-Gateway zu einer Topologie erfolgreich hinzuzufügen definieren.
    
     - Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.
    
6. Geben Sie unter **Überwachungsport für IP/PSTN-Gateway**den Überwachungsport, den das Gateway, der Nebenstellenanlage oder der SBC für SIP-Nachrichten vom Vermittlungsserver verwendet, der dem stammtrunk das PSTN-Gateway zugeordnet werden. (In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt. Survivable Branch Appliance am Zweigstellenstandort sind die Standardports 5081 für TCP und 5082 für TLS.)
    
7. Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll und dann auf **OK**.
    
    > [!NOTE]
    > Aus Sicherheitsgründen wird dringend empfohlen, einen Peer für den Vermittlungsserver bereitzustellen, der TLS verwenden kann. 
  
8. Wählen Sie unter **Zugeordneter Vermittlungsserver**den vermittlungsserverpool, die dem stammtrunk dieses PSTN-Gateway zugeordnet.
    
9. Geben Sie unter **zugeordneter Vermittlungsserver Port**den Überwachungsport, den der Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet wird.
    
    > [!NOTE]
    > Mit Unterstützung mehrerer Trunks in Skype für Business Server können Sie mehrere SIP-Signalisierung Ports auf dem Vermittlungsserver für die Kommunikation mit mehreren PSTN-Gateways definieren. Wenn Sie einen Trunk zu definieren, muss der **zugeordneter Vermittlungsserver Port** innerhalb des Bereichs von die Überwachungsports für das jeweilige Protokoll vom Vermittlungsserver zulässig sein. Dieser Portbereich ist unter Skype für Business Server und Vermittlungspools definiert. Mit der rechten Maustaste vermittlungsserverpool von Interesse, und wählen Sie **Eigenschaften bearbeiten**. Geben Sie den Portbereich im Feld **Überwachungsports** ein.
  
10. Stellen Sie sicher, dass der Peer, den Sie definiert haben, ausgeführt wird und den angegebenen FQDN oder die angegebene IP-Adresse verwendet. Klicken Sie auf **Fertig stellen**.
    
11. Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server** und dann auf **Topologie veröffentlichen**.
    

