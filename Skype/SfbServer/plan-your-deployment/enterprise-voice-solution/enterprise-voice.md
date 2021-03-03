---
title: Planen von Enterprise-VoIP in Skype for Business Server
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Enterprise-VoIP Grundlegendes zur Planung in Skype for Business Server, einschließlich Websites, Regionen, Netzwerkverbindungen zwischen Standorten und Schätzen des Datenverkehrs für die Sprachnutzung.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825675"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>Planen von Enterprise-VoIP in Skype for Business Server
 
Enterprise-VoIP Grundlegendes zur Planung in Skype for Business Server, einschließlich Websites, Regionen, Netzwerkverbindungen zwischen Standorten und Schätzen des Datenverkehrs für die Sprachnutzung.
  
Der Bereitstellungsprozess für Enterprise-VoIP hängt von Ihrer vorhandenen Topologie, Infrastruktur und den Enterprise-VoIP ab, die Sie unterstützen möchten. Die erforderlichen Verfahren hängen davon ab, welche Features Sie auswählen, aber es gibt weitere Planungsüberlegungen, die Sie auf hoher Ebene berücksichtigen müssen.
  
Im Allgemeinen sollten Sie den Typ und die Anzahl der Standorte, die Sie bereitstellen möchten, und deren geografische Standorte, das Anrufvolumen an jedem Standort, die Netzwerkverbindungstypen, die Standorte verbinden, berücksichtigen, ob Sie Redundanz und Failover für die Sprachfunktionen für jeden Standort bereitstellen möchten und ob Sie vorhandene Nebenstellenanlagen verwenden möchten. Es gibt bestimmte Aspekte, z. B. hohe Verfügbarkeit, die Sie bei der Planung von Skype for Business Server als Ganzes berücksichtigen sollten. Diese Überlegungen werden bei Bedarf in den Themen in diesem Abschnitt behandelt.
  
## <a name="sites-and-regions"></a>Websites und Regionen

Identifizieren Sie zunächst die Standorte in Ihrer Topologie, an denen sie Enterprise-VoIP und die Netzwerkregionen, zu denen diese Standorte gehören. Insbesondere müssen Sie überlegen, wie die PSTN-Anbindung (Public Switched Telephone Network) für jeden Standort implementiert wird. Die Zuweisung von Standorten zu Regionen kann aus verwaltungstechnischer und logistischer Sicht ein entscheidender Faktor sein. Entscheiden Sie, wo Gateways lokal bereitgestellt werden, wo Survivable Branch Appliances (SBAs) bereitgestellt werden sollen und wo Sie SIP-Trunks (lokal oder am zentralen Standort) für einen Anbieter von Internettelefoniediensten (Internet Telephony Service Provider, ITSP) konfigurieren können.
  
## <a name="network-links-between-sites"></a>Netzwerkverbindungen zwischen Standorten

Sie müssen auch die Bandbreitenauslastung berücksichtigen, die Sie für die Netzwerkverbindungen zwischen dem zentralen Standort und den Zweigstellenstandorten erwarten. Wenn Sie über ausfallsichere WAN-Verbindungen zwischen Standorten verfügen oder diese bereitstellen möchten, wird empfohlen, an jedem Zweigstellenstandort ein Gateway zur Bereitstellung eines lokalen DID (Direct Inward Dial)-Termins für Benutzer an diesen Standorten zu bereitstellen. Wenn Sie über ausfallsichere WAN-Verbindungen verfügen, die Bandbreite einer WAN-Verbindung jedoch wahrscheinlich eingeschränkt ist, konfigurieren Sie die Anrufsteuerung für diese Verbindung. Wenn Sie keine ausfallsicheren WAN-Verbindungen haben, weniger als 1.000 Benutzer an Ihrem Zweigstellenstandort hosten und keine lokalen geschulten Skype for Business Server-Administratoren verfügbar sind, wird empfohlen, dass Sie eine Survivable Branch Appliance am Zweigstellenstandort bereitstellen. Wenn Sie zwischen 1.000 und 5.000 Benutzer an Ihrem Zweigstellenstandort hosten, keine ausfallsichere WAN-Verbindung haben und geschulte Skype for Business Server-Administratoren verfügbar sind, wird empfohlen, einen Survivable Branch Server mit einem kleinen Gateway am Zweigstellenstandort bereitstellen. Erwägen Sie auch die Aktivierung der Medienumgehung für Verbindungen mit eingeschränkter Bandbreite, wenn Sie über ein Gatewaypeer mit Unterstützung der Medienumgehung verfügen.
  
## <a name="estimating-voice-usage-and-traffic"></a>Schätzen der Sprachnutzung und des Datenverkehrs

Das Microsoft Lync Server 2013-Planungstool verwendet die folgende Metrik, um den Benutzerdatenverkehr an jedem Standort und die Anzahl der Ports zu schätzen, die zur Unterstützung dieses Datenverkehrs erforderlich sind.
  
> Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.
> 
> Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.
> 
> Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.
    
Die Anzahl der Ports wiederum bestimmt die Anzahl der Vermittlungsserver und Gateways, die erforderlich sind. Die PSTN-Gateways( Public Switched Telephone Network), die von den meisten Organisationen als Bereitstellungsumfang zwischen 2 ports und bis zu 960 Ports in Betracht ziehen. (Es gibt noch größere Gateways, die jedoch hauptsächlich von Telefoniedienstanbietern verwendet werden.)
  
Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>Komponenten, Features und Optionen von Enterprise-VoIP

In den folgenden Abschnitten finden Sie weitere Informationen zum Planen ihrer Enterprise-VoIP Bereitstellung.
  
- [Erforderliche Komponenten für Enterprise-VoIP in Skype for Business Server](components-required-for-enterprise-voice.md)
    
- [Planen der Festnetzanbindung in Skype for Business Server](pstn-connectivity-0.md)
    
- [Netzwerkeinstellungen für die erweiterten Enterprise-VoIP in Skype for Business Server](network-settings-for-advanced-features.md)
    
- [Planen der Anrufsteuerung in Skype for Business Server](call-admission-control.md)
    
- [Planen von Notrufdiensten in Skype for Business Server](emergency-services.md)
    
- [Planen der Medienumgehung in Skype for Business](media-bypass.md)
    
- [Planen von Privatleitungen mit Skype for Business](private-telephone-lines.md)
    
- [Planen des Location-Based routing in Skype for Business](location-based-routing.md)
    
- [Planen von Anrufverwaltungsfunktionen in Skype for Business](call-management-features.md)
    
- [Planen von Enterprise-VoIP A0 in Skype for Business Server](enterprise-voice-resiliency.md)
    

