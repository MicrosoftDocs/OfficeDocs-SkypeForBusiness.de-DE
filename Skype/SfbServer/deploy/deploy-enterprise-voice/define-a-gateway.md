---
title: Definieren eines Gateways im Topologie-Generator in Skype for Business Server
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
ms.assetid: 456e5a96-d9f6-42a6-862c-a69464391628
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype for Business Server definieren.'
ms.openlocfilehash: 322c526c87c3a354f11fd0c906256b36e6df526e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233218"
---
# <a name="define-a-gateway-in-topology-builder-in-skype-for-business-server"></a>Definieren eines Gateways im Topologie-Generator in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie ein PSTN-Gateway im Topologie-Generator in Skype for Business Server definieren.
  
Führen Sie die folgenden Schritte aus, um mithilfe des Topologie-Generators einen Peer zu definieren, dem Sie einen Vermittlungs Server zuordnen können, um Verbindungen mit dem öffentlichen Telefonnetz (PSTN) für Benutzer bereitzustellen, die für Enterprise-VoIP aktiviert sind. Ein Peer-to-Mediation-Server kann ein PSTN-Gateway, eine IP-Telefonanlage oder ein Session Border Controller (SBC) für einen Internet-Telefoniedienstanbieter (ITSP) sein, mit dem Sie eine Verbindung herstellen, indem Sie einen SIP-Trunk konfigurieren.
  
### <a name="to-define-a-peer-for-the-mediation-server"></a>So definieren Sie einen Peer für den Vermittlungsserver

1. Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for Business Server 2015**, und klicken Sie dann auf **Skype for Business Server 2015Topology Builder**.
    
2. Klicken Sie unter Skype for Business Server, ihren Websitenamen, freigegebene Komponenten, mit der rechten Maustaste auf den Knoten **PSTN-Gateways** , und klicken Sie dann auf **Neues PSTN-Gateway**.
3. Geben Sie unter **Neues IP/PSTN-Gateway definieren** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) oder die IP-Adresse des Peers ein und klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Wenn Sie TLS (Transport Layer Security) als Transporttyp angeben, müssen Sie anstelle der IP-Adresse des Peers des Vermittlungsservers den FQDN angeben. 
  
4. Definieren Sie den Überwachungsmodus (IPv4 oder IPv6) für die IP-Adresse Ihres neuen PSTN-Gateways und klicken Sie auf **Weiter**.

5. Definieren Sie einen Stammtrunk für das PSTN-Gateway. Ein trunk ist eine logische Verbindung zwischen einem Vermittlungs Server und einem vom Tupel eindeutig identifizierten Gateway.
    
    {Vermittlungsserver-FQDN, Abhör Port für Mediationsserver (TLS oder TCP): Gateway-IP und-FQDN, Gateway-Überwachungs Port}
    
     - Wenn Sie ein PSTN-Gateway im Topologie-Generator definieren, müssen Sie einen Stamm Stamm definieren, um das PSTN-Gateway erfolgreich zu Ihrer Topologie hinzuzufügen.
    
     - Der Stammtrunk kann erst entfernt werden, nachdem das damit verbundene PSTN-Gateway entfernt wurde.
    
6. Geben Sie unter **Abhör Port für IP/PSTN-Gateway**den Abhöranschluss ein, den das Gateway, die Telefonanlage oder SBC für SIP-Nachrichten vom Vermittlungs Server verwenden, die dem Stammverzeichnis des PSTN-Gateways zugeordnet werden. (In der Standardeinstellung ist für ein PSTN-Gateway, eine Nebenstellenanlage oder einen SBC Port 5066 für TCP (Transmission Control Protocol) und Port 5067 für TLS (Transport Layer Security) festgelegt. Bei einer Survivable Branch-Appliance an einer Zweigstelle sind die Standardanschlüsse 5081 für TCP und 5082 für TLS.)
    
7. Klicken Sie unter **SIP-Transportprotokoll** auf das für den Peer zu verwendende Transportprotokoll und dann auf **OK**.
    
    > [!NOTE]
    > Aus Sicherheitsgründen empfehlen wir dringend, einen Peer auf dem Vermittlungs Server bereitzustellen, der TLS verwenden kann. 
  
8. Wählen Sie unter **zugeordneter Vermittlungsserver**den vermittlungsserverpool aus, der dem Stamm Stamm dieses PSTN-Gateways zugeordnet werden soll.
    
9. Geben Sie unter **zugeordneter Vermittlungsserver-Port**den Abhör Port ein, der vom Vermittlungsserver für SIP-Nachrichten vom Gateway verwendet wird.
    
    > [!NOTE]
    > Mit mehreren trunk-Unterstützung in Skype for Business Server können Sie mehrere SIP-Signalisierungs Anschlüsse auf dem Vermittlungsserver für die Kommunikation mit mehreren PSTN-Gateways definieren. Wenn Sie einen trunk definieren, muss sich der **zugeordnete Vermittlungsserver-Port** innerhalb des Bereichs der Abhör Anschlüsse für das jeweilige vom Vermittlungsserver zugelassene Protokoll befinden. Dieser Portbereich wird unter Skype for Business Server und Mediation Pools definiert. Klicken Sie mit der rechten Maustaste auf den Interessenbereich des Mediation Server-Pools, und wählen Sie **Eigenschaften bearbeiten**aus. Specify the port range in the **Listening ports** field.
  
10. Stellen Sie sicher, dass der Peer, den Sie definiert haben, ausgeführt wird und den angegebenen FQDN oder die angegebene IP-Adresse verwendet. Klicken Sie auf **Fertig stellen**.
    
11. Klicken Sie mit der rechten Maustaste auf den Knoten **Skype for Business Server** und dann auf **Topologie veröffentlichen**.
    

