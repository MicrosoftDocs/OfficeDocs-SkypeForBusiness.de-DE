---
title: Skype for Business für Mac-Clientanforderungen
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 790d3e89-2b68-411b-b282-38de5d34dd10
description: Lesen Sie dieses Thema, um mehr über die Hardware-, Software- und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac zu erfahren.
ms.openlocfilehash: dd7dc17c4166838a76b11d9905335575205f4b2b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604774"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business für Mac-Clientanforderungen
 
Lesen Sie dieses Thema, um mehr über die Hardware-, Software- und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac zu erfahren.
  
Die [Skype for Business auf dem Mac-Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) steht zum Download zur Verfügung.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Hardware- und Softwareanforderungen für Skype for Business auf dem Mac

Die Skype for Business auf dem Mac-Client erfordert Mac OS X El Macintoshn und höher und verwendet mindestens 100 MB Speicherplatz. Wir unterstützen die Verwendung aller integrierten Audio- und Videogeräte. Externe Geräte müssen sich im [Skype for Business Lösungskatalog befinden.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Diese Liste ist vorläufig, und einige Geräte sind möglicherweise für Lync qualifiziert, werden jedoch auf Skype for Business auf dem Mac nicht unterstützt. Lesen Sie die [Systemanforderungen](https://products.office.com/office-system-requirements) für die erforderliche Mindesthardware.
  
### <a name="legacy-mac-clients"></a>Legacy-Mac-Clients

Skype for Business Server 2015 unterstützt auch die folgenden Legacyclients auf Computern mit Mac OS 10.5.8 oder neuesten Service Pack- oder Release-Betriebssystemen (Intel-basiert) (Mac OS 10.9 wird derzeit nicht unterstützt). Ausführliche Informationen zu unterstützten Features finden Sie unter Vergleich der [Desktopclientfeatures für Skype for Business.](desktop-feature-comparison.md)
  
- Microsoft Lync für Mac 2011 (siehe [Bereitstellungshandbuch für Lync für Mac 2011)](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14))
    
- Microsoft Communicator für Mac 2011 (siehe [Communicator für Mac 2011 Deployment Guide](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
Diese Clients werden von Skype for Business Server 2019 nicht unterstützt.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Infrastrukturanforderungen für Skype for Business auf dem Mac
<a name="Infrastructure"> </a>

Der Skype for Business auf dem Mac-Client nutzt sowohl die Unified Communications Management Platform (UCMP) als auch die Unified Communications Web API (UCWA), die von unseren Mobilitätsclients verwendet wird.
  
Der Client hat die gleichen Anforderungen wie unsere Mobilitätsclients, da ein Zugriffs-Edgeserver und Reverseproxy in einer unterstützten Konfiguration bereitgestellt werden müssen. 
  
### <a name="authentication"></a>Authentifizierung

Der Skype for Business auf dem Mac-Client unterstützt die zertifikatbasierte Authentifizierung, die moderne Authentifizierung von Microsoft und die mehrstufige Authentifizierung, wenn sie bereitgestellt und aktiviert ist.
  
> [!NOTE]
> Aufgrund einer aktuellen Einschränkung müssen die Exchange Anmeldeinformationen des Benutzers mit den Skype for Business-Anmeldeinformationen übereinstimmen. 
  
### <a name="certificates"></a>Zertifikate

Zertifikate, die auf den Zugriffs-Edge-, Reverseproxy- und Front-End-Servern verwendet werden, dürfen nicht den SHA-512-Hashalgorithmus verwenden.
  
Die HTTP-Zertifikatsperrliste muss definiert sein und vom Client zugänglich sein. Beispielsweise wird kein LDAP-Eintrag im Zertifikat als Zertifikatsperrliste unterstützt.
  
### <a name="dns"></a>DNS

Mobilität muss ordnungsgemäß bereitgestellt werden, damit die Skype for Business auf dem Mac-Client ordnungsgemäß funktioniert. Ein häufiges Fehlerszenario besteht darin, dass beide der folgenden DNS-Einträge im internen Netzwerk aufgelöst werden können:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Weitere Informationen finden Sie unter: [Deploying Mobility in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility), and the [Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Siehe auch
<a name="Infrastructure"> </a>

[DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Häufig gestellte Fragen](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Bekannte Probleme](https://go.microsoft.com/fwlink/p/?LinkId=798228)