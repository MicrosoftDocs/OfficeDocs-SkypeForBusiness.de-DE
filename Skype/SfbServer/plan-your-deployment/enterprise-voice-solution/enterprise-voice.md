---
title: Planen der Enterprise-VoIP in Skype for Business Server
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Enterprise-VoIP die Planung von Grundlagen in Skype for Business Server, einschließlich Standorten, Regionen, Netzwerkverbindungen zwischen Standorten und Der Schätzung des VoIP-Nutzungsdatenverkehrs.
ms.openlocfilehash: bfd7d4b1491b83c6ad3ab65836777e805689c21f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618811"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planen der Enterprise-VoIP in Skype for Business Server
 
Enterprise-VoIP die Planung von Grundlagen in Skype for Business Server, einschließlich Standorten, Regionen, Netzwerkverbindungen zwischen Standorten und Der Schätzung des VoIP-Nutzungsdatenverkehrs.
  
Der Bereitstellungsprozess für Enterprise-VoIP hängt von Ihrer vorhandenen Topologie, Infrastruktur und der Enterprise-VoIP Funktionalität ab, die Sie unterstützen möchten. Die erforderlichen Verfahren hängen davon ab, welche Features Sie auswählen, aber es gibt andere Planungsüberlegungen, die Sie auf hoher Ebene vornehmen müssen.
  
Betrachten Sie im Allgemeinen den Typ und die Anzahl der Standorte, die Sie bereitstellen möchten, und deren geografische Standorte, das Anrufvolumen an jedem Standort, die Typen von Netzwerkverbindungen, die Standorte verbinden, ob Sie Redundanz und Failover für voIP-Funktionen für jeden Standort bereitstellen möchten und ob Sie vorhandene PBX-Geräte verwenden möchten. Es gibt bestimmte Überlegungen, z. B. hohe Verfügbarkeit, die Sie berücksichtigen sollten, wenn Sie Skype for Business Server als Ganzes planen. Diese Überlegungen werden bei Bedarf in den Themen in diesem Abschnitt behandelt.
  
## <a name="sites-and-regions"></a>Websites und Regionen

Identifizieren Sie zunächst die Standorte in Ihrer Topologie, an denen Sie Enterprise-VoIP bereitstellen werden, und die Netzwerkregionen, zu denen diese Standorte gehören. Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird. Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein. Entscheiden Sie, wo Gateways lokal bereitgestellt werden, wo Survivable Branch Appliances (SBAs) bereitgestellt werden und wo Sie SIP-Trunks (lokal oder am zentralen Standort) für einen Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP) konfigurieren können.
  
## <a name="network-links-between-sites"></a>Netzwerkverbindungen zwischen Standorten

Sie müssen auch die Bandbreitennutzung berücksichtigen, die Sie für die Netzwerkverbindungen zwischen Ihrem zentralen Standort und den Zweigstellen erwarten. Wenn Sie über ausfallsichere WAN-Verbindungen zwischen Standorten verfügen oder diese bereitstellen möchten, empfehlen wir, dass Sie an jedem Zweigstellenstandort ein Gateway bereitstellen, um benutzern an diesen Standorten eine lokale DID-Beendigung (Direct Inward Dial) bereitzustellen. Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, die Bandbreite einer WAN-Verbindung jedoch wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung. Wenn Sie keine ausfallsicheren WAN-Verbindungen haben, weniger als 1.000 Benutzer an Ihrem Zweigstellenstandort hosten und keine lokal geschulten Skype for Business Server Administratoren verfügbar sind, wird empfohlen, eine Survivable Branch Appliance am Zweigstellenstandort bereitzustellen. Wenn Sie zwischen 1000 und 5000 Benutzer an Ihrem Zweigstellenstandort hosten, keine ausfallsichere WAN-Verbindung haben und Skype for Business Server Administratoren geschult sind, empfehlen wir, dass Sie einen Survivable Branch Server mit einem kleinen Gateway am Zweigstellenstandort bereitstellen. Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.
  
## <a name="estimating-voice-usage-and-traffic"></a>Schätzen der VoIP-Nutzung und des Datenverkehrs

Das Microsoft Lync Server 2013-Planungstool verwendet die folgende Metrik, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die zur Unterstützung dieses Datenverkehrs erforderlich sind.
  
> Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.
> 
> Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.
> 
> Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.
    
Die Anzahl der Ports bestimmt wiederum die Anzahl der erforderlichen Vermittlungsserver und Gateways. PsTN-Gateways (Public Switched Telephone Network), für die die meisten Organisationen eine Breite von 2 Ports bis zu 960 Ports in Betracht ziehen. (Es gibt noch größere Gateways, die jedoch hauptsächlich von Telefoniedienstanbietern verwendet werden.)
  
Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Komponenten, Features und Optionen von Enterprise-VoIP

Weitere Informationen zur Planung Ihrer Enterprise-VoIP Bereitstellung finden Sie in den folgenden Abschnitten.
  
- [Komponenten, die für Enterprise-VoIP in Skype for Business Server erforderlich sind](components-required-for-enterprise-voice.md)
    
- [Planen der PSTN-Konnektivität in Skype for Business Server](pstn-connectivity-0.md)
    
- [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md)
    
- [Planen von Notrufdiensten in Skype for Business Server](emergency-services.md)
    
- [Planen der Medienumgehung in Skype for Business](media-bypass.md)
    
- [Planen von Privatleitungen mit Skype for Business](private-telephone-lines.md)
    
- [Planen des Location-Based Routings in Skype for Business](location-based-routing.md)
    
- [Planen von Anrufverwaltungsfunktionen in Skype for Business](call-management-features.md)
    
- [Planen Enterprise-VoIP Resilienz in Skype for Business Server](enterprise-voice-resiliency.md)
    

