---
title: Clientanforderungen für Skype for Business auf dem Mac
ms.author: v-cichur
author: cichur
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
description: In diesem Thema erfahren Sie mehr über Hardware-, Software- und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac.
ms.openlocfilehash: 5f967bab3a5dcc41a3419324c9fe09b48a8fb674
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832165"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Clientanforderungen für Skype for Business auf dem Mac
 
In diesem Thema erfahren Sie mehr über Hardware-, Software- und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac.
  
Der [Skype for Business on Mac Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) steht zum Download zur Verfügung.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Hardware- und Softwareanforderungen für Skype for Business auf dem Mac

Für den Skype for Business auf dem Mac-Client ist Mac OS X El Dies und höher erforderlich, und es wird mindestens 100 MB Festplattenspeicher verwendet. Wir unterstützen die Verwendung aller integrierten Audio- und Videogeräte. Externe Geräte müssen sich im [Skype for Business-Lösungskatalog befinden.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Diese Liste ist vorläufig, und einige Geräte sind möglicherweise für Lync qualifiziert, werden jedoch in Skype for Business auf dem Mac nicht unterstützt. Die [Mindesthardwareanforderungen finden](https://products.office.com/office-system-requirements) Sie in den Systemanforderungen.
  
### <a name="legacy-mac-clients"></a>Legacy-Mac-Clients

Skype for Business Server 2015 unterstützt auch die folgenden Legacyclients auf Computern, auf denen Mac OS 10.5.8 oder das neueste Service Pack oder die neueste Version (Intel-basiert) ausgeführt wird (Betriebssystem Mac OS 10.9 wird derzeit nicht unterstützt). Weitere Informationen zu unterstützten Features finden Sie im Vergleich der [Desktopclientfunktionen für Skype for Business.](desktop-feature-comparison.md)
  
- Microsoft Lync für Mac 2011 (siehe [Bereitstellungshandbuch für Lync für Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268786)
    
- Microsoft Communicator für Mac 2011 [(siehe bereitstellungshandbuch Communicator für Mac 2011)](https://go.microsoft.com/fwlink/p/?LinkId=268787)
 
Diese Clients werden von Skype for Business Server 2019 nicht unterstützt.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Infrastrukturanforderungen für Skype for Business auf dem Mac
<a name="Infrastructure"> </a>

Der Skype for Business auf dem Mac-Client nutzt sowohl die Unified Communications Management Platform (UCMP) als auch die Unified Communications Web API (UCWA), die unsere Mobilitätsclients verwenden.
  
Der Client hat die gleichen Anforderungen wie unsere Mobilitätsclients, da Sie einen Zugriffsedgeserver und Reverseproxy in einer unterstützten Konfiguration bereitstellen müssen. 
  
### <a name="authentication"></a>Authentifizierung

Der Skype for Business auf #A0 unterstützt die zertifikatbasierte Authentifizierung, die moderne #A1 und die mehrstufige Authentifizierung bei Bereitstellung und Aktivierung.
  
> [!NOTE]
> Aufgrund einer aktuellen Einschränkung müssen die Exchange-Anmeldeinformationen des Benutzers mit den Skype for Business-Anmeldeinformationen identisch sein. 
  
### <a name="certificates"></a>Zertifikate

Zertifikate, die auf zugriffs-, Reverseproxy- und Front-End-Servern verwendet werden, dürfen nicht den SHA-512-Hashalgorithmus verwenden.
  
Die HTTP-Zertifikatsperrliste muss vom Client definiert und zugänglich sein. Beispielsweise wird kein LDAP-Eintrag im Zertifikat als Zertifikatsperrliste unterstützt.
  
### <a name="dns"></a>DNS

Mobilität muss ordnungsgemäß bereitgestellt werden, damit Skype for Business auf dem Mac-Client ordnungsgemäß funktioniert. Ein häufiges Fehlerszenario besteht in der Auflösung beider der folgenden DNS-Einträge im internen Netzwerk:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Weitere Informationen finden Sie unter: [Deploying Mobility in Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)und [microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Siehe auch
<a name="Infrastructure"> </a>

[DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Häufig gestellte Fragen](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Bekannte Probleme](https://go.microsoft.com/fwlink/p/?LinkId=798228)
