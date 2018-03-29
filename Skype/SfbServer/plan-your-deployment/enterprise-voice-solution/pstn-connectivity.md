---
title: Komponenten für die PSTN-Konnektivität in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Erfahren Sie mehr über SIP-Trunking und PSTN-Gateways für Enterprise-VoIP in Skype für Business Server.
ms.openlocfilehash: 051066643649f9f8f872f4a2795e5ea71417d810
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="pstn-connectivity-components-in-skype-for-business-server-2015"></a>Komponenten für die PSTN-Konnektivität in Skype for Business Server 2015
 
Erfahren Sie mehr über SIP-Trunking und PSTN-Gateways für Enterprise-VoIP in Skype für Business Server.
  
Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird. Außerdem sollte die zugrunde liegende Technologie für Benutzer, die Anrufe tätigen und empfangen, unbemerkt im Hintergrund arbeiten. Aus Sicht des Benutzers sollte ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz wie jede andere SIP-Sitzung scheint.
  
Für PSTN-Verbindungen können Sie entweder einen SIP-Trunk oder ein PSTN-Gateway bereitstellen – mit Nebenstellenanlage (was auch als direkte SIP-Verbindung bezeichnet wird) oder ohne Nebenstellenanlage.
  
## <a name="sip-trunking"></a>SIP-Trunking

Als Alternative zur Verwendung von PSTN-Gateways können Sie Ihre Enterprise-VoIP-Lösung mithilfe von SIP-Trunking an das Telefonfestnetz verbinden. Mit SIP-Trunking sind folgende Szenarien möglich:
  
- Ein Benutzer eines Unternehmens innerhalb oder außerhalb der Unternehmensfirewall kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer führen, das im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters beendet wird.
    
- Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID-Nummer (Direct Inward Dialing) wählt, die dem Unternehmensbenutzer zugeordnet ist.
    
Für diese Bereitstellungslösung ist ein SIP-Trunking-Dienstanbieter erforderlich. 
  
## <a name="pstn-gateways"></a>PSTN-Gateways

PSTN-Gateways sind Drittanbieter-Geräte, die übersetzen Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und einem PSTN oder einer Nebenstellenanlage. PSTN-Gateways arbeiten mit der Vermittlungsserver einen PSTN oder PBX-Anruf an einen Enterprise-VoIP-Client durchzuführen. Der Vermittlungsserver übergibt außerdem Anrufe von Enterprise-VoIP-Clients an das PSTN-Gateway für die Weiterleitung an das PSTN oder PBX-Ressource. Eine Liste der Partner, die mit Microsoft-Geräte bereitstellen, die Arbeit mit Skype für Business Server arbeiten, finden Sie unter [Microsoft Unified Communications-Partnerseite](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Nebenstellenanlagen

 Wenn Sie eine vorhandene VoIP-Infrastruktur, die eine private Branch Exchange, Nebenstellenanlage (PBX) verwendet haben, können Sie Ihre Nebenstellenanlage mit Enterprise-VoIP.
  
Die unterstützten Enterprise Voice-PBX-Integrationsszenarien sind wie folgt:
  
- IP-Nebenstellenanlage, die die medienumgehung mit einem Vermittlungsserver unterstützt.
    
- IP-Nebenstellenanlage, die ein eigenständiges PSTN-Gateway erfordert.
    
- TDM-Nebenstellenanlage (Time Division Multiplexing) mit eigenständigem PSTN-Gateway.
    
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten unterstützt und Versionen am aufgeführten [Unified Communications Open Interoperability Program – Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Ausführliche Informationen zu Partnern, die Enterprise-VoIP-Lösungen anbieten, finden Sie in der [Microsoft Unified Communications-Partnerseite](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Ausführliche Informationen zu Partnern, die Enterprise-VoIP-hardwarelösungen, einschließlich PSTN-Gateways anbieten finden Sie in der [Microsoft Unified Communications-Partnerseite](https://go.microsoft.com/fwlink/p/?linkId=202836).
  

