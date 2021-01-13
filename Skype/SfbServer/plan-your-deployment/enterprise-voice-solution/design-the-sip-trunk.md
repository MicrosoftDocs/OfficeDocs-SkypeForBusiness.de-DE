---
title: Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server
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
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planen Ihrer SIP-Trunking-Topologien für eine E9-1-1-Bereitstellung, die SIP-Trunking-Anbieter verwendet, in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: ef30d721b59f29885004ee948055a91ca8af9490
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825795"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server
 
Planen Ihrer SIP-Trunking-Topologien für eine E9-1-1-Bereitstellung, die SIP-Trunking-Anbieter verwendet, in Skype for Business Server Enterprise-VoIP.
  
Skype for Business Server verwendet SIP-Trunks, um einen Notruf mit dem E9-1-1-Dienstanbieter zu verbinden. Sie können Notruf-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jedem Zweigstellenstandort einrichten. Wenn die WAN-Verbindung zwischen dem Standort des Anrufers und dem Standort, der den Notruf-SIP-Trunk hostet, jedoch nicht verfügbar ist, benötigt ein Anruf, der von einem Benutzer am getrennten Standort angerufen wird, einen speziellen Telefonverwendungsdatensatz in der Sprachrichtlinie des Benutzers, der den Anruf über das lokale PstN-Gateway an das ECRC weiterroutet. Dies gilt auch, wenn Grenzwerte für gleichzeitige Anrufe für die Anrufsteuerung gelten.
  
Es gibt zwei Möglichkeiten, einen SIP-Trunk in einer Skype for Business Server-Umgebung zu implementieren:
  
- Verwenden Sie multihomed Mediation Servers, die ihre nach außen gerichteten öffentlich gerouteten Schnittstellen für die Kommunikation mit dem SIP-Trunk-Anbieter verwenden.
    
- Verwenden Sie einen lokalen Session Border Controller (SBC), um einen sicheren Abgrenzungspunkt zwischen den Vermittlungsservern und den Diensten des SIP-Trunkanbieters zu bieten.
    
Wenn Sie sich für die zweite Methode entscheiden, stellen Sie sicher, dass die SBC-Make-And-Model, die Sie auswählen, zertifiziert wurden und das Übergeben von Standortdaten (Presence Information Data Format Location Object, PIDF-LO) als Teil der SIP INVITE unterstützt. Andernfalls werden die Anrufe an den Anbieter der Notrufdienste ohne Standortinformationen eintreffen. Weitere Informationen zu zertifizierten SBCs finden Sie unter   ["Infrastrukturqualifiziert für Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) und ["Telefonieinfrastruktur für Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
E9-1-1-Dienstanbieter bieten Ihnen Zugriff auf ein Paar sbCs für Redundanz. Sie müssen mehrere Entscheidungen hinsichtlich der Topologie des Vermittlungsservers und der Anrufroutingkonfiguration treffen. Behandeln Sie beide SBCs als gleichrangig und verwenden Sie Roundrobinrouting für Anrufe zwischen ihnen, oder werden Sie einen SBC als primären und den anderen als sekundär festlegen?
  
Weitere Informationen zum Bereitstellen eines SIP-Trunks in Skype for Business Server finden Sie unter ["SIP-Trunking" in Skype for Business Server.](sip-trunking.md) Die folgenden Fragen helfen Ihnen bei der Entscheidung, wie die SIP-Trunks für E9-1-1 bereitgestellt werden sollen.
  
 **Sollten Sie den SIP-Trunk über eine dedizierte geleaste oder eine freigegebene Internetverbindung bereitstellen?**
  
> Es ist wichtig, dass notrufe immer eine Verbindung herstellen. Eine dedizierte Leitung stellt eine Verbindung zur Verfügung, die nicht durch anderen Datenverkehr im Netzwerk vorausbeschäftigt wird, und bietet Ihnen die Möglichkeit, Quality of Service (QoS) zu implementieren. Denken Sie daran, dass die IPSec-Verschlüsselung erforderlich ist, wenn Sie über das öffentliche Internet eine Verbindung mit Notrufanbietern herstellen und die Vertraulichkeit von Notrufen gewährleisten müssen. 
    
 **Ist Ihre E9-1-1-Bereitstellung auf Notfalltoleranz ausgelegt?**
  
> Da es sich um eine Notfalllösung handelt, ist Resilienz wichtig. Stellen Sie ihre primären und sekundären Vermittlungsserver und -trunks an notfalltoleranten Standorten zur Verfügung. Es ist eine gute Idee, den primären Vermittlungsserver bereitzustellen, der den unterstützten Benutzern am nächsten kommt, und Failoveranrufe über den sekundären Vermittlungsserver (an einem anderen geografischen Standort) weiter zu führen. 
    
 **Sollten Sie für jede Zweigstelle einen separaten SIP-Trunk bereitstellen?**
  
> Skype for Business Server bietet mehrere Strategien für die Behandlung von Ausfallsicherheit für Sprachnachrichten in Zweigstellen, darunter: Ausfallsicherheit von Datennetzwerken, Bereitstellen eines SIP-Trunks an jeder Zweigstelle oder Senden von Anrufen an das lokale Gateway während eines Ausfalls. Weitere Informationen finden Sie unter ["SIP-Trunking" in Skype for Business Server.](sip-trunking.md)
    
 **Ist die Anrufsteuerung aktiviert?**
  
> Skype for Business Server führt Notrufe nicht anders als normale Anrufe aus. Aus diesem Grund kann die Bandbreitenverwaltung oder anrufsteuerung negative Auswirkungen auf eine E9-1-1-Konfiguration haben. Notrufe werden blockiert oder an das lokale PstN-Gateway geroutet, wenn eine Anrufanrufanrufe aktiviert ist und der konfigurierte Grenzwert für eine Verbindung überschritten wird, über die Notrufe geroutet werden. Wie weiter oben in diesem Thema erwähnt, verfügen solche Anrufe nicht über Standortdaten und müssen manuell an das ECRC geroutet werden.
    

