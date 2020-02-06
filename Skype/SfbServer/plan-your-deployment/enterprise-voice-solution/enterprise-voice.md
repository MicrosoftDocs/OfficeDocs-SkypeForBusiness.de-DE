---
title: Planen von Enterprise-VoIP in Skype for Business Server
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Grundlagen der Enterprise-VoIP-Planung in Skype for Business Server, einschließlich Websites, Regionen, Netzwerkverbindungen zwischen Websites und schätzen des Zugriffs auf die sprach Nutzung.
ms.openlocfilehash: 7ef2a37a1ab39dd9c2e40544e06cfb995e846f7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802895"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planen von Enterprise-VoIP in Skype for Business Server
 
Grundlagen der Enterprise-VoIP-Planung in Skype for Business Server, einschließlich Websites, Regionen, Netzwerkverbindungen zwischen Websites und schätzen des Zugriffs auf die sprach Nutzung.
  
Der Bereitstellungsprozess für Enterprise-VoIP hängt von Ihrer vorhandenen Topologie, Infrastruktur und der Enterprise-VoIP-Funktionalität ab, die Sie unterstützen möchten. Die erforderlichen Verfahren hängen von den von Ihnen ausgewählten Funktionen ab, aber Sie müssen weitere allgemeine Planungsentscheidungen treffen.
  
In der Regel sollten Sie den Typ und die Anzahl der Websites, die Sie bereitstellen möchten, und deren geographische Speicherorte, das Anrufaufkommen an jedem Standort, die Typen von Netzwerk Links, die Websites verbinden, und zwar unabhängig davon, ob Sie Redundanz und Failover für die Sprachfunktionalität für jeden verwenden möchten. Website, und ob Sie vorhandene PBX-Anlagen verwenden möchten. Bei der Planung von Skype for Business Server als Ganzes sollten Sie bestimmte Aspekte berücksichtigen, beispielsweise die Höchstverfügbarkeit. Diese Überlegungen werden nach Bedarf in den Themen in diesem Abschnitt erläutert.
  
## <a name="sites-and-regions"></a>Standorte und Regionen

Identifizieren Sie zunächst die Websites in Ihrer Topologie, in denen Sie Enterprise-VoIP und die netzwerkregionen bereitstellen, denen diese Websites angehören. Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird. Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein. Entscheiden Sie, wo Gateways lokal bereitgestellt werden sollen, wo Survival Branch Appliances (SBAS) bereitgestellt werden und wo Sie SIP-Trunks (lokal oder am zentralen Standort) an einen Internet-Telefoniedienst (ITSP) konfigurieren können.
  
## <a name="network-links-between-sites"></a>Netzwerkverbindungen zwischen Standorten

Sie müssen auch die Bandbreitennutzung in Frage stellen, die Sie bei den Netzwerkverbindungen zwischen ihrer zentralen Website und ihren Zweigstellen erwarten. Wenn Sie über eine stabile WAN-Verbindung zwischen Websites verfügen oder diese bereitstellen möchten, empfiehlt es sich, ein Gateway an jeder Verzweigungs Website bereitzustellen, um den Benutzern an diesen Standorten eine direkte Durchwahl (DID)-Kündigung zu ermöglichen. Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, aber die Bandbreite einer WAN-Verbindung wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung. Wenn Sie nicht über belastbare WAN-Links verfügen, weniger als 1000-Benutzer an ihrer Zweigstelle hosten und keine lokal geschulten Skype for Business Server-Administratoren verfügbar sind, empfehlen wir, dass Sie eine Survivable Branch-Appliance an der Zweigstelle bereitstellen. Wenn Sie zwischen 1000-und 5000-Benutzern an ihrer Zweigstelle hosten, keine robuste WAN-Verbindung haben und Skype for Business Server-Administratoren geschult haben, empfiehlt es sich, einen überlebensfähigen Verzweigungs Server mit einem kleinen Gateway an der Zweigstelle bereitzustellen. Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.
  
## <a name="estimating-voice-usage-and-traffic"></a>Schätzen von VoIP-Nutzung und -Datenverkehr

Das Planungs Tool für Microsoft lync Server 2013 verwendet die folgende Metrik, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die für die Unterstützung des Datenverkehrs erforderlich sind.
  
> Für **geringes Datenverkehrsaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.
> 
> Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.
> 
> Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.
    
Die Anzahl der Ports wiederum bestimmt die Anzahl der Vermittlungsserver und Gateways, die erforderlich sind. Die PSTN-Gateways (Public Switched Telephone Network), die in den meisten Organisationen für die Bereitstellung von Bereichsgröße von 2 Anschlüssen bis zu 960-Ports in Frage kämen. (Es gibt sogar größere Gateways, die aber hauptsächlich von Telefondienstanbietern verwendet werden.)
  
Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Komponenten, Features und Optionen von Enterprise-VoIP

Weitere Informationen zum Planen Ihrer Enterprise-VoIP-Bereitstellung finden Sie in den folgenden Abschnitten.
  
- [Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind](components-required-for-enterprise-voice.md)
    
- [Planen der PSTN-Konnektivität in Skype for Business Server](pstn-connectivity-0.md)
    
- [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md)
    
- [Planen von Notfalldiensten in Skype for Business Server](emergency-services.md)
    
- [Planen der medienumgehung in Skype for Business](media-bypass.md)
    
- [Planen privater Telefonanschlüsse mit Skype for Business](private-telephone-lines.md)
    
- [Plan für standortbasiertes Routing in Skype for Business](location-based-routing.md)
    
- [Planen der anrufverwaltungsfunktionen in Skype for Business](call-management-features.md)
    
- [Plan for Enterprise Voice resiliency in Skype for Business Server](enterprise-voice-resiliency.md)
    

