---
title: Skype for Business auf Mac-Clientanforderungen
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: In diesem Thema erfahren Sie mehr über die Hardware-, Software-und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac.
ms.openlocfilehash: f4f62246a86dabeb628755d3c75a10bc285ede12
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42013458"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business auf Mac-Clientanforderungen
 
In diesem Thema erfahren Sie mehr über die Hardware-, Software-und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac.
  
Der [Skype for Business auf dem Mac-Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) steht zum Herunterladen zur Verfügung.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Hardware-und Softwareanforderungen für Skype for Business auf dem Mac

Die Skype for Business unter Mac-Client erfordert Mac OS X El Capitan und höher und verwendet mindestens 100MB Speicherplatz. Wir unterstützen die Verwendung aller integrierten Audio-und Videogeräte. Externe Geräte müssen sich im [Katalog mit Skype for Business Lösungen](https://partnersolutions.skypeforbusiness.com/solutionscatalog)befinden. 
  
> [!NOTE]
> Diese Liste ist vorläufig, und einige Geräte sind möglicherweise für lync qualifiziert, werden jedoch für Skype for Business auf dem Mac nicht unterstützt. Lesen Sie die [System Anforderungen](https://products.office.com/office-system-requirements) für die erforderliche Mindesthardware.
  
### <a name="legacy-mac-clients"></a>Ältere Mac-Clients

Skype for Business Server 2015 unterstützt auch die folgenden Legacyclients auf Computern, auf denen Mac OS 10.5.8 oder neueste Service Pack-oder Release-Betriebssysteme (Intel-basiert) installiert sind (Betriebssystem Mac OS 10,9 wird derzeit nicht unterstützt). Ausführliche Informationen zu den unterstützten Features finden Sie unter [Desktop Client Feature Comparison for Skype for Business](desktop-feature-comparison.md).
  
- Microsoft lync für Mac 2011 (siehe [Bereitstellungshandbuch für lync für Mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator für Mac 2011 (siehe [Bereitstellungshandbuch für Communicator für Mac 2011](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Diese Clients werden von Skype for Business Server 2019 nicht unterstützt.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Infrastrukturanforderungen für Skype for Business auf dem Mac
<a name="Infrastructure"> </a>

Der Skype for Business auf dem Mac-Client nutzt sowohl die Unified Communications Verwaltungsplattform (UCMP) als auch die Unified Communications Web API (UCWA), die unsere Mobilitäts Clients verwenden.
  
Der Client hat die gleichen Anforderungen wie unsere Mobilitäts Clients, da Sie über eine Zugriffs Edgeserver und einen Reverseproxy verfügen müssen, die in einer unterstützten Konfiguration bereitgestellt werden. 
  
### <a name="authentication"></a>Authentifizierung

Der Skype for Business auf dem Mac-Client unterstützt die CERT-basierte Authentifizierung, die Microsoft-moderne Authentifizierung und die mehrstufige Authentifizierung bei Bereitstellung und Aktivierung.
  
> [!NOTE]
> Aufgrund einer aktuellen Einschränkung müssen die Exchange-Anmeldeinformationen des Benutzers mit Ihren Skype for Business Anmeldeinformationen übereinstimmen. 
  
### <a name="certificates"></a>Zertifikate

Zertifikate, die auf dem Zugriffs-Edge, dem Reverse-Proxy und den Front-End-Servern verwendet werden, dürfen nicht den SHA-512-Hashalgorithmus verwenden.
  
Die http-Zertifikatsperrliste muss definiert sein und für den Client zugänglich sein. Beispielsweise wird kein LDAP-Eintrag im Zertifikat als Zertifikatsperrliste unterstützt.
  
### <a name="dns"></a>DNS

Die Mobilität muss ordnungsgemäß bereitgestellt werden, damit der Skype for Business auf dem Mac-Client ordnungsgemäß funktioniert. Ein häufiges Fehlerszenario besteht darin, dass beide der folgenden DNS-Einträge im internen Netzwerk aufgelöst werden können:
  
- "lyncdiscoverinternal". \<sipdomain "\>
    
- lyncdiscover. \<sipdomain "\>
    
Weitere Informationen finden Sie unter [Bereitstellen von Mobilität in lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)und im [Microsoft lync Server 2010 Mobilitätsleitfaden](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Siehe auch
<a name="Infrastructure"> </a>

[DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Häufig gestellte Fragen](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Bekannte Probleme](https://go.microsoft.com/fwlink/p/?LinkId=798228)
