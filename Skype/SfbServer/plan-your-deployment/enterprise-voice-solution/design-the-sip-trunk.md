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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
description: Planen Ihrer SIP-Trunkingtopologien für eine E9-1-1-Bereitstellung, die SIP-Trunkinganbieter verwendet, in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: b9a270a63ebfeb1e8132d84f270b72d6cd47710e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625167"
---
# <a name="design-the-sip-trunk-for-e9-1-1-in-skype-for-business-server"></a>Entwerfen des SIP-Trunks für E9-1-1 in Skype for Business Server
 
Planen Ihrer SIP-Trunkingtopologien für eine E9-1-1-Bereitstellung, die SIP-Trunkinganbieter verwendet, in Skype for Business Server Enterprise-VoIP.
  
Skype for Business Server verwendet SIP-Trunks, um einen Notruf mit dem E9-1-1-Dienstanbieter zu verbinden. Sie können Notfalldienst-SIP-Trunks für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jedem Zweigstellenstandort einrichten. Wenn jedoch die WAN-Verbindung zwischen dem Standort des Anrufers und dem Standort, an dem der SIP-Notfalldiensttrunk gehostet wird, nicht verfügbar ist, benötigt ein Anruf, der von einem Benutzer am getrennten Standort getätigt wird, einen speziellen Telefonverwendungsdatensatz in der VoIP-Richtlinie des Benutzers, der den Anruf über das lokale PSTN-Gateway an das ECRC weiterleitet. Dasselbe gilt, wenn gleichzeitige Anrufsteuerungsgrenzwerte gelten.
  
Es gibt zwei Möglichkeiten, einen SIP-Trunk in einer Skype for Business Server Umgebung zu implementieren:
  
- Verwenden Sie multihomed Mediation Server, die ihre nach außen gerichteten öffentlich weitergeleiteten Schnittstellen verwenden, um mit dem SIP-Trunkanbieter zu kommunizieren.
    
- Verwenden Sie einen lokalen Session Border Controller (SBC), um einen sicheren Abgrenzungspunkt zwischen den Vermittlungsservern und den Diensten des SIP-Trunkanbieters bereitzustellen.
    
Wenn Sie die zweite Methode auswählen, stellen Sie sicher, dass die SBC-Make und das Modell, das Sie auswählen, zertifiziert wurden und die Übergabe von PIDF-LO-Standortdaten (Presence Information Data Format Location Object) als Teil der SIP INVITE unterstützen. Andernfalls werden die Anrufe beim Anbieter des Notrufdienstes eintreffen, ohne dass die Standortinformationen entfernt wurden. Ausführliche Informationen zu zertifizierten SBCs finden Sie unter ["Für Microsoft Lync qualifizierte Infrastruktur"](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) und ["Telefonieinfrastruktur für Skype for Business".](../../../SfbPartnerCertification/certification/infra-gateways.md) 
  
E9-1-1-Dienstanbieter bieten Ihnen Zugriff auf ein SBCs-Paar zur Redundanz. Sie müssen mehrere Entscheidungen hinsichtlich der Topologie des Vermittlungsservers und der Anrufweiterleitungskonfiguration treffen. Werden Sie beide SBCs als gleichrangige Peers behandeln und Roundrobinrouting für Anrufe zwischen ihnen verwenden, oder legen Sie einen SBC als primär und den anderen als sekundär fest?
  
Ausführliche Informationen zum Bereitstellen eines SIP-Trunks in Skype for Business Server finden Sie unter [SIP-Trunking in Skype for Business Server.](sip-trunking.md) Die folgenden Fragen helfen Ihnen bei der Entscheidung, wie die SIP-Trunks für E9-1-1 bereitgestellt werden.
  
 **Sollten Sie den SIP-Trunk über eine dedizierte geleaste oder gemeinsam genutzte Internetverbindung bereitstellen?**
  
> Es ist wichtig, dass Notrufe immer eine Verbindung herstellen. Eine dedizierte Leitung stellt eine Verbindung bereit, der kein anderer Datenverkehr im Netzwerk vorangestellt wird, und bietet Ihnen die Möglichkeit, Quality of Service (QoS) zu implementieren. Denken Sie daran, dass eine IPSec-Verschlüsselung erforderlich ist, wenn Sie über das öffentliche Internet eine Verbindung mit Notrufdienstanbietern herstellen und die Vertraulichkeit von Notrufen gewährleisten müssen. 
    
 **Ist Ihre E9-1-1-Bereitstellung auf Notfalltoleranz ausgelegt?**
  
> Da es sich um eine Notfalllösung handelt, ist Resilienz wichtig. Stellen Sie Ihre primären und sekundären Vermittlungsserver und SIP-Trunks an notfalltoleranten Standorten bereit. Es empfiehlt sich, den primären Vermittlungsserver bereitzustellen, der den von ihm unterstützten Benutzern am nächsten kommt, und Failoveranrufe über den sekundären Vermittlungsserver (an einem anderen geografischen Standort) weiterzuleiten. 
    
 **Sollten Sie für jede Zweigstelle einen separaten SIP-Trunk bereitstellen?**
  
> Skype for Business Server bietet mehrere Strategien für die Behandlung von VoIP-Resilienz in Zweigstellen, einschließlich: Ausfallsicherheit von Datennetzwerken, Bereitstellen eines SIP-Trunks in jeder Zweigstelle oder Senden von Anrufen an das lokale Gateway bei Ausfällen. Ausführliche Informationen finden Sie unter [SIP-Trunking in Skype for Business Server.](sip-trunking.md)
    
 **Ist die Anrufsteuerung (Call Admission Control, CAC) aktiviert?**
  
> Skype for Business Server behandelt Notrufe nicht anders als normale Anrufe. Aus diesem Grund kann sich die Bandbreitenverwaltung oder Anrufsteuerung (Call Admission Control, CAC) negativ auf eine E9-1-1-Konfiguration auswirken. Notrufe werden blockiert oder an das lokale PSTN-Gateway weitergeleitet, wenn eine Anrufsteuerung aktiviert ist und der konfigurierte Grenzwert für eine Verbindung überschritten wird, an die Notrufe weitergeleitet werden. Wie weiter oben in diesem Thema erwähnt, weisen solche Anrufe keine Standortdaten auf und müssen manuell an das ECRC weitergeleitet werden.
