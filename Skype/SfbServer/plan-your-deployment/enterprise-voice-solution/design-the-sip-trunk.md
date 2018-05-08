---
title: Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planen Ihre SIP-Trunking-Topologien für eine Bereitstellung von E9-1-1, die SIP-Trunking-Anbietern in Skype für Business Server Enterprise-VoIP verwendet wird.
ms.openlocfilehash: a04256bcad458b639777ec553289deb3c43ddd59
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server-2015"></a>Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server 2015
 
Planen Ihre SIP-Trunking-Topologien für eine Bereitstellung von E9-1-1, die SIP-Trunking-Anbietern in Skype für Business Server Enterprise-VoIP verwendet wird.
  
Skype für Business Server verwendet SIP-Trunks, um ein Notruf zum E9-1-1-Dienstanbieter zu verbinden. Sie können Notrufdienst-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jeder Zweigstelle einrichten. Jedoch zwischen dem Anrufer und der Website, die hostet die WAN-Verbindung der Notrufnummer SIP-Trunk ist nicht verfügbar, dann bei einem Anruf von einem Benutzer am Standort getrennte benötigen einen speziellen telefonverwendungsdatensatz in VoIP-Richtlinie des Benutzers, die den Anruf an weiterleiten, wird die ECRC über das Gateway lokalen public switched Telephone Network (Telefonfestnetz PSTN). Das gleiche trifft zu, wenn in der Anrufsteuerung Begrenzungen für gleichzeitige Anrufe aktiviert sind.
  
Es gibt zwei Methoden, um einen SIP-Trunk in einer Skype für Business Server-Umgebung zu implementieren:
  
- Verwenden Sie mehrfach vernetzte Mediation Server, mit denen ihre ausgerichteten öffentlich weitergeleiteten Schnittstellen zur Kommunikation mit SIP-Trunk-Dienstanbieter.
    
- Verwenden Sie eine lokale Session Border Controller (SBC), um eine sichere Trennung der Vermittlungsserver und den SIP-Trunk des Anbieters Dienste bereitzustellen.
    
Wenn Sie sich für die zweite Methode entscheiden, stellen Sie sicher, dass die Marke/das Modell des von Ihnen ausgewählten SBC die Weitergabe von PIDF-LO (Presence Information Data Format Location Object)-Standortdaten als Teil der SIP INVITE unterstützt. Andernfalls gehen die Anrufe ohne Standortinformationen beim Anbieter für die Notrufunterstützung ein. Ausführliche Informationen zu zertifizierten SBCs finden Sie unter ["Infrastruktur qualifizierte für Microsoft Lync"](https://go.microsoft.com/fwlink/p/?LinkId=248425) und ["Telefonie-Infrastruktur für Skype für Business"](https://technet.microsoft.com/en-us/office/dn947483).
  
Über E9-1-1-Dienstanbieter erhalten Sie Zugriff auf ein SBC-Paar, um Redundanz zu gewährleisten. Sie müssen mehrere Entscheidungen bezüglich der Topologie Vermittlungsserver, und rufen Sie routing-Konfiguration. Möchten Sie beide SBCs als gleichwertig behandeln und Roundrobinrouting für Anrufe zwischen ihnen verwenden oder werden Sie einen SBC als primären und den anderen als sekundären SBC festlegen?
  
Weitere Informationen zur Bereitstellung von SIP-Trunk in Skype für Business Server finden Sie unter [SIP-Trunking in Skype für Business Server 2015](sip-trunking.md). Zur einfacheren Bereitstellung der SIP-Trunks für E9-1-1 sollten Sie zunächst die folgenden Fragen beantworten.
  
 **Soll der SIP-Trunk über eine dedizierte geleaste oder eine gemeinsam genutzte Internetverbindung bereitgestellt werden?**
  
> Es ist wichtig, dass jederzeit Notrufe getätigt werden können. Eine dedizierte Leitung bietet eine Verbindung, die nicht durch anderen Datenverkehr im Netzwerk belegt ist, und ermöglicht gleichzeitig die Implementierung von QoS. Denken Sie daran, dass eine IPSec-Verschlüsselung erforderlich ist, wenn Sie beim Herstellen einer Verbindung mit Anbietern für die Notrufunterstützung über das öffentliche Internet die Vertraulichkeit von Notrufen gewährleisten müssen. 
    
 **Ist Ihre E9-1-1-Bereitstellung für ausfalltoleranz ausgelegt?**
  
> Da es sich um eine Lösung für Notrufe handelt, ist die Ausfallsicherheit von grundlegender Bedeutung. Bereitstellen der primären und sekundären Vermittlungsserver und dem SIP-Trunks in Disaster fehlertolerante Speicherorte. Es ist ratsam, Ihre primäre, die Benutzer am nächsten Vermittlungsserver bereitstellen, das es unterstützt und Route Failover von Anrufen über den sekundären Vermittlungsserver (befindet sich an einem anderen geografischen Standort). 
    
 **Sollten Sie einen separaten SIP-Trunk für jeden Zweigstellenstandort bereitstellen?**
  
> Skype für Business Server bietet mehrere Strategien für die Verarbeitung von VoIP-ausfallsicherheit in Zweigstellen, einschließlich: müssen ausfallsichere Datennetzwerke, einen SIP-Trunk in jeder Zweigstelle bereitstellen oder pushen von Anrufen an das lokale Gateway bei Ausfällen. Weitere Informationen hierzu finden Sie unter [SIP-Trunking in Skype für Business Server 2015](sip-trunking.md).
    
 **Ist die Anrufsteuerung aktiviert?**
  
> Skype für Business Server ist nicht Handle Notrufe eine anders als ein gewöhnliche Anruf. Aus diesem Grund kann sich die Bandbreitenverwaltung oder Anrufsteuerung negativ auf die E9-1-1-Konfiguration auswirken. Notrufe werden möglicherweise blockiert oder zum lokalen PSTN-Gateway geroutet, wenn die Anrufsteuerung aktiviert ist und der konfigurierte Grenzwert für die Verbindung überschritten wird, über die Notrufe geroutet werden. Wie bereits in diesem Thema besprochen verfügen solche Anrufe über keine Standortdaten und müssen manuell an das ECRC weitergeleitet werden.
    

