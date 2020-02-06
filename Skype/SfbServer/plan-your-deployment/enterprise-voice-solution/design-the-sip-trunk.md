---
title: Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planen Ihrer SIP-Trunking-Topologien für eine E9-1-1-Bereitstellung, die SIP-Trunking-Anbieter verwendet, in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: bd310b39affbea9b4d9328c66b54712c0d388b8d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803075"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server
 
Planen Ihrer SIP-Trunking-Topologien für eine E9-1-1-Bereitstellung, die SIP-Trunking-Anbieter verwendet, in Skype for Business Server Enterprise-VoIP
  
Skype for Business Server verwendet SIP-Trunks, um einen Notruf mit dem E9-1-1-Service-Anbieter zu verbinden. Sie können Notrufdienst-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jeder Zweigstelle einrichten. Wenn jedoch die WAN-Verbindung zwischen der Website des Anrufers und der Website, die den SIP-Stamm des Notfall Diensts hostet, nicht verfügbar ist, benötigt ein Anruf eines Benutzers an der getrennten Website einen speziellen Telefon Nutzungs Eintrag in der VoIP-Richtlinie des Benutzers, der den Anruf an die ECRC Sie über das lokale PSTN-Gateway (Public Switched Telephone Network). Das gleiche trifft zu, wenn in der Anrufsteuerung Begrenzungen für gleichzeitige Anrufe aktiviert sind.
  
Es gibt zwei Möglichkeiten, einen SIP-Trunk in einer Skype for Business Server-Umgebung zu implementieren:
  
- Verwenden Sie mehrfach vernetzte Vermittlungsserver, die ihre nach außen gerichteten, öffentlich weitergeleiteten Schnittstellen verwenden, um mit dem SIP-Trunk-Anbieter zu kommunizieren.
    
- Verwenden Sie einen lokalen Session Border Controller (SBC), um einen sicheren abgrenzungspunkt zwischen den Vermittlungsservern und den Diensten des SIP Trunk-Anbieters bereitzustellen.
    
Wenn Sie sich für die zweite Methode entscheiden, stellen Sie sicher, dass die Marke/das Modell des von Ihnen ausgewählten SBC die Weitergabe von PIDF-LO (Presence Information Data Format Location Object)-Standortdaten als Teil der SIP INVITE unterstützt. Andernfalls gehen die Anrufe ohne Standortinformationen beim Anbieter für die Notrufunterstützung ein. Details zu zertifizierten SBCS finden Sie unter ["für Microsoft lync qualifizierte Infrastruktur](https://go.microsoft.com/fwlink/p/?LinkId=248425) " und ["Telefonie-Infrastruktur für Skype for Business"](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
Über E9-1-1-Dienstanbieter erhalten Sie Zugriff auf ein SBC-Paar, um Redundanz zu gewährleisten. Sie müssen mehrere Entscheidungen bezüglich der Mediations Server Topologie und der Konfiguration des Anruf Routings treffen. Möchten Sie beide SBCs als gleichwertig behandeln und Roundrobinrouting für Anrufe zwischen ihnen verwenden oder werden Sie einen SBC als primären und den anderen als sekundären SBC festlegen?
  
Details zum Bereitstellen eines SIP-Trunks in Skype for Business Server finden Sie unter [SIP-Trunking in Skype for Business Server](sip-trunking.md). Zur einfacheren Bereitstellung der SIP-Trunks für E9-1-1 sollten Sie zunächst die folgenden Fragen beantworten.
  
 **Soll der SIP-Trunk über eine dedizierte geleaste oder eine gemeinsam genutzte Internetverbindung bereitgestellt werden?**
  
> Es ist wichtig, dass jederzeit Notrufe getätigt werden können. Eine dedizierte Leitung bietet eine Verbindung, die nicht durch anderen Datenverkehr im Netzwerk belegt ist, und ermöglicht gleichzeitig die Implementierung von QoS. Denken Sie daran, dass eine IPSec-Verschlüsselung erforderlich ist, wenn Sie beim Herstellen einer Verbindung mit Anbietern für die Notrufunterstützung über das öffentliche Internet die Vertraulichkeit von Notrufen gewährleisten müssen. 
    
 **Ist Ihre E9-1-1-Bereitstellung für die Notfalltoleranz konzipiert?**
  
> Da es sich um eine Lösung für Notrufe handelt, ist die Ausfallsicherheit von grundlegender Bedeutung. Stellen Sie Ihre primären und sekundären Vermittlungsserver und SIP-Stämme in Disaster-toleranten Speicherorten bereit. Es empfiehlt sich, den primären Vermittlungsserver den Benutzern, die er unterstützt, am nächsten zu stellen und Failover-Anrufe über den sekundären Vermittlungsserver (an einem anderen geografischen Standort) weiterzuleiten. 
    
 **Sollten Sie einen separaten SIP-Trunk für jeden Zweigstellenstandort bereitstellen?**
  
> Skype for Business Server bietet verschiedene Strategien für die Behandlung von sprach Stabilität in Zweigniederlassungen, einschließlich: mit belastbaren Datennetzwerken, Bereitstellungeines SIP-Trunks an jeder Verzweigung oder durch Pushen von Anrufen beim Ausfall des lokalen Gateways. Ausführliche Informationen finden Sie unter [SIP-Trunking in Skype for Business Server](sip-trunking.md).
    
 **Ist die Anrufsteuerung aktiviert?**
  
> Skype for Business Server behandelt keine Notrufe anders als normale Anrufe. Aus diesem Grund kann sich die Bandbreitenverwaltung oder Anrufsteuerung negativ auf die E9-1-1-Konfiguration auswirken. Notrufe werden möglicherweise blockiert oder zum lokalen PSTN-Gateway geroutet, wenn die Anrufsteuerung aktiviert ist und der konfigurierte Grenzwert für die Verbindung überschritten wird, über die Notrufe geroutet werden. Wie bereits in diesem Thema besprochen verfügen solche Anrufe über keine Standortdaten und müssen manuell an das ECRC weitergeleitet werden.
    

