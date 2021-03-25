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
description: Planen Ihrer SIP-Trunkingtopologien für eine E9-1-1-Bereitstellung, die SIP-Trunkinganbieter verwendet, in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 8685b3263b9e3b6f98bc94e190ac9dd8207348df
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112691"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server
 
Planen Ihrer SIP-Trunkingtopologien für eine E9-1-1-Bereitstellung, die SIP-Trunkinganbieter verwendet, in Skype for Business Server Enterprise-VoIP.
  
Skype for Business Server verwendet SIP-Trunks, um einen Notruf mit dem E9-1-1-Dienstanbieter zu verbinden. Sie können NOTFALLdienst-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jedem Zweigstellenstandort einrichten. Wenn die WAN-Verbindung zwischen dem Standort des Anrufers und dem Standort, der den SIP-Trunk des Notrufdiensts hostet, nicht verfügbar ist, benötigt ein Anruf eines Benutzers am getrennten Standort einen speziellen Telefonnutzungsdatensatz in der Sprachrichtlinie des Benutzers, der den Anruf an das ECRC über das lokale PstN-Gateway weiterverleitunget. Dasselbe gilt, wenn gleichzeitige Anrufsteuerungsgrenzwerte gelten.
  
Es gibt zwei Möglichkeiten, einen SIP-Trunk in einer Skype for Business Server-Umgebung zu implementieren:
  
- Verwenden Sie multihomed Mediation Servers, die ihre nach außen gerichteten öffentlich gerouteten Schnittstellen verwenden, um mit dem SIP-Trunkanbieter zu kommunizieren.
    
- Verwenden Sie einen lokalen Session Border Controller (SBC), um einen sicheren Abgrenzungspunkt zwischen den Vermittlungsservern und den Diensten des SIP-Trunkanbieters zu bieten.
    
Wenn Sie die letztere Methode auswählen, stellen Sie sicher, dass das von Ihnen orientierte SBC-Modell und -Modell zertifiziert wurde und unterstützt das Übergeben von Standortdaten des Standortobjekts (Presence Information Data Format Location Object, PIDF-LO) im Rahmen der SIP-EINLADUNG. Andernfalls erreichen die Anrufe den Notrufdienstanbieter, der seine Standortinformationen entfernt. Weitere Informationen zu zertifizierten SBCs finden Sie unter   ["Infrastrukturqualifiziert](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) für Microsoft Lync" und ["Telefonieinfrastruktur für Skype for Business"](../../../SfbPartnerCertification/certification/infra-gateways.md). 
  
E9-1-1-Dienstanbieter bieten Ihnen Zugriff auf ein Paar sbCs für Redundanz. Sie müssen mehrere Entscheidungen in Bezug auf die Topologie des Vermittlungsservers und die Konfiguration des Anrufroutings treffen. Behandeln Sie beide SBCs als gleichrangig und verwenden Sie das Roundrobinrouting für Anrufe zwischen ihnen, oder werden Sie einen SBC als primär und den anderen als sekundär festlegen?
  
Weitere Informationen zum Bereitstellen eines SIP-Trunks in Skype for Business Server finden Sie unter [SIP-Trunking in Skype for Business Server](sip-trunking.md). Die folgenden Fragen helfen Ihnen bei der Entscheidung, wie sie die SIP-Trunks für E9-1-1 bereitstellen.
  
 **Sollten Sie den SIP-Trunk über eine dedizierte geleaste oder eine freigegebene Internetverbindung bereitstellen?**
  
> Es ist wichtig, dass notrufe immer eine Verbindung herstellen. Eine dedizierte Leitung stellt eine Verbindung zur Verfügung, die von keinem anderen Datenverkehr im Netzwerk vorab entfernt wird, und bietet Ihnen die Möglichkeit, QoS (Quality of Service) zu implementieren. Denken Sie daran, dass die IPSec-Verschlüsselung erforderlich ist, wenn Sie über das öffentliche Internet eine Verbindung zu Notrufanbietern herstellen und die Vertraulichkeit von Notrufen gewährleisten müssen. 
    
 **Ist Ihre E9-1-1-Bereitstellung auf Notfalltoleranz ausgelegt?**
  
> Da es sich um eine Notfalllösung handelt, ist Ausfallsicherheit wichtig. Stellen Sie ihre primären und sekundären Vermittlungsserver und SIP-Trunks an notfalltoleranten Standorten zur Verfügung. Es ist eine gute Idee, den primären Vermittlungsserver bereitzustellen, der den von ihm unterstützten Benutzern am nächsten ist, und Failoveraufrufe über den sekundären Vermittlungsserver (an einem anderen geografischen Standort) weiter zu führen. 
    
 **Sollten Sie einen separaten SIP-Trunk für jede Zweigstelle bereitstellen?**
  
> Skype for Business Server bietet verschiedene Strategien für die Behandlung der Ausfallsicherheit von Sprachnachrichten in Zweigstellen, z. B. die Bereitstellung ausfallsicherer Datennetzwerke, die Bereitstellung eines SIP-Trunks an jeder Zweigstelle oder das Pushen von Anrufen an das lokale Gateway während eines Ausfalls. Weitere Informationen finden Sie unter [SIP-Trunking in Skype for Business Server](sip-trunking.md).
    
 **Ist die Anrufsteuerung aktiviert?**
  
> Skype for Business Server führt notrufe nicht anders aus als ein gewöhnlicher Anruf. Aus diesem Grund kann sich die Bandbreitenverwaltung oder Anrufsteuerung negativ auf eine E9-1-1-Konfiguration auswirken. Notrufe werden blockiert oder an das lokale PSTN-Gateway geroutet, wenn eine Anrufverknung aktiviert ist und der konfigurierte Grenzwert auf einer Verbindung überschritten wird, über die Notrufe geroutet werden. Wie weiter oben in diesem Thema erwähnt, verfügen solche Anrufe nicht über Standortdaten und müssen manuell an das ECRC geroutet werden.
