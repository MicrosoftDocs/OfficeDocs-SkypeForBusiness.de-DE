---
title: Komponenten für die Festnetzanbindung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Erfahren Sie mehr über das SIP-Trunking und pstN-Gateways für Enterprise-VoIP in Skype for Business Server.
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813535"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Komponenten für die Festnetzanbindung in Skype for Business Server
 
Erfahren Sie mehr über das SIP-Trunking und pstN-Gateways für Enterprise-VoIP in Skype for Business Server.
  
Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird. Außerdem sollte die zugrunde liegende Technologie für Benutzer, die Anrufe tätigen und empfangen, unbemerkt im Hintergrund arbeiten. Aus Benutzersicht sollte ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz wie eine ganz normale SIP-Sitzung wirken.
  
Für Festnetzverbindungen können Sie entweder einen SIP-Trunk oder ein PstN-Gateway (mit einer Nebenstellenanlage, auch als direkte SIP-Verbindung bekannt, oder ohne Nebenstellenanlage) bereitstellen.
  
## <a name="sip-trunking"></a>SIP-Trunking

Als Alternative zu PSTN-Gateways können Sie Ihre Enterprise-VoIP-Lösung mithilfe von SIP-Trunking mit dem Telefonfestnetz verbinden. Mit SIP-Trunking sind folgende Szenarien möglich:
  
- Ein Benutzer eines Unternehmens innerhalb oder außerhalb der Unternehmensfirewall kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer führen, das im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters beendet wird.
    
- Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID-Nummer (Direct Inward Dialing) wählt, die dem Unternehmensbenutzer zugeordnet ist.
    
Für diese Bereitstellungslösung ist ein SIP-Trunking-Dienstanbieter erforderlich. 
  
## <a name="pstn-gateways"></a>PSTN-Gateways

Bei PSTN-Gateways handelt es sich um Drittanbietergeräte, die Signale und Mediendaten zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz oder einer Nebenstellenanlage übersetzen. PSTN-Gateways arbeiten mit dem Vermittlungsserver zusammen, um Anrufe aus dem Festnetz oder über eine Nebenstellenanlage an einen Enterprise-VoIP-Client zu übergeben. Der Vermittlungsserver übergibt außerdem Anrufe von Enterprise-VoIP-Clients an das PSTN-Gateway, damit dieses sie an das Telefonfestnetz oder die Nebenstellenanlage weiterleitet. Eine Liste der Partner, die mit Microsoft zusammenarbeiten, um Geräte zur Verfügung zu stellen, die mit Skype for Business Server funktionieren, finden Sie auf der [Microsoft Unified Communications Partners-Website.](https://go.microsoft.com/fwlink/p/?linkId=202836) 
  
## <a name="private-branch-exchanges"></a>Nebenstellenanlagen

 Wenn Sie über eine vorhandene Voiceinfrastruktur verfügen, die eine Nebenstellenanlage (Private Branch Exchange, PBX) verwendet, können Sie Ihre Nebenstellenanlage mit Enterprise-VoIP.
  
Die folgenden Szenarien mit Integration von Enterprise-VoIP und einer Nebenstellenanlage werden unterstützt:
  
- IP-Nebenstellenanlage mit Unterstützung der Medienumgehung und einem Vermittlungsserver.
    
- IP-Nebenstellenanlage, die ein eigenständiges PSTN-Gateway erfordert.
    
- TDM-Nebenstellenanlage (Time Division Multiplexing) mit eigenständigem PSTN-Gateway.
    
> [!NOTE]
> Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur für Produkte und Versionen unterstützt, die im [Unified Communications Open Interoperability Program - Lync Server aufgeführt sind.](https://go.microsoft.com/fwlink/p/?linkId=214406) 
  
Details zu Partnern, die Enterprise-VoIP anbieten, finden Sie auf der [Microsoft Unified Communications Partners-Website.](https://go.microsoft.com/fwlink/p/?linkId=202836)
  
Weitere Informationen zu Partnern, die Enterprise-VoIP hardwarelösungen, einschließlich PSTN-Gateways, anbieten, finden Sie auf der [Microsoft Unified Communications Partners-Website.](https://go.microsoft.com/fwlink/p/?linkId=202836)
  

