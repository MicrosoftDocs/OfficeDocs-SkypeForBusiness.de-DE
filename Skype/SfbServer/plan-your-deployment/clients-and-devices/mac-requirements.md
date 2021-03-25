---
title: Skype for Business on Mac-Clientanforderungen
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
ms.openlocfilehash: 866eda0cc5e82db1da1b69bee3eb4bf26df6d7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109281"
---
# <a name="skype-for-business-on-mac-client-requirements"></a>Skype for Business on Mac-Clientanforderungen
 
In diesem Thema erfahren Sie mehr über Hardware-, Software- und Infrastrukturanforderungen für die Ausführung von Skype for Business auf einem Mac.
  
Der [Skype for Business on Mac-Client](https://products.office.com/skype-for-business/download-app?tab=tabs-3#Mac) steht zum Download zur Verfügung.
  
## <a name="hardware-and-software-requirements-for-skype-for-business-on-mac"></a>Hardware- und Softwareanforderungen für Skype for Business auf Mac

Der Skype for Business on Mac-Client erfordert Mac OS X El Capitan und höher und verbraucht mindestens 100 MB Speicherplatz. Wir unterstützen die Verwendung aller integrierten Audio- und Videogeräte. Externe Geräte müssen sich im [Skype for Business-Lösungskatalog befinden.](https://partnersolutions.skypeforbusiness.com/solutionscatalog) 
  
> [!NOTE]
> Diese Liste ist vorläufig, und einige Geräte sind möglicherweise für Lync qualifiziert, werden jedoch nicht auf Skype for Business auf dem Mac unterstützt. Lesen Sie die [Systemanforderungen für](https://products.office.com/office-system-requirements) die erforderliche Mindesthardware.
  
### <a name="legacy-mac-clients"></a>Legacy-Mac-Clients

Skype for Business Server 2015 unterstützt auch die folgenden Legacyclients auf Computern, auf denen Mac OS 10.5.8 oder das neueste Service Pack oder die neueste Version (Intel-basiertes) Betriebssystem ausgeführt wird (Mac OS 10.9-Betriebssystem wird derzeit nicht unterstützt). Weitere Informationen zu unterstützten Features finden Sie unter Vergleich der [Desktopclientfeatures für Skype for Business](desktop-feature-comparison.md).
  
- Microsoft Lync für Mac 2011 (siehe [Lync for Mac 2011 Deployment Guide](/previous-versions/office/office-for-mac-2011/jj984275(v=office.14)))
    
- Microsoft Communicator für Mac 2011 (siehe [Communicator für Mac 2011 Deployment Guide](/previous-versions/office/office-for-mac-2011/jj984270(v=office.14)))
 
Diese Clients werden von Skype for Business Server 2019 nicht unterstützt.
   
## <a name="infrastructure-requirements-for-skype-for-business-on-mac"></a>Infrastrukturanforderungen für Skype for Business auf Mac
<a name="Infrastructure"> </a>

Der Skype for Business on Mac-Client nutzt sowohl die Unified Communications Management Platform (UCMP) als auch die Unified Communications Web API (UCWA), die von unseren Mobilitätsclients verwendet wird.
  
Der Client hat die gleichen Anforderungen wie unsere Mobilitätsclients, da Ein Zugriffs-Edgeserver und Reverseproxy in einer unterstützten Konfiguration bereitgestellt werden müssen. 
  
### <a name="authentication"></a>Authentifizierung

Der Skype for Business on Mac-Client unterstützt die Cert-basierte Authentifizierung, die moderne Microsoft-Authentifizierung und die mehrstufige Authentifizierung, wenn sie bereitgestellt und aktiviert ist.
  
> [!NOTE]
> Aufgrund einer aktuellen Einschränkung müssen die Exchange-Anmeldeinformationen des Benutzers mit den Skype for Business-Anmeldeinformationen identisch sein. 
  
### <a name="certificates"></a>Zertifikate

Zertifikate, die auf den Zugriffs-Edge-, Reverseproxy- und Front-End-Servern verwendet werden, dürfen nicht den SHA-512-Hashalgorithmus verwenden.
  
Die HTTP-Zertifikatsperrliste muss vom Client definiert und zugänglich sein. Beispielsweise unterstützen wir keinen LDAP-Eintrag im Zertifikat als Zertifikatsperrliste.
  
### <a name="dns"></a>DNS

Mobilität muss ordnungsgemäß bereitgestellt werden, damit Skype for Business auf dem Mac-Client ordnungsgemäß funktioniert. Ein häufiges Fehlerszenario besteht in der Auflösung beider der folgenden DNS-Einträge im internen Netzwerk:
  
- lyncdiscoverinternal.\<sipdomain\>
    
- lyncdiscover.\<sipdomain\>
    
Weitere Informationen finden Sie unter [Deploying Mobility in Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mobility)und [im Microsoft Lync Server 2010 Mobility Guide](https://go.microsoft.com/fwlink//p/?LinkId=798226).
  
## <a name="see-also"></a>Siehe auch
<a name="Infrastructure"> </a>

[DNS-Anforderungen für Skype for Business Server](../../plan-your-deployment/network-requirements/dns.md)

[Häufig gestellte Fragen](https://go.microsoft.com/fwlink/p/?LinkId=798227)
  
[Bekannte Probleme](https://go.microsoft.com/fwlink/p/?LinkId=798228)