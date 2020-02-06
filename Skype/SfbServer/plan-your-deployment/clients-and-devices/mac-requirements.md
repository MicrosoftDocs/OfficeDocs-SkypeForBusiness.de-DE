---
title: Skype for Business für Mac-Clientanforderungen
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
description: Lesen Sie dieses Thema, um Informationen zu Hardware-, Software-und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac zu erhalten.
ms.openlocfilehash: 08f3aeabbfd88b432c28f05727ec7cf009e297a7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803595"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business für Mac-Clientanforderungen
 
Lesen Sie dieses Thema, um Informationen zu Hardware-, Software-und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac zu erhalten.
  
Der [Skype for Business für Mac-Client](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-3#Mac) steht zum Download zur Verfügung.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Hardware-und Softwareanforderungen für Skype for Business für Mac

Der Skype for Business für Mac-Client erfordert Mac OS X El Capitan und höher und verwendet mindestens 100MB Speicherplatz. Die Verwendung aller integrierten Audio- und Videogeräte wird unterstützt. Externe Geräte müssen im [Skype for Business-Lösungskatalog](https://partnersolutions.skypeforbusiness.com/solutionscatalog)vorhanden sein. 
  
> [!NOTE]
> Diese Liste ist vorläufig, und einige Geräte sind möglicherweise für lync qualifiziert, werden aber von Skype for Business auf dem Mac nicht unterstützt. Beziehen Sie sich auf die [System Anforderungen](https://products.office.com/en-us/office-system-requirements) für die erforderliche minimale Hardware.
  
### <a name="legacy-mac-clients"></a>Legacy-Mac-Clients

Skype for Business Server 2015 unterstützt auch die folgenden Legacy-Clients auf Computern, auf denen Mac OS 10.5.8 oder neueste Service Pack-oder Release-Betriebssysteme (Intel-basiert) ausgeführt werden (Betriebssystem Mac OS 10,9 wird derzeit nicht unterstützt). Details zu den unterstützten Features finden Sie unter [Vergleich der Desktop-Clientfunktionen für Skype for Business](desktop-feature-comparison.md).
  
- Microsoft lync für Mac 2011 (siehe [lync für Mac 2011 – Bereitstellungshandbuch](https://go.microsoft.com/fwlink/p/?LinkId=268786))
    
- Microsoft Communicator für Mac 2011 (siehe [Communicator für Mac 2011 – Bereitstellungshandbuch](https://go.microsoft.com/fwlink/p/?LinkId=268787))
 
Diese Clients werden von Skype for Business Server 2019 nicht unterstützt.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Infrastrukturanforderungen für Skype for Business für Mac
<a name="Infrastructure"> </a>

Der Skype for Business für Mac-Client nutzt sowohl die Unified Communications-Verwaltungsplattform (UCMP) als auch die Unified Communications Web-API (UCWA), die unsere Mobilitäts Clients verwenden.
  
Für den Client gelten die gleichen Anforderungen wie bei unseren Mobilitätsclients in der Hinsicht, dass Sie einen Zugriffs-Edgeserver und Reverseproxy in einer unterstützten Konfiguration bereitstellen müssen. 
  
### <a name="authentication"></a>Authentifizierung

Der Skype for Business für Mac-Client unterstützt die CERT-basierte Authentifizierung, die moderne Microsoft-Authentifizierung und die mehrstufige Authentifizierung, wenn diese bereitgestellt und aktiviert ist.
  
> [!NOTE]
> Aufgrund einer derzeitigen Beschränkung müssen die Exchange-Anmeldeinformationen des Benutzers mit den Anmeldeinformationen von Skype for Business identisch sein. 
  
### <a name="certificates"></a>Zertifikate

Zertifikate, die auf den Zugriffs-Edge-, Reverseproxy- und Front-End-Servern verwendet werden, dürfen nicht den SHA-512-Hashalgorithmus verwenden.
  
Die HTTP-Zertifikatsperrliste muss definiert und für den Client zugänglich sein. Beispielsweise unterstützen wir keinen LDAP-Eintrag im Zertifikat als Zertifikatsperrliste.
  
### <a name="dns"></a>DNS

Mobilität muss ordnungsgemäß bereitgestellt sein, damit Skype for Business auf dem Mac-Client ordnungsgemäß funktioniert. Ein typisches Fehlerszenario wäre es, wenn im internen Netzwerk die folgenden beiden DNS-Einträge aufgelöst werden können:
  
- lyncdiscoverinternal. \<sipdomain\>
    
- lyncdiscover. \<sipdomain\>
    
Weitere Informationen finden Sie unter: [Bereitstellen von Mobilität in lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=798224)und im [Microsoft lync Server 2010-Mobilitätsleitfaden](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Siehe auch
<a name="Infrastructure"> </a>

[DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Häufig gestellte Fragen](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Bekannte Probleme](https://go.microsoft.com/fwlink/p/?LinkId=798228)
